# Ćwiczenia - bluetooth - parowanie urządzeń

💡Do realizacji ćwiczeń wymagany jest tablet lub smartfon oraz głośnik bluetooth

1. Otwórz dokumentację:

    <https://developer.android.com/guide/topics/permissions/overview>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/permissions>
    <https://developer.android.com/guide/topics/connectivity/bluetooth>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/setup>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/find-bluetooth-devices>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/transfer-data>

1. Pobierz i rozpakuj ![android_icons](android_icons.zip)

1. AndroidManifest.xml:

   ```xml
   <uses-permission
        android:name="android.permission.BLUETOOTH"
        android:maxSdkVersion="30" />

    <!-- Uprawnienia dla Androida 12+ (API 31+) -->
    <uses-permission android:name="android.permission.BLUETOOTH_CONNECT" />
    <uses-permission
        android:name="android.permission.BLUETOOTH_SCAN"
        android:usesPermissionFlags="neverForLocation" />

    <!-- Lokalizacja wymagana TYLKO dla Androida 11 i starszych -->
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

    <uses-permission android:name="android.permission.BLUETOOTH_ADMIN"
        android:maxSdkVersion="30"/>

    <!-- Deklaracja, że Bluetooth jest wymagany do działania aplikacji -->
    <uses-feature android:name="android.hardware.bluetooth" />
   ```

1. Dodaj zmienne do ActivityMain:

   ```java
   private BluetoothDeviceViewModel viewModel;
    private BluetoothDeviceAdapter adapter;
    private BluetoothAdapter bluetoothAdapter;
    private BluetoothConnectionManager bluetoothConnectionManager;
    private ActivityResultLauncher<Intent> enableBluetoothLauncher;
   ```

1. W OnCreate() :

   ```java
   BluetoothManager bluetoothManager = (BluetoothManager) getSystemService(BLUETOOTH_SERVICE);

        if (bluetoothManager != null) {
            bluetoothAdapter = bluetoothManager.getAdapter();
        }
   ```

1. Zawartość activity_main.xml:

   ```xml
      <?xml version="1.0" encoding="utf-8"?>

    <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="<http://schemas.android.com/apk/res/android>"
        xmlns:app="<http://schemas.android.com/apk/res-auto>"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <!-- Lista urządzeń zajmująca całą dostępną przestrzeń od góry do przycisków -->
        <androidx.recyclerview.widget.RecyclerView
            android:id="@+id/recyclerViewDevices"
            android:layout_width="0dp"
            android:layout_height="0dp"
            android:layout_marginTop="8dp"
            app:layout_constraintBottom_toTopOf="@+id/layoutButtons"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent" />

        <!-- Dolny panel z przyciskami sterującymi -->
        <LinearLayout
            android:id="@+id/layoutButtons"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:padding="12dp"
            android:background="#FFFFFF"
            android:elevation="8dp"
            app:layout_constraintBottom_toBottomOf="parent">

            <Button
                android:id="@+id/btnStartScan"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:layout_marginEnd="4dp"
                android:text="Start"
                android:backgroundTint="#4CAF50" />

            <Button
                android:id="@+id/btnStopScan"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:layout_marginHorizontal="4dp"
                android:text="Stop"
                android:backgroundTint="#F44336" />

            <Button
                android:id="@+id/btnClear"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:layout_marginStart="4dp"
                android:text="Wyczyść"
                android:backgroundTint="#2196F3" /> 

        </LinearLayout>

    </androidx.constraintlayout.widget.ConstraintLayout>

   ```

1. Przy uruchomieniu raz spradzić czy jest bluetooth włączony

   ![blue_on](../../media/2026-04-30-11-39-33.png)

   ```java
   // Rejestracja callbacku dla wyniku zapytania o włączenie Bluetooth
               enableBluetoothLauncher = registerForActivityResult(
                new ActivityResultContracts.StartActivityForResult(),
                result -> {
                    if (result.getResultCode() == RESULT_OK) {
                        Log.d(TAG, "onActivityResult() called with: result = [" + result + "Użytkownik kliknął zezwól");
                        Toast.makeText(MainActivity.this, "Włączono Bluetooth", Toast.LENGTH_SHORT).show();
                    } else {
                        // Użytkownik kliknął "Odmów" - nie uruchamiamy skanowania Bluetooth
                        Log.d(TAG, "onActivityResult() called with: result = [" + result + "]Użytkownik kliknął odmów");
                        Toast.makeText(MainActivity.this, "Nie włączono Bluetooth", Toast.LENGTH_SHORT).show();
                    }
                }
        );
   ```

1. Struktura projektu, sugerowana:

   ![struktura_projektu_bluetooth](../../media/2026-04-30-11-58-50.png)

1. Klasa DeviceModel – model danych, który reprezentuje urządzenie. Zawiera pola na nazwę, adres oraz identyfikator zasobu ikony. Dzięki temu łatwiej jest przypisać odpowiednią ikonę (np. na podstawie typu urządzenia).

   ```java
   public class DeviceModel {
    private String name;
    private String address;
    private int iconResId; // identyfikator zasobu graficznego (np. R.drawable.ic_headphones)
   ```

   Dodaj konstruktor oraz gettery i settery.

1. Klasa BluetoothConnectionManager - implementuje interfejs

   ```java
   public interface BluetoothScanInterface {
    void startScan();
    void stopScan();
   }
   ```

   i zarządza procesem skanowania, rejestrując oraz wyrejestrowując BroadcastReceiver.

   ```java
   public class BluetoothConnectionManager implements BluetoothScanInterface {

    private Context context;
    private BluetoothAdapter bluetoothAdapter;
    private BluetoothBroadcastReceiver broadcastReceiver;
    private boolean isScanning = false;

    public BluetoothConnectionManager(Context context, BluetoothBroadcastReceiver.OnDeviceFoundListener listener) {
        this.context = context.getApplicationContext();
        // Pobranie adaptera Bluetooth
        BluetoothManager manager = (BluetoothManager) context.getSystemService(Context.BLUETOOTH_SERVICE);
        bluetoothAdapter = manager.getAdapter();
        // Utworzenie instancji oddzielnego BroadcastReceivera
        broadcastReceiver = new BluetoothBroadcastReceiver(listener);

        IntentFilter filter = new IntentFilter();
        filter.addAction(BluetoothDevice.ACTION_FOUND);
        filter.addAction(BluetoothDevice.ACTION_BOND_STATE_CHANGED);
        filter.addAction(BluetoothAdapter.ACTION_DISCOVERY_FINISHED);
        this.context.registerReceiver(broadcastReceiver, filter);
    }
   ```

   w metodzie startScan:

   ```java
   bluetoothAdapter.startDiscovery();
   ```

1. BluetoothBroadcastReceiver.java – odpowiada za odbiór zdarzeń systemowych

   ```java
        public class BluetoothBroadcastReceiver extends BroadcastReceiver {
          // Interfejs umożliwiający przekazanie znalezionego urządzenia
          public interface OnDeviceFoundListener {
              void onDeviceFound(BluetoothDevice device);
          }

          private OnDeviceFoundListener listener;

          public BluetoothBroadcastReceiver(OnDeviceFoundListener listener) {
              this.listener = listener;
          }

          @Override
          public void onReceive(Context context, Intent intent) {
              String action = intent.getAction();
              if (BluetoothDevice.ACTION_FOUND.equals(action)) {
                  BluetoothDevice device = intent.getParcelableExtra(BluetoothDevice.EXTRA_DEVICE);
                  if (device != null && listener != null) {
                      listener.onDeviceFound(device);
                  }
              }

              if (BluetoothDevice.ACTION_BOND_STATE_CHANGED.equals(action)) {
                  BluetoothDevice device = intent.getParcelableExtra(BluetoothDevice.EXTRA_DEVICE);
                  int bondState = intent.getIntExtra(BluetoothDevice.EXTRA_BOND_STATE, BluetoothDevice.ERROR);

                  switch (bondState) {
                      case BluetoothDevice.BOND_BONDED:
                          // Urządzenie sparowane!
                          Log.v("111","Urządzenie sparowane: " );
                          break;
                      case BluetoothDevice.BOND_BONDING:
                          // W trakcie parowania...
                          Log.v("111","W trakcie parowania...");
                          break;
                      case BluetoothDevice.BOND_NONE:
                          // Parowanie odrzucone lub usunięte
                          Log.v("111","Parowanie odrzucone lub usunięte");
                          break;
                  }
              }

          }

      }

   ```

1. BluetoothDeviceAdapter.java – adapter dla RecyclerView, który korzysta z modelu DeviceModel, aby wyświetlić listę urządzeń wraz z nazwą, adresem i ikoną. Obsługuje również kliknięcia na elementach listy. Fragment kodu:

   ```java
   public class BluetoothDeviceAdapter extends RecyclerView.Adapter<BluetoothDeviceAdapter.ViewHolder> {

    private List<DeviceModel> deviceList;
    private OnItemClickListener listener;

    public interface OnItemClickListener {
        void onItemClick(DeviceModel device);
    }

    public BluetoothDeviceAdapter(List<DeviceModel> deviceList, OnItemClickListener listener) {
        this.deviceList = deviceList;
        this.listener = listener;
    }
   ```

1. Zawartość elementu listy RecyclerView:

   ```xml
      <?xml version="1.0" encoding="utf-8"?>

    <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:padding="12dp"> <ImageView
        android:id="@+id/imageViewIcon"
        android:layout_width="48dp"
        android:layout_height="48dp"
        android:layout_alignParentStart="true"
        android:layout_centerVertical="true"
        app:srcCompat="@drawable/ic_launcher_background" />

        <TextView
            android:id="@+id/textViewDeviceName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_toEndOf="@id/imageViewIcon"
            android:layout_marginStart="12dp"
            android:text="Nazwa urządzenia"
            android:textSize="16sp"
            android:textStyle="bold"
            android:textColor="?android:attr/textColorPrimary" />

        <TextView
            android:id="@+id/textViewDeviceAddress"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_toEndOf="@id/imageViewIcon"
            android:layout_below="@id/textViewDeviceName"
            android:layout_marginStart="12dp"
            android:layout_marginTop="4dp"
            android:textColor="?android:attr/textColorSecondary"
            android:text="00:11:22:33:44:55"
            android:textSize="14sp" />

    </RelativeLayout>
   ```

1. Zawartość MainActivity:

   ```java
    // Inicjalizacja RecyclerView
        RecyclerView recyclerView = findViewById(R.id.recyclerViewDevices);
        recyclerView.setLayoutManager(new LinearLayoutManager(this));

        // Inicjalizacja adaptera, obsługa kliknięć na urządzenia, parowanie
        adapter = new BluetoothDeviceAdapter(new ArrayList<DeviceModel>(), device -> {
            // Zatrzymaj skanowanie Bluetooth
            if (bluetoothConnectionManager != null) {
                bluetoothConnectionManager.stopScan();
            }

            if (bluetoothAdapter != null) {
                // 2. Pobieramy zdalne urządzenie po adresie MAC
                BluetoothDevice remoteDevice = bluetoothAdapter.getRemoteDevice(device.getAddress());

                // 3. Rozpoczynamy parowanie
                if (ActivityCompat.checkSelfPermission(getApplicationContext(), Manifest.permission.BLUETOOTH_CONNECT) == PackageManager.PERMISSION_GRANTED) {
                    int bondState = remoteDevice.getBondState();

                    if (bondState == BluetoothDevice.BOND_NONE) {
                        // Urządzenie nie jest sparowane - parujemy
                        boolean success = remoteDevice.createBond();
                        if (success) {
                            Toast.makeText(getApplicationContext(), "Parowanie z: " + device.getName(), Toast.LENGTH_SHORT).show();
                        }
                    } else if (bondState == BluetoothDevice.BOND_BONDED) {
                        // Urządzenie już jest sparowane - możesz spróbować się połączyć (Connect)
                        Toast.makeText(getApplicationContext(), "Urządzenie już jest sparowane!", Toast.LENGTH_SHORT).show();
                    }
                }
            }
        });

        recyclerView.setAdapter(adapter);
   ```

1. Obsługa przycisków, np.:

   ```java
   Button btnStart = findViewById(R.id.btnStartScan);

        btnStart.setOnClickListener(v -> {
            if (bluetoothConnectionManager != null) {
                bluetoothConnectionManager.startScan();
            }
            btnStart.setEnabled(false);
            btnStop.setEnabled(true);
        });
   ```

1. DeviceTypeMapper:

   ```java
   public class DeviceTypeMapper {

    /**
     * Zwraca odpowiednią ikonę dla urządzenia na podstawie jego klasy Bluetooth.
     */
    public static int getIconForDevice(Context context, BluetoothDevice device) {
        // Sprawdzenie uprawnień (wymagane dla getBluetoothClass() na Android 12+)
        if (ActivityCompat.checkSelfPermission(context, Manifest.permission.BLUETOOTH_CONNECT)
                != PackageManager.PERMISSION_GRANTED) {
            return R.drawable.bluetooth; // Ikona domyślna
        }

        BluetoothClass btClass = device.getBluetoothClass();
        if (btClass != null) {
            int deviceClass = btClass.getDeviceClass();

            switch (deviceClass) {
                case BluetoothClass.Device.AUDIO_VIDEO_LOUDSPEAKER:
                case BluetoothClass.Device.AUDIO_VIDEO_HIFI_AUDIO:
                case BluetoothClass.Device.AUDIO_VIDEO_HEADPHONES:
                case BluetoothClass.Device.AUDIO_VIDEO_WEARABLE_HEADSET:
                    return R.drawable.headphones;

                case BluetoothClass.Device.PERIPHERAL_KEYBOARD:
                    return R.drawable.keyboard;

                case BluetoothClass.Device.PERIPHERAL_POINTING:
                    return R.drawable.mouse;

                case BluetoothClass.Device.COMPUTER_LAPTOP:
                    return R.drawable.laptop_mac;
   ```

1. Po kliknięciu w pozycję listy, sparuj głośnik

   ![widok_okna_parowania](../../media/2026-04-30-08-19-46.png)

1. KONIEC. 🔚
