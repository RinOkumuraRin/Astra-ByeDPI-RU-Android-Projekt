# Astra & Vlady – Design Edition

Diese Version gestaltet den Startbildschirm neu (dunkler Nachthimmel, russische UI, Power-Button, Status, Proxy-Adresse, Einstellungs-Kacheln). Die bestehende VPN-/Proxy-Engine bleibt unverändert.

## Build
GitHub Actions → Astra ByeDPI RU - Build APK → Artefakt `Astra-ByeDPI-RU-APK` herunterladen. Alternativ: `./gradlew assembleDebug` mit Android SDK/NDK.

## Test
1. Alte App bei Bedarf deinstallieren, wenn Signaturen abweichen.
2. Neue Debug-APK installieren.
3. Power-Button und Hauptaktion testen; VPN-Berechtigung erteilen.
4. Im getrennten Zustand Einstellungen öffnen, im verbundenen Zustand erscheint der vorhandene Sicherheitshinweis.
5. Netzwerkfunktionen auf einem echten Android-Gerät testen. Die Emulatorverbindung beweist keine Erreichbarkeit in Russland.

**Hinweis:** Das Artwork ist ein zugeschnittener Ausschnitt des im Chat entworfenen visuellen Konzepts. Der Bildausschnitt dient als Hintergrund, nicht als interaktive Oberfläche. Die technischen Komponenten und Einstellungen stammen weiterhin aus ByeDPI.
