# Ćwiczenia 17 -- Android studio -- GPS, Open Street Maps

Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie GpsMaps na podstawie Empty Views Activity, dobierz odpowiednie API ( min. 28 ).

1. Otworzyć dokumentację:

   <https://developer.android.com/training/location/permissions>

   <https://developer.android.com/reference/kotlin/android/location/LocationManager?hl=en>

   <https://developer.android.com/training/location/request-updates>

   <https://developer.android.com/reference/android/location/Location>

1. Dodaj zależności ( aktualna wersja na

   <https://github.com/osmdroid/osmdroid>):

   ![image1](media/image1.png)

1. Docelowo chcemy uzyskać coś na kształt( marker ustawić na
    czerwony!!!):

   ![image2](media/image2.png)

1. Stwórz podstawowe struktury np.:

   ![image3](media/image3.png)

1. Stwórz layout dla aplikacji jak poniżej lub podobny:

   ![image4](media/image4.png)

   ![image5](media/image5.png)

1. Dodaj listener dla layoutu SwipeRefreshLayout:

   ![image6](media/image6.png)

1. Zadeklaruj w MainActivity.java:

   ```java
   SwipeRefreshLayout swipeRefreshLayout;

    private final String[] permissions = {
            Manifest.permission.ACCESS_FINE_LOCATION,
            Manifest.permission.ACCESS_COARSE_LOCATION,
            Manifest.permission.INTERNET
    };
    private TextView longitude;
    private TextView latitude;
    private TextView archivaldata;
    private TextView text_network;
    private TextView text_gps;
    private MapView map;
    private MapController mapController;
   ```

1. W onCreate() dodaj:

   ![image8](media/image8.png)

1. Dodaj ( ważne: zwróć uwagę na kolejne dwa punkty!!! ):

   ![image9](media/image9.png)

1. W AndroidManifest.xml sprawdź czy masz uprawnienia:

   ```xml
   <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
   ```

1. Sprawdź czy zaimplementowałeś/aś metodę
    onRequestPermissionResult, albo lepiej dodaj launcher:

   ```java
   private final ActivityResultLauncher<String[]> requestMultiplePermissionsLauncher =
            registerForActivityResult(new ActivityResultContracts.RequestMultiplePermissions(),
   ```

1. Add permission check ( if z checkSelfPermission doda się
    automatycznie po wybraniu tej opcji)

   W trakcie realizacji ćwiczeń należy dodać stosowne inne, wymagane uprawnienia!!!

   ```java
   LocationManager locationManager = (LocationManager) getSystemService(LOCATION_SERVICE);
   if (ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED
                && ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_COARSE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
            requestMultiplePermissionsLauncher.launch(permissions);
            return;
        }
   String bp = locationManager.getBestProvider(criteria, true);
        Log.i("AN", "onCreate: " + bp);

        bestprovider.setText(String.format("Best provider: %s", bp));

        if (bp != null) {
            locationManager.requestLocationUpdates(
                    bp,
                    1000,
                    1,
                    this
            );
   ```

1. Sprawdź czy wypisujesz odczyty:

   ```java
   private void updateMap(Location location) {
        // Pobranie współrzędnych
        latitudeD = location.getLatitude();
        longitudeD = location.getLongitude();

        // Aktualizacja tekstów w interfejsie
        latitude.setText(String.format("Latitude: %s", latitudeD));
        longitude.setText(String.format("Longitude: %s", longitudeD));
        archivaldata.setText(String.format("%s %s   :   %s\n", archivaldata.getText(), latitudeD, longitudeD));
   ```

1. Zaimplementuj LocationListener z potrzebnymi metodami:

   ```java
   public class MainActivity extends AppCompatActivity implements LocationListener {
   @Override
    public void onLocationChanged(@NonNull Location location) {

        updateMap(location);

        Toast.makeText(this, "Location updated", Toast.LENGTH_SHORT).show();
    }
   }
   ```

1. Przetestuj aplikację, uruchom na urządzeniu. Przemieść się .

   ![image16](media/image16.png)

1. Część druga -- dodanie mapy

   ![image17](media/image17.png)

1. Parametry:

   ![image18](media/image18.png)

   Zmieniamy dostawcę kafelek od roku 2026:

   ```java
   XYTileSource cyclOSM = new XYTileSource(
                "CyclOSM",
                0, 20, 256, ".png",
                new String[]{
                        "https://a.tile-cyclosm.openstreetmap.fr/cyclosm/",
                        "https://b.tile-cyclosm.openstreetmap.fr/cyclosm/",
                        "https://c.tile-cyclosm.openstreetmap.fr/cyclosm/"
                },
                "© OpenStreetMap contributors, CyclOSM"
        );
        map.setTileSource(cyclOSM);
   ```

1. Dodanie punktu:

   ![image19](media/image19.png)

1. Dodanie markera i setMapListenera ( nie obligatoryjne ) :

   ![image20](media/image20.png)

1. Dodaj iconę markera, najlepiej plik.png itp:

   ![image21](media/image21.png)

1. Marker:

   ![image22](media/image22.png)

   lub po nowemu:

   ```java
    Drawable drawable = getResources().getDrawable(R.drawable.marker, null);
        Bitmap bitmap = Bitmap.createScaledBitmap(
                ((BitmapDrawable) drawable).getBitmap(),
                35,
                35,
                true
        );
        drawable = new BitmapDrawable(getResources(), bitmap);
        marker.setIcon(drawable);
   ```

1. Dodaj obligatoryjnie menu, zalecane railway navigation :( opis i objaśnienie w punkcie 25)

   <https://m3.material.io/components/navigation-rail/guidelines>

   ![railway](../../media/2026-11-26-13-54-39.png)
   ![image23](media/image23.png)

1. Dodaj metodę sprawdzającą dostęp do GPS i internetu (colory czerwony
    i zielony na TextView)

   ![nowy2](../../media/2026-11-26-14-00-31.png)

1. Wykonaj zadania
   - wysłanie sms-em koordynat

     ![image25](media/image25.png)

     ![image26](media/image26.png)

   - zapisanie zdjęć mapy na karcie

     ![image27](media/image27.png)

   - udostępnienie wyników

     ![image28](media/image28.png)

1. Dodatkowe zadanie: wczytaj dane
    pogodowe dla obecnej lokalizacji:

   ![image29](media/image29.png)

   ![image30](media/image30.png)

   ![image31](media/image31.png)

   ![pogoda1](../../media/2026-11-26-13-56-19.png)
1. Dla chętnych skorzystaj z retrofit2:

   ```xml
     dependencies {
       implementation("androidx.activity:activity-ktx:1.13.0")
       // Retrofit
       implementation("com.squareup.retrofit2:retrofit:3.0.0")
       // konwerter Gson do automatycznego zamieniania JSONa na obiekty Java
       implementation("com.squareup.retrofit2:converter-gson:3.0.0")
     }
   ```

1. KONIEC.🔚
