# Ćwiczenia 17 -- Android studio -- GPS, Open Street Maps

Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie GpsMaps na podstawie Empty Activity, dobierz
    odpowiednie API ( min. 26).

1. Otworzyć dokumentację:

   <https://developer.android.com/training/location/permissions>

   <https://developer.android.com/reference/kotlin/android/location/LocationManager?hl=en>

   <https://developer.android.com/training/location/request-updates>

   <https://developer.android.com/reference/android/location/Location>

1. Dodaj zależności ( aktualna wersja na

   <https://github.com/osmdroid/osmdroid>):

   ![image1](media/image1.png)

1. Docelowo chcemy uzyskać coś na kształt( marker ustawić na
    czerwony!!!):

   ![image2](media/image2.png)

1. Stwórz podstawowe struktury np.:

   ![image3](media/image3.png)

1. Stwórz layout dla aplikacji jak poniżej lub podobny:

   ![image4](media/image4.png)

   ![image5](media/image5.png)

1. Dodaj listener dla layoutu SwipeRefreshLayout:

   ![image6](media/image6.png)

1. Zadeklaruj w MainActivity.java:

   ![image7](media/image7.png)

1. W onCreate() dodaj:

   ![image8](media/image8.png)

1. Dodaj ( ważne: zwróć uwagę na kolejne dwa punkty!!! ):

   ![image9](media/image9.png)

1. W AndroidManifest.xml sprawdź czy masz uprawnienia:

   ![image10](media/image10.png)

1. Add permission check ( if z checkSelfPermission doda się
    automatycznie po wybraniu tej opcji)

   W trakcie realizacji ćwiczeń należy dodać stosone inne, wymagane uprawnienia!!!

   ![image11](media/image11.png)

1. Sprawdź czy zaimplementowałeś/aś metodę
    onRequestPermissionResult, np.:

   ![image12](media/image12.png)

1. Sprawdź czy wypisujesz odczyty:

   ![image13](media/image13.png)

1. Zaimplementuj LocationListener z potrzebnymi metodami:

   ![image14](media/image14.png)

   ![image15](media/image15.png)

1. Przetestuj aplikację, uruchom na urządzeniu. Przemieść się .

   ![image16](media/image16.png)

1. Część druga -- dodanie mapy

   ![image17](media/image17.png)

1. Parametry:

   ![image18](media/image18.png)

1. Dodanie punktu:

   ![image19](media/image19.png)

1. Dodanie markera i setMapListenera ( nie obligatoryjne ) :

   ![image20](media/image20.png)

1. Dodaj iconę markera, najlepiej plik.png itp:

   ![image21](media/image21.png)

1. Marker:

   ![image22](media/image22.png)

1. Dodaj obligatoryjnie menu górne:( opis i objaśnienie w punkcie 25)

   ![image23](media/image23.png)

1. Dodaj metodę sprawdzającą dostęp do GPS i internetu (colory czerwony
    i zielony na TextView)

   ![image24](media/image24.png)

1. Wykonaj zadania
   - wysłanie sms-em koordynat

     ![image25](media/image25.png)

     ![image26](media/image26.png)

   - zapisanie zdjęć mapy na karcie

     ![image27](media/image27.png)

   - udostępnienie wyników

     ![image28](media/image28.png)

   ![image29](media/image29.png)

1. Dodatkowe zadanie: wczytaj dane
    pogodowe dla obecnej lokalizacji:

    ![image30](media/image30.png)

   ![image31](media/image31.png)

   ![image32](media/image32.png)

1. KONIEC.🔚
