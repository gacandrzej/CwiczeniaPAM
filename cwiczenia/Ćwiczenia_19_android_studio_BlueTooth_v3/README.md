Ćwiczenia 19 -- Android studio -- bluetooth
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie BlueTooth na podstawie Empty Activity,
    dobierz odpowiednie API ( 28 -- Android 9).
2.  Otwórz dokumentację:
<https://developer.android.com/guide/topics/permissions/overview>
<https://developer.android.com/guide/topics/connectivity/bluetooth/permissions>
<https://developer.android.com/guide/topics/connectivity/bluetooth>
<https://developer.android.com/guide/topics/connectivity/bluetooth/setup>
<https://developer.android.com/guide/topics/connectivity/bluetooth/find-bluetooth-devices>
<https://developer.android.com/guide/topics/connectivity/bluetooth/transfer-data>
3.  Zadeklaruj potrzebne stałe, np.:
![](media/image1.png)
![](media/image2.png)
4.  AndroidManifest.xml:
![](media/image3.png)
5.  Przygotuj w activity_main.xml:
![](media/image4.png)
![](media/image5.png)
6.  Utwórz nowy layout o nazwie list_view_items.xml
![](media/image6.png)
7.  Dokończ tworzenie list dla sparowanych urządzeń i nowych urządzeń,
    np.:
![](media/image7.png)
8.  Jeśli bluetooth na urządzeniu jest wyłączony ustaw kolor czerwony na
    wybranych komponentach,
a kolor zielony jeśli bluetooth jest włączony, np.:
poniższy fragment wywołuje również okno z ustawieniami do włączenia
przez użytkownika!!!
![](media/image8.png)
9.  Napisz metodę sprawdzającą dostępność bluetooth na urządzeniu,
    fragment poniżej:
![](media/image9.png)
![](media/image10.png)
10. Zaimplementuj metody onResume(), onPause() itd.:.
11. Zaimplementuj także metodę onDestroy(), np.:
![](media/image11.png)
12. Utwórz listę sparowanych urządzeń:
![](media/image12.png)
13. Przetestuj aplikację, uruchom na urządzeniu. Wyświetl listę
    sparowanych urządzeń.
![](media/image13.png)
14. Stwórz metodę wyszukującą nowe urządzenia, poniżej przykładowy
    szkielet (patrz następny punkt):
![](media/image14.png)
15. Zarejestruj receiver:
![](media/image15.png)
![](media/image16.png)
![](media/image17.png)
16. Przetestuj wykrywalność nowych urządzeń:
![](media/image18.png)
17. Widoczność urządzenia dla innych urządzeń:
![](media/image19.png)
18. Dodaj receiver podający stany:
![](media/image20.png)
![](media/image21.png)
19. Dodaj receiver dla zmiany stanu skanowania:
IntentFilter:
![](media/image22.png)
Receiver:
![](media/image23.png)
20. Część druga: napisanie komunikatora tekstowego po bluetooth.
<https://developer.android.com/guide/topics/connectivity/bluetooth/connect-bluetooth-devices>
![](media/image24.png)
![](media/image25.png)
<https://developer.android.com/guide/topics/connectivity/bluetooth/transfer-data>
![](media/image26.png)
![](media/image27.png)
![](media/image28.png)
21. Wykonaj zadania
    a)  parowanie urządzeń towarzyszących:
<https://developer.android.com/guide/topics/connectivity/companion-device-pairing>
b)  przetestuj działanie komunikatora
c)  wybierz zadanie
<!-- -->
22. KONIEC.
