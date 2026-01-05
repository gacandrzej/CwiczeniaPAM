Ćwiczenia 15 -- Android studio -- BaseAdapter, Spinner
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie ArrayAdapter na podstawie Empty Activity,
    dobierz odpowiednie API ( min. 26).
2.  Otworzyć dokumentację:
<https://developer.android.com/guide/topics/ui/controls/spinner>
<https://developer.android.com/guide/topics/resources/string-resource#java>
3.  Docelowo chcemy uzyskać :
![](media/image1.png)
![](media/image2.png)
4.  Dodaj w activity_main.xml
![](media/image3.png)
5.  W raw umieść plik z danymi:
> ![](media/image4.png)
6.  Uzupełnij MainActivity.java:
![](media/image5.png)
7.  ![](media/image6.png)
    Sprawdź czy poprawnie wczytujesz dane, np.:
8.  Przetestuj aplikację, uruchom na urządzeniu.
![](media/image7.png)
9.  Dodaj pliki png do drawable
![](media/image8.png)
10. Utwórz tablicę dla plików:
> ![](media/image9.png)
11. Dalej, szkielet dla onCreate():
![](media/image10.png)
12. Utwórz plik spinner_item.xml:
![](media/image11.png)
13. Utwórz klasę MyAdapter.java, rozrzesz ją o BaseAdapter:
![](media/image12.png)
14. Sprawdź wbudowane metody:
![](media/image13.png)
15. Ostatnia metoda:
![](media/image14.png)
16. Wykonaj zadania:
    a)  dodaj obsługę kliknięcia w item, wyświetl toast
> ![](media/image15.png)
> ![](media/image16.png)
>
> ![](media/image17.png)
b)  utwórz przycisk dodający nowy element do listy
c)  zachowaj całą listę w ShredPreferences, sprawdź stan linty po
    rotacji urządzenia
d)  przebuduj projekt tworząc klasę i listę, utwórz stosowny adapter
    ![](media/image18.png)
![](media/image19.png)
> ![](media/image20.png)
>
> Obsługa dla listenera:
>
> ![](media/image21.png)
>
> Metoda czytająca dane:
>
> ![](media/image22.png)
17. KONIEC.
