# Ćwiczenia 22 -- Android studio -- Rest API

📔 Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie RestApi na podstawie Empty Activity, dobierz
    odpowiednie API ( 28 -- Android 9).

1. Otwórz dokumentację:

    <https://developer.android.com/reference/org/json/JSONArray>
    <https://developer.android.com/reference/org/json/JSONObject>
    <https://developer.android.com/reference/android/os/AsyncTask>
    <https://developer.android.com/reference/java/util/concurrent/package-summary>
    <https://developer.android.com/reference/java/util/concurrent/Executor>

1. Efekt końcowy

   ![img_1.png](media/image14.png)

1. Stwórz klasę MyAsyncTask

   ![image1](media/image1.png)

1. Zaimplementuj metodę doInBackground(), <kbd>Alt</kbd>+<kbd>Enter</kbd>

   ![image2](media/image2.png)

1. Zaimplementuj pozostałe metody :

   ![image3](media/image3.png)

1. Wywołaj wątek

   ![image4](media/image4.png)

1. Przetestuj aplikację. Oczekiwany efekt:

   ![image5](media/image5.png)

1. Sprawdź zawartość strony: <https://randomuser.me/api>

   ![image6](media/image6.png)

1. Dodaj:

   ![image7](media/image7.png)

1. Odczytaj składowe

   ![image8](media/image8.png)

1. Uzupełnij metodę onProgressUpdate

   ![image9](media/image9.png)

1. Przetestuj aplikację:

   ![image10](media/image10.png)

1. Krok 3: załaduj zdjęcie:

    <https://developer.android.com/topic/performance/graphics/load-bitmap>

    <https://square.github.io/picasso/>

   ```xml
   implementation \'com.squareup.picasso:picasso:*(insert latest version)*\'
   ```

   ![image11](media/image11.png)

1. Załaduj zdjęcie:

   ![image12](media/image12.png)

1. Dodaj datę urodzenia oraz wiek tak, aby otrzymać:

   ![img.png](media/image13.png)

1. Samodzielnie dodaj pola: telefon, państwo, miasto i ulicę.

1. Dodaj nawigację dolną, możesz skorzystać z

   <https://github.com/gacandrzej/BottomNav>

   ![img.png](media/image15.png)

1. Po kliknięciu w pozycję listy otwiera się nowy widok:

   ![img.png](media/image16.png)

1. Wykonaj:

    - dodaj zmianę wartości, zdjęcia poprzez odświeżenie
        SwipeRefreshLayout **swipeRefreshLayout**;
        zastąp zdarzenie kliknięcia w przycisk na przeciągnięcie palcem
        **swipeRefreshLayout**.setOnRefreshListener(() -\>

    - utwórz aktywność dla innego API np.:

       <https://rickandmortyapi.com/api/character/>

      ![img.png](media/image17.png)

      lub

      - <https://www.apicountries.com/countries>

      - <https://api.fbi.gov/wanted/v1/list>

      - <https://api.coinbase.com/v2/currencies/crypto>

        ![img.png](media/image18.png)

    - Umieść dane osób na komponencie ListView lub RecyclerView,
        kliknięcie pozycji listy przenosi do nowej aktywności na której
        wyświetlisz zdjęcie i dane osoby

    - zbuduj własne API: <https://www.postman.com/>

    - skorzystaj z innej biblioteki niż Picasso

    - zrealizuj ćwiczenie w oparciu o:

      - <https://developer.android.com/reference/java/util/concurrent/package-summary>
      - <https://developer.android.com/reference/java/util/concurrent/Executor>

1. KONIEC.😀
