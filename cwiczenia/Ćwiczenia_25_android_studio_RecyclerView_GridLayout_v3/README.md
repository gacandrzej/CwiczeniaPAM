# Ćwiczenia 25 -- Android studio -- RecyclerView, GridLayout

Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie MyAsyncTask na podstawie Empty Activity,
    dobierz odpowiednie API ( 28 -- Android 9).

1. Otwórz dokumentację:

    <https://developer.android.com/reference/androidx/recyclerview/widget/RecyclerView>

    <https://developer.android.com/jetpack/androidx/releases/recyclerview>

    <https://developer.android.com/guide/topics/ui/layout/recyclerview>

    <https://developer.android.com/reference/androidx/recyclerview/widget/DividerItemDecoration>

1. Zależności ( brak dodatkowych)

   ![image1](media/image1.png)

1. Chcemy uzyskać w pierwszej części listę dla tekstów (po prawej
    GridLayout):

   ![image2](media/image2.png)

   ![image3](media/image3.png)

1. activity_main.xml:

   ![image4](media/image4.png)

1. Dodaj w strings.xml:

   ![image5](media/image5.png)

   ```text
    I am strong.
    I believe in myself.
    Each day is a new opportunity to grow and be a better version of myself.
    Every challenge in my life is an opportunity to learn from.
    I have so much to be grateful for.
    Good things are always coming into my life.
    New opportunities await me at every turn.
    I have the courage to follow my heart.
    Things will unfold at precisely the right time.
    I will be present in all the moments that this day brings.
    ```

    ![image6](media/image6.png)

1. Dodaj nowe pakiety: adapter, config i data ( New → Package )

   ![image7](media/image7.png)

1. Utwórz klasę, która będzie źródłem danych o nazwie Datasource:

   ![image8](media/image8.png)

1. Klasa Description:

   ![image9](media/image9.png)

1. Jeżeli stworzysz klasę Description to wówczas dodaj do klasy
    Datasource:

   ![image10](media/image10.png)

1. Dodaj kod i przetestuj aplikację, wyświetl długość listy:

   ![image11](media/image11.png)

1. Dodajemy RecyclerView:

   ![image12](media/image12.png)

1. Dodaj w main_activity.xml:

   ![image13](media/image13.png)

1. W res - \> layout utwórz list_item,.xml:

   ![image14](media/image14.png)

1. Utwórz klasę ItemAdapter:

   ![image15](media/image15.png)

1. Dodaj construktor:

   ![image16](media/image16.png)

1. Wewnątrz klasy ItemAdapter utwórz klasę zagnieżdżoną o nazwie
    ItemViewHolder:

   ![image17](media/image17.png)

1. Rozszerz klasę ItemViewHolder o RecyclerView.ViewHolder oraz dodaj
    constuktor z view:

   ![image18](media/image18.png)

   ![image19](media/image19.png)

1. Dodaj TextView, cała klasa ItemViewHolder:

   ![image20](media/image20.png)

1. Rozszerz klasę adaptera ItemAdapter :

   ![image21](media/image21.png)

1. Napraw błędy:

   ![image22](media/image22.png)

1. Zaimplementuj trzy metody, napierw getItemCount():

   ![image23](media/image23.png)

1. Implementuj metodę onCreateViewHolder( ):

   ![image24](media/image24.png)

1. Zaimplementuj metodę onBindViewHolder():

   ![image25](media/image25.png)

1. W onCreate() dodaj kod ustawiający adapter dla RecyclerView:

   ![image26](media/image26.png)

1. Dodaj separator:

   ![image27](media/image27.png)

   ![image28](media/image28.png)

1. Przetestuj aplikację.

   ![image2](media/image2.png)

1. Dodaj menu dla zmiany układów:

   ![image29](media/image29.png)

1. W MainActivity dodaj potrzebne metody i zadeklaruj użycie layoutów:

   ![image30](media/image30.png)

1. Obsługa menu:

   ![image31](media/image31.png)

   ![image32](media/image32.png)

1. Przetestuj przełączenie układów:

   ![image3](media/image3.png)

1. Dodatkowe zadania
    - dodaj do projektu 12 zdjęć i utwórz do ich obsługi adapter i
        potrzebne klasy ItemAdapterImage i DataSourceImage
    - dodaj nową aktywność po tapnięciu w zdjęcie:

        ![image33](media/image33.png)

    - dodaj metodę odświeżającą elementy RecyclerView
    - zrealizuj powyższe ćwiczenie z wykorzystaniem \...

        <https://developer.android.com/guide/topics/ui/layout/recyclerview-custom>

    - inne zadanie ...

1. Efekt:

   ![image34](media/image34.png)

1. KONIEC.🔚
