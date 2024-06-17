---
lab:
  title: Erkunden von Copilot in Microsoft Edge
---
# Erkunden von Microsoft Copilot in Microsoft Edge

In dieser Übung erfahren Sie, wie Microsoft Copilot generative KI verwenden kann, damit Sie beim Erstellen neuer Inhalte noch produktiver sein können. Im Szenario für diese Übung beginnen Sie mit einigen allgemeinen Hinweisen für eine Geschäftsidee und verwenden Copilot in Microsoft Edge, um Unterstützung bei der Entwicklung eines Geschäftsplans und einer Präsentation für potenzielle Investoren zu erhalten.

Diese Übung dauert ca. **40** Minuten.

> **Hinweis:** Bei dieser Übung wird davon ausgegangen, dass Sie über ein [persönliches Microsoft-Konto](https://signup.live.com) (z. B. ein Konto vom Typ „outlook.com“) verfügen, mit dem Sie auf Ihrem Computer bei [Microsoft Edge](https://www.microsoft.com/edge/download) angemeldet sind.

## Verwenden von Copilot, um ein Dokument zu erkunden und für eine Idee zu recherchieren

Wenn Sie mit der Erkundung von generativer KI beginnen möchten, verwenden Sie Microsoft Copilot in Edge, um ein vorhandenes Dokument zu untersuchen und einige Erkenntnisse daraus zu extrahieren.

1. Navigieren Sie in Microsoft Edge zu [OneDrive](https://onedrive.live.com) unter `https://onedrive.live.com`, und melden Sie sich mit Ihrem persönlichen Microsoft-Konto an. Schließen Sie alle Begrüßungsnachrichten oder Angebote, die angezeigt werden.
1. Öffnen Sie auf einer anderen Browserregisterkarte das Dokument [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) von `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`. Wenn das Dokument in Edge geöffnet wird, wählen Sie die Option **Eine Kopie auf OneDrive speichern** aus, und speichern Sie das Dokument im Ordner **Dokumente** auf OneDrive. Das Dokument sollte dann automatisch in Microsoft Word Online geöffnet werden.

    > **Tipp**: Wenn die Option zum Speichern einer Kopie der Datei auf OneDrive nicht angezeigt wird, laden Sie sie auf Ihren lokalen Computer herunter. Öffnen Sie dann in OneDrive den Ordner **Dokumente**, und verwenden Sie die Schaltfläche **+ Neu hinzufügen**, um die Datei **Business Idea.docx** von Ihrem lokalen Computer auf OneDrive hochzuladen.

1. Zeigen Sie den Text in **Business Idea.docx** an, der einige allgemeine Ideen für eine Reinigungsfirma in New York City beschreibt.
1. Verwenden Sie das Symbol **Copilot** auf der Edge-Symbolleiste, um den Copilot-Bereich zu öffnen, wie hier gezeigt:

    ![Screenshot: Bereich „Copilot“ in Microsoft Edge](./media/generative-ai/edge-copilot.png)

1. Scrollen Sie im Bereich „Copilot“ nach unten, um bei Bedarf alle Inhalte anzuzeigen. Stellen Sie sicher, dass die Registerkarte **Chat** ausgewählt ist und dass der Unterhaltungsstil auf **Ausgewogener** festgelegt ist. Dadurch wird sichergestellt, dass Copilot mit einem ausgewogenen Maß an Kreativität und sachlicher Präzision reagiert.
1. Geben Sie im Bereich „Copilot“ im Chatfeld unten den folgenden Prompt ein:

    ```
    What is this document about?
    ```

    Bestätigen Sie bei entsprechender Aufforderung, dass Sie Copilot den Zugriff auf die Seite gestatten möchten.

1. Überprüfen Sie die Antwort von Copilot, die die wichtigsten Punkte im Dokument zusammenfassen sollte, wie hier gezeigt:

    ![Screenshot: Bereich „Copilot“ mit einer Antwort](./media/generative-ai/copilot-response.png)

    > **Hinweis:** Die spezifische Antwort kann variieren.

1. Geben Sie den folgenden Prompt ein:

    ```
    How do I go about setting up a business in New York?
    ```

1. Überprüfen Sie die Antwort. Sie sollte einige Ratschläge und Links zu Ressourcen, die Ihnen bei der Gründung eines Unternehmens in New York helfen, und möglicherweise einige vorgeschlagene Folgeprompts zum Abrufen weiterer Informationen enthalten.

    > **Wichtig:** Die KI-generierte Antwort basiert auf öffentlichen Informationen aus dem Web. Sie kann Ihnen zwar helfen, die für eine Unternehmensgründung erforderlichen Schritte zu verstehen, es ist aber nicht garantiert, dass sie zu 100 % korrekt ist, und sie ersetzt nicht die Notwendigkeit einer professionellen Beratung!

## Verwenden von Copilot zum Erstellen von Inhalten für einen Geschäftsplan

Sie haben eine erste Recherche durchgeführt. Nun hilft Copilot Ihnen beim Entwickeln eines Geschäftsplans für Ihre Reinigungsfirma.

1. Das Dokument **Business Idea.docx** ist noch in Microsoft Edge geöffnet. Geben Sie im Bereich „Copilot“ den folgenden Prompt ein:

    ```
    Suggest a name for my cleaning business
    ```

1. Überprüfen Sie die Vorschläge, und wählen Sie einen Namen für Ihre Reinigungsfirma aus (oder geben Sie weitere Prompts ein, um einen Namen zu finden, der Ihnen gefällt).
1. Geben Sie den folgenden Prompt ein, und ersetzen Sie *Contoso Cleaning* durch den Firmennamen Ihrer Wahl:

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

1. Überprüfen Sie die Antwort, und verwenden Sie unterhalb der Ausgabe das Symbol **Kopieren** (&#128461;), um sie in die Zwischenablage zu kopieren. Markieren Sie dann den gesamten Text im Dokument **Business Ideas.docx**, und fügen Sie den kopierten Text in das Dokument ein, um ihn zu ersetzen. Bereinigen Sie schließlich den eingefügten Text, indem Sie den ursprünglichen Text in der Antwort (in der Copilot die Anweisung bestätigt hat) durch eine Überschrift mit dem Namen Ihrer Reinigungsfirma ersetzen. Sie sollten ein Dokument mit einem Geschäftsplan erhalten, ähnlich wie hier gezeigt:

    ![Screenshot: Word-Dokument mit einem von Copilot generierten Geschäftsplan](./media/generative-ai/generated-content.png)

1. Geben Sie im Copilot-Bereich den folgenden Prompt ein:

    ```
    Create a corporate logo for the cleaning company. The logo should be round and include an iconic New York landmark.
    ```

1. Überprüfen Sie die Antwort, die vier Optionen für ein von Microsoft Designer erstelltes Logo darstellen sollte.
1. Verwenden Sie weitere Prompts, um das Design zu durchlaufen (z. B. `Make it green and blue`), bis Sie über ein Logo verfügen, mit dem Sie zufrieden sind.
1. Klicken Sie mit der rechten Maustaste auf das gewünschte Logodesign, und kopieren Sie es in die Zwischenablage. Fügen Sie es dann wie folgt oben im Dokument für den Geschäftsplan ein:

    ![Screenshot: Word-Dokument mit einem von Copilot generierten Bild](./media/generative-ai/generated-image.png)

1. Schließen Sie die Microsoft Word-Registerkarte, und kehren Sie zum Ordner **Dokumente** auf Ihrem OneDrive zurück.

## Verwenden von Copilot zum Erstellen von Inhalten für eine Präsentation

Mit der Hilfe von Copilot haben Sie einen Entwurf eines Geschäftsplans für die Idee einer Reinigungsfirma erstellt. Nun benötigen Sie eine wirkungsvolle Präsentation, um einen Investor davon zu überzeugen, Ihnen die finanziellen Mittel für die Gründung Ihres Unternehmens zu leihen.

1. Fügen Sie im Ordner **Dokumente** auf OneDrive eine neue **PowerPoint-Präsentation** hinzu.

    Wenn der Bereich **Designer** automatisch geöffnet wird, schließen Sie ihn.

1. Geben Sie auf der Titelfolie für die Präsentation den Namen Ihrer Reinigungsfirma als Titel und `Investor Opportunity` als Untertitel ein.
1. Fügen Sie eine neue Folie hinzu, indem Sie das Folienlayout **Zwei Inhalte** verwenden. (Es enthält einen Titel und zwei Platzhalter für Inhalte.)
1. Ändern Sie den Folientitel in `Benefits of Hiring a Commercial Cleaner`.
1. Geben Sie im Copilot-Bereich den folgenden Prompt ein:

    ```
    Write a summary of the benefits of using a corporate cleaning company for your business. The summary should consist of five short bullet points.
    ```

1. Kopieren Sie die Antwort von Copilot in die Zwischenablage, und fügen Sie sie in den linken Inhaltsplatzhalter ein. Löschen Sie dann den ersten Satz, der die Anforderung bestätigt, und formatieren Sie den Text im Platzhalter neu, bis Sie zufrieden sind.
1. Geben Sie im Copilot-Bereich den folgenden Prompt ein:

    ```
    Create a photorealistic image of a clean office.
    ```

1. Wenn Copilot ein Bild generiert hat, das Ihnen gefällt, kopieren Sie es in die Zwischenablage, und fügen Sie es in den Inhaltsplatzhalter rechts auf der Folie ein.

    Wenn der Bereich **Designer** automatisch geöffnet wird, wählen Sie ein Foliendesign aus, das Ihnen gefällt. Schließen Sie dann den Bereich **Designer**.

1. Wenden Sie alle weiteren Neuformatierungen an, die Ihrer Meinung nach erforderlich sind, bis Sie etwa eine Folie wie die folgende haben:

    ![Screenshot: PowerPoint-Präsentation mit von Copilot generierten Inhalten](./media/generative-ai/powerpoint-slide.png)

1. Wählen Sie auf der PowerPoint-Titelleiste den Standardpräsentationsnamen (**Präsentation**) aus, und benennen Sie ihn in `Business Presentation.pptx` um.
1. Schließen Sie die PowerPoint-Registerkarte, und kehren Sie zum Ordner **Dokumente** auf Ihrem OneDrive zurück.

## Verwenden von Copilot zum Verfassen einer E-Mail

Sie haben einige Begleitmaterialien erstellt, die Ihnen bei den ersten Schritten mit Ihrem Unternehmen helfen sollen. Jetzt ist es an der Zeit, einen Investor zu finden, um eine Startfinanzierung zu erhalten.

1. Verwenden Sie das **App-Startfeld** am linken Ende der OneDrive-Titelleiste, um **Outlook** zu öffnen.
1. Erstellen Sie eine neue E-Mail, und geben Sie in das Feld **An** Ihre eigene E-Mail-Adresse ein.
1. Wählen Sie im Bereich „Copilot“ die Registerkarte **Verfassen** aus. Legen Sie dann die folgenden Optionen fest, um neue Inhalte zu verfassen:
    - **Schreiben über**: `Request a meeting with an investment bank to discuss funding for a commercial cleaning business.`
    - **Ton**: Professionell
    - **Format**: E-Mail
    - **Länge**: Mittel
1. Wählen Sie **Entwurf generieren** aus, und überprüfen Sie die generierte Ausgabe.
1. Verwenden Sie den generierten Inhalt, um Ihre E-Mails zu vervollständigen, wie hier gezeigt:

    ![Screenshot: Eine von Copilot generierte E-Mail](./media/generative-ai/generated-email.png)

    Sie können die E-Mail an sich selbst senden, wenn Sie möchten.

## Herausforderung

Sie haben nun gesehen, wie Sie Copilot verwenden, um Ideen zu recherchieren und Inhalte zu generieren. Möchten Sie noch mehr entdecken? Wählen Sie zum Starten einer neuen Copilot-Sitzung auf der Registerkarte **Chat** das Symbol **Neues Thema** neben dem Feld „Prompt“ aus, und nutzen Sie Copilot, um eine Veranstaltung zur Förderung der Lesekompetenz von Kindern in einer örtlichen Bibliothek zu planen. Sie können beispielsweise Folgendes ausprobieren:

- Tipps recherchieren, wie Kinder schon früh zum Lesen angeregt werden können
- Einen Flyer oder ein Poster für die Veranstaltung erstellen
- Eine E-Mail für eine Kampagne verfassen, um lokale Kinderautoren einzuladen, auf der Veranstaltung zu sprechen
- Eine Präsentation zur Eröffnung der Veranstaltung erstellen

Sie können so erfinderisch sein, wie Sie möchten. Entdecken Sie, wie Copilot Ihnen bei der Suche nach Informationen, der Erstellung und Optimierung von Texten, bei der Erstellung von Bildern sowie bei der Beantwortung von Fragen helfen kann.


## Zusammenfassung

In dieser Übung haben Sie Copilot in Microsoft Edge verwendet, um Informationen zu suchen und Inhalte zu generieren. Sie haben hoffentlich gesehen, wie die Verwendung von generativer KI in einem Copilot die Produktivität und Kreativität steigern kann.

Während die in diesen Übungen verwendeten kostenlosen Dienste zweifellos sehr leistungsfähig sind, können Sie mit Diensten wie [Copilot für Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365)noch mehr erreichen, da Microsoft Copilot in Windows- und Microsoft Office-Produktivitätsanwendungen integriert ist und stark kontextualisierte Hilfe bei allgemeinen Aufgaben bietet. Mit Microsoft 365 können Sie die Leistungsfähigkeit von generativer KI auf Ihre Geschäftsdaten und -prozesse übertragen und gleichzeitig in Ihre vorhandene IT-Infrastruktur integrieren, um eine verwaltbare, sichere Lösung zu gewährleisten.