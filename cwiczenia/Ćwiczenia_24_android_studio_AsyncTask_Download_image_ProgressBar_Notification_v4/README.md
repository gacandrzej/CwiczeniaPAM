Ćwiczenia 24 -- Android studio -- AsyncTask, ExecutorService,
DownloadManager
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie MyAsyncTask na podstawie Empty Activity,
    dobierz odpowiednie API.
2.  Otwórz dokumentację:
> <https://developer.android.com/reference/android/os/AsyncTask>
>
> <https://developer.android.com/reference/android/app/PendingIntent>
>
> <https://developer.android.com/training/notify-user/build-notification#progressbar>
>
> <https://developer.android.com/reference/java/util/concurrent/package-summary>
>
> <https://developer.android.com/reference/java/util/concurrent/Executor>
3.  activity_main.xml:
![](media/image1.png)
4.  Zadeklaruj potrzebne stałe, np.: ( adres wybierz dowolny)
![](media/image2.png)
5.  Utwórz klasę MyAsyncTask
![](media/image3.png)
6.  Dodaj metodę doInBackground:
![](media/image4.png)
7.  Ustaw pobrane zdjęcie:
![](media/image5.png)
8.  Dla dostępnych urządzeń:
> ![](media/image6.png)
9.  Uruchom Pixel i wywołaj instancję klasy:
![](media/image7.png)
10. Sprawdzenie logCata:
> ![](media/image8.png)
11. Uzyskany efekt ( tylko zdjęcie u dołu):
> ![](media/image9.png)
Widok z ProgressDialog:
![](media/image10.png)
12. Klasa ExecutorService:
    a)  zrealizuj powyższe ćwiczenie z wykorzystaniem Klasy
        ExecutorService:
![](media/image11.png)
![](media/image12.png)
13. Sprawdź pobranie zdjęcia:
> ![](media/image13.png)
14. Zastąp przestarzały DialogProgress na rzecz ProgressBar:
    ![](media/image14.png)
15. Utwórz klasę :
![](media/image15.png)
16. Sprawdź uprawnienia od wersji 33+ tiramisu
> ![](media/image16.png)
17. Wywołaj
18. ![](media/image18.png)
    Sprawdź logcata:
19. Metoda executeMyService2():
![](media/image19.png)
20. Powiadomienie: dodaj powiadomienie z paskiem postępu, w stylu:
![](media/image20.png)
21. ![](media/image21.png)
    Fragment z realizacji:
![](media/image22.png)
22. Wywołanie na Pixel 4a:
![](media/image23.png)
23. Sprawdzenie:
![](media/image24.png)
24. LogCat:
![](media/image26.png)
25. Użyj:
<https://developer.android.com/reference/android/app/DownloadManager>
26. Efekt: ( środkowe po kliknięciu w powiadomienie DownloadManagera )
![](media/image27.png)
![](media/image13.png)
27. KONIEC.
