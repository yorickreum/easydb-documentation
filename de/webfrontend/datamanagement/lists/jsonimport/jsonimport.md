# JSON Importer

Der JSON-Importer kann zum Massenimport von Daten im [JSON format](../../../technical/datamanagement/jsonimport.md) verwendet werden.

Den Importer finden Sie unter "Listen &gt; JSON Import".

Die Konfiguration für den JSON-Importer kann in einer Manifestdatei \(.json\) hochgeladen werden. Das Manifest enthält Nutzlasten und andere Informationen, die den Importeur voreinstellen.

## Frontend Formular

![](jsonimporter_de.jpg)

Felder:

* URL manifest.json: \(Optional\) Indem Sie auf die Schaltfläche 'Laden' neben der Eingabe klicken, erhalten Sie eine URL, um die manifest.json zu laden. 
* Quelle: \(Optional\) Name der Quellinstanz
* Payloads base URI: \(Optional\) Basis-URI für alle Payloads in der Liste. It will be prepended to each payload.
* Upload Typ für Dateien: Siehe [Import von Dateien ](../importfiles/importfiles.html)
* EAS-URL Ersetzung für Dateien: \(Optional\) Der Speicherort für jede Datei-URL wird durch den hier konfigurierten Wert ersetzt.
* Payload Liste
  * Aktivieren: Checkbox zum Aktivieren oder Überspringen der Payloads
  * Status: Aktueller Status des Payloads. Wartend/Erfolgreich/Fehler
  * URL: URL des Payloads
  * Aktionen
    * Öffnet den Payload in einem neuen Tab.

Funktionen:

* Start: Es startet den Import aller aktivierten Payloads.
* Zurückrollen \(Rollback\): Es erfolgt ein Zurückrollen der importierten Daten \(z.B. wenn beim Laden der Payloads ein Fehler auftritt\).  Alle erstellten Daten werden rückgängig gemacht. Die Rollback-Daten gehen verloren, wenn der JSON Importer geschlossen wird und alle erfolgreich erstellten Daten verbleiben in der Datenbank. 
* Logs


