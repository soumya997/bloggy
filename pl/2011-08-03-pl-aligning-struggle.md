---
layout: post
title: Walka z dopasowaniem maski
name: aligning-struggle
comments: true
---

No ładnie, minęły już dwa tygodnie od kiedy ostatni raz pisałem... to po części dlatego, że zacząłem robić mój pierwszy laser kaskadowy i większość dni spędzam w cleanroomie. Po tych kilku dniach mam już trochę wprawy, kilka zdjęć i dużo do napisania!

Powoli nabieram pewności siebie przy dopasowywaniu masek i wywoływaniu ich, ale były takie dni, że spędzałem 3 godziny próbując postawić mały krok naprzód bez ŻADNYCH rezultatów. Yash zostawia mnie teraz samego, więc jestem całkiem niezależny - z jednej strony to bardzo pouczające, a z drugiej robię błędy, których nie zrobiłbym, pytając wcześniej Yasha. Oto co mam do powiedzenia o dopasowywaniu maski...

Pierwsza jest prościutka. Służy ona do usunięcia rezystu znajdującego się na brzegach i w rogach próbki (tzw. edge beads) - tworzy on tam większe krople, które mogą przeszkadzać w późniejszych etapach. Kolejna maska jest już ważniejsza, bo za jej pomocą definiuje się rdzeń lasera (ridge). Jednak wciąż nie ma punktów odniesienia, więc wystarczy dopasować wzór do kierunków krystalograficznych. Zdjęcie poniżej przedstawia próbkę n+ po wywołaniu paska lasera. n+ znaczy tyle, że jest to zwyczajne domieszkowane podłoże GaAs - nie ma tam "kanapkowej" struktury QCL. Używam jej do testów - każdy krok robię najpierw na niej, żeby zobaczyć czy wszystko działa tak jak oczekuję.

{% include _figure.html src="samples/n_1st_developing.png" caption="próbka n+ po pierwszym wywołaniu" %}

Następnie trzeba próbki wytrawić, o czym napisałem już [kilka słów]({% post_url 2011-07-19-pl-etching %}) i napiszę kiedyś więcej. Po trawieniu należy wywołać dolne kontakty - po jednym symetrycznie po obu stronach lasera. W piątek spędziłem nad tym 3 godziny. Za każdym razem, gdy oglądałem próbkę pod mikroskopem po wywołaniu, widziałem kompletnie niedopasowany wzór - jeden kontakt był zdecydowanie bliżej niż drugi. Wywoływanie można powtarzać kilka razy, ale zajmuje to trochę czasu: czyszczenie acetonem i izopropanolem, nałożenie rezystu, wygrzanie, dopasowanie maski, 5 minut w chlorobenzenie, 2-3 minuty wywoływania i w końcu 2-3 minuty czyszczenia. Całkowity czas jednego powtórzenia to prawie godzina - przynajmniej na razie, póki się nie wprawię. Ponieważ mogę przebywać w cleanroomie tylko do 17:30. poszedłem do domu i kontynuowałem w poniedziałek rano. Jakimś cudem udało mi się ustawić dobrze n+, ale prawdziwe próbki tylko mnie frustrowały. Kiedy przyszedł Yash, okazało się że używałem złego rozmiaru maski: jest ich na płytce 5 lub 6, każdy zaprojektowany na inną szerokość lasera. Jak mogłem tego nie zauważyć?! Albo Yash mi zapomniał powiedzieć, albo ja zapomniałem że mi powiedział.

Gdy już wiedziałem, którego wzoru użyć, praca wreszcie ruszyła się z miejsca i mogłem bardziej skupić się na wywoływaniu niż na dopasowywaniu. Jednak to pierwsze też nie jest takie proste, bo czas wywoływania może się znacząco różnić między jedną próbką a drugą. Poniższy obrazek przedstawia nie do końca wywołany wzór:

{% include _figure.html src="samples/4or5_2nd-developing_underdeveloped.jpg" caption="Nie do końca wywołana próbka." %}

Widać dwa kontakty (jasny pasek na górze i kawałek drugiego na dole) w pełni wywołane, zaś środkowy - ten mieniący się kolorami - zupełnie niewywołany. To dziwne, bo proces powinien być jednorodny. Na szczęście "niedowywołanie" skutkuje tylko kolejnymi pięcioma minutami wywoływania. Jak już zrobiłem to poprawnie, trzeba było napylić metal (AuGeNi), ale o tym kiedy indziej. Po ewaporacji - jakżeby inaczej - więcej wywoływania! Tym razem ustawianie maski poszło już nieźle, ale na dole można zobaczyć co się stało po wywoływaniu: pasek na laserze pięknie odszedł, za to pozostały rezyst wyglądał okropnie. Zmieniliśmy chlorobenzen i wywoływacz na nowe, wiedzieliśmy też że rezyst był zmieniany kilka godzin wcześniej, więc ciężko było odgadnąć przyczynę. Spróbowaliśmy jeszcze raz, z takim samym skutkiem.

{% include _figure.html src="samples/nplusweird.jpg" caption="Niesforny rezyst." %}

Zdezorientowani, wyciągnęliśmy ciężką artylerię: rezyst 1828, najgrubszy jakiego używamy. O dziwo, tym razem poszło gładko, tzn. rezyst wyglądał normalnie, bo napotkałem kolejny problem: to co miało zejść, znikało bardzo opornie. W końcu przyszło mi powtarzać wywoływanie 5 razy, co dało całkowity czas rzędu 8-9 minut, podczas gdy normalnie 1-2 minuty wystarczają. Panie i Panowie, na dole przedstawiam Wam próbkę gotową na napylenie górnego kontaktu. Jeśli się przyjrzycie, ten jasny pasek (czyli wywołany rezyst) nałożony jest na pasek lasera. Po prawej stronie tego paska widać małą, niebieskawą plamkę pozostałego rezystu, ale nie ma ona znaczenia, bo tę część i tak się ucina na końcu.

{% include _figure.html src="samples/nr4_topcontacts_developed.jpg" caption="Próbka po trzech dniach wywoływania." %}