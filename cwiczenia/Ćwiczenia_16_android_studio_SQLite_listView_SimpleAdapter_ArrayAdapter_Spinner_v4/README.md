# Ćwiczenia 16 -- SQLite, ArrayAdapter, SimpleAdapter, ListView, Spinner

💡Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie SQLite na podstawie Empty Activity, dobierz
    odpowiednie API ( min. 28).
1. Otworzyć dokumentację:

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

1. Dodaj zależności ( jeśli są potrzebne)

1. Docelowo chcemy uzyskać coś na kształt**, tematykę możesz dobrać pod
    swój projek**t:

   ![image1](media/image1.png)

   ![image2](media/image2.png)

1. Wykorzystaj do zbudowania interfejsu użytkownika ćwiczenia 15.

    <https://developer.android.com/guide/topics/ui/controls/spinner>

    <https://developer.android.com/guide/topics/resources/string-resource#java>

    <https://developer.android.com/reference/android/widget/ListView#setAdapter(android.widget.ListAdapter>)

1. Stwórz podstawowe struktury dla bazy oraz ją utwórz:

   <https://developer.android.com/training/data-storage/sqlite>

1. Sprawdź, czy baza powstała View → Tool Windows → Device File Explorer

   /data/data/com.example.twoja_nazwa/databases/shop.db

   ![image3](media/image3.png)

1. Dodaj plugin :

   ![image4](media/image4.png)

1. Visual Code:
   Uwaga: bazę można podejrzeć w visual code po dodaniu rozszerzenia
   vscode-sqlite lub w programie DB browser SQLite

1. Utwórz menu, ćwiczenia 4, zamiast switch użyj if -else:

   ![image6](media/image6.png)

   ![image7](media/image7.png)

1. Przetestuj aplikację, uruchom na urządzeniu.

1. Dodaj metody onPause() i onSaveInstanceState(Bundle bundle)

1. Obsługa dwóch języków i nie tylko:

   <https://developer.android.com/guide/topics/resources/localization>

1. Dodaj niezbędne klasy, adaptery i dane.

   ![image8](media/image8.png)

1. Dodatkowo wykonaj:

    - logowanie do aplikacji z rejestracją
    - zapisanie zdjęć w bazie w postaci Stringów i ich poprawny odczyt
    - udostępnienie zamówienia z menu, aplikacja do wyboru

      <https://developer.android.com/training/sharing/send>

1. Dla chętnych, przepisz aplikację z użyciem room.

   ![image9](media/image9.png)

   ![image10](media/image10.png)

1. App Inspection:

   ![image11](media/image11.png)

1. KONIEC.🔚
