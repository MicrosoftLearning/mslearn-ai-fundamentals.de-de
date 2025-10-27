---
lab:
  title: Erkunden des automatisierten maschinelles Lernens
---

# Erkunden des automatisierten maschinelles Lernens

In dieser Übung verwenden Sie das automatisierte maschinelle Lernen, um ein Machine Learning-Modell zu trainieren und auszuwerten. Anschließend stellen Sie das trainierte Modell bereit und testen es.

> **Hinweis:** Diese Übung dient dazu, Sie durch die Schritte zum Trainieren und Testen eines Modells mithilfe von***Azure Machine Learning*** zu führen. Wenn Sie über ein Azure-Abonnement mit ausreichenden Berechtigungen verfügen, können Sie einen Azure Machine Learning-Arbeitsbereich bereitstellen und diese für die Übung verwenden. Azure Machine Learning ist jedoch für unternehmensweite Skalierungs-Machine Learning-Lösungen konzipiert, die große Datenmengen und cloudbasierte Compute umfassen. Einige Vorgänge in Azure Machine Learning erfordern eine Bereitstellungsberechnung, die erhebliche Zeit in Anspruch nehmen kann. Wenn Sie keinen Zugriff auf Azure haben oder nur begrenzte Zeit haben, um die Übung abzuschließen, wird auch eine browserbasierte***ML Lab-App*** bereitgestellt, die die Kernfunktionen von Azure ML enthält, die in dieser Übung verwendet wird, und Sie können dies verwenden, um echte Machine Learning-Modelle zu trainieren und zu testen, genau wie in Azure ML. Obwohl die Benutzeroberfläche in ML Lab nicht*mit Azure Machine Learning identisch* ist, ist es ähnlich genug, um den Übergang zu Azure Machine Learning intuitiv zu gestalten. Beachten Sie, dass die ML Lab-App im Browser ausgeführt wird, sodass die Aktualisierung der Seite an jedem Punkt die App neu startet!

Diese Übung sollte ungefähr**35** Minuten dauern ( weniger, wenn Sie die browserbasierte ML Lab-App verwenden).

## Erstellen eines Arbeitsbereichs

Ein Arbeitsbereich wird verwendet, um alle Ihre maschinellen Lernressourcen zusammenzuhalten, wodurch es einfacher ist, Daten, Code, Modelle und andere Ressourcen an einem zentralen Ort zu verwalten.

1. Öffnen Sie das Portal für die Umgebung, die Sie in dieser Übung verwenden möchten, und melden Sie sich an, wenn Sie dazu aufgefordert werden:
    - Azure-basiertes[Azure Machine Learning Studio](https://ml.azure.com){:target="_blank"} unter`https://ml.azure.com`
    - Browserbasierte[ML Lab](https://aka.ms/ml-lab){:target="_blank"} unter`https://aka.ms/ml-lab`

    > **Tipp**: Wenn Azure Machine Learning Studio in einem vorhandenen Arbeitsbereich geöffnet wird, navigieren Sie zur**Seite "Alle Arbeitsbereiche** ".

1. Erstellen Sie einen neuen Arbeitsbereich mit einem geeigneten Namen.

    Wenn Sie Azure Machine Learning verwenden, benötigen Sie keinen*Hub* für diese Übung. Wählen Sie geeignete erweiterte Einstellungen basierend auf Richtlinieneinschränkungen in Ihrem Azure-Abonnement aus.

1. Nachdem der Arbeitsbereich erstellt wurde, wählen Sie ihn aus, um seine**Startseite** anzuzeigen.

    Beachten Sie, dass der Arbeitsbereich mehrere Seiten enthält, die im Navigationsbereich auf der linken Seite angezeigt werden. Sie können diesen Bereich erweitern und reduzieren, indem Sie oben das Menü **&#9776;** verwenden.

## Herunterladen von Daten

In dieser Übung verwenden Sie ein Dataset von Eisverkäufen, um ein Modell zu trainieren, das die Nachfrage nach Eiscremes an einem bestimmten Tag basierend auf saisonalen und meteorologischen Merkmalen vorhersagt.

1. Laden Sie auf einer neuen Browserregisterkarte**[ml-data.zip](https://aka.ms/mslearn-ml-data)** von`https://aka.ms/mslearn-ml-data` Ihrem lokalen Computer herunter.
1. Extrahieren Sie das heruntergeladene**ml-data.zip** Archiv, um die darin enthaltenen Dateien anzuzeigen. Beachten Sie, dass eine dieser Dateien**ice-cream.csv**ist, die die für diese Übung erforderlichen Eisumsatzdaten enthält.

## Verwenden von automatisiertem maschinellem Lernen zum Trainieren eines Modells

Automatisiertes maschinelles Lernen ermöglicht es Ihnen, mehrere Algorithmen und Parameter zu testen, um mehrere Modelle zu trainieren und das beste Modell für Ihre Daten zu identifizieren.

1. Zeigen Sie im Portal die Seite**Automatisierte ML** (unter**Dokumenterstellung**) an.

1. Erstellen Sie einen neuen automatisierten ML-Auftrag mit den folgenden Einstellungen, und verwenden Sie nach Bedarf**Weiter**, um die Benutzeroberfläche zu durchlaufen:

    > **Tipp**: Wenn in den folgenden Schritten keine expliziten Informationen für eine Einstellung angegeben werden, verwenden Sie den Standardwert.

    **Grundeinstellungen**:

    - Zuweisen eines eindeutigen**Auftragsnamens** für Ihren automatisierten Machine Learning-Job

   **Vorgangsart und Daten**:

    - Legen Sie den Vorgangstyp auf**Regression**fest.
    - Erstellen Sie eine neuen***tabellarische*** Datenressource namens**ice-cream**
        - Laden Sie die lokale**ice-cream.csv** Datei in den Standardspeicher des Arbeitsbereichs hoch.
        - Fügen Sie<u>nur</u> die folgenden Spalten hinzu (*Datum* ist für jede Zeile eindeutig und fügt eigene Funktionen hinzu):
            - **DayOfWeek**
            - **Monat**
            - **Temperature**
            - **Niederschlag**
            - **IceCreamsSold**
        - Erstellen Sie dann das Datenobjekt.
    - Stellen Sie sicher, dass Ihre neu erstellte**ice-cream**-Datenressource ausgewählt ist, bevor Sie zum nächsten Schritt wechseln.

    > **Hinweis:** Wenn Sie ein Azure-Abonnement verwenden, für das Sie kein Admin sind, wurde der schlüsselbasierte Zugriff auf den Speicher möglicherweise durch eine Richtlinie nicht zugelassen. In diesem Fall müssen Sie mit Ihrem Admin zusammenarbeiten, um den schlüsselbasierten Zugriff zuzulassen oder Ihren Azure Machine Learning-Arbeitsbereich neu zu konfigurieren, um die Entra-ID-Authentifizierung für den Zugriff auf den Speicher zu verwenden. Wenn Sie dies nicht tun können, verwenden Sie die browserbasierte***ML Lab***-App für diese Übung.

    **Task-Einstellungen**:

    - Legen Sie die**Zielspalte** (die Beschriftung, die das Modell vorherzusagen soll) auf**IceCreamsSold**fest.
    - Legen Sie**zusätzliche Konfigurationseinstellungen** fest:
        - Legen Sie die**primäre Metrik** auf die Metrik fest, die Sie zum Auswerten der Modellleistung verwenden möchten. Verwenden Sie in dieser Übung die*R<sup>2</sup>*-Bewertung.
        - Wählen Sie die Modellalgorithmen aus, die Sie ausprobieren möchten (oder lassen Sie sie alle ausgewählt)
    - Festlegen**von Featurisierungseinstellungen**:
        - Verwenden Sie diese Einstellungen, um die Featurisierung anzupassen (wie die Datenfeatures für Modelltraining vorbereitet werden)
    - Legen Sie**Grenzwerte** fest:
        - Verwenden Sie die Grenzwerte, um den Trainingsauftrag frühzeitig basierend auf bestimmten Kriterien zu beenden. Legen Sie in dieser Übung die folgenden Grenzwerte fest:
            - **Metric score threshold** (Metrischer Bewertungsschwellenwert): 0,9
            - **Experiment timeout minutes** 15
        
        > **Beachten Sie,** dass Sie diese Grenzwerte bei der Verwendung von Azure Machine Learning festlegen müssen, da das Ausführen von Trainingsaufträgen für jeden möglichen Algorithmus und jede Kombination aus Reifung möglicherweise Stunden dauern kann!

    **Compute:**

    - Verwenden Sie**serverloses** Compute

    **Überprüfung**

    - Überprüfen Sie die Einstellungen, und überprüfen Sie sie sorgfältig. Übermitteln Sie dann den Trainingsauftrag. Wird automatisch gestartet.

1. Warten Sie auf den Abschluss des Auftrags.

    > **Tipp**: Wenn Sie Azure Machine Learning verwenden, kann es eine Weile dauern – jetzt ist es vielleicht eine gute Zeit für eine Kaffeepause!

## Überprüfen des besten Modells

Wenn der Auftrag für automatisiertes maschinelles Lernen abgeschlossen ist, können Sie das am besten trainierte Modell überprüfen.

1. Zeigen Sie auf der Registerkarte**Übersicht** der Seite Auftragsdetails die Informationen zum Auftrag an, und notieren Sie sich die beste Modellzusammenfassung.
  
1. Klicken Sie auf den**Algorithmusnamen**, um die Details des besten Modells anzuzeigen. Zeigen Sie dann auf der Detailseite des untergeordneten Auftrags die folgenden Registerkarten an:
    - **Übersicht:** Allgemeine Details für den untergeordneten Auftrag.
    - **Modell**: Informationen über das trainierte Modell.
    - **Metrikenauswertungsmetriken** und Visualisierungen für das Modell basierend auf den Testdaten, die während des Trainingsprozesses verwendet werden.
    - **Ausgaben und Protokolle**: Während des Trainingsprozesses protokollierte Informationen.

## Bereitstellen und Testen des Modells

1. Wählen Sie auf der Registerkarte**Modell** für das beste Modell, das von Ihrem automatisierten Machine-Learning-Job trainiert wurde, die Option**Bereitstellen** aus, um das Modell auf einem Echtzeitendpunkt bereitzustellen.

    Wählen Sie die geeigneten Optionen für**Instanzen** und**virtuelle Computer** für die Berechnung aus, auf der der bereitgestellte Endpunkt ausgeführt wird (was von dem in Ihrem Azure-Abonnement verfügbaren Kontingent abhängig sein kann), und weisen Sie geeignete**Endpunkt** und**Bereitstellungsnamen** zu.

1. Warten Sie auf eine Benachrichtigung, dass die Bereitstellung abgeschlossen ist.

    > **Tipp**: In Azure Machine Learning Studio kann die Endpunktbereitstellung 5 bis 10 Minuten dauern.

## Testen des bereitgestellten Diensts

Jetzt können Sie den bereitgestellten Dienst testen.

1. Wählen Sie im Navigationsmenü die Seite**Endpunkte** aus, und öffnen Sie den von Ihnen erstellten Echtzeitendpunkt.

1. Zeigen Sie auf der Endpunktseite die Registerkarte**Test** an.

1. Ersetzen Sie im Bereich**Input data to test endpoint** (Eingabedaten zum Testen des Endpunkts) den JSON-Code der Vorlage durch die folgenden Eingabedaten:

    ```json
   {
     "input_data": {
        "columns": [
            "DayOfWeek",
            "Month",
            "Temperature",
            "Rainfall"
        ],
        "index": [0],
        "data": [["Wednesday","June",70.5,0.05]]
     }
   }
    ```

1. Klicken Sie auf die Schaltfläche**Testen**.

1. Überprüfen Sie die Testergebnisse, die eine vorhergesagte Anzahl von Vermietungen basierend auf den Eingabefeatures enthalten, ähnlich wie hier:

    ```JSON
   [
       120.16208168753236
   ]
    ```

    Im Testbereich wurden die Eingabedaten erfasst und das von Ihnen trainierte Modell verwendet, um die vorhergesagte Anzahl von Vermietungen zurückzugeben.

## Anzeigen von Code zum Verwenden des Modells

Nachdem Sie nun über ein vorhersagendes Modell verfügen, können Entwickelnde Anwendungen erstellen, die diesen nutzen.

1. Zeigen Sie auf der Seite „Echtzeitendpunkt“ die Registerkarte**Nutzen** an.
1. Überprüfen Sie den Beispielcode, um Ihr Modell zu nutzen.

## Wenn die Zeit es zulässt

Wenn Sie mit automatisiertem maschinellem Lernen experimentieren möchten, versuchen Sie, ein**Klassifizierungsmodell** basierend auf der**penguins.csv** Datei zu trainieren, die**im ml-data.zip** Archiv enthalten war, das Sie zuvor heruntergeladen haben. Verwenden Sie alle Spalten in diesem Dataset.

Nach dem Training und Bereitstellung eines Klassifizierungsmodells können Sie es im Endpunkt mit dem folgenden JSON testen:

```json
{
    "input_data": {
    "columns": [
        "CulmenLength",
        "CulmenDepth",
        "FlipperLength",
        "BodyMass"
    ],
    "index": [0],
    "data": [[45.2,13.8,215,4750]]
    }
}
```

## Bereinigung

Wenn Sie Azure Machine Learning zum Abschließen dieser Übung verwendet haben, sollten Sie die von Ihnen erstellten Ressourcen löschen, um unnötige Azure-Nutzung zu vermeiden.

1. Wählen Sie in[Azure Machine Learning Studio](https://ml.azure.com) auf der Registerkarte**Endpunkte** den Endpunkt aus, den Sie bereitgestellt haben. Klicken Sie dann auf**Löschen**, und bestätigen Sie, dass Sie den Endpunkt löschen möchten.

    Durch das Löschen Ihrer Compute-Instanz wird sichergestellt, dass Ihrem Abonnement keine Computeressourcen in Rechnung gestellt werden. Ihnen wird jedoch eine geringe Datenspeichermenge in Rechnung gestellt, solange der Azure Machine Learning-Arbeitsbereich in Ihrem Abonnement enthalten ist. Wenn Sie mit dem Erkunden von Azure Machine Learning fertig sind, können Sie Ihren Azure Machine Learning-Arbeitsbereich und die zugehörigen Ressourcen löschen.

So löschen Sie Ihren Arbeitsbereich:

1. Öffnen Sie im[Azure-Portal](https://portal.azure.com) auf der Seite**Ressourcengruppen** die Ressourcengruppe, die Sie beim Erstellen des Azure Machine Learning-Arbeitsbereichs angegeben haben.
2. Klicken Sie auf**Ressourcengruppe löschen**, geben Sie den Ressourcengruppennamen ein, um zu bestätigen, dass Sie ihn löschen möchten, und klicken Sie dann auf**Löschen**.
