# Ćwiczenia - bluetooth - parowanie urządzeń

💡Do realizacji ćwiczeń wymagany jest tablet lub smartfon oraz głośnik bluetooth

1. Otwórz dokumentację:

    <https://developer.android.com/guide/topics/permissions/overview>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/permissions>
    <https://developer.android.com/guide/topics/connectivity/bluetooth>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/setup>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/find-bluetooth-devices>
    <https://developer.android.com/guide/topics/connectivity/bluetooth/transfer-data>

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

1. Po kliknięciu w pozycję listy, sparuj głośnik

 ![widok_okna_parowania](../../media/2026-04-30-08-19-46.png)

1. KONIEC. 🔚
