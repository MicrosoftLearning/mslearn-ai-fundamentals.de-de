---
lab:
  title: Analysieren von Text mit Language Studio
---

# Analysieren von Text mit Language Studio

In dieser Übung erkunden Sie die Funktionen von Azure KI Language, indem Sie einige Beispiele für Hotelbewertungen analysieren. Sie verwenden Language Studio, um zu verstehen, ob die Bewertungen vorwiegend positiv oder negativ sind.

Die Verarbeitung natürlicher Sprache (Natural Language Processing oder NLP) befasst sich mit geschriebener und gesprochener Sprache. Sie können mit NLP Lösungen erstellen, die eine semantische Bedeutung aus Text oder Sprache extrahieren oder aussagekräftige Antworten in natürlicher Sprache formulieren.

Angenommen, das fiktive Reisebüro Margie's Travel bittet seine Kunden, Bewertungen für Hotelaufenthalte zu schreiben. Sie können den Sprachdienst nutzen, um Schlüsselsätze zu identifizieren, um festzustellen, welche Bewertungen positiv und welche negativ sind, oder um den Bewertungstext auf die Erwähnung bekannter Entitäten wie Orte oder Personen zu analysieren.

Azure KI Language Service umfasst Textanalyse- und NLP-Funktionen. Dazu gehören die Identifizierung von Schlüsselausdrücken im Text und die Klassifizierung von Texten auf der Grundlage von Stimmungen.

## Erstellen einer *Language*-Ressource

Sie können viele Azure KI Language-Features entweder mit einer **Sprach-** oder **Azure KI Services**-Ressource verwenden. Es gibt einige Instanzen, in denen nur eine Sprachressource verwendet werden kann. Für die nachstehende Übung verwenden wir eine **Sprachressource**. Falls noch nicht erfolgt, erstellen Sie in Ihrem Azure-Abonnement eine **Language**-Ressource.

1. Öffnen Sie auf einer anderen Browserregisterkarte das Azure-Portal auf [https://portal.azure.com](https://portal.azure.com?azure-portal=true), und melden Sie sich mit dem Microsoft-Konto an, das Ihrem Azure-Abonnement zugeordnet ist.

1. Klicken Sie auf die Schaltfläche **&#65291;Ressource erstellen** und suchen Sie nach *Sprachdienst*. Wählen Sie **Erstellen** eines **Sprachdienst**-Plans. Sie werden zu einer Seite umgeleitet, um **Weitere Features auszuwählen**. Behalten Sie die Standardauswahl bei, und klicken Sie auf **Weiter, um Ihre Ressource zu erstellen**. 

1. Konfigurieren Sie sie auf der Seite **Sprache erstellen** mit den folgenden Einstellungen:
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine Ressourcengruppe mit einem eindeutigen Namen*.
    - **Region:** USA, Osten.
    - **Name**: *Geben Sie einen eindeutigen Namen ein*.
    - **Tarif**: *Free F0 oder S, wenn Free F0 nicht verfügbar ist*
    - **Durch Aktivieren dieses Kontrollkästchens bestätige ich, dass ich die folgenden Bedingungen gelesen und verstanden habe**: *Ausgewählt*.

1. Wählen Sie die Option **Überprüfen und erstellen** und dann **Erstellen** aus, und warten Sie, bis die Bereitstellung abgeschlossen ist.

## Konfigurieren Ihrer Ressource in Azure KI Language Studio

1. Öffnen Sie auf einer anderen Browserregisterkarte **Language Studio** auf [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true), und melden Sie sich an.

1. Wenn die Aufforderung **Wählen Sie eine Azure-Ressource aus** angezeigt wird, nehmen Sie die folgenden Konfigurationen vor:
    - **Azure-Verzeichnis**: *Standardverzeichnis, das Verzeichnis, das Sie verwenden*
    - **Azure-Abonnement:** *Wählen Sie das von Ihnen verwendete Abonnement aus*
    - **Ressourcentyp**: Language
    - **Ressourcenname**: *Wählen Sie die soeben erstellte Sprachdienstressource aus*

Wählen Sie dann **Fertig** aus.

> **Wichtig:** Ab Juli 2023 umfassen Azure KI Services alle bisher als Cognitive Services und Azure Applied AI Services bezeichneten Dienste. In einigen Benutzeroberflächen wird der Verweis noch von `Cognitive Services` auf `Azure AI services` aktualisiert. Die beiden Namen beziehen sich auf den gleichen Ressourcentyp.

> **Hinweis:** Sollten Sie ***nicht*** zur Auswahl einer Sprachressource aufgefordert werden, kann dies daran liegen, dass Ihr Abonnement mehrere Sprachressourcen enthält. Gehen Sie in diesem Fall folgendermaßen vor:
> 1. Wählen Sie auf der Leiste am oberen Seitenrand die Schaltfläche **Einstellungen (&#9881;)** aus. 
> 1. Gehen Sie auf der Seite **Einstellungen** zur Registerkarte **Ressourcen**.
> 1. Wählen Sie die soeben erstellte Ressource aus, und wählen Sie **Ressource wechseln** aus. Stellen Sie sicher, dass „Verwaltete Identität“ **Aktiviert** ist.
> ![Aktivieren Sie die Sprachressource.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. Wählen Sie oben auf der Seite **Language Studio** aus, um zur Startseite von Language Studio zurückzukehren.

## Analysieren von Bewertungen in Language Studio

1. Navigieren Sie in einem Webbrowser zu **Language Studio** auf [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true).

1. Wählen Sie auf der Startseite **Willkommen bei Language Studio** die Registerkarte **Text klassifizieren** aus, und wählen Sie dann die Kachel **Stimmung analysieren und Meinungen ermitteln** aus.

1. Wählen Sie unter *Textsprache auswählen* die Sprache **Englisch** aus.

1. Wählen Sie unter *Wählen Sie Ihre Azure-Ressource* Ihre Ressource aus.

1. Kopieren Sie die folgende Bewertung, und fügen Sie diese unter *Geben Sie Ihren eigenen Text ein, laden Sie eine Datei hoch, oder verwenden Sie einen unserer Beispieltexte* ein:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Aktivieren Sie das Kontrollkästchen, um zu bestätigen, dass die Demo Verbrauch und Kosten verursachen kann, und wählen Sie dann **Ausführen** aus.

1. Überprüfen Sie die Ausgabe. Beachten Sie, dass das *Dokument* sowie jeder *Satz* auf die Stimmung hin analysiert wird. Wählen Sie **Satz 1** aus, um die Stimmungsanalyse für diesen Satz anzuzeigen. 

Beachten Sie, dass eine allgemeine Stimmung gefolgt von Bewertungen neben den drei Kategorien *positive Bewertung*, *neutrale Bewertung* und *negative Bewertung* angezeigt wird. In jeder der Kategorien wird eine Bewertung zwischen 0 und 1 bereitgestellt. Diese Konfidenzwerte geben an, wie wahrscheinlich es ist, dass der angegebene Text eine bestimmte Stimmung ausdrückt. 

Wählen Sie erneut **Satz 1** aus, um ihn zu schließen.

1. Scrollen Sie nach oben, um **Textfeld löschen**auszuwählen, kopieren Sie die folgende Bewertung, und fügen Sie sie ein:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. Klicken Sie auf **Run** (Ausführen). Überprüfen Sie die Ausgabe, und überprüfen Sie die Stimmung und das Konfidenzebene.

1. Wählen Sie erneut **Textfeld löschen**aus, kopieren Sie die folgende Bewertung, und fügen Sie sie ein:

    >Sehr laut und die Zimmer sind winzig The Lombard Hotel, San Francisco, USA 5.9.2018 Das Hotel befindet sich in der Lombard Street, einer sehr belebten sechsspurigen Straße direkt an der Golden Gate Bridge. Verkehr vom frühen Morgen bis spät in die Nacht, vor allem an Wochenenden. Der Lärm wäre nicht so schlimm, wenn die Zimmer besser isoliert wären, aber das sind sie nicht. Ich musste mir Watte in die Ohren stecken, um schlafen zu können – ich war zu müde, um die Stadt am nächsten Tag zu genießen. Die Zimmer sind WINZIG. Ich wählte das Zimmer, weil es zwei Doppelbetten hatte – aber das Zimmer hatte kaum Platz für sie. Mit einer vierköpfigen Familie im Zimmer war es eng. Trotzdem sind die Zimmer sauber und man hat sich bemüht, sie zu modernisieren. Das Hotel liegt im Yachthafenviertel mit vielen guten Restaurants und in Gehweite zum Presidio. Kann ein gutes Hotel für junge Erwachsene mit kleinem Budget sein.

1. Wählen Sie **Ausführen** aus, und überprüfen Sie die Stimmung sowie die Konfidenzebene. Sehen Sie sich den Text an, und vergleichen Sie den Text mit der Stimmungsanalyse, die der Dienst zurückgegeben hat.

In dieser Übung haben Sie Language Studio verwendet, um entweder eine neue Sprachressource zu erstellen oder eine vorhandene Sprachressource zu verwenden. Sie haben die Ressource in „Einstellungen“ aktiviert, bevor Sie den Stimmungs- und Opinion Mining-Dienst ausprobieren. Anschließend haben Sie den Dienst mit Texten getestet.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das **Azure-Portal** auf [https://portal.azure.com](https://portal.azure.com), und wählen Sie die Ressourcengruppe aus, die die von Ihnen erstellte Ressource enthält.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

Weitere Informationen über die Möglichkeiten dieses Diensts erfahren Sie auf der [Sprachdienst-Seite](https://learn.microsoft.com/azure/ai-services/language-service/overview).
