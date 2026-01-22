# Ćwiczenia 10 -- Android studio -- Navigation Drawer

💡 _*Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.*_
1.  Utwórz nowy projekt o nazwie MyNavigationDrawer na podstawie Empty
    Activity (dobrać odpowiednie API ).
2.  Otworzyć dokumentację:
> <https://developer.android.com/guide/navigation/navigation-ui>
>
> <https://developer.android.com/reference/androidx/drawerlayout/widget/DrawerLayout>
3.  Przejdź do właściwości projektu: <kbd>Shift</kbd>+<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>S</kbd>. 
    Przejżyj zależności. Zamknij okno.
4.  Dodać 8 ikon dla pozycji menu  
 ```text
 drawable -> New -> Vector assets
```   

![](media/image1.png)

5.  Utwórz plik menu:   
```text
    res-> Android Resource File (file name:  drawer_menu, resource type: menu)
```

6.  Dodaj 
```xml
<group android:checkableBehavior="single">
```
7.  Dodaj cztery itemy
8.  Dodaj po group nowy item
```xml
<item android:title="Wykresy funkcji">
with    
<menu>
<item></item>   
<item></item>   
<item></item>   
<item></item>   
</menu>
```
9.  Powinieneś uzyskać:
![](media/image2.png)
![](media/image3.png)

10. Dodaj layout 
```text
New-> Layout Resource File (file name: **drawer_header**
```

11. Powinieneś uzyskać:  
![](media/image4.png)  
12. W activity_main.xml zmień layout na DrawerLayout  
![](media/image5.png)
![](media/image6.png)
13. Dodaj w strings.xml:
> ![](media/image7.png)
14. W MainActivity.java w metodzie onCreate dodaj:
![](media/image8.png)
15. Uruchom aplikację i przetestuj:
    ![](media/image9.png)
16. KONIEC, część 2 w ćwiczeniach 11.
