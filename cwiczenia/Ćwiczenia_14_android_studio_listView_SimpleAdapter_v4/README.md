Ćwiczenia 14 -- Android studio -- SimpleAdapter, ListView
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie SimpleAdapter na podstawie Empty Activity,
    dobierz odpowiednie API.
2.  Otworzyć dokumentację:
> [https://developer.android.com/reference/android/widget/SimpleAdapter](https://developer.android.com/reference/android/widget/SimpleAdapter)
<https://developer.android.com/reference/android/widget/ListView#summary>
> <https://developer.android.com/reference/android/widget/AdapterView.OnItemClickListener>
<https://developer.android.com/guide/topics/resources/string-resource>
> <https://developer.android.com/guide/topics/ui/dialogs>
![](media/image1.png)
3.  Dodaj zależności.
4.  Docelowo chcemy uzyskać coś na kształt, wybierz tematykę:
5.  Dodaj w activity_main.xml listę
> ![](media/image2.png)
6.  Dodaj pliki zdjęć do res ... .
![](media/image3.png)
![](media/image4.png)
7.  Nazwy umieść w string-array:
8.  Uzupełnij MainActivity.java:
![](media/image5.png)
9.  Uzupełnij :
> ![](media/image6.png)
10. Dodaj elementy do hashMap (metoda put), następnie do listy (metoda
    add), kod w pętli for możesz zamknąć w metodę, która przyda się przy
    dodawaniu nowych produktów
![](media/image7.png)
11. Utwórz plik list_view_items.xml:
![](media/image8.png)
12. Dodaj do onCreate() elementy \[ from \] i \[ to \]
13. Na przykład:
![](media/image9.png)
14. Stwórz obiekt SimpleAdapter:
![](media/image10.png)
15. Ustaw adapter zgodnie z dokumentacją:
![](media/image11.png)
16. Na przykład:
![](media/image12.png)
17. Wykonaj zadania
    a)  dodaj obsługę kliknięcia w item listView, wyświetl toast
![](media/image13.png)
b)  dodaj obsługę kliknięcia w item ListView, nowa aktywność z opisem
    pozycji i obrazkiem, zapewnić powrót
> Zmień deklarację na
> ![](media/image14.png)
![](media/image15.png)
> ![](media/image16.png)
>
> ![](media/image17.png)
c)  dodaj opcję dodania nowej pozycji listy poprzez przycisk w kształcie
    (+)
![](media/image18.png)
[https://developer.android.com/guide/topics/ui/dialogs](https://developer.android.com/guide/topics/ui/dialogs)
![](media/image19.png)
![](media/image20.png)
Kształt dla przycisku:
![](media/image21.png)
oraz
![](media/image22.png)
d)  dodaj spiner dla wyboru nazwy obrazka:
> ![](media/image23.png)
>
> ![](media/image24.png)
>
> ![](media/image25.png)
e)  dodaj przycisk usuwający zaznaczony element listy.
> ![](media/image26.png)
>
> Oraz dodaj metodę na kształt:
>
> ![](media/image27.png)
f)  zadbaj o to, aby nowo dodany element był na liście po obrocie
    urządzenia o 90 stopni (ShredPreferences)
> <https://developer.android.com/training/data-storage/shared-preferences>
>
> <https://developer.android.com/reference/android/content/SharedPreferences>
>
> <https://developer.android.com/develop/ui/views/components/settings/use-saved-values>
18. KONIEC.
