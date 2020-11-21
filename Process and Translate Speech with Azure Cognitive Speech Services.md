# Transcribe speech input to text
## 1. Wstęp 
Serwis służący do transkrypcji w czasie rzeczywistym dźwięku i mowy na tekst.
## 2. Użycie
Przykładowym użyciem jest rozwiązanie dla osób które nie słyszą - usługa może przemieniać na tekst mowę z filmu i następnie wyświetlać go jako napisy. Oczywiście wiele filmów ma wbudowane napisy, ale jest nadal dużo takich które ich nie mają, a to uniemożliwia osobom niesłyszącym ich obejrzanie. Innym zastosowaniem są wydarzenia relacjonowane na żywo w sieci, których w czasie pandemii jest znacznie więcej niż kiedyś. 
## 3. Implementacja
Po utworzeniu serwisu na Azure, do dalszej pracy potrzebne będą klucz z subskrypcją i Ep do którego będziemy się odpytywać. Na wejściu EP podawany jest plik audio, na wyjściu dostajemy obiekt z wykrytym tekstem.
## 4. Koszty
Mamy dwa tiery - darmowy i standard. Darmowy ma pewne ograniczenia, na przykład umożliwia przetwarzanie jedynie do 5 godzin audio na tekst. W standardowym tierze 1 godzina audio to 1 dolar.
# Synthesize Text Input to Speech
## 1. Wstęp 
Serwis służący do zamiany tekstu na mowę. Dostępne są standardowe głosy lub ich edycja i rozszerzanie przez sieć neuronową. 
## 2. Użycie
Ciekawym zastosowaniem AI jest odtwarzanie głosów aktorów których już nie ma na świecie, lub z innych powodów nie jest możliwa praca z nimi. Kiedyś trafiłem na film na yt gdzie za pomocą AI ktoś odwtorzył głos postaci z gry do moda, co umożliwiło czytanie sentencji przez AI które nigdy nie zostały wypowiedziane przez prawdziwego aktora. Film dotyczył gry Gothic 2, ale w sieci pełno jest innych przykładów użycia takich botów. 
## 3. Implementacja
Do implementacji potrzebne są dwie rzeczy - klucz subskrypcji i EP. Działa to podobnie jak w speech-text, na wejsciu podajemy tekst, a następnie komputer przeczyta dany tekst.
## 4. Koszty
Podobnie jak w speech-text, mamy dwa tiery. W darmowym mamy ograniczenia w postaci liczby znaków na miesiąć. W standardowym tierze przy funkcji neuronowej to około 14 euro za 1 mln znaków.
# Translate speech with the speech service
## 1. Wstęp 
Serwis służący do tłumaczenia mowy na inny język. W przeciwieństwie do tradycyjnego tłumaczenia komputerem, serwis jest w stanie za pomocą sieci neuronowych przetłumaczyć znacznie lepiej dany tekst.
## 2. Użycie
Komunikacja z osobami które nie posługują się naszym językiem. Kontakty biznesowe z osobami nie znającymi polskiego ani angielskiego.
## 3. Implementacja
Jako że serwis potrafi rozpoznać język w którym został wysłany tekst do EP, to na zwrotce dostajemy wykryty język i tekst na który został przetłumaczony. Standardowo, musimy podać EP i API key do naszych zasobów na Azure przed wykonaniem zapytania. 
## 4. Koszty
5 bezpłatnych godzin na miesiąc, potem około 2 euro za godzinę. 
