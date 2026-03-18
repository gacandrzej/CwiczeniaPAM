# Ćwiczenia 14 -- Android studio -- SimpleAdapter, ListView

💡 Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie SimpleAdapter na podstawie Empty Activity,
    dobierz odpowiednie API.
1. Otworzyć dokumentację:

   <[https://developer.android.com/reference/android/widget/SimpleAdapter](https://developer.android.com/reference/android/widget/SimpleAdapter)
   <https://developer.android.com/reference/android/widget/ListView#summary>
   <https://developer.android.com/reference/android/widget/AdapterView.OnItemClickListener>
   <https://developer.android.com/guide/topics/resources/string-resource>
   <https://developer.android.com/guide/topics/ui/dialogs>

1. Efekt końcowy:

   ![image1.png](media/image1.png)

1. Dodaj zależności.

   ![dependecies](../../media/2026-03-18-10-06-01.png)

1. Docelowo chcemy uzyskać coś na kształt, wybierz tematykę:
1. Dodaj w activity_main.xml listę

   ![image2](media/image2.png)

1. Dodaj pliki zdjęć do res ... .

  ![image3](media/image3.png)

1. Nazwy umieść w string-array:

   ![image4](media/image4.png)

   ```xml
   <string-array name="dogsDescription">
        <item>Mały, energiczny pies o jedwabistej sierści. Choć wyglądem przypomina psa kanapowego, zachowuje instynkt i odwagę prawdziwego teriera.</item>
        <item>Wytrzymały i pojętny pies o szorstkiej sierści. Znany z radosnego usposobienia, dużej pewności siebie oraz zamiłowania do kopania i zabaw.</item>
        <item>Spokojniejszy od innych terierów, o charakterystycznej sylwetce i jedwabistej szacie. Jest lojalny, łagodny wobec dzieci i łatwy w prowadzeniu.</item>
        <item>Długowłosa odmiana najmniejszego psa świata. Bardzo przywiązany do właściciela, odważny i czujny, o wielkiej osobowości w małym ciele.</item>
        <item>Jeden z najpopularniejszych psów rodzinnych. Wyjątkowo łagodny, inteligentny i cierpliwy. Uwielbia aportowanie, wodę i kontakt z ludźmi.</item>
        <item>Potężny pies zaprzęgowy o gęstej sierści. Niezależny, bardzo wytrzymały i przyjacielski, ale wymagający dużo ruchu i konsekwentnego wychowania.</item>
        <item>Wysoce inteligentny i elegancki pies o kędzierzawej sierści. Szybko się uczy, jest aktywny i świetnie sprawdza się w psich sportach oraz jako pies towarzyszący.</item>
        <item>Cavalier King Charles Spaniel to pies o wyjątkowo łagodnym i radosnym usposobieniu. Uwielbia towarzystwo ludzi, jest cierpliwy i bardzo wrażliwy.</item>
        <item>Wszechstronny pies o przyjaznej naturze. Znany z doskonałego węchu, inteligencji i chęci do pracy. Idealny towarzysz rodziny i oddany pomocnik.</item>
    </string-array>
   ```

1. Uzupełnij MainActivity.java:

   ![image5](media/image5.png)

1. Uzupełnij :

   ![image6](media/image6.png)

1. Dodaj elementy do hashMap (metoda put), następnie do listy (metoda
    add), kod w pętli for możesz zamknąć w metodę, która przyda się przy
    dodawaniu nowych produktów

   ![image7](media/image7.png)

1. Utwórz plik list_view_items.xml:

   ![image8](media/image8.png)

1. Dodaj do onCreate() elementy from i to

1. Na przykład:

   ![image9](media/image9.png)

1. Stwórz obiekt SimpleAdapter:

   ![image10](media/image10.png)

1. Ustaw adapter zgodnie z dokumentacją:

   ![image11](media/image11.png)

1. Na przykład:

   ![image12](media/image12.png)

1. Wykonaj zadania:

   a)  dodaj obsługę kliknięcia w item listView, wyświetl toast

   ![image13](media/image13.png)

   b)  dodaj obsługę kliknięcia w item ListView, nowa aktywność z opisem
        pozycji i obrazkiem, zapewnić powrót

   Zmień deklarację na

   ![image14](media/image14.png)

   ![image15](media/image15.png)

   ![image16](media/image16.png)

   ![image17](media/image17.png)

c)  dodaj opcję dodania nowej pozycji listy poprzez przycisk w kształcie
    (+)

   ![image18](media/image18.png)

   [https://developer.android.com/guide/topics/ui/dialogs](https://developer.android.com/guide/topics/ui/dialogs)

   ![image19](media/image19.png)

   ![image20](media/image20.png)

   Kształt dla przycisku:

   ![image21](media/image21.png)

   oraz

   ![image22](media/image22.png)

   d)  dodaj spiner dla wyboru nazwy obrazka:

   ![image23](media/image23.png)

   ![image24](media/image24.png)

   ![image25](media/image25.png)

   e)  dodaj przycisk usuwający zaznaczony element listy.

   ![image26](media/image26.png)

   Oraz dodaj metodę na kształt:

   ![image27](media/image27.png)

   f)  zadbaj o to, aby nowo dodany element był na liście po obrocie
       urządzenia o 90 stopni (ShredPreferences)

    <https://developer.android.com/training/data-storage/shared-preferences>
   
    <https://developer.android.com/reference/android/content/SharedPreferences>

    <https://developer.android.com/develop/ui/views/components/settings/use-saved-values>

1. KONIEC.🔚
