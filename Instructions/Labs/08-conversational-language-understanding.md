---
lab:
  title: Verwenden von Conversational Language Understanding mit Language Studio
---

# Verwenden von Conversational Language Understanding mit Language Studio

Wir erwarten immer häufiger, dass Computer KI einsetzen können, um gesprochene oder eingegebene Befehle in natürlicher Sprache zu verstehen. Sie können z. B. ein Heimautomatisierungssystem verwenden, um Geräte in Ihrem Zuhause mithilfe von Sprachbefehlen wie „Licht einzuschalten“ oder „Lüfter einschalten“ zu steuern. KI-fähige Geräte können diese Befehle verstehen und entsprechende Aktionen durchführen.

In dieser Übung verwenden Sie Language Studio, um ein Projekt zu erstellen und zu testen, das Anweisungen an Geräte wie Lampen oder Lüfter sendet. Sie werden die Funktionen des Conversational Language Understanding-Diensts verwenden, um Ihr Projekt zu konfigurieren. 

## Erstellen einer *Language*-Ressource

Sie können viele Azure KI Language-Features entweder mit einer **Sprach-** oder **Azure KI Services**-Ressource verwenden. Es gibt einige Instanzen, in denen nur eine Sprachressource verwendet werden kann. Für die nachstehende Übung verwenden wir eine **Sprachressource**. Falls noch nicht erfolgt, erstellen Sie in Ihrem Azure-Abonnement eine **Language**-Ressource.

1. Öffnen Sie auf einer anderen Browserregisterkarte das Azure-Portal auf [https://portal.azure.com](https://portal.azure.com?azure-portal=true), und melden Sie sich mit dem Microsoft-Konto an, das Ihrem Azure-Abonnement zugeordnet ist.

1. Klicken Sie auf die Schaltfläche **&#65291;Ressource erstellen** und suchen Sie nach *Sprachdienst*. Wählen Sie **Erstellen** eines **Sprachdienst**-Plans. Sie werden zu einer Seite umgeleitet, um *Weitere Features auszuwählen**. Behalten Sie die Standardauswahl bei und klicken Sie auf **Weiter, um Ihre Ressource zu erstellen**. 

1. Konfigurieren Sie sie auf der Seite **Sprache erstellen** mit den folgenden Einstellungen:
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine Ressourcengruppe mit einem eindeutigen Namen*.
    - **Region:** *Wählen Sie die geografisch nächstgelegene Region aus. Wenn Sie sich im Osten der USA befinden, verwenden Sie „USA, Osten 2“.*
    - **Name**: *Geben Sie einen eindeutigen Namen ein*.
    - **Tarif**: *Free F0 oder S, wenn Free F0 nicht verfügbar ist*
    - **Durch Aktivieren dieses Kontrollkästchens bestätige ich, dass ich die folgenden Bedingungen gelesen und verstanden habe**: *Ausgewählt*.

1. Wählen Sie die Option **Überprüfen und erstellen** und dann **Erstellen** aus, und warten Sie, bis die Bereitstellung abgeschlossen ist.


### Erstellen einer Conversational Language Understanding-App

Um das Verstehen natürlicher Sprache mit Conversational Language Understanding zu implementieren, erstellen Sie eine App und fügen dann Entitäten, Absichten und Äußerungen hinzu, um die Befehle zu definieren, die die Anwendung ausführen soll.

1. Öffnen Sie auf einer neuen Browserregisterkarte das Language Studio-Portal unter [https://language.azure.com](https://language.azure.com?azure-portal=true), und melden Sie sich mit dem Microsoft-Konto an, das Ihrem Azure-Abonnement zugeordnet ist.

1. Wenn Sie zur Auswahl einer Sprachressource aufgefordert werden, wählen Sie die folgenden Einstellungen aus:
    - **Azure-Verzeichnis**: *Das Azure-Verzeichnis, das Ihr Abonnement enthält*.
    - **Azure-Abonnement:** *Ihr Azure-Abonnement*
    - **Sprachressource**: *Die Sprachressource, die Sie zuvor erstellt haben*.

   Sollten Sie ***nicht*** zur Auswahl einer Sprachressource aufgefordert, kann dies daran liegen, dass Ihr Abonnement mehrere Sprachressourcen enthält. Gehen Sie in diesem Fall folgendermaßen vor:
    1. Wählen Sie oben auf der Leiste die Schaltfläche **Einstellungen (&#9881;)** aus.
    2. Gehen Sie auf der Seite **Einstellungen** zur Registerkarte **Ressourcen**.
    3. Wählen Sie die soeben erstellte Sprachressource aus, und klicken Sie auf **Ressource wechseln**.
    4. Wählen Sie oben auf der Seite **Language Studio** aus, um zur Startseite von Language Studio zurückzukehren.

1. Klicken Sie oben im Portal im Menü **Neu erstellen** auf die Option **Conversational Language Understanding**.

1. Geben Sie im Dialogfeld **Projekt erstellen** auf der Seite **Grundlegende Informationen eingeben** die folgenden Details ein, und wählen Sie **Weiter** aus:
    - **Name**: *Erstellen Sie einen eindeutigen Namen.*
    - **Primäre Sprache für Äußerungen**: *Englisch*
    - **Enable multiple languages in project** (Mehrere Sprachen im Projekt aktivieren): *Nicht auswählen*
    - **Beschreibung:** `Simple home automation`

    > **Tipp**: Notieren Sie sich ihren *Projektnamen*, da Sie ihn später noch verwenden werden.

1. Wählen Sie auf der Seite **Überprüfen und fertigstellen** die Option **Erstellen** aus.

### Erstellen von Absichten, Äußerungen und Entitäten

Eine *Absicht* ist eine Aktion, die Sie ausführen möchten. Angenommen, Sie möchten ein Licht einschalten und einen Ventilator ausschalten. In diesem Fall definieren Sie zwei Absichten: eine zum Einschalten und eine zum Ausschalten eines Geräts. Für jede Absicht geben Sie Beispiele für *Äußerungen* an, die die Art der Sprache angeben, mit der die Absicht ausgedrückt wird.

1. Vergewissern Sie sich, dass im Bereich **Schemadefinition** die Option **Absichten** ausgewählt ist. Wählen Sie dann **Hinzufügen** aus, fügen Sie eine Absicht mit dem Namen `switch_on` (in Kleinbuchstaben) hinzu, und wählen Sie **Absicht hinzufügen** aus.

    ![Wählen Sie im Bereich „Buildschema“ unter „Absichten“ „Hinzufügen“ aus.](media/conversational-language-understanding/build-schema.png)

    ![Fügen Sie die switch_on-Absicht hinzu, und wählen Sie dann „Absicht hinzufügen“ aus.](media/conversational-language-understanding/add-intent.png)

1. Wählen Sie die Absicht **switch_on** (einschalten) aus. Dadurch werden Sie auf die Seite **Datenbeschriftung** weitergeleitet. Wählen Sie in der Dropdownliste **Absicht** die Option **switch_on** aus. Geben Sie neben der Absicht **switch_on** die Äußerung `turn the light on` ein, und drücken Sie die **Eingabetaste**, um diese Äußerung in die Liste aufzunehmen.

    ![Fügen Sie dem Trainingssatz eine Äußerung hinzu, indem Sie „turn the light on“ (Licht einschalten) unter „Äußerung“ eingeben.](media/conversational-language-understanding/add-utterance-on.png)

1. Der Sprachdienst benötigt mindestens fünf verschiedene Beispieläußerungen für jede Absicht, um das Sprachmodell genügend zu trainieren. Fügen Sie der Absicht **switch_on** (einschalten) fünf weitere Beispieläußerungen hinzu:  
    - `switch on the fan`
    - `put the fan on`
    - `put the light on`
    - `switch on the light`
    - `turn the fan on`

1. Wählen Sie im Bereich **Entitäten für Training bezeichnen** auf der rechten Seite des Bildschirms die Option **Bezeichnungen** und dann **Entität hinzufügen** aus. Geben Sie `device` (in Kleinbuchstaben) ein, und wählen Sie **Auflisten** und dann **Entität hinzufügen** aus.

    ![Fügen Sie eine Entität hinzu, indem Sie „Tags“ im Bereich „Entitäten für das Training markieren“ und dann „Entität hinzufügen“ auswählen.](media/conversational-language-understanding/add-entity.png)

    ![Geben Sie das Gerät unter „Entitätsname“ ein, und wählen Sie Liste und dann „Entität hinzufügen“ aus.](media/conversational-language-understanding/add-entity-device.png)

1. Markieren Sie in der Äußerung ***turn the fan on*** (Ventilator einschalten) das Wort „fan“ (Ventilator). Wählen Sie dann in der angezeigten Liste im Feld *Search for an entity* (Nach einer Entität suchen) **device** aus.

    ![Markieren Sie das Wort „fan“ (Ventilator) in der Äußerung, und wählen Sie „device“ (Gerät) aus.](media/conversational-language-understanding/switch-on-entity.png)

1. Führen Sie die gleichen Schritte für alle Ausdrücke aus. Bezeichnen Sie den Rest der Äußerungen *fan* (Ventilator) oder *light* (Licht) mit der Entität **device** (Gerät). Überprüfen Sie anschließend, ob die folgenden Äußerungen vorhanden sind, und wählen Sie **Save changes** (Änderungen speichern) aus:

    | **Absicht** | **Äußerung** | **Entität** |
    | --------------- | ------------------ | ------------------ |
    | switch_on   | Put on the fan („Mach den Ventilator an.“)      | Gerät: *Ventilator auswählen* |
    | switch_on   | Put on the light („Mach das Licht an.“)    | Gerät: *Licht auswählen* |
    | switch_on   | Switch on the light („Schalte das Licht ein.“) | Gerät: *Licht auswählen* |
    | switch_on   | Turn the fan on („Schalte den Ventilator an.“)     | Gerät: *Ventilator auswählen* |
    | switch_on   | Switch on the fan („Schalte den Ventilator ein.“)   | Gerät: *Ventilator auswählen* |
    | switch_on   | Turn the light on („Schalte das Licht an.“)   | Gerät: *Licht auswählen* |

    ![Wählen Sie „Speichern“ aus, wenn Sie fertig sind.](media/conversational-language-understanding/save-changes.png) 

1. Wählen Sie im linken Bereich **Schemadefinition** aus, und überprüfen Sie, ob Ihre Absicht **switch_on** aufgeführt ist. Wählen Sie dann **Hinzufügen** aus, und fügen Sie eine neue Absicht mit dem Namen `switch_off` (in Kleinbuchstaben) hinzu.

    ![Kehren Sie zum Bildschirm „Buildschema“ zurück, und fügen Sie eine switch_off-Absicht hinzu.](media/conversational-language-understanding/add-switch-off.png) 

1. Wählen Sie die Absicht **switch_off** aus. Dadurch werden Sie auf die Seite **Datenbeschriftung** weitergeleitet. Wählen Sie in der Dropdownliste **Absicht** die Option **switch_off** aus. Fügen Sie neben der Absicht **switch_off** die Äußerung `turn the light off` hinzu.

1. Fügen Sie der Absicht **switch_off** (ausschalten) fünf weitere Beispieläußerungen hinzu.
    - `switch off the fan`
    - `put the fan off`
    - `put the light off`
    - `turn off the light`
    - `switch the fan off`

1. Bezeichnen Sie die Wörter *light* (Licht) oder *fan* (Ventilator) mit der Entität **device** (Gerät). Überprüfen Sie anschließend, ob die folgenden Äußerungen vorhanden sind, und wählen Sie **Save changes** (Änderungen speichern) aus:  

    | **Absicht** | **Äußerung** | **Entität** | 
    | --------------- | ------------------ | ------------------ |
    | switch_off   | Put the fan off („Mach den Ventilator aus.“)    | Gerät: *Ventilator auswählen* | 
    | switch_off   | Put the light off („Mach das Licht aus.“)  | Gerät: *Licht auswählen* |
    | switch_off   | Turn off the light („Schalte das Licht aus.“) | Gerät: *Licht auswählen* |
    | switch_off   | Switch the fan off („Schalte den Ventilator aus.“) | Gerät: *Ventilator auswählen* |
    | switch_off   | Switch off the fan („Stell den Ventilator aus.“) | Gerät: *Ventilator auswählen* |
    | switch_off   | Turn the light off („Schalte das Licht aus.“) | Gerät: *Licht auswählen* |

### Trainieren des Modells

Jetzt können Sie die von Ihnen definierten Absichten und Entitäten verwenden, um das Conversational Language Understanding-Modells für Ihre App zu trainieren.

1. Wählen Sie auf der linken Seite von Language Studio **Trainingsaufträge** aus, und wählen Sie dann **Trainingsauftrag starten** aus. Verwenden Sie folgende Einstellungen:
    - **Train a new model** (Neues Modell trainieren): *Ausgewählt und einen Modellnamen wählen*
    - **Trainingsmodus**: Standardtraining (kostenlos)
    - **Datenaufteilung**: *Wählen Sie „Automatisches Aufteilen des Testsatzes aus Trainingsdaten“ aus, und behalten Sie die Standardprozentsätze bei.*
    - Wählen Sie unten auf der Seite **Trainieren** aus.

1. Warten Sie, bis das Training abgeschlossen ist.

### Bereitstellen und Testen des Modells

Wenn Sie Ihr trainiertes Modell in einer Clientanwendung verwenden möchten, müssen Sie es als Endpunkt bereitstellen, an den die Clientanwendungen neue Äußerungen senden können. Aus diesen werden Absichten und Entitäten vorhergesagt.

1. Wählen Sie in Language Studio auf der linken Seite **Bereitstellen eines Modells** aus.

1. Wählen Sie den Namen Ihres Modells aus, und dann **Bereitstellung hinzufügen**. Verwenden Sie die folgenden Einstellungen:
    - **Erstellen oder Auswählen eines vorhandenen Bereitstellungsnamens**: *Wählen Sie „Neuen Bereitstellungsnamen erstellen“ aus. Fügen Sie einen eindeutigen Namen hinzu*.
    - **Zuweisen des trainierten Modells zu Ihrem Bereitstellungsnamen**; *Wählen Sie den Namens des trainierten Modells aus.*
    - Klicken Sie auf **Bereitstellen**.

    > **Tipp**: Notieren Sie sich den *Namen Ihrer Bereitstellung*, da Sie ihn später noch verwenden werden. 

1. Wählen Sie nach dem Bereitstellen des Modells links auf der Seite **Testen von Bereitstellungen**, und wählen Sie dann Ihr bereitgestelltes Modell unter **Name der Bereitstellung** aus.

1. Geben Sie den folgenden Text ein, und wählen Sie dann **Test ausführen** aus:

    `switch the light on`

    ![Testen Sie Ihr Modell, indem Sie Ihr bereitgestelltes Modell auswählen, dann Text eingeben und „Test ausführen“ auswählen.](media/conversational-language-understanding/test-model.png) 

    Das zurückgegebene Ergebnis sollte nun die vorhergesagte Absicht (**switch_on**) und die vorhergesagte Entität (**device**) mit einer Zuverlässigkeitsbewertung enthalten. Diese gibt die Wahrscheinlichkeit an, die das Modell für die vorhergesagte Absicht und die vorhergesagte Entität berechnet hat. Auf der JSON-Registerkarte sehen Sie die Zuverlässigkeit der jeweiligen potenziellen Absicht (wobei die vorhergesagte Absicht die höchste Zuverlässigkeitsbewertung aufweist).

1. Löschen Sie den Inhalt des Textfelds, und testen Sie das Modell mit den folgenden Äußerungen unter *Eigenen Text eingeben oder ein Textdokument hochladen*:
    - `turn off the fan`
    - `put the light on`
    - `put the fan off`

Sie haben nun erfolgreich ein Conversational Language-Projekt und definierte Entitäten, Absichten und Äußerungen konfiguriert. Sie haben gesehen, wie Sie ein Modell in Language Studio trainieren und bereitstellen. Und Sie haben es sowohl mit Äußerungen getestet, die Sie definiert haben, als auch mit solchen, die Sie nicht explizit definiert haben, die das Modell aber bestimmen konnte.

> **HINWEIS:** Conversational Language Understanding liefert die Intelligenz, um die Absicht der Eingabe zu interpretieren; es führt keine Aktionen aus, wie z. B. das Einschalten des Lichts oder des Lüfters. Ein*e Entwickler*in müsste eine Anwendung entwickeln, die mit Hilfe des Conversational Language Understanding-Modells die Absicht von Benutzer*innen ermittelt und dann die entsprechende Aktion automatisiert.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben. 1. Wählen Sie die Ressource aus, dann **Löschen** und dann **Ja**, um den Löschvorgang zu bestätigen. Dann wird die Ressource gelöscht.

## Weitere Informationen

Diese App veranschaulicht nur einen Teil der Funktionen des Features Conversational Language Understanding des Sprachdiensts. Weitere Informationen über die Möglichkeiten dieses Diensts erfahren Sie auf der Seite [Conversational Language Understanding](https://docs.microsoft.com/azure/cognitive-services/language-service/conversational-language-understanding/overview).
