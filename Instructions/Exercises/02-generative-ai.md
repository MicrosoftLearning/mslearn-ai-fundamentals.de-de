---
lab:
  title: Erkunden von generativer KI im Azure AI Foundry-Portal
---

# Erkunden generativer KI im Azure AI Foundry-Portal

Generative KI beschreibt eine Kategorie von Fähigkeiten innerhalb der KI, die Inhalte erstellen. Personen interagieren in der Regel mit generativer KI, die mit Chatanwendungen integriert wurde. In dieser Übung testen Sie generative KI im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen. 

Diese Übung dauert ca. **20** Minuten.

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartbereiche, die bei der ersten Anmeldung angezeigt werden. 

1. Navigieren Sie im Browser zu `https://ai.azure.com/managementCenter/allResources`, und wählen Sie **Neu erstellen** aus. Wählen Sie anschließend die Option zum Erstellen einer **Azure AI Foundry-Ressource** aus.

1. Geben Sie im Assistenten *Projekt erstellen* einen gültigen Namen für Ihr Projekt ein.

1. Erweitern Sie *Erweiterte Optionen*, um folgende Einstellungen vorzunehmen:
    - **Abonnement**: Ihr Azure-Abonnement
    - **Ressourcengruppe**: Erstellen oder wählen Sie eine Ressourcengruppe aus.
    - **Region**: Wählen Sie einen der folgenden Standorte aus:
        * East US
        * Frankreich, Mitte
        * Korea, Mitte
        * Europa, Westen
        * USA (Westen)

    Klicken Sie auf **Erstellen**. Warten Sie, bis Ihr Projekt erstellt wurde. Dies kann einige Minuten dauern.

1. Wenn das Projekt erstellt wird, gelangen Sie zu einer *Übersichtsseite* der Projektdetails.

1. Wählen Sie im Menü auf der linken Seite des Bildschirms **Playgrounds**. 

    >*Hinweis:* Erweitern Sie zum Lesen des Inhalts das Menü, indem Sie oben auf das Symbol „Erweitern“ klicken.

## Erkunden von generativer KI im Chat-Playground von Azure AI Foundry

1. Wählen Sie auf der Seite „Playgrounds“ von Azure AI Foundry die Option **Chat-Playground ausprobieren**. Der Chat-Playground ist eine Benutzeroberfläche, über die Sie versuchen können, eine Chatanwendung mit verschiedenen generativen KI-Modellen zu erstellen.  

    >*Hinweis:* Wenn der Bereich *Setup* auf dem Bildschirm des Chat-Playgrounds nicht angezeigt wird, erweitern Sie die Fenstergröße.  

1. Um den Chat-Playground zu verwenden, müssen Sie ihn einem bereitgestellten Modell zuordnen. Wählen Sie im Bereich *Setup* im Chat-Playground **+Bereitstellung erstellen** aus. Wenn Sie dazu aufgefordert werden, wählen Sie *Aus Basismodellen* aus, andernfalls fahren Sie mit dem nächsten Schritt fort. 

1. Suchen Sie nach dem Modell **gpt-4o** und wählen Sie dann **Bestätigen** aus. Behalten Sie die Standardwerte für Modellnamen, Bereitstellungstyp und Bereitstellungsdetails bei. Wählen Sie anschließend **Bereitstellen** aus.

1. Im Chat-Playground können Sie Ihr eingesetztes Modell verwenden, wenn es im Auswahlmenü *Bereitstellung* erscheint. Schließen Sie alle geöffneten Tipps oder Schnellstartbereiche. 

    >*Hinweis:* Sie müssen jedes Mal **Änderungen übernehmen** auswählen, wenn Sie Änderungen am *Setup* vornehmen. 

1. Navigieren Sie zum Bereich *Chatverlauf*. Das Abfragefeld wird für die Eingabe von Prompts verwendet. 

1. Berücksichtigen Sie die folgenden Möglichkeiten, wie Sie Antworten von einem generativen KI-Assistenten verbessern können:
    - Beginnen Sie mit einem konkreten Ziel für die Aufgabe, die der Assistent übernehmen soll
    - Iterieren Sie auf der Grundlage früherer Eingabeaufforderungen und Antworten, um das Ergebnis zu verfeinern.
    - Geben Sie eine Quelle an, um die Antwort auf einen bestimmten Bereich von Informationen zu stützen.
    - Fügen Sie Kontext hinzu, um die Eignung und Relevanz der Antwort zu maximieren.
    - Legen Sie klare Erwartungen an die Antwort fest.

1. Versuchen wir, eine Antwort mithilfe eines Prompts mit einem spezifischen Ziel zu generieren. Geben Sie in das Chat-Feld den folgenden Prompt ein:

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

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das **Azure-Portal** unter [https://portal.azure.com](https://portal.azure.com), und wählen Sie die Ressourcengruppe aus, die die von Ihnen erstellten Ressourcen enthält.

1. Wählen Sie die Ressourcen, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressourcen werden dann gelöscht.
