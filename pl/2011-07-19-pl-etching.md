---
layout: post
title: Trawienie
name: etching
comments: true
---

Jest to druga część [tej opowieści]({% post_url 2011-07-13-pl-cleanroom-hemt %}). Kiedy maska i próbka są dopasowane, na kilka sekund włącza się źródło UV. Używamy tu rezystu pozytywnego, co znaczy że ta część, która została poddana działaniu światła, zostanie rozpuszczona w kolejnym kroku (wywoływanie). Brzmi trochę jak domowa fotografika, prawda?

Wszystkie etapy chemiczne odbywają się pod specjalnym wyciągiem, który zbiera potencjalnie niebezpieczne opary. Próbka jest zanurzana w wywoływaczu, który rozpuszcza naświetlony rezyst. Żeby zobaczyć, czy wszystko się dobrze wywołało, wystarczy zwyczajny optyczny mikroskop. Najciekawszym wynalazkiem w tym etapie jest _DI weir_, czyli taka dwukomorowa śluza, w której przepływa dejonizowana woda. Gdzieś tam muszą być elektrody, które mierzą rezystancję wody - jeśli jest czysta, powinna ona wynosić około 18MΩ·cm. Wkładamy więc tam próbkę, która oczywiście zanieczyszcza wodę, i czekamy aż rezystancją wróci ponad 10MΩ·cm - wtedy możemy uznać, że nasza próbka jest wyczyszczona.

Jeszcze jedna ciekawostka o pokoju ligoraficznym: jest żółty. Na wszystkie okna naklejona jest filtrująca folia, która zapobiega dostaniu się tam wysokoenergetycznej części promieniowania słonecznego. Można się tam poczuć jak na jednym z obrazów van Gogha. Na pewno ludzie czasem się zapominają i wychodzą z pokoju z próbką w dłoniach przed wywołaniem... Na szczęście, wystarczy wtedy tylko zmyć rezyst i nanieść go jeszcze raz, a z próbką nic złego się nie dzieje.

{% include _figure.html src="samples/hemt_after_developing.png" caption="Po wywołaniu: widoczne śmieci to niezmyty do końca rezyst." %}

Czas na etap, w którym kluczowy jest... czas. **Trawienie** odbywa się w roztworze kwasu, który przygotowuje się kilka godzin wcześniej. Czasem trzeba trawić kilka razy, żeby uzyskać żądaną głębokość wyżłobienia. Nie wiem jeszcze od czego dokładnie zależy szybkość tego procesu, ale na pewno pośrednio od zanieczyszczeń i parametrów materiałowych. Trawienie mokre, w odróżnieniu od suchego, jest anizotropowe. Oznacza to, że ścianki mojego urządzenia nie będą proste, tylko pochylone, ponieważ rozpuszczanie materiału zatrzymuje się na pewnych kierunkach krystalograficznych (poniżej rysunek, który to obrazuje). Do sprawdzenia, czy trawienie przebiegło pomyślnie, używamy sprytnego narzędzia zwanego DEKTAK - profilometru. Myślałem, że pomiary powierzchni z nanometrową (a nawet subnanometrową) rozdzielczością wykonuje się teraz tylko AFM/STM, zdziwiłem się więc widząc DEKTAK, o którym zawsze myślałem jak o przodku mikroskopów bliskich oddziaływań. Ciekaw jestem, jak mocno może zniszczyć próbkę, bo przecież jest to diamentowe ostrze jeżdżące po niej. Najwidoczniej nie jest to takie ważne w przypadku QCL.

{% include _figure.html src="drawings/etching_wet-chemical_vs_rie_de.png" caption="Zauważcie, że trawione ściany są pochyłe (anizotropowość)." %}