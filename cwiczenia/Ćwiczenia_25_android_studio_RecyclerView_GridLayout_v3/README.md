Ćwiczenia 25 -- Android studio -- RecyclerView, GridLayout
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie MyAsyncTask na podstawie Empty Activity,
    dobierz odpowiednie API ( 28 -- Android 9).
2.  Otwórz dokumentację:
    <https://developer.android.com/reference/androidx/recyclerview/widget/RecyclerView>
    <https://developer.android.com/jetpack/androidx/releases/recyclerview>
    <https://developer.android.com/guide/topics/ui/layout/recyclerview>
    <https://developer.android.com/reference/androidx/recyclerview/widget/DividerItemDecoration>
3.  Zależności ( brak dodatkowych)
![](media/image1.png)
4.  Chcemy uzyskać w pierwszej części listę dla tekstów (po prawej
    GridLayout):
![](media/image2.png)
![](media/image3.png)
5.  activity_main.xml:
![](media/image4.png)
6.  Dodaj w strings.xml:
![](media/image5.png)
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
![](media/image6.png)
7.  Dodaj nowe pakiety: adapter, config i data ( New → Package )
![](media/image7.png)
8.  Utwórz klasę, która będzie źródłem danych o nazwie Datasource:
![](media/image8.png)
9.  Klasa Description:
![](media/image9.png)
10. Jeżeli stworzysz klasę Description to wówczas dodaj do klasy
    Datasource:
![](media/image10.png)
11. Dodaj kod i przetestuj aplikację, wyświetl długość listy:
![](media/image11.png)
12. Dodajemy RecyclerView:
![](media/image12.png)
13. Dodaj w main_activity.xml:
![](media/image13.png)
14. W res - \> layout utwórz list_item,.xml:
![](media/image14.png)
15. Utwórz klasę ItemAdapter:
![](media/image15.png)
16. Dodaj construktor:
![](media/image16.png)
17. Wewnątrz klasy ItemAdapter utwórz klasę zagnieżdżoną o nazwie
    ItemViewHolder:
![](media/image17.png)
18. Rozszerz klasę ItemViewHolder o RecyclerView.ViewHolder oraz dodaj
    constuktor z view:
![](media/image18.png)
![](media/image19.png)
19. Dodaj TextView, cała klasa ItemViewHolder:
![](media/image20.png)
20. Rozszerz klasę adaptera ItemAdapter :
![](media/image21.png)
21. Napraw błędy:
![](media/image22.png)
22. Zaimplementuj trzy metody, napierw getItemCount():
![](media/image23.png)
23. Implementuj metodę onCreateViewHolder( ):
![](media/image24.png)
24. Zaimplementuj metodę onBindViewHolder():
![](media/image25.png)
25. W onCreate() dodaj kod ustawiający adapter dla RecyclerView:
![](media/image26.png)
26. Dodaj separator:
![](media/image27.png)
![](media/image28.png)
27. Przetestuj aplikację.
    ![](media/image2.png)
28. Dodaj menu dla zmiany układów:
![](media/image29.png)
29. W MainActivity dodaj potrzebne metody i zadeklaruj użycie layoutów:
![](media/image30.png)
30. Obsługa menu:
![](media/image31.png)
![](media/image32.png)
31. Przetestuj przełączenie układów:
![](media/image3.png)
32. Dodatkowe zadania
    a)  dodaj do projektu 12 zdjęć i utwórz do ich obsługi adapter i
        potrzebne klasy ItemAdapterImage i DataSourceImage
    b)  dodaj nową aktywność po tapnięciu w zdjęcie:
        ![](media/image33.png)
    c)  dodaj metodę odświeżającą elementy RecyclerView
    d)  zrealizuj powyższe ćwiczenie z wykorzystaniem \...
        <https://developer.android.com/guide/topics/ui/layout/recyclerview-custom>
    e)  inne zadanie ...
33. Efekt:
![](media/image34.png)
34. KONIEC.
