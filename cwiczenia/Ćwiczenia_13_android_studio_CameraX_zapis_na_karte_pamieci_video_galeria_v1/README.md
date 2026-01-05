Ćwiczenia 13 -- Android studio -- CameraX + zapis na sd + zapis do
galerii + video
Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.
1.  Wzorujemy się na labie:
    <https://developer.android.com/codelabs/camerax-getting-started#0>
2.  Utwórz projekt o nazwie CameraX na podstawie Empty Activity, dobierz
    odpowiednie API ( ).
3.  Otworzyć dokumentację:
    <https://developer.android.com/training/camerax>
    <https://developer.android.com/training/data-storage>
    <https://developer.android.com/reference/android/provider/MediaStore#summary>
    <https://developer.android.com/reference/android/os/Environment>
4.  Dodaj zależności w build.gradle(Module: CameraX.app)
![](media/image1.png)
5.  Dodaj w xml Button, PreviewView w dowolnym layout, np.
    ![](media/image2.png)
6.  Uzupełnij MainActivity.java:
    ![](media/image3.png)
7.  Dalej, szkielet dla onCreate():
![](media/image4.png)
![](media/image5.png)
8.  Dodaj i uzupełnij metodę getOutputDirectory() - rozbuduj ją :
![](media/image6.jpeg)
9.  Dodaj do AndroidManifest.xml
    ![](media/image7.png)
10. Dodaj kolejną metodę po Ctrl+o:
    ![](media/image8.png)
11. Dodaj metodę startCamera:
![](media/image9.png)
12. Dodaj zawartość takePhoto():
![](media/image10.png)
13. Reszta z dokumentacji dla klasy CameraX i:
    <https://developer.android.com/codelabs/camerax-getting-started#4>
14. Sprawdź, czy zdjęcie zapisuje się w pamięci wew.→Android→data→
    com.example.CameraX-\>files-\>Pictures
15. Dodaj zdjęcie do galerii.
16. Dodatkowe zadania
    a)  dodaj obsługę zapisu na kartę SD
    b)  przeprowadź zapis video do pliku mp4
    c)  dodaj obsługę bokeh, night,:
        <https://developer.android.com/training/camerax/vendor-extensions>
17. KONIEC.
