Ćwiczenia 23 -- Android studio -- Service
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie MySimpleServiceMusic na podstawie Empty
    Activity, dobierz odpowiednie API ( 28 -- Android 9).
2.  Otwórz dokumentację:
[https://developer.android.com/guide/components/foreground-services](https://developer.android.com/guide/components/foreground-services)
[https://developer.android.com/reference/android/app/PendingIntent](https://developer.android.com/reference/android/app/PendingIntent)
3.  Utwórz nowy service o nazwie MyForegroundService, New → Service →
    Service :
4.  Sprawdź obecność wpisów w AndroidManifest.xml:
![](media/image1.png)
5.  W MainActivity:
![](media/image2.png)
6.  W metodzie onStart():
![](media/image3.png)
7.  ![](media/image4.png)
    W metodzie onStop():
8.  Szkielet metody onButtonClick():
![](media/image5.png)
9.  Definiuje wywołania zwrotne dla wiązania usług, przekazywane do
    bindService():
![](media/image6.png)
10. W klasie MyForegroundService zaimplementuj potrzebne metody do
    testów:
![](media/image7.png)
11. Zapoznaj się z fragmentem:
![](media/image8.png)
12. Odśwież informacje o cyklu życia:
13. Dodaj metodę onStartCommand ( jeśli musisz :)
![](media/image10.png)
14. Przygotuj metody testowe:
![](media/image11.png)
15. Sprawdź czy zwracasz binder:
![](media/image12.png)
Przetestuj aplikację:
![](media/image13.png)
16. Upewnij się, że dodałeś/aś kanał:
<https://developer.android.com/training/notify-user/channels>
![](media/image14.png)
17. Pozostałe zadania:
    a)  przekształć service w usługę odtwarzającą muzykę dla aplikacji.
    b)  Przetestuj działanie usługi podczas zamykania aplikacji,
        otwierania, wznawiania, minimalizacji
    c)  dodaj nawigację do obsługi aplikacji, przyciski play, pause,
        resume i stop
> ![](media/image15.png)
d)  dodaj całkowity czas utworu oraz aktualnie odtwarzany
![](media/image16.png)
> ![](media/image17.png)
e)  dodaj TextView na nazwę utworu
f)  ![](media/image18.png)
    dodaj funkcjonalność odtworzenia
    muzyki z sieci z danego url, np.:
g)  dodaj odtwarzanie muzyki z plików \*.mp3
> ![](media/image19.png)
h)  dodaj widget z 3 przyciskami play, pause i stop
> ![](media/image20.png)
>
> ![](media/image21.png)
i)  dodaj odtwarzanie na powiadomnieniu
> ![](media/image22.png)
j)  dodaj odtwarzanie na ekranie blokady
> ![](media/image23.png)
18. KONIEC.
