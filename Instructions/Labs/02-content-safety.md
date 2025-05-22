---
lab:
  title: "Erkunden von Azure\_KI Services"
---

# Erkunden von Azure KI Services

Mit Azure KI Services können Benutzer*innen KI-Anwendungen mit sofort einsatzbereiten, vorgefertigten und anpassbaren APIs und Modellen erstellen. In dieser Übung erstellen Sie eine Ressource im Azure-Portal und testen Azure KI Services. Ziel dieser Übung ist es, einen allgemeinen Eindruck davon zu gewinnen, wie Azure KI Services bereitgestellt und verwendet werden.

## Erstellen einer *Azure KI Services*-Ressource im Azure-Portal.

1. Öffnen Sie auf einer Browserregisterkarte das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com?azure-portal=true), und melden Sie sich mit dem Microsoft-Konto an, das Ihrem Azure-Abonnement zugeordnet ist.

1. Klicken Sie auf die Schaltfläche **＋Ressource erstellen** und suchen Sie nach *Azure KI Services*. Wählen Sie **Erstellen** eines **Azure KI Services**-Plans aus. Sie werden zu einer Seite weitergeleitet, um eine Azure KI Services-Ressource zu erstellen. Konfigurieren Sie sie mit den folgenden Einstellungen:
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine Ressourcengruppe mit einem eindeutigen Namen*.
    - **Region:** *Wählen Sie die geografisch nächstgelegene Region aus. Wenn Sie sich im Osten der USA befinden, verwenden Sie „USA, Osten 2“.*
    - **Name**: *Geben Sie einen eindeutigen Namen ein*.
    - **Tarif**: *Standard S0.*
    - **Durch Aktivieren dieses Kontrollkästchens bestätige ich, dass ich die folgenden Bedingungen gelesen und verstanden habe**: *Ausgewählt*.

1. Wählen Sie die Option **Überprüfen und erstellen** und dann **Erstellen** aus, und warten Sie, bis die Bereitstellung abgeschlossen ist.

    *Herzlichen Glückwunsch! Sie haben soeben eine Azure KI Services-Ressource erstellt oder bereitgestellt. Die von Ihnen bereitgestellte Ressource ist eine Multi-Dienstressource.*

1. Klicken Sie nach Abschluss der Bereitstellung auf *Zu Ressource wechseln*. 

## Überprüfen der Schlüssel und des Endpunkts

Um Azure KI Services in Anwendungen zu integrieren, benötigen Fachkräfte in der Entwicklung einen Dienstschlüssel und einen Endpunkt. Die für die Anwendungsentwicklung verwendeten Schlüssel und Endpunkte finden Sie im Azure-Portal. 

1. Wählen Sie im Azure-Portal Ihre Ressource aus. Suchen Sie im Menü auf der linken Seite unter *Ressourcenverwaltung* nach *Schlüssel und Endpunkte*. Wählen Sie **Schlüssel und Endpunkte** aus, um den Endpunkt und die Schlüssel für Ihre Ressource anzuzeigen. 

## Azure KI Services in Aktion

Beginnen wir mit dem Erstellen eines Azure AI Foundry-Projekts.

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot der Azure AI Foundry-Startseite mit ausgewählter Option „Agent erstellen“.](./media/azure-ai-foundry-home-page.png)
 
1. Öffnen Sie in einem neuen Browserfenster die Seite [Azure KI Services erkunden](https://ai.azure.com/explore/aiservices).

1. Wählen Sie auf der Seite *KI Services* die Kachel *Vision + Dokument*, um die Azure KI Vision- und Dokument-Funktionen zu testen.

    ![Screenshot der Kachel „Vision und Dokument“, die auf der Seite „KI Services“ ausgewählt wurde.](./media/vision-document-tile.png)

1. Wählen Sie unter *Alle Vision-Funktionen anzeigen* die Registerkarte **Gesicht**. 

1. Wählen Sie die Demo-Kachel *Gesichter in einem Bild erkennen* aus. 

1. Probieren Sie den Face Service aus, bei dem es sich um einen von vielen Azure KI Services handelt. Klicken Sie auf ein Bild und sehen Sie sich die erkannten Attribute an. 

    ![Screenshot der Demo zur Gesichtserkennung im Azure AI Foundry-Portal.](./media/detect-faces-demo.png)

1. Scrollen Sie nach unten zum Abschnitt **Code ausführen**. Wählen Sie **Code anzeigen**. Scrollen Sie nach unten zum Abschnitt, der mit *import os* beginnt. Im bereitgestellten Beispielcode finden Sie Platzhalter, in die Sie einen Schlüssel und einen Endpunkt einfügen können.

    ![Screenshot des Bildschirms „Code anzeigen“ mit einer Ansicht der Code-Platzhalter für Schlüssel und Endpunkt.](./media/view-code-example.png) 

1. Wenn Sie eine Anwendung erstellen möchten, die Azure KI Services verwendet hat, könnten Sie mit dem bereitgestellten Code beginnen. Indem Sie die Platzhalter durch den Schlüssel und Endpunkt Ihres eigenen Diensts ersetzen, kann Ihre Anwendung Anforderungen senden und Antworten empfangen, die Azure KI Services nutzen. Im Falle des Face-Dienstes wird mit der Anfrage *request* der Face-Dienst aufgefordert, das Bild zu analysieren. Die *Antwort* sind die erkannten Attribute. 

    >**Hinweis:** Sie benötigen keine Programmierkenntnisse, um die Übungen in diesem Kurs durchzuführen. Wir werden weiterhin einen Blick auf Azure KI Services in Aktion über das Azure AI Foundry-Portal werfen.  
 
## Bereinigen 

Wenn Sie fertig sind, können Sie die Azure KI Services-Ressource aus dem Azure-Portal löschen. Das Löschen der Ressource ist eine Möglichkeit, die Kosten zu senken, die anfallen, wenn die Ressource im Abonnement vorhanden ist. Navigieren Sie dazu zur Seite **Übersicht** Ihrer Azure KI Services-Ressource. Wählen Sie oben auf dem Bildschirm **Löschen** aus.

