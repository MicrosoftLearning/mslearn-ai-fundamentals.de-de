---
lab:
  title: Analysieren von Text im Azure AI Foundry-Portal
---

# Analysieren von Text im Azure AI Foundry-Portal

Azure KI Language umfasst eine Textanalyse mit Funktionen wie Entitätserkennung, Schlüsselbegriffserkennung, Zusammenfassung und Stimmungsanalyse. Angenommen, das fiktive Reisebüro Margie's Travel bittet seine Kunden, Bewertungen für Hotelaufenthalte zu schreiben. Sie können den Sprachdienst verwenden, um benannte Entitäten zu extrahieren, Schlüsselausdrücke zu identifizieren, Text zusammenzufassen und vieles mehr.

In dieser Übung verwenden Sie Azure AI Language im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen, um Hotelbewertungen zu analysieren. 

Diese Übung dauert ca.**20** Minuten.

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Öffnen Sie in einem Webbrowser unter`https://ai.azure.com` das[Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo**Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das**Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot: Startseite des Azure AI Foundry-Portals](./media/ai-foundry-portal.png)

1. Scrollen Sie auf der Seite nach unten, und wählen Sie die Kachel**Azure KI Services erkunden** aus.

    ![Screenshot: Kachel „Azure KI Services erkunden“](./media/ai-services.png)

1. Wählen Sie auf der Seite „Azure KI Services“ die Kachel**Sprache und Übersetzer** aus.

    ![Screenshot: Kachel „Sprache und Übersetzer“](./media/language-tile.png)

1. Wählen Sie auf der Seite**Sprache und Übersetzer** die Option**Language-Playground testen** aus. Erstellen Sie dann ein neues Projekt mit den folgenden Einstellungen, wenn Sie dazu aufgefordert werden:
    - **Projektname:***Geben Sie einen gültigen Namen für Ihr Projekt ein.*
    - **Erweiterte Einstellungen**:
        - **Abonnement:***Geben Sie Ihr Azure-Abonnement an.*
        - **Ressourcengruppe**:*Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
        - **Region:***Wählen Sie eine**empfohlene AI Foundry**-Region aus.*
        - **AI Foundry oder Azure OpenAI***Erstellen Sie eine neue Azure AI Foundry-Ressource mit einem gültigen Namen.*

1. Klicken Sie auf**Erstellen**. Warten Sie, bis Ihr Projekt erstellt wurde. Dies kann einige Minuten dauern.

1. Wenn das Projekt erstellt wird, gelangen Sie zu einem**Language**-Playground (falls nicht, wählen Sie im Aufgabenbereich auf der linken Seite**Playgrounds** aus, und öffnen Sie den Language-Playground von dort aus.)

    Der Language-Playground ist eine Benutzeroberfläche, auf der Sie einige Azure KI Language-Funktionen ausprobieren können.  

## Verwenden von Azure KI Language zum Analysieren von Text

Azure KI Language bietet eine Vielzahl von Textanalysefunktionen.

### Extrahieren benannter Entitäten mit Azure AI Language im Azure AI Foundry-Portal

*Benannte Entitäten* sind Wörter, die Personen, Orte und Objekte mit Eigennamen beschreiben. Verwenden wir die Funktion zur Extraktion benannter Entitäten von Azure AI Language, um die verschiedenen Arten von Informationen in einer Bewertung zu identifizieren.

1. Wählen Sie im Speech-Playground**Informationen extrahieren** aus. Wählen Sie dann die Kachel**Benannte Entitäten extrahieren** aus. 

1. Geben Sie unter*Beispiel* die folgende Bewertung ein:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Klicken Sie auf**Ausführen**. Überprüfen Sie die Ausgabe.

    ![Screenshot: Benutzeroberfläche „Benannte Entitäten extrahieren“ im Language-Playground](./media/entity-extraction.png)

    Beachten Sie im Abschnitt*Details*, dass die extrahierten Entitäten mit zusätzlichen Informationen wie Typ und Konfidenzwerten versehen sind. Die Konfidenzbewertung stellt die Wahrscheinlichkeit dar, dass der identifizierte Typ tatsächlich zu dieser Kategorie gehört.

### Extrahieren von Schlüsselausdrücken mit Azure AI Language im Azure AI Foundry-Portal

*Schlüsselbegriffe* sind die wichtigsten Informationen im Text. Verwenden wir die Schlüsselbegriffserkennungs-Funktion von Azure AI Language, um wichtige Informationen aus einer Bewertung abzurufen.

1. Wählen Sie im Speech-Playground**Informationen extrahieren** aus. Wählen Sie dann die Kachel**Schlüsselbegriffe extrahieren** aus. 

1. Geben Sie unter*Beispiel* die folgende Bewertung ein:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Klicken Sie auf**Ausführen**. Überprüfen Sie die Ausgabe.

    ![Screenshot: Benutzeroberfläche „Schlüsselbegriffe extrahieren“ im Language-Playground](./media/key-phrases.png)

    Beachten Sie die verschiedenen Ausdrücke, die im Abschnitt*Details* extrahiert wurden. Diese Ausdrücke sollten am meisten zur Bedeutung des Texts beitragen.

### Zusammenfassen von Text mit Azure AI Language im Azure AI Foundry-Portal
 
Sehen wir uns die Zusammenfassungsfunktionen von Azure AI Language an.

1. Wählen Sie im Speech-Playground die Option**Informationen zusammenfassen** und wählen Sie dann die Kachel**Text zusammenfassen**.

1. Geben Sie unter*Beispiel* die folgende Bewertung ein:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Klicken Sie auf**Ausführen**. Überprüfen Sie die Ausgabe.

    ![Screenshot: Benutzeroberfläche „Text zusammenfassen“ im Language-Playground](./media/summarize-text.png)

    Beachten Sie, dass die*Extraktive Zusammenfassung* unter*Details* Rangbewertungen für die wichtigsten Sätze liefert.

### Analysieren der Stimmung in Text

Die Stimmungsanalyse ist eine häufige Aufgabe beim Analysieren von Texten wie Hotelbewertungen.

1. Wählen Sie im Language-Playground die Option**Text klassifizieren** aus. Wählen Sie dann die Kachel**Stimmung analysieren** aus.

1. Geben Sie unter*Beispiel* die folgende Bewertung ein:
    
    ```
    Disappointing Stay at The City Hotel
    The City Hotel, London
    9/5/2018
    My experience at The City Hotel in London was far from pleasant. The constant noise from nearby train tracks made it nearly impossible to sleep, with vibrations felt throughout the building. The rooms were outdated, dusty, and poorly maintained—dripping faucets, squeaky beds, and broken fixtures were just the beginning. Sound insulation was nonexistent, so every conversation from neighboring rooms was clearly audible. While the location near public transport was convenient and the staff were friendly, these positives couldn't make up for the overall discomfort and lack of value. I wouldn’t recommend this hotel to anyone seeking a restful or enjoyable stay.
    ```

1. Klicken Sie auf**Ausführen**. Überprüfen Sie die Ausgabe.

    ![Screenshot: Benutzeroberfläche „Stimmungsanalyse“ im Language-Playground](./media/sentiment-analysis.png)

    Beachten Sie, dass die Analyse eine Gesamtstimmungsbewertung und einzelne Bewertungen für jeden Satz generiert.

## Erkennen der Sprache und Übersetzen von Text

Azure KI Language ermöglicht es Ihnen, die Sprache zu erkennen, in der ein Text verfasst ist. Darüber hinaus können Sie mit Azure KI Übersetzer Texte ganz einfach von einer Sprache in eine andere übersetzen.

### Sprache erkennen

Beginnen wir damit, die Sprache zu erkennen, in der eine Bewertung geschrieben ist.

1. Wählen Sie im Bereich**Text klassifizieren** die Kachel**Sprache erkennen** aus.

1. Geben Sie unter*Beispiel* die folgende Bewertung ein:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Klicken Sie auf**Ausführen**. Überprüfen Sie die Ausgabe.

    ![Screenshot: Benutzeroberfläche „Sprache erkennen“ im Language-Playground](./media/detect-language.png)

    Beachten Sie, dass die Sprache als Französisch erkannt wird. 

### Text übersetzen

Jetzt übersetzen wir die französische Bewertung ins Englische.

1. Verwenden Sie oben auf der Seite den Link**&larr;** (Zurück) neben dem Seitentitel**Language-Playground**, um alle verfügbaren Playgrounds anzuzeigen.
1. Öffnen Sie in der Liste der Playgrounds den**Übersetzer-Playground**.
1. Wählen Sie im Übersetzer-Playground die Option**Textübersetzung** aus.
1. Wählen Sie im Bereich**Konfigurieren** die folgenden Sprachoptionen aus:
    - **Übersetzen von**: Französisch
    - **Übersetzen in**: Englisch
1. Geben Sie unter*Beispiel* die französischsprachige Bewertung ein:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Wählen Sie**Übersetzen** aus. Überprüfen Sie die Ausgabe.

    ![Screenshot: Benutzeroberfläche „Textübersetzung“ im Übersetzer-Playground](./media/text-translation.png)

    Die französische Bewertung wird ins Englische übersetzt.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das**Azure-Portal** unter[https://portal.azure.com](https://portal.azure.com), und wählen Sie die Ressourcengruppe aus, die die von Ihnen erstellten Ressourcen enthält.
1. Wählen Sie**Ressourcengruppe löschen** aus, und**geben Sie zur Bestätigung den Namen der Ressourcengruppe ein**. Die Ressourcengruppe wird dann gelöscht.

## Weitere Informationen

Weitere Informationen über die Möglichkeiten dieses Diensts erfahren Sie auf der[Sprachdienst-Seite](https://learn.microsoft.com/azure/ai-services/language-service/overview).
