---
title: "79 - Mitteilungen"
menu:
  main:
    name: "Mitteilungen"
    identifier: "webfrontend/administration/messages"
    parent: "webfrontend/administration"
---
# Mitteilungen

Mitteilungen erfüllen in easydb verschiedene Aufgaben. Sie können für Nachrichten verwendet werden, die ein Benutzer bestätigen muss, z. B. zum Akzeptieren von Nutzungsbedingungen.

Mitteilungen werden auch verwendet, um ein Impressum anzuzeigen oder andere Informationen für den Benutzer dauerhaft zugänglich zu machen.

Es besteht die Möglichkeit, Mitteilungen nur für bestimmte Benutzer-Gruppen sichtbar zu machen und sie zeitlich einzuschränken.

Mitteilungen werden dem Benutzer gezeigt, wenn er sich angemeldet hat oder die easydb aufruft (bei anonymen Login).

>HINWEIS: easydb merkt sich, wann welcher Benutzer welche Mitteilung bestätigt oder gesehen hat. Damit ist nachvollziehbar und beweisbar, dass ein Benuzter Nutzungsbedingungen akzeptiert hat. In einer späteren Version werden wir diese Daten auch dem Administrator zugänglich machen.

## Allgemein {#general}

|Einstellung|Erläuterung|
|---|---|
|Verwendung|Art der Mitteilung:<br><br> **Systemnachricht beim Login**: Nachdem sich der Benutzer authentifiziert oder unauthentifiziert angemeldet hat, erscheint eine Nachricht, die bestätigt werden muss, um fortzufahren z.B. Nutzungsbedingungen. <br> **Ständiger Hinweis im Hauptmenü**:  Information, die im Hauptmenü angezeigt wird, z.B. easydb Version, Impressum <br> **Hinweis vor dem Download**: Beim Start eines Downloads erhält der Benutzer eine Mitteilung und muss diese erst bestätigen, um fortzufahren.<br> **Startseite in der Suche**: Informationstext für den Benutzer in der Rechercheansicht. Wird kein Text hinterlegt, werden hier standardmäßig für den Benutzer freigegebene Datensätze angezeigt. <br> **Ständiger Hinweis im Benutzermenü**: Information, die oben rechts neben dem Benutzermenü als Button erscheint. Der Button trägt den Titel des Hinweises als Bezeichnung, z.B. Nutzungsbedingungen und öffnet ein Pop-Up, in dem der Hinweis erscheint. Der Hinweis-Button ist auch ohne Benutzer-Login abrufbar. <br> **Ständiger Hinweis im Selbstregistrierungsformular**: Information, die im [Selbstregistrierungsformular](../../userprefs/selfregister) erscheint. Es erscheint ein Linktext, über den die Nachricht in einem Pop-Up-Fenster abgerufen werden kann. Wird zusätzlich ein Bestätigungshinweis eingetragen, muss der Linktext gelesen werden, bevor die Registrierung abgeschlossen werden kann. Die Bestätigungscheckbox wird automatisch nach dem öffnen des Linktext aktiviert. |
|*Formatierung*|*Für eigene Textformatierungen oder Linktexte kann [Markdown](https://de.wikipedia.org/wiki/Markdown) verwendet werden.* |
|Titel|Titel der Nachricht. Wird für *Ständiger Hinweis* als Link benutzt. Mehrsprachig.|
|Typ|Design der Nachricht. Bestimmt, wie die Nachricht präsentiert wird, hat aber sonst keine Auswirkung auf die Funktionalität.|
|Ständiger Hinweis|Wenn gesetzt, wird die Mitteilung am unteren rechten Bildschirmrand angezeigt und steht auf Klick ständig für den Benutzer zur Verfügung. Benutzen Sie ständige Hinweise, um ein Impressum oder Informationen zu ihrer Datenbank zu hinterlegen.|
|Bestätigungshinweis|Wenn eingegeben, muss der Benutzer eine Checkbox markieren und damit den Text bestätigen. Mehrsprachiges Feld.|
|Jede neue Version bestätigen|Wenn gesetzt, werden alle Benutzer erneut um Bestätigung gebeten, wenn die Mitteilung vom Administrator neu gespeichert wurde.|
|Gültig von|Legt die erste Minute der Gültigkeit fest. Bleibt das Feld frei, beginnt die Gültigkeit sofort.|
|Gültig bis|Legt die letzte Minute der Gültigkeit fest. Bleibt das Feld frei, ist es zeitlich uneingeschränkt gültig.|
|Nachricht|Der eigentliche Text der Mitteilung. Mehrsprachig.|


## Gruppen

Standardmäßig sind Mitteilungen für Benutzer nicht sichtbar. Hier legen Sie fest, für welche Gruppen die Mitteilung angezeigt werden soll.
