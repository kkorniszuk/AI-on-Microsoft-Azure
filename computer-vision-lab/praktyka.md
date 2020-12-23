# Część praktyczna
## 1.Scenariusz
W ramach labu stworzyłem aplikację która w czasie rzeczywistym monitoruje czy osoba przed komputerem ma założoną maseczkę. 
Rozwiązuje ona problem który będzie teraz występował w biurach - z uwagi na restrykcję związane z pandemią COVID-19 oraz ograniczeniami w pracy stacjonarnej, niektóre firmy zdecydowały się na wprowadzenie obowiązku noszenia maseczek w biurach.
System może działać w tle (tak jak desktime, który monitoruje czas pracy i aplikacje których używamy). 
Jeśli pracownik nie ma maseczki na twarzy, na ekranie wyświetla się odpowiedni komunikat. 
## 2. 
Najpierw znalazłem odpowiednią ilość zdjęć do trenowania modeli - około 50, które biorą pod uwagę różne scenariusze. Po wytrenowaniu i przetestowaniu modelu uzyskałem link do API. Użyłem go w stworzonej aplikacji angularowej, w której zaimplementowałem użycie 
API z kamerki internetowej i asynchroniczne callbacki wykonywane co 5 sekund do wspomnianego API w serwisie Custom Vision.
## 3. Architektura
Stworzone rozwiązanie składa się z dwóch składowych. Pierwsza część to API udostępnione przez Microsoft w którym znajduje się wytrenowany na podstawie odpowiednich zdjęć osób z maseczkami i bez maseczek (oraz częściowo nałożonymi maseczkami) model.
Ma on na celu rozpoznawać czy osoba jest w masce czy nie (lub czy ma ją częśćiowo nałożoną). Mamy zatem trzy tagi na zdjęciach. Druga część to aplikacja stworzona za pomocą 
frameworka Angular, która jest z jednej strony graficznym interfejsem do obsługi rozwiązania, a z 2 strony zbiera dane od użytkownika z kamerki internetowej z której korzysta i następnie wysyła je do 
API i przetwarza odpowiedź. 
![Alt text](https://github.com/kkorniszuk/AI-on-Microsoft-Azure/blob/main/computer-vision-lab/Custom%20Vision.png?raw=true "Title")
## 4. Kod i komentarz do aplikacji
Kod znajduje się na oddzielnym repozytorium (projekt stworzony za pomocą frameworka Angular, repo ma dostęp publiczny):
https://github.com/kkorniszuk/Custom-Vision-COVID

Video na YT z komentarzem i prezentacją działania aplikacji: 

https://www.youtube.com/watch?v=8cI0rsT4ll0&feature=youtu.be
