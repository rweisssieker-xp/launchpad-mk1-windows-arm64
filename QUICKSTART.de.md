# Launchpad MK1 unter Windows ARM64

Experimentelle Vorschau nur für das originale **NOVLPD01 / USB 1235:000E**. Die EXE verwendet Microsofts vorhandenen WinUSB-Treiber. Sie ist selbst noch nicht code-signiert. Der eigene unsignierte Kerneltreiber, fremde Installer und persönliche Diagnoseprotokolle sind nicht enthalten.

1. ZIP in einen eigenen Ordner entpacken. Andere Launchpad-Anwendungen schließen.
2. In PowerShell im Ordner zuerst `./LaunchpadBridge.exe --inbox-plan` ausführen. Das prüft nur den vorgesehenen Treiber.
3. In einer Administrator-PowerShell im selben Ordner `./LaunchpadBridge.exe --bind-inbox` ausführen.
4. Launchpad am selben USB-Port aus- und wieder einstecken.
5. Normal ausführen: `./LaunchpadBridge.exe --probe`, danach `./LaunchpadBridge.exe --led-sweep` für alle 80 LEDs in drei Farben.
6. Für MIDI/Ableton: `./LaunchpadBridge.exe --ableton` starten und das Fenster offen lassen.

In Ableton: Bedienoberfläche **Launchpad**; Ein- und Ausgang jeweils **Launchpad MK1 Ableton**. **LP MK1 Bridge** ist intern. Für Instrumentenspiel müssen außerdem MIDI-Eingang, Monitoring/Armierung und ein Instrument in Live passend eingerichtet sein. Leere Session-Clips erzeugen allein keinen Drum-Sound.

Die Portbrücke und die echte Geräteantwort wurden geprüft. Die endgültige Session-/Mixer-Einrichtung in Ableton ist noch nicht vollständig praktisch bestätigt. Die ausführliche englische README benennt Testumfang und Grenzen.

`--self-test` benötigt keine Hardware. Bei Fehlern keine Sicherheitseinstellungen abschalten. Automatische Telemetrie oder Log-Uploads sind nicht vorhanden.
