Langkah Ke 1 :
    Buka File AndroidManifest.xml Yang Ada Di Foler android/src/main dan Tambahankan Permisions Disebelum Tag Penutup ```</manifest>``` dan Sesudah Tag Penutup ```</application>``` :

        <uses-permission android:name="android.permission.INTERNET"/>

Langkah Ke 2 : 
    Buka File build.gradle Yang Ada Di Folder android/app/build.gradle dan Edit Code :

    buildTypes {
        release {
            // TODO: Add your own signing config for the release build.
            // Signing with the debug keys for now, so `flutter run --release` works.
            signingConfig signingConfigs.debug
        }
    }

Menjadi Seperti Berikut :

    buildTypes {
        release {
            // TODO: Add your own signing config for the release build.
            // Signing with the debug keys for now, so `flutter run --release` works.
            signingConfig signingConfigs.debug

            //Ditambahakan 2 Code Berikut
            shrinkResources false
            minifyEnabled false
            //END
        }
    }
Langkah Ke 3 :
    Buka Terminal/CMD di VSCODE Dengan Menekan Tombol CTRL+Shift+` kemudian ketikan:

        1. start ms-settings:developers //Untuk Mengaktifkan Windows Developer Mode
            - Kemudian Aktifkan Developer Mode
        2. flutter clean
        3. flutter build apk --release

