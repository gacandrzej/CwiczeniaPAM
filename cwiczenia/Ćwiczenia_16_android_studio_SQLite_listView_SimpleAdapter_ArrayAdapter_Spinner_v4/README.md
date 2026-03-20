Ćwiczenia 16 -- Android studio -- SQLite, ArrayAdapter, SimpleAdapter,
ListView, Spinner
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Utwórz projekt o nazwie SQLite na podstawie Empty Activity, dobierz
    odpowiednie API ( min. 28).
2.  Otworzyć dokumentację:
<https://developer.android.com/reference/android/database/sqlite/SQLiteDatabase>
<https://developer.android.com/reference/android/database/sqlite/SQLiteOpenHelper>
<https://developer.android.com/reference/android/database/Cursor>
<https://developer.android.com/reference/android/content/ContentValues>
a.  metody:
<https://developer.android.com/reference/android/database/sqlite/SQLiteOpenHelper#getWritableDatabase>()
<https://developer.android.com/reference/android/database/sqlite/SQLiteOpenHelper#getReadableDatabase>()
<https://developer.android.com/reference/android/database/sqlite/SQLiteDatabase#execSQL(java.lang.String>)
<https://developer.android.com/reference/android/database/sqlite/SQLiteDatabase#rawQuery(java.lang.String,%20java.lang.String>\[\])
<https://developer.android.com/reference/android/database/sqlite/SQLiteDatabase#insert(java.lang.String,%20java.lang.String,%20android.content.ContentValues>)
3.  Dodaj zależności ( jeśli są potrzebne)
4.  Docelowo chcemy uzyskać coś na kształt**, tematykę możesz dobrać pod
    swój projek**t:
![](media/image1.png)
![](media/image2.png)
5.  Wykorzystaj do zbudowania interfejsu użytkownika ćwiczenia 15.
<https://developer.android.com/guide/topics/ui/controls/spinner>
<https://developer.android.com/guide/topics/resources/string-resource#java>
<https://developer.android.com/reference/android/widget/ListView#setAdapter(android.widget.ListAdapter>)
6.  Stwórz podstawowe struktury dla bazy oraz ją utwórz:
<https://developer.android.com/training/data-storage/sqlite>
7.  Sprawdź, czy baza powstała View → Tool Windows → Device File
    Explorer
/data/data/com.example.twoja_nazwa/databases/shop.db
![](media/image3.png)
8.  Dodaj plugin :
![](media/image4.png)
9.  Visual Code:
Uwaga: bazę można podejrzeć w visual code po dodaniu rozszerzenia
vscode-sqlite lub w programie DB browser SQLite
10. Utwórz menu, ćwiczenia 4, zamiast switch użyj if -else:
![](media/image6.png)
![](media/image7.png)
11. Przetestuj aplikację, uruchom na urządzeniu.
12. Dodaj metody onPause() i onSaveInstanceState(Bundle bundle)
13. Obsługa dwóch języków i nie tylko:
> <https://developer.android.com/guide/topics/resources/localization>
14. Dodaj niezbędne klasy, adaptery i dane.
![](media/image8.png)
15. Dodatkowe zadania
    a)  logowanie do aplikacji z rejestracją
    b)  zapisanie zdjęć w bazie w postaci Stringów i ich poprawny odczyt
    c)  udostępnienie zamówienia z menu, aplikacja do wyboru
<https://developer.android.com/training/sharing/send>
16. Dla chętnych, przepisz aplikację z użyciem room.
> ![](media/image9.png)
>
> ![](media/image10.png)
17. App Inspection:
> ![](media/image11.png)
18. KONIEC.
