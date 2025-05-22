---
lab:
  title: Erkunden von generativer KI im Azure AI Foundry-Portal
---

# Erkunden generativer KI im Azure AI Foundry-Portal

Generative KI beschreibt eine Kategorie von Fähigkeiten innerhalb der KI, die Inhalte erstellen. Personen interagieren in der Regel mit generativer KI, die mit Chatanwendungen integriert wurde. In dieser Übung testen Sie generative KI im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen. 

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

1. Wählen Sie im Menü auf der linken Seite des Bildschirms **Playgrounds**.

## Erkunden von generativer KI im Chat-Playground von Azure AI Foundry

1. Wählen Sie auf der Seite „Playgrounds“ von Azure AI Foundry die Option **Chat-Playground ausprobieren**. Der Chat-Playground ist eine Benutzeroberfläche, über die Sie versuchen können, eine Chatanwendung mit verschiedenen generativen KI-Modellen zu erstellen.  

1. Um den Chat-Playground zu verwenden, müssen Sie ihn einem bereitgestellten Modell zuordnen. Im Chat-Playground wählen Sie **Bereitstellung erstellen**. Suchen Sie nach **GPT-4** und wählen Sie es aus. 

1. Im Fenster *Modell bereitstellen* behalten Sie die Standardbenennung und -auswahl bei und wählen **Bereitstellen**. Es kann einen Moment dauern, bis das Modell bereitgestellt wird. Sie können den Status Ihrer Bereitstellung überprüfen, indem Sie *Modelle und Endpunkte* im linken Menü unter *Meine Ressourcen* auswählen.
1. Im Chat-Playground können Sie Ihr eingesetztes Modell verwenden, wenn es im Auswahlmenü *Bereitstellung* erscheint. Stellen Sie sicher, dass das bereitgestellte Modell ausgewählt wurde. Wichtig ist, dass Sie **Änderungen übernehmen** wählen müssen, nachdem Sie Änderungen am *Setup* vorgenommen haben. 

1. Berücksichtigen Sie die folgenden Möglichkeiten, wie Sie Antworten von einem generativen KI-Assistenten verbessern können:
    - Beginnen Sie mit einem konkreten Ziel für die Aufgabe, die der Assistent übernehmen soll
    - Iterieren Sie auf der Grundlage früherer Eingabeaufforderungen und Antworten, um das Ergebnis zu verfeinern.
    - Geben Sie eine Quelle an, um die Antwort auf einen bestimmten Bereich von Informationen zu stützen.
    - Fügen Sie Kontext hinzu, um die Eignung und Relevanz der Antwort zu maximieren.
    - Legen Sie klare Erwartungen an die Antwort fest.

1. Versuchen wir einmal, eine Antwort mit einem Prompt mit einem bestimmten Ziel zu erstellen. Geben Sie in das Chat-Feld den folgenden Prompt ein:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Überprüfen Sie die Antwort. **Hinweis**: Beachten Sie, dass die konkrete Antwort, die Sie erhalten, aufgrund der Art der generativen KI variieren kann.
 
1. Versuchen wir es mit einem anderen Prompt. Geben Sie Folgendes ein:

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. Sehen Sie sich die Antwort an, die einige Übernachtungsmöglichkeiten in Paris enthalten sollte.

1. Wiederholen wir dies auf der Grundlage früherer Prompts und Antworten, um das Ergebnis zu verfeinern. Geben Sie den folgenden Prompt ein:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Überprüfen Sie die Antwort, die Restaurants in der Nähe eines Ortes aus der vorherigen Antwort enthalten sollte. 

1. Lassen Sie uns nun eine Quelle bereitstellen, um die Reaktion auf einen bestimmten Informationsumfang zu stützen. Geben Sie Folgendes ein: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Überprüfen Sie die Antwort, die Informationen auf der Grundlage der bereitgestellten Website enthalten sollte. 

1. Versuchen wir, Kontext hinzuzufügen, um die Relevanz der Antwort zu maximieren. Geben Sie den folgenden Prompt ein: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Überprüfen Sie die Antwort und die Begründung für die Antwort.  

1. Versuchen Sie nun, klare Erwartungen für die Reaktion festzulegen. Geben Sie den folgenden Prompt ein:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Überprüfen Sie die Antwort, die eine nummerierte Liste von Sehenswürdigkeiten zur Verfügung stellen sollte, die in Paris zu sehen sind.

1. Wenn Sie fertig sind, können Sie das Browserfenster schließen.
