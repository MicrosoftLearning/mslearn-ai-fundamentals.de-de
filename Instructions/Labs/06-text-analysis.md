---
lab:
  title: Analysieren von Text im Azure AI Foundry-Portal
---

# Analysieren von Text im Azure AI Foundry-Portal

Die Verarbeitung natürlicher Sprache (Natural Language Processing oder NLP) befasst sich mit geschriebener und gesprochener Sprache. Sie können mit NLP Lösungen erstellen, die eine semantische Bedeutung aus Text oder Sprache extrahieren oder aussagekräftige Antworten in natürlicher Sprache formulieren.

Der Azure AI Language-Dienst umfasst Textanalyse mit Funktionen wie Entitätserkennung, Schlüsselbegriffserkennung, Zusammenfassung und Stimmungsanalyse. Angenommen, das fiktive Reisebüro Margie's Travel bittet seine Kunden, Bewertungen für Hotelaufenthalte zu schreiben. Sie können den Sprachdienst verwenden, um benannte Entitäten zu extrahieren, Schlüsselausdrücke zu identifizieren, Text zusammenzufassen und vieles mehr.

In dieser Übung verwenden Sie Azure AI Language im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen, um Hotelbewertungen zu analysieren. 

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

1. Wählen Sie auf der Seite *Playgrounds* die Kachel **Speech-Playground**, um einige Azure KI Language-Funktionen auszuprobieren.

## Extrahieren benannter Entitäten mit Azure AI Language im Azure AI Foundry-Portal

*Benannte Entitäten* sind Wörter, die Personen, Orte und Objekte mit Eigennamen beschreiben. Verwenden wir die Funktion zur Extraktion benannter Entitäten von Azure AI Language, um die verschiedenen Arten von Informationen in einer Bewertung zu identifizieren.

1. Wählen Sie im Speech-Playground **Informationen extrahieren** aus. Wählen Sie dann die Kachel **Benannte Entitäten extrahieren** aus. 

1. Kopieren Sie unter *Beispiel* die folgende Bewertung, und fügen Sie sie ein:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Klicken Sie auf **Ausführen**. Überprüfen Sie die Ausgabe. Beachten Sie im Abschnitt *Details*, dass die extrahierten Entitäten mit zusätzlichen Informationen wie Typ und Konfidenzwerten versehen sind. Die Konfidenzbewertung stellt die Wahrscheinlichkeit dar, dass der identifizierte Typ tatsächlich zu dieser Kategorie gehört.

## Extrahieren von Schlüsselausdrücken mit Azure AI Language im Azure AI Foundry-Portal

*Schlüsselbegriffe* sind die wichtigsten Informationen im Text. Verwenden wir die Schlüsselbegriffserkennungs-Funktion von Azure AI Language, um wichtige Informationen aus einer Bewertung abzurufen.

1. Wählen Sie im Speech-Playground **Informationen extrahieren** aus. Wählen Sie dann die Kachel **Schlüsselbegriffe extrahieren** aus. 

1. Kopieren Sie unter *Beispiel* die folgende Bewertung, und fügen Sie sie ein:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Klicken Sie auf **Ausführen**. Überprüfen Sie die Ausgabe. Beachten Sie die verschiedenen Ausdrücke, die im Abschnitt *Details* extrahiert wurden. Diese Ausdrücke sollten am meisten zur Bedeutung des Texts beitragen.

## Zusammenfassen von Text mit Azure AI Language im Azure AI Foundry-Portal
 
1. Sehen wir uns die Zusammenfassungsfunktionen von Azure AI Language an. Wählen Sie im Speech-Playground die Option *Informationen zusammenfassen* und wählen Sie dann die Kachel **Text zusammenfassen**.

1. Kopieren Sie unter *Beispiel* die folgende Bewertung, und fügen Sie sie ein:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Klicken Sie auf **Ausführen**. Überprüfen Sie die Ausgabe. Beachten Sie, dass die *Extraktive Zusammenfassung* unter *Details* Rangbewertungen für die wichtigsten Sätze liefert.   

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das **Azure-Portal** unter [https://portal.azure.com](https://portal.azure.com), und wählen Sie die Ressourcengruppe aus, die die von Ihnen erstellten Ressourcen enthält.

1. Wählen Sie die Ressourcen, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressourcen werden dann gelöscht.

## Weitere Informationen

Weitere Informationen über die Möglichkeiten dieses Diensts erfahren Sie auf der [Sprachdienst-Seite](https://learn.microsoft.com/azure/ai-services/language-service/overview).
