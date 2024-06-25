---
lab:
  title: Erkunden von Azure OpenAI Service
---

# Erkunden von Azure OpenAI

Azure OpenAI Service bringt die von OpenAI entwickelten generativen KI-Modelle auf die Azure-Plattform und ermöglicht Ihnen die Entwicklung leistungsstarker KI-Lösungen, die von der Sicherheit, Skalierbarkeit und Integration anderer Dienste der Azure-Cloudplattform profitieren.

In dieser Übung erkunden Sie Azure OpenAI Service und verwenden es, um generative KI-Modelle bereitzustellen und damit zu experimentieren.

Diese Übung dauert ungefähr **25** Minuten.

## Vorbereitung

Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service sowohl für Text- und Codemodelle als auch für DALL-E Bilderzeugungsmodelle freigegeben wurde.

- Besuchen Sie [https://azure.microsoft.com/free](https://azure.microsoft.com/free), um sich für ein kostenloses Azure-Abonnement zu registrieren.
- Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Bereitstellen einer Azure OpenAI-Ressource

Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement:** *Ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service freigegeben wurde.*
    - **Ressourcengruppe:** *Wählen Sie entweder eine bereits vorhandene Ressourcengruppe, oder erstellen Sie eine mit einem Namen Ihrer Wahl.*
    - **Region:** USA, Osten\*
    - **Name:** *Wählen Sie einen Namen Ihrer Wahl aus.*
    - **Tarif**: Standard S0.

    > \* Unterschiedliche Regionen weisen unterschiedliche Verfügbarkeiten und Kontingente für Modelle auf. In dieser Übung verwenden Sie ein GPT-35-Turbo-Modell für die Textgenerierung und ein DALL-E-Modell für die Bildgenerierung, die beide in „USA, Osten“ unterstützt werden.

3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Erkunden von Azure OpenAI Studio

Sie können Modelle in Ihrem Azure OpenAI Service mithilfe von Azure OpenAI Studio bereitstellen, verwalten und erkunden.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressourcen die Schaltfläche **Erkunden**, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu [Azure OpenAI Studio](https://oai.azure.com/) navigieren.

    Wenn Sie Azure OpenAI Studio zum ersten Mal öffnen, sollte es wie folgt aussehen:

    ![Screenshot von Azure OpenAI Studio.](./media/generative-ai/ai-studio.png)

1. Sehen Sie sich die verfügbaren Seiten im linken Bereich an. Sie können jederzeit oben auf die Startseite zurückkehren. Außerdem bietet OpenAI Studio mehrere Seiten, auf denen Sie folgendes tun können:
    - Experimentieren Sie mit Modellen in einem *Playground*.
    - Verwalten Sie Modellimplementierungen und Daten.

## Bereitstellen eines Modells für die Sprachgenerierung

Um mit der Generierung natürlicher Sprachen zu experimentieren, müssen Sie zuerst ein Modell bereitstellen.

1. Sehen Sie sich auf der Seite **Modelle** die verfügbaren Modelle in Ihrer Azure OpenAI Service-Instanz an.
1. Wählen Sie eines der **gpt-35-turbo**-Modelle aus, für die der Status **Bereitstellbar** **Ja** ist, und wählen Sie dann **Bereitstellen** aus:

    ![Screenshot der Seite „Modelle“ in Azure KI Studio.](./media/generative-ai/deploy-model.png)

1. Erstellen Sie eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname:** *Ein eindeutiger Name für die Modellimplementierung*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Bereitstellungstyp**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Verwenden des *Chat*-Playgrounds zum Arbeiten mit dem Modell

Nachdem Sie nun ein Modell bereitgestellt haben, können Sie es im *Chat*-Playground verwenden, um Ausgaben in natürlicher Sprache aus Prompts zu generieren, die Sie in einer Chat-Oberfläche übermitteln.

1. Navigieren Sie in [Azure OpenAI Studio](https://oai.azure.com/) im linken Bereich zum Playground **Chat**.

    Der *Chat*-Playground bietet eine Chatbot-Schnittstelle, mit der Sie mit Ihrem bereitgestellten Modell interagieren können, wie im Folgenden gezeigt:

    ![Screenshot des Chat-Playgrounds in Azure OpenAI Studio.](./media/generative-ai/chat-playground.png)

1. Stellen Sie im Bereich **Konfiguration** sicher, dass die Modellimplementierung ausgewählt ist.
1. Wählen Sie im Bereich **Assistenteneinrichtung** die Systemmeldungsvorlage **Standard** aus, und sehen Sie sich die Systemmeldung an, die diese Vorlage erstellt. Die Systemmeldung legt fest, wie sich das Modell in Ihrer Chatsitzung verhält.
1. Geben Sie im Abschnitt **Chatsitzung** die folgende Benutzernachricht ein.

    ```
   What is generative AI?
    ```

1. Beobachten Sie die vom Modell zurückgegebene Ausgabe, die eine Definition der generativen KI bereitstellen sollte.
1. Geben Sie die folgende Benutzernachricht als Folgefrage ein:

    ```
   What are three benefits it provides?
    ```

1. Sehen Sie sich die Ausgabe an. Sie werden feststellen, dass die Chat-Sitzung die vorherige Eingabe und die vorherige Antwort berücksichtigt hat, um den Kontext zu erfassen (d.h. sie interpretiert „es“ korrekt als „generative KI“) und dass sie eine passende Antwort auf der Grundlage der Anforderungen liefert (sie sollte drei Vorteile der generativen KI zurückgeben).

## Verwenden des *DALL-E*-Playground zum Generieren von Bildern

Neben Language Generation-Modellen unterstützt Azure OpenAI Service das DALL-E 2-Modell für die Bildgenerierung.

> **Hinweis:** Sie müssen den Zugriff auf die DALL-E-Funktionalität in Ihrem Azure OpenAI Service-Zugangsantrag beantragt und erhalten haben, um diesen Abschnitt der Übung zu bearbeiten.

1. Navigieren Sie in [Azure OpenAI Studio](https://oai.azure.com/) im linken Bereich zum **DALL-E**-Playground.
1. Geben Sie den folgenden Prompt ein:

    ```
    A robot eating spaghetti
    ```

1. Wählen Sie **Generieren** aus und sehen Sie sich die Ergebnisse an. Diese sollten ein Bild enthalten, das auf der Beschreibung basiert, die Sie im Prompt eingegeben haben, ähnlich wie dieses:

    ![Screenshot des DALL-E-Playgrounds in Azure OpenAI Studio.](./media/generative-ai/dall-e-playground.png)

1. Generieren Sie ein zweites Bild, indem Sie den Prompt wie folgt ändern:

    ```
    A robot eating spaghetti in the style of Rembrandt
    ```
1. Stellen Sie sicher, dass das neue Bild den Anforderungen des Prompt entspricht, ähnlich wie dieses:

    ![Screenshot der von DALL-E generierten Bilder in Azure OpenAI Studio.](./media/generative-ai/dall-e-results.png)

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im [Azure-Portal](https://portal.azure.com/?azure-portal=true) zu löschen.
