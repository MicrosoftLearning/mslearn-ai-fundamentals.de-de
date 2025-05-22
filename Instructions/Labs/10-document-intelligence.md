---
lab:
  title: 'Extrahieren von Daten aus Dokumenten in Azure AI Foundry '
---

# Extrahieren von Daten aus Dokumenten in Azure AI Foundry 

Mit dem **Azure KI Dokument Intelligenz**-Dienst können Sie Informationen aus Formularen und Dokumenten analysieren und extrahieren und anschließend Feldnamen und Daten identifizieren. 

Wie baut Dokument Intelligenz auf der optischen Zeichenerkennung (OCR) auf? OCR kann zwar gedruckte oder handschriftliche Dokumente lesen, extrahiert den Text jedoch in einem unstrukturierten Format, das nur schwer in einer Datenbank gespeichert oder analysiert werden kann. Dokument Intelligenz macht aus unstrukturierten Daten durch die Erfassung der Textstruktur, wie z. B. Datenfelder und Informationen in Tabellen, einen Sinn. 

In dieser Übung verwenden Sie die vorgefertigten Modelle von Azure KI Dokument Intelligenz im Azure AI Foundry-Portal, die Microsoft-Plattform zum Erstellen intelligenter Anwendungen, um Daten von einem Beleg zu erkennen. 

## Erstellen eines Projekts im Azure KI Foundry-Portal

Beginnen wir mit dem Erstellen eines Azure AI Foundry-Projekts.

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot der Azure AI Foundry-Startseite mit ausgewählter Option „Agent erstellen“.](./media/azure-ai-foundry-home-page.png)

1. Wählen Sie auf der Startseite **+ Agent erstellen**.

1. Geben Sie im Assistenten **Agent erstellen** einen gültigen Namen für Ihr Projekt ein. 

1. Wählen Sie **Erweiterte Optionen** und nehmen Sie die folgenden Einstellungen vor:
    - **Azure AI Foundry-Ressource**: *Behalten Sie den Standardnamen bei.*
    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
    - **Region**: Wählen Sie einen der folgenden Standorte aus:
        * East US
        * Frankreich, Mitte
        * Korea, Mitte
        * Europa, Westen
        * USA (Westen)

1. Wählen Sie **Erstellen** und überprüfen Sie Ihre Konfiguration. Warten Sie, bis der Einrichtungsvorgang abgeschlossen ist.

    >**Hinweis**: Wenn Sie eine Berechtigungsfehlermeldung erhalten, klicken Sie auf die Schaltfläche **Korrigieren**, um die erforderlichen Berechtigungen hinzuzufügen und fortzufahren.

1. Nach der Erstellung Ihres Projekts werden Sie standardmäßig zum Agents-Playground im Azure AI Foundry-Portal weitergeleitet, der in etwa wie folgt aussieht:

    ![Screenshot eines Azure KI-Projekts im Azure AI Foundry-Portal.](./media/ai-foundry-project-2.png)

1. Öffnen Sie in einem neuen Browserfenster die Seite [Azure KI Services erkunden](https://ai.azure.com/explore/aiservices).

1. Wählen Sie auf der Seite *KI Services* die Kachel *Vision + Dokument*, um die Azure KI Vision- und Dokument-Funktionen zu testen.

## Analysieren eines Belegs mit Azure KI Dokument Intelligenz in Azure AI Foundry 

Sie sind jetzt bereit, eine Quittung für das fiktive Northwind Traders Einzelhandelsunternehmen zu analysieren.

1. Scrollen Sie auf der Seite *Vision + Dokument* nach unten und wählen Sie **Dokument**. Wählen Sie unter *Vorgefertigte Modelle für bestimmte Dokumente* die Kachel **Belege** aus.

1. Beachten Sie, dass in der Dropdown-Liste unter *Ausprobieren* Ihre Azure KI Services-Ressource ausgewählt ist. Nehmen Sie keine Änderung vor.

1. Verwenden Sie auf Ihrem Computer [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt), um ein Beispielbild eines Belegs zu öffnen. Speichern Sie es in Ihrem Download-Ordner oder auf Ihrem Desktop. 
 
1. Wählen Sie in Azure AI Foundry auf der Seite *Belege* die Option **Nach Dateien suchen** und navigieren Sie zu dem Ordner, in dem Sie das Bild gespeichert haben. Wählen Sie das Bild der Quittung und dann **Öffnen** aus. Das Bild wird auf der linken Seite des Bildschirms angezeigt.

    ![Screenshot: Northwind-Quittung](media/document-intelligence/receipt.jpg)

1. Wählen Sie auf der rechten Seite **Analyse ausführen** aus.

1. Wenn die Analyse ausgeführt wurde, werden die Ergebnisse zurückgegeben. Beachten Sie, dass der Dienst bestimmte Datenfelder wie Händlername, Adresse, Telefonnummer und Transaktionsdatum und -uhrzeit sowie die Positionen, Zwischensummen, Steuern und Gesamtbeträge erkannt hat. Neben jedem Feld ist die prozentuale Wahrscheinlichkeit angegeben, dass das Feld richtig ist.

    ![Screenshot des Ergebnisses der Empfangsanalyse im Azure AI Foundry-Portal, der die Begrenzungsrahmen um die Datenfelder und den Text in diesen extrahierten Feldern zeigt.](media/receipt-lab-result.png)

In dieser Übung haben Sie das vorgefertigte Belegmodell von Azure KI Dokument Intelligenz im Azure AI Foundry-Portal verwendet. Aus den zurückgegebenen Ergebnissen konnten Sie ersehen, wie Dokument Intelligenz bestimmte Felder identifizieren konnte, sodass Daten aus alltäglichen Dokumenten einfacher verarbeitet werden können. Bevor Sie die Demo schließen, probieren Sie doch einige der Musterbelege aus, auch in verschiedenen Sprachen.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige der Funktionen des Azure KI Dokument Intelligenz-Diensts veranschaulicht. Weitere Informationen zu den Möglichkeiten dieses Diensts finden Sie auf der Seite [Dokument Intelligenz](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
