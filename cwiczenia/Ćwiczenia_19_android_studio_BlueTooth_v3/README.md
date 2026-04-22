# Ćwiczenia 19 -- Android studio -- bluetooth

💡Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie BlueTooth na podstawie Empty Activity,
    dobierz odpowiednie API.

1. Otwórz dokumentację:

    <https://developer.android.com/guide/topics/permissions/overview>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/permissions>
    <https://developer.android.com/guide/topics/connectivity/bluetooth>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/setup>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/find-bluetooth-devices>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/transfer-data>

1. Zadeklaruj potrzebne stałe, np.:

   ![image1](media/image1.png)

   ![image2](media/image2.png)

1. AndroidManifest.xml:
![ image3.png ](media/image3.png)
1. Przygotuj w activity_main.xml:
![ image4.png ](media/image4.png)
![ image5.png ](media/image5.png)
1. Utwórz nowy layout o nazwie list_view_items.xml
![ image6.png ](media/image6.png)
1. Dokończ tworzenie list dla sparowanych urządzeń i nowych urządzeń,
    np.:
![ image7.png ](media/image7.png)
1. Jeśli bluetooth na urządzeniu jest wyłączony ustaw kolor czerwony na
    wybranych komponentach,
a kolor zielony jeśli bluetooth jest włączony, np.:
poniższy fragment wywołuje również okno z ustawieniami do włączenia
przez użytkownika!!!
![ image8.png ](media/image8.png)
1. Napisz metodę sprawdzającą dostępność bluetooth na urządzeniu,
    fragment poniżej:
![ image9.png ](media/image9.png)
![ image10.png ](media/image10.png)
1. Zaimplementuj metody onResume(), onPause() itd.:.
1. Zaimplementuj także metodę onDestroy(), np.:
![ image11.png ](media/image11.png)
1. Utwórz listę sparowanych urządzeń:
![ image12.png ](media/image12.png)
1. Przetestuj aplikację, uruchom na urządzeniu. Wyświetl listę
    sparowanych urządzeń.
![ image13.png ](media/image13.png)
1. Stwórz metodę wyszukującą nowe urządzenia, poniżej przykładowy
    szkielet (patrz następny punkt):
![ image14.png ](media/image14.png)
1. Zarejestruj receiver:
![ image15.png ](media/image15.png)
![ image16.png ](media/image16.png)
![ image17.png ](media/image17.png)
1. Przetestuj wykrywalność nowych urządzeń:
![ image18.png ](media/image18.png)
1. Widoczność urządzenia dla innych urządzeń:
![ image19.png ](media/image19.png)
1. Dodaj receiver podający stany:
![ image20.png ](media/image20.png)
![ image21.png ](media/image21.png)
1. Dodaj receiver dla zmiany stanu skanowania:
IntentFilter:
![ image22.png ](media/image22.png)
Receiver:
![ image23.png ](media/image23.png)
1. Część druga: napisanie komunikatora tekstowego po bluetooth.
<https://developer.android.com/guide/topics/connectivity/bluetooth/connect-bluetooth-devices>
![ image24.png ](media/image24.png)
![ image25.png ](media/image25.png)
<https://developer.android.com/guide/topics/connectivity/bluetooth/transfer-data>
![ image26.png ](media/image26.png)
![ image27.png ](media/image27.png)
![ image28.png ](media/image28.png)
1. Wykonaj zadania
    a)  parowanie urządzeń towarzyszących:
<https://developer.android.com/guide/topics/connectivity/companion-device-pairing>
b)  przetestuj działanie komunikatora
c)  wybierz zadanie
<!-- -->
1. KONIEC.
