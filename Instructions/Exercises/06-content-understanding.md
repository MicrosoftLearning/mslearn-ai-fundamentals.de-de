---
lab:
  title: "Extrahieren von Daten mit „Inhaltsverständnis“ im Azure\_AI Foundry-Portal"
---

# Extrahieren von Daten mit „Inhaltsverständnis“ im Azure AI Foundry-Portal

„Verständnis von Azure AI-Inhalten“ bietet eine multimodale Analyse von Dokumenten, Audiodateien, Videos und Bildern zum Extrahieren von Informationen.

In dieser Übung verwenden Sie „Verständnis von Azure AI-Inhalten“ im Azure AI Foundry-Portal, der Microsoft-Plattform zum Erstellen intelligenter Anwendungen, um Informationen aus Rechnungen zu extrahieren. 

Diese Übung dauert ca. **25** Minuten.

## Erstellen eines Azure AI Foundry-Projekts für das Inhaltsverständnis

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot: Startseite des Azure AI Foundry-Portals](./media/ai-foundry-portal.png)

1. Scrollen Sie auf der Seite nach unten, und wählen Sie die Kachel **Azure KI Services erkunden** aus.

    ![Screenshot: Kachel „Azure KI Services erkunden“](./media/ai-services.png)

1. Wählen Sie auf der Seite „Azure KI Services“ die Kachel **Inhaltsverständnis testen** aus.

    ![Screenshot: Schaltfläche „Inhaltsverständnis testen“](./media/try-content-understanding.png)

1. Wählen Sie auf der Seite „Inhaltsverständnis“ die Option **Projekt erstellen, um zu beginnen** aus. Wählen Sie dann im Dialogfeld **Projekt erstellen** den empfohlenen Ressourcentyp (**Azure AI Foundry-Ressource**) aus:

    ![Screenshot: Analyseergebnisse](./media/resource-type.png)

1. Geben Sie auf **nächsten** Seite einen gültigen Namen für Ihr Projekt ein. Wählen Sie dann **Erweiterte Optionen** aus, und nehmen Sie die folgenden Einstellungen vor:
    - **Azure KI Foundry-Ressource**: *Ein gültiger Name für Ihre Azure KI Foundry-Ressource*
    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
    - **Region:** Wählen Sie einen der folgenden Standorte aus\*:
        * USA (Westen)
        * Schweden, Mitte
        * Australien (Osten)

    \**Zum Zeitpunkt der Erstellung dieses Artikels wird Inhaltsverständnis in diesen Regionen unterstützt.*

    ![Screenshot: Projekteinstellungen](./media/content-project-settings.png)

1. Klicken Sie auf **Erstellen**. Warten Sie, bis der Einrichtungsvorgang abgeschlossen ist. Dies kann einige Minuten dauern.

## Extrahieren von Informationen aus einer Rechnung

1. Laden Sie [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) von `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf` herunter. 

1. Wählen Sie auf der Seite „Inhaltsverständnis“die Registerkarte **Ausprobieren** und dann die Kachel **Rechnungsdatenextraktion** aus.

    ![Screenshot: Seite „Ausprobieren“ von „Inhaltsverständnis“](./media/content-understanding-invoice.png)

    Eine Beispielrechnung wird bereitgestellt.

1. Wählen Sie die Beispielrechnung aus, und verwenden Sie die Schaltfläche **Analyse ausführen**, um Informationen daraus zu extrahieren. Wenn die Analyse abgeschlossen ist, zeigen Sie die Ergebnisse an.

    ![Screenshot: Ergebnisse der Analyse der Beispielrechnung](./media/sample-invoice-analysis.png)

1. Laden Sie über den Link **Zu Dateien navigieren** das Dokument **contoso-invoice-1.pdf** hoch, das Sie zuvor heruntergeladen haben, und führen Sie eine Analyse für diese Datei aus.

    ![Screenshot: Ergebnisse der Analyse der Contoso-Rechnung](./media/contoso-invoice-analysis.png)

    Beachten Sie, dass das Analysetool für Inhaltsverständnis Informationen aus dieser Rechnung extrahieren kann, auch wenn sie anders als das Beispiel formatiert ist.

1. Zeigen Sie im Bereich rechts, wo die extrahierten Felder angezeigt werden, die Registerkarte **Ergebnis** an, um die JSON-Antwort anzuzeigen, die an eine Clientanwendung gesendet würde. Eine Fachkraft in der Entwicklung schreibt Code, um diese Antwort zu verarbeiten und sie in irgendeiner Form zu verwenden.

    ![Screenshot: Ergebnisse der Analyse der Contoso-Rechnung](./media/invoice-analysis-json.png)

## Bereinigen

Wenn Sie die Arbeit mit dem Content Understanding Service beendet haben, sollten Sie die Ressourcen, die Sie in dieser Übung erstellt haben, löschen, um unnötige Azure-Kosten zu vermeiden.

- Löschen Sie im Azure-Portal die Ressourcengruppe, die Sie in dieser Übung erstellt haben.
