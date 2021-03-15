---
layout: post
title: Jak świeci laser?
name: how-laser-lases
comments: true
---

Skąd wiem, że mój laser działa poprawnie? Muszę oczywiście wykonać na nim jakiś pomiar, bo promieniowanie to nie jest widoczne dla ludzkiego oka (a raczej dla **żadnego** oka). W naszej grupie możemy przeprowadzać co najmniej kilka różnych eksperymentów na QCLach. Najprostszym z nich jest charakterystyka LIV (moc-prąd-napięcie) - dane z niego wskazują, czy laser świeci i dla jakiego natężenia świecenie jest najmocniejsze.

Po pierwsze, muszę zamontować laser na kriostacie. Końcówkę kriostatu nazywamy zimnym palcem. Jak obydwie nazwy wskazują, używane są one do schłodzenia naszego urządzenia - robimy to poprzez zalanie kriostatu ciekłym helem o temperaturze około 4.5K lub -269C. Jest on tak skonstruowany, że mała komora, w której znajduje się próbka, nie jest wypełniana, ponieważ mogłoby to zakłócać pomiar. Zimno od helu jest przenoszone przez cienką, metalową część - stąd nazwa zimny palec. Przed postawieniem kriostatu na stole pomiarowym, muszę się jeszcze upewnić, czy żadne połączenie nie jest przerwane - wystarczy zmierzyć opór urządzenia zwykłym multimetrem.

{% include _figure.html src='samples/zimnypalec.jpg' caption='Zimny palec' %}

Kriostat ma cztery okna, przez które promieniowanie wychodzi na zewnątrz. Przed pomiarem LIV, wyciągam jedno z nich i umieszczam tam termostos. Jeśli ta nazwa nic Wam nie mówi, to może stos termopar pomoże. W każdym razie jest to element, który nawet małe zmiany temperatury konwertuje na mierzalne napięcie. Laser świeci więc na taki detektor, wywołuje malutkie jego ocieplenie, a ja widzę prąd.

Jakie użyteczne informacje można wyciągnąć z takiego pomiaru? Niestety, moc którą otrzymuje jest podana tylko w relatywnych jednostkach, więc nie ma z tego wielkiego pożytku. Mogę jednak wyznaczyć natężenie prądu, dla którego otrzymujemy najmocniejsze świecenie, czyli takie, przy którym kaskady są do siebie **dopasowane**. Widać to na rysunku z [poprzedniego postu]({% post_url 2011-10-13-kwantowy-laser-kaskadowy-w-prostych-slowach %}) - innymi słowy, urządzenie świeci najmocniej dla konkretnego nachylenia tego diagramu, którym to steruje się za pomocą prądu. Poza tym, powtarzam pomiar w różnych temperaturach, żeby zobaczyć kiedy robi się zbyt gorąco, by laser pracował (zazwyczaj jakieś -200C). Obserwując różne elementy wykresu można dowiedzieć się dużo o samym działaniu urządzenia: dla jakich prądów świeci, czy emituje jakieś dodatkowe promieniowanie, jaka jest jego rezystywność etc. Poniżej znajduje się wykres LIV mojego pierwszego lasera. Jest on zaprojektowany na emisję dwukolorową, więc widać po prawej stronie wzgórek, gdzie zachodzi emisja drugiego koloru (czyli promieniowania o nieco innej energii). Mniej więcej proste linie na górze to zależność między prądem a napięciem.

{% include _figure.html src='drawings/myfirstliv.png' caption='LIV mojego lasera' %}