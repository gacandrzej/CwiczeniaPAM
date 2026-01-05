Ćwiczenia 17 -- Android studio -- GPS, Open Street Maps
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie GpsMaps na podstawie Empty Activity, dobierz
    odpowiednie API ( min. 26).
2.  Otworzyć dokumentację:
<https://developer.android.com/training/location/permissions>
<https://developer.android.com/reference/kotlin/android/location/LocationManager?hl=en>
<https://developer.android.com/training/location/request-updates>
<https://developer.android.com/reference/android/location/Location>
3.  Dodaj zależności ( aktualna wersja na
    <https://github.com/osmdroid/osmdroid>):
![](media/image1.png)
4.  Docelowo chcemy uzyskać coś na kształt( marker ustawić na
    czerwony!!!):
![](media/image2.png)
5.  Stwórz podstawowe struktury np.:
![](media/image3.png)
6.  Stwórz layout dla aplikacji jak poniżej lub podobny:
![](media/image4.png)
![](media/image5.png)
7.  Dodaj listener dla layoutu SwipeRefreshLayout:
![](media/image6.png)
8.  Zadeklaruj w MainActivity.java:
![](media/image7.png)
9.  W onCreate() dodaj:
![](media/image8.png)
10. Dodaj ( ważne: zwróć uwagę na kolejne dwa punkty!!! ):
![](media/image9.png)
11. W AndroidManifest.xml sprawdź czy masz uprawnienia:
![](media/image10.png)
12. Add permission check ( if z checkSelfPermission doda się
    automatycznie po wybraniu tej opcji)
> W trakcie realizacji ćwiczeń należy dodać stosone inne, wymagane
> uprawnienia!!!
![](media/image11.png)
13. ![](media/image12.png)
    Sprawdź czy zaimplementowałeś/aś metodę
    onRequestPermissionResult, np.:
14. Sprawdź czy wypisujesz odczyty:
![](media/image13.png)
15. Zaimplementuj LocationListener z potrzebnymi metodami:
![](media/image14.png)
![](media/image15.png)
16. Przetestuj aplikację, uruchom na urządzeniu. Przemieść się .
![](media/image16.png)
17. Część druga -- dodanie mapy
![](media/image17.png)
18. Parametry:
![](media/image18.png)
19. Dodanie punktu:
![](media/image19.png)
20. Dodanie markera i setMapListenera ( nie obligatoryjne ) :
![](media/image20.png)
21. Dodaj iconę markera, najlepiej plik.png itp:
![](media/image21.png)
22. Marker:
![](media/image22.png)
23. Dodaj obligatoryjnie menu górne:( opis i objaśnienie w punkcie 25)
> ![](media/image23.png)
24. Dodaj metodę sprawdzającą dostęp do GPS i internetu (colory czerwony
    i zielony na TextView)
![](media/image24.png)
25. Wykonaj zadania
    a)  wysłanie sms-em koordynat
> ![](media/image25.png)
>
> ![](media/image26.png)
b)  zapisanie zdjęć mapy na karcie
> ![](media/image27.png)
c)  udostępnienie wyników
![](media/image28.png)
26. ![](media/image29.png)
    Dodatkowe zadanie: wczytaj dane
    pogodowe dla obecnej lokalizacji:
> ![](media/image30.png)
>
> ![](media/image31.png)
>
> ![](media/image32.png)
27. KONIEC.
