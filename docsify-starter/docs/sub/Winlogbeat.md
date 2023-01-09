# Winlogbeat

Winlogbeat ist ein Event-Log Shipping Service für Windows Systeme. Damit lassen sich Event-Logs von einem Windows-System zu einem Zielsystem, wie Elasticsearch, senden. 
In Verbindung mit Elasticseatch und Kibana, kann Winlogbeat als Monitoring Lösung verwendet werden.
Die Aktuelle Version ist 8.5.3, welche am 06.12.2022 veröffentlicht wurde.

## Installation

1. Die neuste Winlogbeat Version von [https://www.elastic.co/de/downloads/beats/winlogbeat](Elastic) herunterladen.
2. Das Zip-File in C:\Program Files entpacken.
3. Den Ordner winlogbeat-<Version> in Winlogbeat umbenennen.
4. Powershell als Admin starten:
    ```ps
    cd 'C:\Program Files\Winlogbeat'
    ```
    ```ps
    .\install-service-winlogbeat.ps1
    ```

## Konfiguration

Im winlogbeat.yml File können nun Konfigurationen vorgenommen werden:
1. Es muss eine Verbindung zum Elasticsearch hergestellt werden:
    ```yml
    output.elasticsearch:
        hosts: ["https://192.168.38.105:9200"]
        username: "vagrant"
        password: "vagrant"
    ```
2. Ebenfalls muss eine Verbindung zu Kibana hergestellt werden:
       ```yml
    setup.kibana:
        host: "192.168.38.105:5601"
        username: "vagrant"
        password: "vagrant"
    ```
1. Ausserdem können weitere Event-Logs hinzugefügt werden:
    ```yml
    winlogbeat.event_logs:
        - name: Application
            ignore_older: 72h

        - name: System

        - name: Security

        - name: Microsoft-Windows-Sysmon/Operational

        - name: Windows PowerShell
            event_id: 400, 403, 600, 800

        - name: Microsoft-Windows-PowerShell/Operational
            event_id: 4103, 4104, 4105, 4106

        - name: ForwardedEvents
            tags: [forwarded]
    ```
    - Um die Konfiguration zu testen kann folgender Befehl ausgeführt werden:
    ```ps
    C:\Program Files\Winlogbeat> .\winlogbeat.exe test config -c .\winlogbeat.yml -e
    ```
2. Wenn alles geklappt hat kann Winlogbeat gestartet werden:
   ```ps
   C:\Program Files\Winlogbeat> Start-Service winlogbeat
   ```
   
