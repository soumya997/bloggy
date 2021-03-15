---
layout: post
comments: true
name: playability
title: Użyteczność słów w Scrabble
---

Strategia odgrywa ogromną rolę w grze w Scrabble. Przychodzi jednak taki moment, że tylko nauka słówek pomaga podnieść poziom gry. Gdy grałem regularnie, interesowało mnie jak tę naukę zoptymalizować. Są tacy, którzy wkuwali kolejne pozycje ze słownika. Nie słyszałem, by ktoś wytrwał do końca. W anglojęzycznych skrablach jest to chyba warunek konieczny wstąpienia do czołówki. Poziom polskojęzycznych turniejów, co zrozumiałe, aż tak wygórowany nie jest. Inni znajomi skrabliści uczyli się siódemek wg prawdopodobieństwa ich wylosowania, takich jak OCEANIT/OCTANIE, IZATYNO, AZTECKI, RILSANY itd. — wygenerowanie takiej listy jest stosunkowo łatwe. Na pewno nie jest to jednak optymalne wyjście, bo wiele słów będzie miało układ liter niepasujący do typowej planszy albo nie da nam przewagi wartej czasu poświęconego na ich naukę.

### Użyteczność słów

Amerykański skrablista, John O'Laughlin, opublikował w 2007 [_playability list_](http://pages.cs.wisc.edu/~o-laughl/collins/), czyli listę _zagrywalności_ słów. Ja będę nazywał to po prostu _użytecznością_, żeby nie łamać sobie języka. Aby wygenerować taką listę, trzeba mieć do dyspozycji program, który rozegra ze sobą miliony gier. Obecnie (początek 2015) najlepszym takim komputerowym graczem jest [Elise](http://www.codehappy.net/elise/), którego niestety (na razie) nie da się zaadaptować do gry polskimi literami. Jest za to stary dobry [Quackle](http://people.csail.mit.edu/jasonkb/quackle/), który od niedawna pozwala na grę po polsku. Nie znalazłem nigdzie dokładnego opisu algorytmu, jakiego użył olaugh, ale z różnych przesłanek odtworzyłem poniższą procedurę. Główna zasada brzmi: **użyteczność słowa to liczba punktów których nie zdobylibyśmy w danym ruchu, nie znając tego słowa, za to znając kolejne najlepsze**.

Najpierw trzeba wygenerować kilkadziesiąt najdroższych ruchów. Quackle jest w tym bardzo sprawny i robi to w ułamku sekundy.


    Speedy Player B: Turn 1
       A B C D E F G H I J K L M N O      Speedy Player A          ĆŁNÓPŚY 74  
      ------------------------------  -> Speedy Player B          EEIKRSY   0   
     1|=     '       =       '     =| --Static Player's choices (your play: 1)-----
     2|  -       "       "       -  | best *H7 S(I)EKIERY 61 
     3|    -       '   '       -    | best  H4 SIEK(I)ERY 61 
     4|'     -       '       -     '|  25.2 E5 ESK(A)ERY  36 I
     5|        -           -        |  39.9 C7 K(A)ISERY  24 E
     6|  "       "       "       "  |  40.0 C7 K(A)RESIE  22 Y
     7|    '       '   '       '    |  41.6 D8 (G)RYSIE   18 EK
     8|=   A G A D z I E     '     =|  41.6 D8 (G)ISERY   18 EK
     9|    '       '   '       '    |  43.0 D8 (G)IEREK   18 SY
    10|  "       "       "       "  |  44.0 D8 (G)RESY    16 EIK
    11|        -           -        |  44.9 D8 (G)REKI    16 ESY
    12|'     -       '       -     '| --Tracking-----------------------------------
    13|    -       '   '       -    | ?AAAAAAAĄBBCCCĆDDEEEEĘFGHHIIIIIIJJKKLLLŁŁMMM
    14|  -       "       "       -  | NNNNNŃOOOOOOÓPPPRRRSSSŚTTTUUWWWWYYYZZZZZŹŻ  86
    15|=     '       =       '     =|
      ------------------------------


Zapisujemy najlepsze słowo i jego wartość punktową, po czym idziemy w dół listy. Pomiędzy dwiema pozycjami `SIEKIERY` (H7 i H4) punktowo nie ma żadnej różnicy. Kolejny ruch, `ESK(A)ERY`, da nam mniej punktów, więc zapisujemy różnicę. Ściślej mówiąc, jest to różnica wartości **słowa i stojaka**, który nam zostaje po ułożeniu słowa. O wartości stojaków napiszę kiedy indziej. W tym przypadku dopisujemy więc słowu `SIEKIERY` 25.2 punktu i kontynuujemy grę.

    Speedy Player A: Turn 4
       A B C D E F G H I J K L M N O   -> Speedy Player A          BFLPRSY   132 
       ------------------------------     Speedy Player B          ?ACGLTW   114 
     1|=     '       W       '     =| --Static Player's choices (your play: 1)-----
     2|  -       "   A   "       -  | best *B2  FL(O)PY  32 BRS
     3|    -       ' Z '       -    |  2.51 12G B(E)LFRY 28 PS
     4|B O T K I     K       -     '|  2.51 11G F(I)BRYL 28 PS
     5|        N A P A Ś Ć -        |  3.00 B2  FL(O)RY  30 BPS
     6|  "       " Ł     "       "  |  4.36 B2  SF(O)RY  28 BLP
     7|    '       Ó S '       '    |  6.96 11G F(I)BRY  24 LPS
     8|=   A G A D z I E     '     =|  6.96 E7  F(A)RBY  24 LPS
     9|    '       ' E '       '    |  7.02 B2  SP(O)RY  22 BFL
    10|  "       "   K   "       "  |  7.02 B2  PS(O)RY  22 BFL
    11|        -     I     -        |  7.03 2G  B(A)SF   20 LPRY
    12|'     -       E       -     '| --Tracking-----------------------------------
    13|    -       ' R '       -    | ?AAAAĄCCCDDEEEEĘGHHIIIIIJJLLŁMMMNNNNŃOOOOOPR
    14|  -       "   Y   "       -  | RSSTTUUWWWYYZZZZŹŻ  62
    15|=     '       =       '     =|
       ------------------------------

Tutaj znajomość `FLOPY` nie daje nam już aż takiej przewagi, bo kolejne najlepsze słowo (`BELFRY`) jest gorsze tylko o 2.51 (nominalnie o 4pkt, ale lepiej zostawić sobie `PS` niż `BRS`).

Jeszcze inna sytuacja:

    Speedy Player B: Turn 11
       A B C D E F G H I J K L M N O      Speedy Player A          AEIŁNSZ  380 
       ------------------------------  -> Speedy Player B          ?AKNNOO   286 
     1|=     '       =       F O T O| --Static Player's choices (your play: 1)-----
     2|  -       "       " C I   R  | best *A2 pOKONAN(A) 80 
     3|    -       '   S K U L N Y M| best  A2 dOKONAN(A) 80 
     4|'     -       ' P   M I   B E|  3.00 A2 KANONOw(A) 77 
     5|        -       I   O J   A S|  10.0 C2 pOKONAN(Y) 70 
     6|  "       T R Z E J       C  |  10.0 C2 dOKONAN(Y) 70 
     7|    '       '   Ś       ' H I|  10.0 C2 KsOANON(Y) 70 
     8|=     '   G Z I Ć     '     G|  10.0 C2 KANONOw(Y) 70 
     9|A R Y       A   '       '   Ł|  11.0 L7 NAKOp(A)NO 69 
    10|  Ó   B U Ź C E   "       W Y|  12.0 L7 KANON(A)dO 68 
    11|  D Ż E T   H       -     E  |  78.8 8A KuNO       35 ANO
    12|'     -     L ' K   P A M P Ę| --Tracking-----------------------------------
    13|    z E Z N A W A Ń     A R  | AEIŁNSZ  7
    14|  -       " L   D "     S Ą  |
    15|=   W Y D Z I W I     ' O   =|
       ------------------------------

Tutaj do naszego rankingu zostaną włączone tylko `POKONANA` i `DOKONANA` jako najlepsze premie z danego składu, ale ich _użyteczność_ dostanie wartość 78.8, czyli różnicę pomiędzy nimi a **kolejnym słowem z listy, do którego zagrania trzeba użyć innego zestawu liter**. Niesprawiedliwe byłoby bowiem, gdybyśmy dali im tylko 3 punkty tylko dlatego, że z danego składu jest więcej siódemek. Obecne rozwiązanie nie jest idealne, ale nie wiem jak z tym sobie poradzić lepiej.

Wygenerowałem 90 milionów gier, po analizie których uzyskałem ranking użyteczności. Lista jest do pobrania [stąd](../downloads/playability-pl.txt). Liczba obok słowa oznacza sumę punktów, które zyskalibyśmy przez znajomość danego słowa we wszystkich zasymulowanych grach. Obecność krótkich słów z zietami, eniami i esiami nie powinna dziwić, wszak bardzo często położenie takiej litery na potrójnej premii literowej jest droższe niż jakikolwiek inny ruch z _żużlowego_ składu. Z oczywistych ciekawostek: OFF, PFF i UFF są naprawdę bezużyteczne.

Zachęcam do analizy listy i wyciągania ciekawych wniosków, ale też wytykania błędów w metodologii jej otrzymywania — chętnie stworzę lepszą, jeśli będę wiedział jak. Nieco zmieniony kod źródłowy Quackle'a, którym się posłużyłem do utworzenia listy, znajduje się na moim [githubie](https://github.com/alkamid/quackle/blob/master/test/testharness.cpp). W bliżej nieokreślonej przyszłości chciałbym wygenerować listę najlepszych przedłużek, sprawdzić po ilu grach otrzymujemy zadowalającą zbieżność (wydaje się, że nie potrzeba aż 90mln), skompresować powyższą listę do form podstawowych, poszukać ciekawych zależności schowanych w liście, i tak dalej. Gdyby ktoś był zainteresowany, mam też nieobrobione dane, z których można na przykład wyłuskać użyteczność słów w pierwszej lub ostatniej fazie partii.