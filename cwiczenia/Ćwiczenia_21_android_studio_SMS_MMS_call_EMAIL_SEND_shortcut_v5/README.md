Ćwiczenia 21 -- Android studio -- sms, email send, shortcut
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie MySmsMailShortcut na podstawie Empty
    Activity, dobierz odpowiednie API ( 28 -- Android 9).
2.  Otwórz dokumentację:
<https://developer.android.com/guide/components/intents-common#ComposeEmail>
> <https://developer.android.com/guide/components/intents-common#SendMessage>
<https://developer.android.com/reference/android/telephony/SmsManager>
<https://developer.android.com/guide/topics/ui/shortcuts>
3.  AndroidManifest.xml
![](media/image1.png)
4.  Przygotuj activity_main.xml ( podanie numeru telefonu, treści
    wiadomości, przyciski do wysyłki smsa i maila pole dla emaila,
    miejsce do odbioru smsów )
5.  Przykładowa struktura:
> ![](media/image2.png)
6.  Dodaj potrzebne zmienne:
> ![](media/image3.png)
7.  Stwórz metodę wysyłającą sms poprzez SmsManagera, np.:
![](media/image4.png)
8.  Przetestuj aplikację, np.:
![](media/image5.png)
![](media/image6.png)
![](media/image7.png)
9.  Stwórz metodę wysyłającą sms poprzez Intent, np.:
![](media/image8.png)
10. Wyślij mail poprzez Intent, np.:
![](media/image9.png)
11. Przetestuj wysyłanie maila.
![](media/image10.png)
12. Dodaj klasę MyReceiver.java rozszerz ją o BroadcastReceiver
![](media/image11.png)
13. Możesz zapisać w onReceive() przychodzące smsy do pliku
> ![](media/image12.png)
14. Dodaj w AndroidManifest.xml obsługę odbiornika
![](media/image13.png)
15. Przetestuj odbiór smsów.
16. Dodaj skróty w ikonie aplikacji dla funkcjonalności:
    a.  ![](media/image14.png)
        wyślij sms ( skrót statyczny)
    b.  wyślij email ( skrót statyczny)
    c.  wyślij mms ( skrót dynamiczny)
    d.  zadźwoń dla chętnych , lub otwarcie przeglądarki
<https://developer.android.com/guide/topics/ui/shortcuts/creating-shortcuts>
Realizacja dla skrótów statycznych:
Zawartość z AndroidManifest.xml:
![](media/image15.png)
![](media/image16.png)
Realizacja skrótów dynamicznych:
![](media/image17.png)
![](media/image18.png)
17. Zrealizuj dodatkowo zadania
    a)  zaimplementuj wysyłanie wieloczęściowego smsa
<https://developer.android.com/reference/android/content/Intent#ACTION_SEND_MULTIPLE>
![](media/image19.png)
b)  zaimplementuj wysyłanie mmsa
c)  zapisanie przychodzących smsów i wyświetlenie w menu na RecycledView
<https://developer.android.com/guide/topics/ui/layout/recyclerview>
d)  dodaj ikonę dla aplikacji New - \> Image Asset
![](media/image20.png)
![](media/image21.png)
e)  napisz klasę, w której zrealizujesz wykonanie rozmowy telefonicznej
    (osobne ćwiczenia)
<!-- -->
18. ![](media/image22.png)
    Napisz test wysłania maila i go
    wykonaj:
19. Lub z Espresso:
> ![](media/image23.png)
![](media/image24.png)
20. KONIEC.
