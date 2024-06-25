---
lab:
  title: Extrahieren von Formulardaten in Dokument Intelligenz Studio
---

# Extrahieren von Formulardaten in Dokument Intelligenz Studio

Azure KI Dokument Intelligenz kann Informationen aus Formularen und Dokumenten analysieren und extrahieren und dann Feldnamen und Daten identifizieren. 

Wie baut Dokument Intelligenz auf der optischen Zeichenerkennung (OCR) auf? OCR kann zwar gedruckte oder handschriftliche Dokumente lesen, extrahiert den Text jedoch in einem unstrukturierten Format, das nur schwer in einer Datenbank gespeichert oder analysiert werden kann. Dokument Intelligenz gibt unstrukturierten Daten einen Sinn, indem die Struktur des Texts erfasst wird, z. B. Schlüssel-Wert-Paare und Informationen in Tabellen. 

In dieser Übung sehen Sie sich ein vordefiniertes Modell in Dokument Intelligenz an, das trainiert wird, um Daten für Quittungen zu erkennen. 

> **HINWEIS** Azure KI Dokument Intelligenz ist der neue Name für die Azure-Formularerkennung. Möglicherweise wird im Azure-Portal oder in Document Intelligence Studio weiterhin „Azure-Formularerkennung“ angezeigt.

## Erstellen einer *Dokument Intelligenz*-Ressource

Sie können Azure KI Dokument Intelligenz verwenden, indem Sie entweder eine *Dokument Intelligenz*- oder eine *Azure KI Services*-Ressource erstellen. In dieser Übung erstellen Sie *Dokument Intelligenz*-Ressource, sofern Sie noch keine haben.

1. Öffnen Sie auf einer anderen Browserregisterkarte[Dokument Intelligenz Studio](https://formrecognizer.appliedai.azure.com/studio), und melden Sie sich mit Ihrem Microsoft-Konto an.
1. Wählen Sie **Einstellungen** und anschließend die Registerkarte **Ressourcen** aus. Wählen Sie **Neue Ressource erstellen** aus.
1. Geben Sie im Dialogfeld „Ressource erstellen“ Folgendes ein:
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine Ressourcengruppe mit einem eindeutigen Namen*.
    - **Name der neuen Ressource**: *Geben Sie einen eindeutigen Namen ein.*
    - **Speicherort:** *Wählen Sie eine Region aus. Wenn Sie sich im Osten der USA befinden, verwenden Sie „USA, Osten 2“.*
    - **Tarif**: *Kostenlose FO (falls verfügbar, andernfalls Standard SO)*.
1. Wählen Sie **Weiter** und dann **Fertig stellen** aus. Warten Sie, bis die Ressource bereitgestellt wurde.

    >**Hinweis:** Wenn Ihre Ressource nicht aufgeführt wird, müssen Sie die Seite unter Umständen **aktualisieren**.

Lassen Sie Dokument Intelligenz Studio geöffnet.

## Analysieren einer Quittung in Dokument Intelligenz Studio

Sie sind jetzt bereit, eine Quittung für das fiktive Northwind Traders Einzelhandelsunternehmen zu analysieren.

1. Wählen Sie [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) aus, um ein Beispieldokument auf Ihren Computer herunterzuladen. Öffnen Sie den Ordner . 
1. Wählen Sie **Dokument Intelligenz Studio** aus, um zur Seite **Erste Schritte mit Dokument Intelligenz Studio** zurückzukehren, und wählen Sie unter „Receipts“ **Ausprobieren** aus.
1. Stellen Sie in der Dropdownliste „Prebuilt“ sicher, dass **Receipts** ausgewählt ist.
1. Wählen Sie **Nach einer Datei suchen** aus, und navigieren Sie zu dem Ordner, in dem Sie das Bild gespeichert haben. Wählen Sie das Bild der Quittung und dann **Öffnen** aus. Das Bild wird auf der linken Seite des Bildschirms angezeigt.

    ![Screenshot: Northwind-Quittung](media/document-intelligence/receipt.jpg)

1. Wählen Sie auf der rechten Seite **Analyse ausführen** aus.
1. Wenn die Analyse ausgeführt wurde, werden die Ergebnisse zurückgegeben. Beachten Sie, dass der Dienst bestimmte Datenfelder wie Händlername, Adresse, Telefonnummer und Transaktionsdatum und -uhrzeit sowie die Positionen, Zwischensummen, Steuern und Gesamtbeträge erkannt hat. Neben jedem Feld ist die prozentuale Wahrscheinlichkeit angegeben, dass das Feld richtig ist.

In dieser Übung haben Sie Dokument Intelligenz Studio zum Erstellen einer Dokument Intelligenz-Ressource verwendet. Anschließend haben Sie den Dienst verwendet, um eine Quittung zu analysieren. Aus den zurückgegebenen Ergebnissen konnten Sie ersehen, wie Dokument Intelligenz bestimmte Felder identifizieren konnte, sodass Daten aus alltäglichen Dokumenten einfacher verarbeitet werden können. Warum versuchen Sie nicht, einige Beispielquittungen, einschließlich Quittungen in anderen Sprachen, auszuprobieren, bevor Sie Dokument Intelligenz Studio schließen?

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige der Funktionen des Azure KI Dokument Intelligenz-Diensts veranschaulicht. Weitere Informationen zu den Möglichkeiten dieses Diensts finden Sie auf der Seite [Dokument Intelligenz](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
