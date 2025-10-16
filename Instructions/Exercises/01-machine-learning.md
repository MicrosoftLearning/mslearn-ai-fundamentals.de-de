---
lab:
  title: Erkunden des automatisierten maschinellen Lernens in Azure Machine Learning
---

# Erkunden des automatisierten maschinellen Lernens in Azure Machine Learning

In dieser Übung verwenden Sie das Feature für automatisiertes maschinelles Lernen in Azure Machine Learning, um ein Machine Learning-Modell zu trainieren und auszuwerten. Anschließend stellen Sie das trainierte Modell bereit und testen es.

Diese Übung dauert ca. **35** Minuten.

## Erstellen eines Azure Machine Learning-Arbeitsbereichs

Um Azure Machine Learning verwenden zu können, müssen Sie einen Azure Machine Learning-Arbeitsbereich in Ihrem Azure-Abonnement bereitstellen. Anschließend können Sie Azure Machine Learning Studio verwenden, um mit den Ressourcen in Ihrem Arbeitsbereich zu arbeiten.

> **Tipp**: Wenn Sie bereits über einen Azure Machine Learning-Arbeitsbereich verfügen, können Sie diesen verwenden und mit der nächsten Aufgabe fortfahren.

1. Melden Sie sich mit Ihren Microsoft-Anmeldeinformationen beim [Azure-Portal](https://portal.azure.com) in `https://portal.azure.com` an.

1. Klicken Sie auf **＋Ressource erstellen**, suchen Sie nach *Machine Learning*, und erstellen Sie eine neue **Azure Machine Learning**-Ressource mit den folgenden Einstellungen:
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
    - **Name**: *Geben Sie einen eindeutigen Namen für den Arbeitsbereich ein.*
    - **Region:** USA, Osten.
    - **Speicherkonto**: *Für Ihren Arbeitsbereich wird standardmäßig ein neues Speicherkonto erstellt*.
    - **Schlüsseltresor**: *Für Ihren Arbeitsbereich wird standardmäßig ein neuer Schlüsseltresor erstellt*.
    - **Application Insights**: *Für Ihren Arbeitsbereich wird standardmäßig eine neue Application Insights-Ressource erstellt*.
    - **Containerregistrierung**: Keine (*wird automatisch erstellt, wenn Sie das erste Mal ein Modell in einem Container bereitstellen*).

1. Klicken Sie auf**Überprüfen + erstellen** und dann auf **Erstellen**. Warten Sie, bis Ihr Arbeitsbereich erstellt wurde (dies kann einige Minuten dauern), und wechseln Sie dann zur bereitgestellten Ressource.

#### Studio starten 

1. Wählen Sie in Ihrer Azure Machine Learning-Arbeitsbereichsressource **Studio starten** (oder öffnen Sie einen neuen Browser-Tab und navigieren Sie zu [https://ml.azure.com](https://ml.azure.com) und melden Sie sich mit Ihrem Microsoft-Konto bei Azure Machine Learning Studio an). Schließen Sie alle angezeigten Nachrichten.

1. In Azure Machine Learning Studio sollte Ihr neu erstellter Arbeitsbereich angezeigt werden. Andernfalls wählen Sie im linken Menü **Alle Arbeitsbereiche** aus, und wählen Sie dann den soeben erstellten Arbeitsbereich aus.

## Verwenden von automatisiertem maschinellem Lernen zum Trainieren eines Modells

Automatisiertes maschinelles Lernen ermöglicht es Ihnen, mehrere Algorithmen und Parameter zu testen, um mehrere Modelle zu trainieren und das beste Modell für Ihre Daten zu identifizieren. In dieser Übung verwenden Sie ein Dataset mit Verlaufsdetails zu Fahrradvermietungen, um ein Modell zu trainieren, das basierend auf saisonalen und meteorologischen Merkmalen die Anzahl der Fahrradvermietungen vorhersagt, die an einem bestimmten Tag zu erwarten sind.

> **Quellenangaben**: *Die in dieser Übung verwendeten Daten werden von [Capital Bikeshare](https://www.capitalbikeshare.com/system-data) abgeleitet und in Übereinstimmung mit der [Lizenzvereinbarung](https://www.capitalbikeshare.com/data-license-agreement) für veröffentlichte Daten verwendet.*

1. Zeigen Sie in [Azure Machine Learning Studio](https://ml.azure.com?azure-portal=true) die Seite **Automated ML** (Automatisiertes ML) (unter **Dokumenterstellung**) an.

1. Erstellen Sie einen neuen automatisierten ML-Auftrag mit den folgenden Einstellungen, und verwenden Sie nach Bedarf **Weiter**, um die Benutzeroberfläche zu durchlaufen:

    **Grundeinstellungen**:

    - **Jobname**: Das Feld Jobname sollte bereits mit einem eindeutigen Namen vorausgefüllt sein. Nehmen Sie keine Änderungen vor.
    - **Name des neuen Experiments**: `mslearn-bike-rental`
    - **Beschreibung:** `Automated machine learning for bike rental prediction`
    - **Tags**: *keine*

   **Vorgangsart und Daten**:
    
    >**HINWEIS:** Einige Abonnements verfügen über Berechtigungen, die nicht zulassen, dass *bike-data* dem *workspaceblobstore* hinzugefügt werden. Wenn dieses Problem auftritt, müssen Sie derzeit entweder zu einem persönlichen Abonnement wechseln oder die Berechtigungen Ihres Abonnements anpassen. 

    - **Tasktyp auswählen**: Regression
    - **Auswählen von Daten**:
        - Erstellen Sie eine neue Datenressource mit den folgenden Einstellungen:
            - **Datentyp**:
                - **Name**: `bike-rentals`
                - **Beschreibung:** `Historic bike rental data`
                - **Typ:** Tabelle (mltable)
            - **Datenquelle**:
                - Klicken Sie auf **Aus lokalen Dateien**
            - **Zielspeichertyp**:
                - **Datenspeichertyp**: Azure Blob Storage
                - **Name**: workspaceblobstore
            - **MLtable-Auswahl**:
                - *Laden Sie den Ordner [bike-data](https://aka.ms/bike-rentals) von `https://aka.ms/bike-rentals` herunter, und entpacken Sie diesen.*
                - **Ordner hochladen**: *Laden Sie den extrahierten Ordner **bike-data** hoch, der die Daten- und Tabellendefinitionsdateien enthält, die Sie für Ihr Trainingsdataset benötigen.*
                - **Hinweis**: *Wenn Sie in einer Meldung aufgefordert werden, die Datenüberprüfung zum Fortfahren zu überspringen, wählen Sie die Option zum Überspringen der Datenüberprüfung aus.*
        - Wählen Sie die neu erstellte Datenressource **bike-rentals** aus, und definieren Sie den Auftrag für automatisiertes maschinelles Lernen auf der nächsten Seite (**Aufgabeneinstellungen**).

    **Task-Einstellungen**:

    - **Tasktyp**: Regression
    - **Dataset:** bike-rentals
    - **Zielspalte**: Verleihe (Integer)
    - **Zusätzliche Konfigurationseinstellungen**:
        - **Primary metric** (Primäre Metrik): NormalizedRootMeanSquaredError
        - **Explain best model** (Bestes Modell erklären): *<u>Nicht</u> ausgewählt*
        - **Ensemblestapelung aktivieren**: *<u>Nicht</u> ausgewählt*
        - **Alle unterstützten Modelle verwenden**: <u>Nicht</u> ausgewählt. *Sie beschränken den Auftrag darauf, nur einige bestimmte Algorithmen auszuprobieren*.
        - **Zulässige Modelle**: *Wählen Sie nur **RandomForest** und **LightGBM** aus. Normalerweise sollten Sie so viele Modelle wie möglich ausprobieren, aber jedes hinzugefügte Modell verlängert die Zeitspanne, die zum Ausführen des Auftrags benötigt wird*.
    - **Grenzwerte**: *Erweitern Sie diesen Abschnitt*
        - **Maximale Testversionen**: `3`
        - **Maximale gleichzeitige Testversionen**: `3`
        - **Maximale Knoten**: `3`
        - **Metrischer Bewertungsschwellenwert**: `0.085` (*sodass wenn ein Modell eine normalisierte Wurzel der mittleren Fehlerquadratsumme von 0,085 oder weniger erreicht, der Auftrag beendet wird.*)
        - **Experiment Timeout**: `15`
        - **Iterationstimeout**: `15`
        - **Vorzeitige Beendigung aktivieren**: *Ausgewählt*
    - **Validierung und Test**:
        - **Validierungstyp**: Aufteilung der Train-Validation
        - **Prozentsatz der Validierungsdaten**: 10
        - **Testdataset**: Keins

    **Compute:**

    - **Computetyp auswählen**: Serverlos
    - **VM-Typ:** CPU
    - **VM-Dienstebene**: Dediziert.
    - **VM-Größe:** Standard_DS3_V2\*
    - **Anzahl von Instanzen**: 1

    \* *Wenn Ihr Abonnement die Ihnen zur Verfügung stehenden VM-Größen einschränkt, wählen Sie eine beliebige Größe.*

1. Übermitteln des Trainingsauftrags Wird automatisch gestartet.

1. Warten Sie auf den Abschluss des Auftrags. Dies kann einige Zeit in Anspruch nehmen und ist möglicherweise ein guter Zeitpunkt für eine Kaffeepause.

## Überprüfen des besten Modells

Wenn der Auftrag für automatisiertes maschinelles Lernen abgeschlossen ist, können Sie das am besten trainierte Modell überprüfen.

1. Beachten Sie auf der Registerkarte **Übersicht** des automatisierten ML-Auftrags die Zusammenfassung des besten Modells.
    ![Screenshot: Zusammenfassung des besten Modells des automatisierten Machine Learning-Auftrags mit einem Rahmen um den Algorithmusnamen.](./media/use-automated-machine-learning/complete-run.png)
  
1. Wählen Sie den Text unter **Algorithmusname**, um das beste Modell und seine Details anzuzeigen.

1. Klicken Sie auf die Registerkarte **Metriken**, und wählen Sie die Diagramme **residuals** und **predicted_true** aus, wenn diese nicht bereits ausgewählt sind.

    Überprüfen Sie die Diagramme, die die Leistung des Modells anzeigen. Das **Residualwertediagramm** zeigt die *Residualwerte* (die Unterschiede zwischen vorhergesagten und tatsächlichen Werten) als Histogramm an. Das Diagramm **predicted_true** vergleicht die vorhergesagten Werte mit den tatsächlichen Werten.

## Bereitstellen und Testen des Modells

1. Wählen Sie auf der Registerkarte **Modell** für das beste Modell, das von Ihrem Auftrag für automatisiertes maschinelles Lernen trainiert wurde, die Option **Bereitstellen** aus und verwenden Sie die Option **Echtzeitendpunkt**, um das Modell mit den folgenden Einstellungen bereitzustellen:
    - **VM**: Standard_DS3_v2
    - **Instanzenanzahl:** 3
    - **Endpunkt**: Neu
    - **Endpunktname**: *Behalten Sie die Standardeinstellung bei, oder stellen Sie sicher, dass sie global eindeutig ist*
    - **Bereitstellungsname**: *Standardeinstellung beibehalten*
    - **Rückschließen der Datensammlung**: *Disabled* (Deaktiviert)
    - **Paketmodell**: *Disabled* (Deaktiviert)

    > **Hinweis** Wenn Sie eine Meldung erhalten, dass nicht genügend Kontingent für die Auswahl der virtuellen Maschine *Standard_DS3_v2* vorhanden ist, wählen Sie bitte eine andere aus.

1. Warten Sie, bis die Bereitstellung gestartet wurde. Dieser Vorgang kann einige Sekunden in Anspruch nehmen. Der **Bereitstellungsstatus** für den Endpunkt wird im Hauptteil der Seite als *Wird ausgeführt* angezeigt.
1. Warten Sie, bis der **Bereitstellungsstatus** in *Erfolgreich* geändert wird. Dies kann 5-10 Minuten dauern.

## Testen des bereitgestellten Diensts

Jetzt können Sie den bereitgestellten Dienst testen.

1. Wählen Sie in Azure Machine Learning Studio im linken Menü **Endpunkte** aus, und öffnen Sie den von Ihnen erstellten Echtzeitendpunkt.

1. Zeigen Sie auf der Seite „Echtzeitendpunkt“ die Registerkarte **Test** an.

1. Ersetzen Sie im Bereich **Input data to test endpoint** (Eingabedaten zum Testen des Endpunkts) den JSON-Code der Vorlage durch die folgenden Eingabedaten:

    ```json
      {
     "input_data": {
       "columns": [
         "day",
         "mnth",
         "year",
         "season",
         "holiday",
         "weekday",
         "workingday",
         "weathersit",
         "temp",
         "atemp",
         "hum",
         "windspeed"
       ],
       "index": [0],
       "data": [[1,1,2022,2,0,1,1,2,0.3,0.3,0.3,0.3]]
     }
    }

    ```

1. Klicken Sie auf die Schaltfläche **Testen**.

1. Überprüfen Sie die Testergebnisse, die eine vorhergesagte Anzahl von Vermietungen basierend auf den Eingabefeatures enthalten, ähnlich wie hier:

    ```JSON
    [
      352.3564674945718
    ]
    ```

    Im Testbereich wurden die Eingabedaten erfasst und das von Ihnen trainierte Modell verwendet, um die vorhergesagte Anzahl von Vermietungen zurückzugeben.

## Anzeigen von Code zum Nutzen des Diensts

Nachdem Sie nun über einen vorhersagenden Dienstendpunkt verfügen, können Entwickelnde Anwendungen erstellen, die diesen nutzen.

1. Zeigen Sie auf der Seite „Echtzeitendpunkt“ die Registerkarte **Nutzen** an.
1. Überprüfen Sie den Beispielcode zum Nutzen Ihres Endpunkts, der für mehrere Programmiersprachen bereitgestellt wird.

Sehen wir uns an, was Sie getan haben. Sie haben ein Dataset mit Fahrradverleih-Verlaufsdaten verwendet, um ein Modell zu trainieren. Das Modell sagt auf der Grundlage von saisonalen und meteorologischen *Merkmalen*F vorher, die ausgeliehen werden. Schließlich haben Sie das Modell getestet und den Code überprüft, den Entwickelnde zum Erstellen einer Anwendung verwenden können, um diesen zu nutzen.

## Bereinigung

Der von Ihnen erstellte Webdienst wird in einer *Azure-Containerinstanz* gehostet. Wenn Sie nicht weiter experimentieren möchten, sollten Sie den Endpunkt löschen, um eine unnötige Azure-Nutzung zu vermeiden.

1. Wählen Sie in [Azure Machine Learning Studio](https://ml.azure.com) auf der Registerkarte **Endpunkte** den Endpunkt aus, den Sie bereitgestellt haben. Klicken Sie dann auf **Löschen**, und bestätigen Sie, dass Sie den Endpunkt löschen möchten.

    Durch das Löschen Ihrer Compute-Instanz wird sichergestellt, dass Ihrem Abonnement keine Computeressourcen in Rechnung gestellt werden. Ihnen wird jedoch eine geringe Datenspeichermenge in Rechnung gestellt, solange der Azure Machine Learning-Arbeitsbereich in Ihrem Abonnement enthalten ist. Wenn Sie mit dem Erkunden von Azure Machine Learning fertig sind, können Sie Ihren Azure Machine Learning-Arbeitsbereich und die zugehörigen Ressourcen löschen.

So löschen Sie Ihren Arbeitsbereich:

1. Öffnen Sie im [Azure-Portal](https://portal.azure.com) auf der Seite **Ressourcengruppen** die Ressourcengruppe, die Sie beim Erstellen des Azure Machine Learning-Arbeitsbereichs angegeben haben.
2. Klicken Sie auf **Ressourcengruppe löschen**, geben Sie den Ressourcengruppennamen ein, um zu bestätigen, dass Sie ihn löschen möchten, und klicken Sie dann auf **Löschen**.
