---
lab:
  title: Erkunden von generativer KI im Azure AI Foundry-Portal
---

# Erkunden generativer KI im Azure AI Foundry-Portal

Generative KI beschreibt eine Kategorie von Fähigkeiten innerhalb der KI, die Inhalte erstellen. Menschen interagieren häufig mit generativer KI, die in Chatanwendungen integriert wurde. In dieser Übung testen Sie generative KI im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen. 

Diese Übung dauert ca. **20** Minuten.

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot: Startseite des Azure AI Foundry-Portals](./media/ai-foundry-portal.png)

1. Suchen Sie im Abschnitt **Modelle und Fähigkeiten erkunden** nach `gpt-4o`. Wählen Sie dann in den Suchergebnissen das Modell **gpt-4o** aus, um dessen Details anzuzeigen.

    ![Screenshot: Detailseite des gpt-4o-Modells](./media/gpt-4o-details.png)

1. Wählen Sie **Dieses Modell verwenden** aus.

1. Geben Sie im Assistenten **Projekt erstellen** einen gültigen Namen für Ihr Projekt ein. Erweitern Sie **Erweiterte Optionen**, um die folgenden Einstellungen für Ihr Projekt festzulegen:
    - **Azure AI Foundry-Ressource**: *Geben Sie einen gültigen Namen für Ihre AI Foundry-Ressource ein.*
    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
    - **Region:** Wählen Sie eine der **empfohlenen AI Foundry**-Regionen aus.\*
    
    \**Modellimplementierungen unterliegen regionalen Kontingenten. Wenn Sie eine Region auswählen, in der Sie nicht über ein ausreichendes Kontingent verfügen, müssen Sie möglicherweise später eine alternative Region für eine neue Ressource auswählen.*

1. Klicken Sie auf **Erstellen**. Warten Sie, bis Ihr Projekt erstellt wurde. Dies kann einige Minuten dauern.

    Wenn Sie aufgefordert werden, das Modell in einer anderen Region bereitzustellen, verwenden Sie dazu die Standardeinstellungen.

## Erkunden von generativer KI im Chat-Playground von Azure AI Foundry

1. Nachdem das Projekt erstellt wurde, wählen Sie im Aufgabenbereich auf der linken Seite die Option **Playgrounds** aus. 

    >*Tipp*: Erweitern Sie ggf. das Menü, um dessen Inhalt anzuzeigen, indem Sie oben auf das Symbol „Erweitern“ klicken.

1. Wählen Sie auf der Seite „Playgrounds“ von Azure AI Foundry die Option **Chat-Playground ausprobieren**. Schließen Sie alle geöffneten Tipps oder Schnellstartbereiche.

    Der Chat-Playground ist eine Benutzeroberfläche, über die Sie versuchen können, eine Chatanwendung mit verschiedenen generativen KI-Modellen zu erstellen.

    ![Screenshot: Detailseite des gpt-4o-Modells](./media/chat-playground.png)

    >*Tipp*: Vergrößern Sie das Fenster, falls der Bereich **Setup** nicht auf dem Bildschirm des Chat-Playgrounds angezeigt wird.  

1. Um den Chat-Playground zu verwenden, müssen Sie ihn einem bereitgestellten Modell zuordnen. Vergewissern Sie sich im Bereich **Setup** des Chat-Playgrounds, dass das zuvor bereitgestellte Modell **gpt-4o** ausgewählt ist. 

    >*Hinweis:* Sie müssen jedes Mal **Änderungen übernehmen** auswählen, wenn Sie Änderungen im Bereich **Setup** vornehmen.

1. Beachten Sie im Bereich **Setup** die Standardanweisungen und den Standardkontext für das Modell, die in etwa wie folgt lauten sollten:

    `You are an AI assistant that helps people find information.`

    Solche Anweisungen werden im Allgemeinen als *Systemprompts* bezeichnet und dienen dazu, Richtlinien und Einschränkungen für die Antworten des Modells vorzugeben.

1. Sehen Sie sich den Bereich *Chatverlauf* an. Dieser Bereich enthält einige Beispielprompts, die Ihnen bei den ersten Schritten helfen, und ein Abfragefeld, in das Sie Ihre eigenen Prompts eingeben können. 

1. Versuchen wir, eine Antwort mithilfe eines Prompts mit einem spezifischen Ziel zu generieren. Geben Sie in das Chat-Feld den folgenden Prompt ein:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Überprüfen Sie die Antwort. Bedenken Sie, dass die konkrete Antwort, die Sie erhalten, aufgrund der Natur generativer KI variieren kann.

1. Versuchen wir es mit einem anderen Prompt. Geben Sie Folgendes ein:

    ```prompt
    Where's a good location in the city to stay?
    ```

1. Sehen Sie sich die Antwort an, die einige Übernachtungsmöglichkeiten in Paris enthalten sollte. Beachten Sie, dass die Chatsitzung den Kontext aus früheren Prompts beibehält, sodass sie z. B. weiß, dass es sich bei der fraglichen „Stadt“ um Paris handelt.

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

## Anzeigen des Clientcodes

1. Wählen Sie oben auf der Seite „Chat-Playground“ die Option **Code anzeigen** aus.
1. Sehen Sie sich die Codebeispiele an, die für mehrere Programmiersprachen, SDKs und Authentifizierungsoptionen bereitgestellt werden.

    Diese Codebeispiele ermöglichen Fachkräften in der Entwicklung einen schnellen Einstieg in die Erstellung von Clientanwendungen, die mit Ihrem bereitgestellten Modell chatten.

1. Schließen Sie das Fenster mit dem Beispielcode.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das **Azure-Portal** unter [https://portal.azure.com](https://portal.azure.com), und wählen Sie die Ressourcengruppe aus, die die von Ihnen erstellten Ressourcen enthält.
1. Wählen Sie **Ressourcengruppe löschen** aus, und **geben Sie zur Bestätigung den Namen der Ressourcengruppe ein**. Die Ressourcengruppe wird dann gelöscht.
