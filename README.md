# Azure Content Moderator
## 1. Wstęp 
Serwis służy do wyszukiwania fraz takich jak przekleństwa, treści dla dorosłych lub po prostu wyszukiwania słów które mają się w tekście nie pojawiać. Miejsce gdzie taki bot może być użyty to: 
- czaty
- fora dyskusyjne
- czat z botem
- dokumenty
- wszelkie inne teksty, w których nie chcemy na przykład przekleńśtw lub treści nieodpowiednich dla dzieci
## 2. Użycie
Serwis umożliwia blokowanie lub zatwierdzanie treści w oparciu o pewne standardy. Zamiast wyznaczać do tego ludzi, bot może automatycznie odrzucać lub zatwierdzać posty na forach dyskusyjnych jeśli zawierają obraźliwe słowa lub treści dla dorosłych. W ten sposób można na przykład regulować czat dla uczniów podczas zdalnej edukacji żeby unikać tam treści nie na temat szkoły. Innym zastosowaniem jest kotrola pracowników i treści przez nie przesyłanych - podczas pracy nie powinni oni skupiać uwagi na rzeczach które nie są związane z ich pracą.
## 3. Implementacja
Po podaniu tekstu do API, każda potencjalna fraza zawierająca słowa z black-listy jest zwracana w odpowiedzi typu JSON. Dane odpowiedzi są dodatkowo grupowane w kilka grup - w zależności jak bardzo wyszukane frazy pasują do danych fraz. Indeksy mają wartości od 0 do 1 - im więcej tym bardziej prawdopodobne że dana fraza zawiera wyszukiwane słowo lub zwrot.

Możliwe jest również zaimplementowanie bota do wyszukiwania PII (personally identifiable information - wrażliwe dane osobowe). Po znalezieniu danej frazy zawierającej na przykład email lub telefon dostajemy z API odpowiedź w postaci JSON z indeksami gdzie znaleziono w tekście takie frazy.
## 4. Koszty
Mamy dwie instacje - darmową, dostępną w części regionów z ograniczeniem do 1 transakcji na sekundę oraz do 10 transakcji na sekundę. Koszt tej drugiej zależy od ilości zapytań, do 1 miliona wynosi 1$ za każde 1k transakcji, powyżej 5 milionów to już 0.75$ za kazde 1000 transakcji. Im więcej transakcji tym każde 1k jest tańsze.
Pełny cennik:
https://azure.microsoft.com/en-us/pricing/details/cognitive-services/content-moderator/
# LUIS
## 1. Wstęp 
LUIS (Language Understanding Intelligent Service) to serwis służacy do rozumienia tekstu i mowy. Dzięki niemu możliwe jest określenie ogólnej intencji i znaczenia tego co chce wyrazić dana osoba i otrzymanie dodatkowych informacji o tekście. Problemem zrozumienia tekstu i mowy jest jego brak sztywnych ram - proste zdania w danym języku nie stanowią problemów dla botów, ale wyczulenie technologii na slangi czy tak zwane phrasal verbs tworzy pewne wyzwania w projektowaniu takich botów.
## 2. Użycie
Jest to na tyle ciekawy serwis, że można podać wiele przykładów jego użycia. W zasadzie dowolna praca człowieka wymagająca komunikacji mogłaby zostać przez taki bot zastąpiona, oczywiście jeśli byłby w stanie pracować na jego poziomie. Przykładowe użycie może dotyczyć serwisu który będzie zatwierdzał lub odrzucał reklamacje. Rozmowa z botem będzie przebiegać na odpowiadaniu na jego pytania. Bot dysponując wiedzą od użytkownika będzie albo reklamacje przyjmował i dysponował ją dalej albo odrzucał. 

Innym zastosowaniem jest edukacja - bot mógłby wyręczyć nauczyciela i sprawdzać otwarte zadania jego uczniów i na podstawie ich tekstów wystawiać im odpowiednie oceny. 
## 3. Implementacja
LUIS używa trzech aspektów do rozummienia języka: 
- wypowiedzi - dane wejściowe użytkownika dla aplikacji
- intencje - zamiar, czyli cel wyrażony w wypowiedzi użytkownika
- encje - jednostki reprezentujące słowa i frazy do wyodrębnienia
Dzieląc zdania na częśći, możemy rozpoznawać dane frazy. Dla przykładu bot do rozpoznawania reklamacji może w danym tekście starać się znajdować przyczyny zepsucia się produktu lub datę zakupu i czy gwarancja nadal obowiązuje.

Tworzenie serwisu obejmuje stworzenie zasobu typu LUIS i podpięcie subskrypcji. Następnie należy stworzyć encje które określą konkretne działania użytkownika. Kolejnym krokiem jest wytrenowanie LUIS oraz stworzenie endpointa i opublikowanie aplikacji z botem. 
## 4. Koszty
LUIS składa się z 2 instancji - darmowej, mogącej rozpoznawać jedynie tekst do 10k transakcji na miesiąc oraz standardowej. Tutaj przepustowośc jest znacznie wyższa (50 a nie 5 transakcji na sekudnę) oraz istnieje możliwość rozpoznawania mowy - 5.50$ za 1000 transakcji. Rozpoznawanie znaczenia tekstu w tym pakiecie to 1.50$ za 1k transakcji. 
# Text Analytics API
## 1. Wstęp 
Jest to serwis do rozpoznawania emocji oraz zamiarów użytkownika, a także w jakim języku został napisany dany tekst. 
## 2. Użycie
Dobrym przykładem użycia jest psychologia - taki bot mógłby na przykład pomóc osobom w potrzebie dzięki temu że jest w stanie rozpoznać intencje oraz emocje które dane osoba przekazuje razem z tekstem. Świadczy o tym wiele rzeczy, na przykład używanie wielokropków oznaczać może zakłopotanie, pisanie samymi wielkimi literami złość a używanie niektórych emotikon radość.
Jeszcze innym przykładem jest sprawdzanie czy opinia o jakiejś instytucji jest pozytywna czy negatywna. Taki scenariusz był realizowany na jednym z labów w poprzednim semestrze - fikcyjny hotel dostawał opinie o pobycie i jeśli były negatywne to odsyłał je dalej, gdzie były analizowane. Był w stanie sprawdzić czy w danej opinii są frazy lub znaki mogące świadczyć o tym że dana osoba nie była zadowolona z pobytu.
## 3. Implementacja
Serwis wystawia REST API podające na wyjściu jak bardzo dane zdanie jest nacechowane daną emocją w skali od 0 do 1. Zdania bardziej pozytywne będą bliższe 1, zdania nacechowane negatywnie 0. Jeśli wynik wynosi 0.5, zdanie jest neutrealne. Można w ten sposób zaimplementować wspomnianego bota do rozpoznawania nastawienia klientów - poszczególne opinie trafiałyby do kolejki, gdzie byłyby dalej analizowane.
## 4. Koszty
Ceny dla serwisu Text Analytics do rozpoznawania min. emocji zależą od wybranego pakietu i mogą być albo podliczane w ramach ilości transakcji lub za każdy miesiąc.
