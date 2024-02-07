---
lab:
  title: Lesen von Text in Vision Studio
---

# Lesen von Text in Vision Studio

In dieser Übung verwenden Sie den Azure KI-Dienst, um die optischen Zeichenerkennungsfunktionen von Azure KI Vision zu erkunden. Sie werden Vision Studio verwenden, um mit dem Extrahieren von Text aus Bildern zu experimentieren, ohne Code schreiben zu müssen.

Maschinelles Sehen wird oft eingesetzt, um in ein Bild eingebetteten Text zu erkennen und zu interpretieren. Dies wird optische Zeichenerkennung (OCR, Optical Character Recognition) genannt. In dieser Übung verwenden Sie eine Azure KI-Dienstressource, die Azure KI Vision-Dienste umfasst. Anschließend verwenden Sie Vision Studio, um OCR mit verschiedenen Typen von Bildern auszuprobieren.

## Erstellen einer *Azure KI Services*-Ressource

Sie können die OCR-Funktionen von Azure KI Vision mit einer **Azure KI Services**-Ressource für mehrere Dienste verwenden. Wenn dies noch nicht erfolgt ist, erstellen Sie eine **Azure KI Services**-Ressource in Ihrem Azure-Abonnement.

1. Öffnen Sie auf einer neuen Browserregisterkarte das **Azure-Portal** unter [https://portal.azure.com](https://portal.azure.com?azure-portal=true), und melden Sie sich mit dem Microsoft-Konto an, das Ihrem Azure-Abonnement zugeordnet ist.

1. Klicken Sie auf die Schaltfläche **＋Ressource erstellen** und suchen Sie nach *Azure KI Services*. Wählen Sie **Erstellen** eines **Azure KI Services**-Plans aus. Sie werden zu einer Seite weitergeleitet, um eine Azure KI Services-Ressource zu erstellen. Konfigurieren Sie sie mit den folgenden Einstellungen:
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine Ressourcengruppe mit einem eindeutigen Namen*.
    - **Region:** USA, Osten.
    - **Name**: *Geben Sie einen eindeutigen Namen ein*.
    - **Tarif**: *Standard S0.*
    - **Durch Aktivieren dieses Kontrollkästchens bestätige ich, dass ich die folgenden Bedingungen gelesen und verstanden habe**: *Ausgewählt*.

1. Wählen Sie die Option **Überprüfen und erstellen** und dann **Erstellen** aus, und warten Sie, bis die Bereitstellung abgeschlossen ist.

## Verbinden Ihrer Azure KI Services-Ressource mit Vision Studio

Verbinden Sie als Nächstes die oben bereitgestellte Azure KI Services-Ressource mit Vision Studio.

1. Navigieren Sie auf einer anderen Browserregisterkarte zu **Vision Studio** unter [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Melden Sie sich mit Ihrem Konto an, und stellen Sie sicher, dass Sie dasselbe Verzeichnis wie das Verzeichnis verwenden, in dem Sie Ihre Azure KI Services-Ressource erstellt haben.

1. Wählen Sie auf der Startseite von Vision Studio **Alle Ressourcen anzeigen** unter der Überschrift **Erste Schritte mit Vision** aus.

    ![Der Link „Alle Ressourcen anzeigen“ ist unter „Erste Schritte mit Vision in Vision Studio“ hervorgehoben.](./media/analyze-images-vision/vision-resources.png)

1. Zeigen Sie auf der Seite **Wählen Sie eine Ressource aus, mit der Sie arbeiten möchten** mit dem Mauszeiger in der Liste auf die Ressource, die Sie oben erstellt haben, aktivieren Sie dann das Kontrollkästchen links neben dem Ressourcennamen, und wählen Sie dann **Als Standardressource auswählen** aus.

    > **Hinweis**: Wenn Ihre Ressource nicht aufgeführt wird, müssen Sie die Seite unter Umständen **aktualisieren**.

    ![Das Dialogfeld „Wählen Sie eine Ressource aus, mit der Sie arbeiten möchten“ wird angezeigt, wobei die Ressource „cog-ms-learn-vision-SUFFIX Cognitive Services“ hervorgehoben und markiert ist. Die Schaltfläche „Als Standardressource auswählen“ ist hervorgehoben.](./media/analyze-images-vision/default-resource.png)

1. Schließen Sie die Einstellungsseite, indem Sie in der oberen rechten Bildschirmecke „x“ auswählen.

## Extrahieren von Text aus Bildern im Vision Studio
    
1. Navigieren Sie in einem Webbrowser zu **Vision Studio** unter [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Wählen Sie auf der Startseite **Erste Schritte mit Vision** die Option **Optische Zeichenerkennung** und anschließend die Kachel **Text aus Bildern extrahieren** aus.

1. Bestätigen Sie unter der Unterüberschrift **Try It Out** die Ressourcennutzungsrichtlinie, indem Sie diese lesen und das Kontrollkästchen aktivieren.  

1. Wählen Sie [**https://aka.ms/mslearn-ocr-images**](https://aka.ms/mslearn-ocr-images) aus, um **ocr-images.zip**herunterzuladen. Öffnen Sie dann den Ordner.

1. Wählen Sie im Portal **Nach einer Datei suchen** aus, und navigieren Sie zu dem Ordner auf Ihrem Computer, in den Sie **ocr-images.zip** heruntergeladen haben. Wählen Sie **advert.jpg** und dann **Öffnen**aus.

1. Überprüfen Sie nun, was zurückgegeben wird:
    - Unter **Erkannte Attribute** wird der im Bild gefundene Text in einer hierarchischen Struktur von Regionen, Zeilen und Wörtern angeordnet.
    - Auf dem Bild wird die Position des Texts durch einen Begrenzungsrahmen angegeben, wie hier gezeigt:

    ![Eine Abbildung des Texts, der auf dem Bild umrandet ist.](media/read-text-computer-vision/text-bounding-boxes.png)

1. Sie können jetzt ein anderes Bild ausprobieren. Wählen Sie **Nach einer Datei suchen** aus, und navigieren Sie zu dem Ordner, in dem Sie die Dateien aus GitHub gespeichert haben. Wählen Sie **letter.jpg** aus.

    ![Ein Bild eines getippten Briefs.](media/read-text-computer-vision/letter.jpg)

1. Überprüfen Sie die Ergebnisse für das zweite Bild. Der Text und die Begrenzungsrahmen des Texts sollten zurückgegeben werden. Wenn Sie Zeit haben, probieren Sie **note.jpg** und **receipt.jpg** aus.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu bearbeiten, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das **Azure-Portal** unter [https://portal.azure.com](https://portal.azure.com?azure-portal=true), und wählen Sie die Ressourcengruppe aus, die die von Ihnen erstellte Ressource enthält.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

Weitere Informationen zu den Möglichkeiten dieses Dienstes finden Sie in der Dokumentation zu Azure KI Vision unter [Optische Zeichenerkennung](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr).
