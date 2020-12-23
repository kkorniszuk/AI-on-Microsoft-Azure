# Computer vision lab
## Computer Vision API
1. Przedstawienie serwisu
Serwis do wyodrębniania tekstu (OCR), rozpoznawania obrazów (pojęć, obiektów) oraz analizy przemieszczania się ludzi w czasie rzeczywistym. Można zatem wykrywać konkretne obiekty na przesłanym obrazie lub video.
2. Przykłady użycia
Przykładem użycia jest analiza ilości osób w danym miejscu - dla przykłady gdy w mediach poda się różne liczby w różnych stacjach TV, można to wtedy łatwo zweryfikować za pomocą tego serwisu. Inny przykład użycia to skanowanie tekstu napisanego ręcznie do tekstu przetworzalnego przez komputer.
3. Użycie
Podobnie jak w innych serwisach, wymagane jest posiadanie ważnej subskrypcji a następnie można już korzystać z EP. Microsoft udostępnia odpowiednie API do używania ich w tym serwisie, możemy zatem używać w tym celu języka C#. Po przesłaniu obrazu na EP dostajemy odpowiedź w postaci json i analizę zawartości obrazu. 
4. Cennik
Do 20 transakcji na minutę jest za darmo. Potem płacimy 0,844 za 1000 transakcji do miliona transakcji za rozpoznawanie twarzy. 
## Custom Vision
1. Przedstawienie serwisu
Serwis służy do niestandardowego tworzenia modeli SI które mają na celu rozpoznawanie konkretnej zawartości na zdjęciach i wideo. Udostępniona jest też usługa w postaci interfejsu GUI, który z 1 strony bardzo mocno upraszcza trenowanie sieci oraz testowanie, a z 2 strony pozwala się skupić na wykonaniu modelu a nie konfiguracji platformy (jedna z największych zalet technologii chmurowych).
2. Przykłady użycia
Przykładem użycia jest rozpoznawanie konkretnych rodzajów obiektów na zdjeciu, jak na przykład to czy dana osoba ma maseczkę czy nie. Możliwe jest rozpoznawanie konkretnych produktów na zdjeciu, monitorowanie pomieszczeń (na przykład wykrywanie nietypowych zachowań ludzi w strzeżonych obiektach).
3. Użycie
Tworzymy projekt na platformie https://www.customvision.ai/. Następnie w celu wytrenowania modelu dodajemy zdjęcia i oznaczamy odpowiednimi tagami interesujące nas przedmioty lub obiekty. Im wiecej zdjeć i im bardziej sa urozmaicone i poprawnie dobrane, tym lepszy efekt w postaci dobrze wytrenowanego modelu otrzymamy. Następnie po wykonaniu iteracji treningu dostajemy szczegóły EP i możemy zacząć wysyłać tam zawartość w celu rozpoznania interesujących nas obiektów. Odpowiedź jest w postaci json, dzięki czemu jest możliwe użycie tego serwisu w wielu środowiskach, od technologii związanych z JS, po backendy tworzone w pythonie.
4. Cennik
Za darmo można użyć do 5000 obrazów na uczenie w jednym projeckie i 2 transakcje na sekundę. Płacąc 1,687 euro za 1000 transakcji dostajemy 10 transakcji możliwych do wykonania na sekundę.
## Video Indexer
1. Przedstawienie serwisu
Serwis służy do wyodrębniania metadanych z zawartości audio i video. Mogą to być słowa, tekst pisany, twarze, osoby mówiące, znane osoby (aktorzy, politycy) lub marki. 
2. Przykłady użycia
Jednym z przykładów użycia jest sprawdzenie czy dane wideo przed publikacją nie zawiera produktów znanych marek. Dla przykładu platforma YouTube może usuwać lub blokować filmy które zawierają lokowane produkty. Serwis może też posłużyć do wyszukiwania muzyki w danym filmie. 
3. Użycie
Po stworzeniu usługi oraz pobraniu API key możemy zauplodować video które zostanie przetworzone. 
4. Cennik
Do 10 godzin bezpłatnego użycia. Po przekroczeniu darmowych limitów analiza wideo to 0,127 euro za minutę sygnału i 0,034 euro za minutę audio.
