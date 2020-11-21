# Bot dla osób chorych na covid
## 1. Use case
Bot którego stworzyłem ma służyć do pomocy osób chorych na covid lub mających podejrzenie że mają jego objawy. Poza tym jest w stanie podać atkualne statystyki covida dla danego kraju. W przyszłości bota można rozszerzyć o funkcje pomocy osobom w potrzebie - na przykład gdy ktoś w podeszłym wieku nie jest w stanie zrobić sobie sam zakupów lub potrzebuje pomocy w wyprowadzeniu psa a sam jest na kwarantannie.
## 2. Architektura
Bota stworzyłem za pomocą Bot Framework Composer. Bardzo przyspiesza on budowę bota ze względu na zastosowanie GUI oraz ma wsparcie dla innych przydatnych narzędzi takich jak Bot Framework Emulator, który pozwala na testowanie bota i wykrywanie błędów. Planowałem użycie zasobu LUIS do zbudowania prostego modelu który pozwalałby na wykrycie czy dana osoba potrzebuje pomocy z zakupami itd., ale nie udało mi się niestety podłączyć do mojego bota ze względu na to że dostawałem błędy przy próbie autoryzacji mojego klucza dla serwisu LUIS. 
Mimo to stworzyłem prosty model, który całkiem dobrze radzi sobie z wykrywaniem intencji użytkownika gdy zaczyna pisać o potencjalnych objawach covid-19 lub o tym że nie jest w stanie zrobić sobie na przykład zakupów. 
Kolejną funkcjonalnością jest odczyt aktualnych statystyk covida dla danego kraju. Bot informuje nas wtedy ile do tej pory było przypadków zachorowań, śmierci i uzdrowień. Poza tym bot ma też kilka mniejszycj featerów, takich jak zakończenie aktualnego wątku.
## 3. Kod i uruchomienie
Bota udostępniłem jako projekt z Bot Framework Composera. Jest w repozytorium w folderze CovidBot. Lokalne uruchomienie wymaga Composera i Emulatora. Po sklonowaniu repozytorium otwieramy go jako projekt w Composerze. 
Link do video: https://www.youtube.com/watch?v=4VMYV3RtRGw&feature=youtu.be
