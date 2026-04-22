Ćwiczenia 21 -- Android studio -- sms, email send, shortcut
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie MySmsMailShortcut na podstawie Empty
    Activity, dobierz odpowiednie API ( 28 -- Android 9).
2. Otwórz dokumentację:
<https://developer.android.com/guide/components/intents-common#ComposeEmail>

> <https://developer.android.com/guide/components/intents-common#SendMessage>
<https://developer.android.com/reference/android/telephony/SmsManager>
<https://developer.android.com/guide/topics/ui/shortcuts>

1. AndroidManifest.xml
![image1](media/image1.png)
2. Przygotuj activity_main.xml ( podanie numeru telefonu, treści
    wiadomości, przyciski do wysyłki smsa i maila pole dla emaila,
    miejsce do odbioru smsów )
3. Przykładowa struktura:

> ![image2](media/image2.png)

1. Dodaj potrzebne zmienne:

> ![image3](media/image3.png)

1. Stwórz metodę wysyłającą sms poprzez SmsManagera, np.:
![image4](media/image4.png)
2. Przetestuj aplikację, np.:
![image5](media/image5.png)
![image6](media/image6.png)
![image7](media/image7.png)
3. Stwórz metodę wysyłającą sms poprzez Intent, np.:
![image8](media/image8.png)
4. Wyślij mail poprzez Intent, np.:
![image9](media/image9.png)
5. Przetestuj wysyłanie maila.
![image10](media/image10.png)
6. Dodaj klasę MyReceiver.java rozszerz ją o BroadcastReceiver
![image11](media/image11.png)
7. Możesz zapisać w onReceive() przychodzące smsy do pliku

> ![image12](media/image12.png)

1. Dodaj w AndroidManifest.xml obsługę odbiornika
![image13](media/image13.png)
2. Przetestuj odbiór smsów.
3. Dodaj skróty w ikonie aplikacji dla funkcjonalności:
    a.  ![image14](media/image14.png)
        wyślij sms ( skrót statyczny)
    b.  wyślij email ( skrót statyczny)
    c.  wyślij mms ( skrót dynamiczny)
    d.  zadźwoń dla chętnych , lub otwarcie przeglądarki
<https://developer.android.com/guide/topics/ui/shortcuts/creating-shortcuts>
Realizacja dla skrótów statycznych:
Zawartość z AndroidManifest.xml:
![image15](media/image15.png)
![image16](media/image16.png)
Realizacja skrótów dynamicznych:
![image17](media/image17.png)
![image18](media/image18.png)
4. Zrealizuj dodatkowo zadania
    a)  zaimplementuj wysyłanie wieloczęściowego smsa
<https://developer.android.com/reference/android/content/Intent#ACTION_SEND_MULTIPLE>
![image19](media/image19.png)
b)  zaimplementuj wysyłanie mmsa
c)  zapisanie przychodzących smsów i wyświetlenie w menu na RecycledView
<https://developer.android.com/guide/topics/ui/layout/recyclerview>
d)  dodaj ikonę dla aplikacji New - \> Image Asset
![image20](media/image20.png)
![image21](media/image21.png)
e)  napisz klasę, w której zrealizujesz wykonanie rozmowy telefonicznej
    (osobne ćwiczenia)
<!-- -->
1. ![image22](media/image22.png)
    Napisz test wysłania maila i go
    wykonaj:
2. Lub z Espresso:

> ![image23](media/image23.png)
![image24](media/image24.png)

1. KONIEC.
