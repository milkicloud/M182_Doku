# Sysmon

Der System Monitor, kurz Sysmon ist ein Windows Service, welcher in der Lage ist jegliche Vorgänge auf einem Client zu loggen.
Vorallem kann Sysmon zum entdecken von Schadsoftware und Eindringlingen genutzt werden.
Sysmon-Logs können von dritt-Applikationen verwendet werden um Geräte in Netzwerken zu Monitoren.
Grundsätzlich ist Sysmon ein sehr mächtiges Logging Tool und Erfahrungen damit sind von grossem Vorteil.
Die Aktuelle Version von Sysmon ist v14.13

## Installation

Um Sysmon auf einer Windows-Machine zu installieren braucht man nur die Sysmon64.exe herunterzuladen und diese mit dem Parameter -i auszuführen.
Optional kann man dabei auch ein Konfigurations-File mitgeben.
Sysmon gehört zu den Sysinternals und kann direkt von Microsoft heruntergeladen werden.

In einer Unternehmung könnte man Sysmon zum einen direkt in ein Template-Image integrieren und zum anderen per Softwareverteilungsystem oder GPO verteilen.

## Konfiguration

Die Konfiguration von Sysmon erfolgt in einem XML-File.