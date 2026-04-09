# Ćwiczenia 24 -- Android studio -- AsyncTask, ExecutorService, DownloadManager

💡Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie MyAsyncTask na podstawie Empty Activity,
    dobierz odpowiednie API.

1. Otwórz dokumentację:

   <https://developer.android.com/reference/android/os/AsyncTask>

   <https://developer.android.com/reference/android/app/PendingIntent>

   <https://developer.android.com/training/notify-user/build-notification#progressbar>

   <https://developer.android.com/reference/java/util/concurrent/package-summary>

   <https://developer.android.com/reference/java/util/concurrent/Executor>

1. activity_main.xml:

   ![image1](media/image1.png)

1. Zadeklaruj potrzebne stałe, np.: ( adres wybierz dowolny)

   ![image2](media/image2.png)

1. Utwórz klasę MyAsyncTask

   ![image3](media/image3.png)

1. Dodaj metodę doInBackground:

   ![image4](media/image4.png)

1. Ustaw pobrane zdjęcie:

   ![image5](media/image5.png)

1. Dla dostępnych urządzeń:

   ![image6](media/image6.png)

1. Uruchom Pixel i wywołaj instancję klasy:

   ![image7](media/image7.png)

1. Sprawdzenie logCata:

   ![image8](media/image8.png)

1. Uzyskany efekt ( tylko zdjęcie u dołu):

   ![image9](media/image9.png)

   Widok z ProgressDialog:

   ![image10](media/image10.png)

1. Klasa ExecutorService:

   - zrealizuj powyższe ćwiczenie z wykorzystaniem Klasy
     ExecutorService:

   ![image11](media/image11.png)

   ![image12](media/image12.png)

1. Sprawdź pobranie zdjęcia:

   ![image13](media/image13.png)

1. Zastąp przestarzały DialogProgress na rzecz ProgressBar:

   ![image14](media/image14.png)

1. Utwórz klasę :

   ![image15](media/image15.png)

1. Sprawdź uprawnienia od wersji 33+ tiramisu

   ![image16](media/image16.png)

1. Przetestuj aplikację:

   ![image17](media/image17.png)

1. Sprawdź logcata:

   ![image18](media/image18.png)

1. Metoda executeMyService2():

   ![image19](media/image19.png)

1. Powiadomienie: dodaj powiadomienie z paskiem postępu, w stylu:

   ![image20](media/image20.png)

   ![image21](media/image21.png)

1. Fragment z realizacji:

   ![image22](media/image22.png)

1. Wywołanie na Pixel 4a:

   ![image23](media/image23.png)

1. Sprawdzenie:

   ![image24](media/image24.png)

1. LogCat:

   ![image26](media/image26.png)

1. Użyj:

   <https://developer.android.com/reference/android/app/DownloadManager>

1. Efekt: ( środkowe po kliknięciu w powiadomienie DownloadManagera )

   ![image27](media/image27.png)

   ![image28](media/image13.png)

1. KONIEC.🔚
