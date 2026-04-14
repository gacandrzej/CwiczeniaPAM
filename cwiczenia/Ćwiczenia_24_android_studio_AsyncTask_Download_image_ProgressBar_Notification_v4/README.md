# Ćwiczenia 24 -- Android studio -- AsyncTask, ExecutorService, DownloadManager

💡Na koniec zajęć prześlij pliki źródłowe (.xml, .java)+ obrazek do zasobu
w teams.

1. Utwórz projekt o nazwie MyAsyncTask na podstawie Empty Activity,
    dobierz odpowiednie API.

1. Otwórz dokumentację:

   <https://developer.android.com/reference/android/os/AsyncTask>

   <https://developer.android.com/reference/android/app/PendingIntent>

   <https://developer.android.com/training/notify-user/build-notification#progressbar>

   <https://developer.android.com/reference/java/util/concurrent/package-summary>

   <https://developer.android.com/reference/java/util/concurrent/Executor>

1. activity_main.xml:

      ```xml
            <?xml version="1.0" encoding="utf-8"?>

    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity"
        android:gravity="center_horizontal"
        android:orientation="vertical">

        <ImageView
            android:id="@+id/image_view"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:background="@drawable/ic_launcher_foreground"
            android:scaleType="fitCenter"
            android:contentDescription="@string/loaded_image" />

        <ProgressBar
            android:id="@+id/progress_bar"
            android:visibility="gone"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:indeterminateTint="@color/blue" />

    </LinearLayout>
   ```

1. Zadeklaruj potrzebne zmienne i stałe w MainActivity, np.: ( adres wybierz dowolny)

   ```java
   static final String TAG = "MainActivity";
    private static final String CHANNEL_ID = "Andrzej";
    private static final int NOTIFICATION_ID_PROGRESSBAR = 4;
    private NotificationManager notificationManager;
    private String imageSrc;
    private ProgressBar progressBar;
    private ImageView imageView;
   imageSrc = "https://img.freepik.com/free-photo/painting-mountain-lake-with-mountain-background_188544-9126.jpg";
   ```

1. Utwórz klasę MyAsyncTask

   ```java
   public class MyAsyncTask extends AsyncTask<String, String, Bitmap> {
    private ProgressDialog dialog;
    private Context context;
    private ImageView imageView;
    public MyAsyncTask(Context context, ImageView imageView) {
        this.context = context;
        this.imageView = imageView;
    }

    @Override
    protected void onPreExecute() {
            dialog = new ProgressDialog(context);
            dialog.setMessage("###################");
            dialog.setProgressStyle(ProgressDialog.STYLE_SPINNER);
            dialog.setIndeterminate(true);
            dialog.setProgress(0);
            dialog.show();
            Log.d(MainActivity.TAG, "onPreExecute() called");
    }
   ```

1. Dodaj metodę doInBackground:

   ```java
   @Override
    protected Bitmap doInBackground(String... strings) {
        Bitmap image;
        try {
            URL url = new URL(strings[0]);
            HttpURLConnection httpURLConnection = (HttpURLConnection) url.openConnection();
            httpURLConnection.connect();
            image = BitmapFactory.decodeStream(httpURLConnection.getInputStream());
            Log.d(MainActivity.TAG, "doInBackground() called with: strings = [" + strings + "]");
            dialog.setProgress(50);
            try {
                Thread.sleep(5000);
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        return image;
    }
   ```

1. Ustaw pobrane zdjęcie:

   ```java
    @Override
    protected void onPostExecute(Bitmap bitmap) {
        if (dialog != null) {
            dialog.cancel();
            dialog.dismiss();
        }

        if (imageView != null && bitmap != null) {
            Log.d(MainActivity.TAG, "onPostExecute() called with: bitmap = [" + bitmap + "]");
            imageView.setImageBitmap(bitmap);
        }
    }
   ```

1. Dla dostępnych urządzeń:

   ![image6](media/image6.png)

1. Uruchom Pixel i wywołaj instancję klasy:

   ![image7](media/image7.png)

1. Zezwól na powiadomnienia:

   ![allow_notification](../../media/2026-04-14-09-47-42.png)

1. Sprawdzenie logCata:

   ![image8](media/image8.png)

1. Uzyskany efekt ( tylko zdjęcie u dołu):

   ![image9](media/image9.png)

   Widok z ProgressDialog:

   ![image10](media/image10.png)

1. Klasa ExecutorService:

   - zrealizuj powyższe ćwiczenie z wykorzystaniem Klasy
     ExecutorService:

   ![image11](media/image11.png)

   ![image12](media/image12.png)

1. Sprawdź pobranie zdjęcia:

   ![image13](media/image13.png)

1. Zastąp przestarzały DialogProgress na rzecz ProgressBar:

   ![image14](media/image14.png)

1. Utwórz klasę :

   ![image15](media/image15.png)

1. Sprawdź uprawnienia od wersji 33+ tiramisu

   ![image16](media/image16.png)

1. Przetestuj aplikację:

   ![image17](media/image17.png)

1. Sprawdź logcata:

   ![image18](media/image18.png)

1. Metoda executeMyService2():

   ![image19](media/image19.png)

1. Powiadomienie: dodaj powiadomienie z paskiem postępu, w stylu:

   ![image20](media/image20.png)

   ![image21](media/image21.png)

1. Fragment z realizacji:

   ![image22](media/image22.png)

1. Wywołanie na Pixel 4a:

   ![image23](media/image23.png)

1. Sprawdzenie:

   ![image24](media/image24.png)

1. LogCat:

   ![image26](media/image26.png)

1. Użyj:

   <https://developer.android.com/reference/android/app/DownloadManager>

1. Efekt: ( środkowe po kliknięciu w powiadomienie DownloadManagera )

   ![image27](media/image27.png)

   ![image28](media/image13.png)

1. KONIEC.🔚
