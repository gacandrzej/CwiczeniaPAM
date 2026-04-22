# Ćwiczenia 15 -- Android studio -- BaseAdapter, Spinner

💡Na koniec zajęć prześlij pliki źródłowe (.xml, .java) + screeny do zasobu
w teams.

1. Utwórz projekt o nazwie ArrayAdapter na podstawie Empty Activity,
    dobierz odpowiednie API.

1. Otworzyć dokumentację:

   <https://developer.android.com/guide/topics/ui/controls/spinner>

   <https://developer.android.com/guide/topics/resources/string-resource#java>

   <https://developer.android.com/reference/android/widget/BaseAdapter>

1. Docelowo chcemy uzyskać :

   ![image1](media/image1.png)

   ![image2](media/image2.png)

1. Dodaj w activity_main.xml

   ![image3](media/image3.png)

1. W raw umieść plik z danymi:

   ![image4](media/image4.png)

1. Uzupełnij MainActivity.java:

   ![image5](media/image5.png)

1. Sprawdź czy poprawnie wczytujesz dane, np.:

   ![image6](media/image6.png)

1. Przetestuj aplikację, uruchom na urządzeniu.

   ![image7](media/image7.png)

1. Dodaj pliki png do drawable

   ![image8](media/image8.png)

1. Utwórz tablicę dla plików:

   ![image9](media/image9.png)

1. Dalej, szkielet dla onCreate():

   ![image10](media/image10.png)

1. Utwórz plik spinner_item.xml:

   ![image11](media/image11.png)

1. Utwórz klasę MyAdapter.java, rozrzesz ją o BaseAdapter:

   ![image12](media/image12.png)

1. Sprawdź czy posiadasz wbudowane metody:

   ![image13](media/image13.png)

1. Ostatnia metoda:

   ![image14](media/image14.png)

1. Wykonaj zadania:

   - dodaj obsługę kliknięcia w item, wyświetl toast

   ![image15](media/image15.png)

   ![image16](media/image16.png)

   ![image17](media/image17.png)

   - utwórz przycisk dodający nowy element do listy

   - zachowaj całą listę w ShredPreferences, sprawdź stan listy po
     rotacji urządzenia

   - przebuduj projekt tworząc klasę i listę, utwórz stosowny adapter

     ![image18](media/image18.png)

     ![image19](media/image19.png)

     ![image20](media/image20.png)

     Obsługa dla listenera:

     ![image21](media/image21.png)

     Metoda czytająca dane:

     ![image22](media/image22.png)

1. KONIEC.🔚
