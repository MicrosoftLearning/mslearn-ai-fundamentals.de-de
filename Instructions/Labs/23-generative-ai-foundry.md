---
lab:
  title: Erkunden von generativer KI im Azure AI Foundry-Portal
---

# Erkunden von generativer KI im Azure AI Foundry-Portal

Generative KI beschreibt eine Kategorie von Fähigkeiten innerhalb der KI, die Inhalte erstellen. Personen interagieren in der Regel mit generativer KI, die mit Chatanwendungen integriert wurde. In dieser Übung testen Sie generative KI im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen. 

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Navigieren Sie auf einer Browserregisterkarte zu [Azure AI Foundry](https://ai.azure.com?azure-portal=true).

1. Melden Sie sich mit Ihrem Konto an. 

1. Wählen Sie auf der Startseite des Azure AI Foundry-Portals die Option **Projekt erstellen** aus. In Azure AI Foundry sind Projekte Container, die Ihnen beim Organisieren Ihrer Arbeit helfen.  

    ![Screenshot der Startseite von Azure AI Foundry mit ausgewähltem „Projekt erstellen“.](./media/azure-ai-foundry-home-page.png)

1. Im Bereich *Projekt erstellen* sehen Sie einen generierten Projektnamen, den Sie so beibehalten können. Je nachdem, ob Sie in der Vergangenheit einen Hub erstellt haben, wird entweder eine Liste der zu erstellenden *neuen* Azure-Ressourcen oder eine Dropdownliste vorhandener Hubs angezeigt. Wenn Sie die Dropdown-Liste der vorhandenen Hubs sehen, wählen Sie *Neuen Hub erstellen*, erstellen Sie einen eindeutigen Namen für Ihren Hub und wählen Sie *Weiter*.  
 
    ![Screenshot des Erstellens eines Projektbereichs mit automatisch generierten Namen für Hub und Projekt.](./media/azure-ai-foundry-create-project.png)

> **Wichtig**: Sie benötigen eine Azure KI Services-Ressource, die an einem bestimmten Ort bereitgestellt wird, um den Rest des Labs durchzuführen.

1. Wählen Sie im gleichen Fenster *Projekt erstellen* die Option **Anpassen** und wählen Sie einen der folgenden **Standorte**: USA, Osten, Frankreich, Mitte, Südkorea, Mitte, Europa, Westen oder USA, Westen, um den Rest des Labs zu vervollständigen. Wählen Sie dann **Erstellen** aus. 

1. Notieren Sie sich die erstellten Ressourcen: 
- Azure KI Services
- Azure KI-Hub
- Azure KI-Projekt
- Speicherkonto
- Key vault
- Ressourcengruppe  
 
1. Nachdem die Ressourcen erstellt wurden, gelangen Sie auf die Seite *Übersicht* Ihres Projekts. Wählen Sie im Menü auf der linken Seite des Bildschirms **Playgrounds**.
 
    ![Screenshot des linken Menüs auf dem Projektbildschirm, auf dem „KI Services“ ausgewählt ist.](./media/azure-ai-foundry-playgrounds.png)  

## Erkunden von generativer KI im Chat-Playground von Azure AI Foundry

1. Wählen Sie auf der Seite „Playgrounds“ von Azure AI Foundry die Option **Chat-Playground ausprobieren**. Der Chat-Playground ist eine Benutzeroberfläche, über die Sie versuchen können, eine Chatanwendung mit unterschiedlichen generativen KI-Modellen zu erstellen.  

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