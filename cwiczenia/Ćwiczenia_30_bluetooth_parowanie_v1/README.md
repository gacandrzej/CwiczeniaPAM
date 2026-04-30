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
1. Przy uruchomieniu raz spradzić czy jest bluetooth włączony

   ![blue_on](../../media/2026-04-30-11-39-33.png)
1. Po kliknięciu w pozycję listy, sparuj głośnik

 ![widok_okna_parowania](../../media/2026-04-30-08-19-46.png)

1. KONIEC. 🔚
