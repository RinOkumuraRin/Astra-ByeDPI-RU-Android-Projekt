# Astra ByeDPI – Android APK bauen (Russisch)

Dies ist ein **Build-Projekt**, keine fertige APK. Es nutzt die reale native ByeDPI-Engine und den hev-socks5-tunnel aus den jeweiligen Open-Source-Projekten. Die Abhängigkeiten werden beim Build aus GitHub geladen; eine Internetverbindung ist erforderlich.

## Ohne Android Studio: GitHub Actions
1. Lege auf GitHub ein neues privates Repository an und lade den **Inhalt** dieses ZIP-Archivs hoch (inklusive `.github/workflows/build-apk.yml`). GitHub kann beim Browser-Upload versteckte Dateien übersehen; prüfe den Workflow-Pfad.
2. Öffne **Actions** → **Build Astra ByeDPI Android APK** → **Run workflow**.
3. Nach erfolgreichem Build die Datei unter **Artifacts** herunterladen, entpacken und die darin enthaltene `app-debug.apk` auf Android installieren.
4. Die APK ist mit einem Debug-Schlüssel signiert; nicht für öffentliche Distribution verwenden.

## Lokal
Android Studio mit Android SDK 34, CMake 3.22.1 und NDK installieren. Vor dem Build:
```
git clone --depth 1 https://github.com/hufrea/byedpi.git app/src/main/cpp/byedpi
git clone --depth 1 https://github.com/heiher/hev-socks5-tunnel.git app/src/main/jni/hev-socks5-tunnel
```
Dann `gradlew assembleDebug` (Windows: `gradlew.bat assembleDebug`).

## Einschränkungen
Die Build-Umgebung hier hat keinen Android SDK/NDK und keinen GitHub-Netzzugriff. **Der Build ist nicht getestet**, und die aktuelle Upstream-Version der nativen Komponenten könnte inkompatibel mit der alten ByeDPI Android 1.2.0 sein. Der Workflow kann deshalb fehlschlagen. Besser ist, die zur Version 1.2.0 passenden Submodule-Commits aus dem Original-Repository zu verwenden. Das Projekt bietet keine automatische Strategieoptimierung und keine garantierte Discord-UDP-Sprachqualität. Eine lokale VPN-Schnittstelle ist keine externe VPN-Verschlüsselung.

Lizenz: GPL-3.0, siehe LICENSE. Quellcode-Änderungen und Lizenzhinweise bei Weitergabe beibehalten.
