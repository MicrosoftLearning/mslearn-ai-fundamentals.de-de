---
lab:
  title: Analysieren von Bildern in Vision Studio
---

# Analysieren von Bildern in Vision Studio 

**Azure KI Vision** umfasst zahlreiche Funktionen zum Verständnis von Bildinhalten und Kontext sowie zum Extrahieren von Informationen aus Bildern. Azure KI Vision Studio ermöglicht es Ihnen, viele Funktionen der Bildanalyse auszuprobieren. 

In dieser Übung verwenden Sie Vision Studio, um Bilder mithilfe der zum Ausprobieren integrierten Funktionen zu analysieren. Angenommen, das fiktive Einzelhandelsunternehmen *Northwind Traders* möchte einen „Smart Store“ implementieren, der von KI überwacht wird, um zu identifizieren, welche Kunden Unterstützung benötigen, und Mitarbeiter*innen zu diesen Kunden zu schicken. Mit Azure KI Vision können Bilder von den Kameras im Geschäft analysiert und aussagekräftige Beschreibungen der Bilder generiert werden.

## Erstellen einer *Azure KI Services*-Ressource

Sie können die Bildanalysefunktionen von Azure KI Vision mit einer **Azure KI Services**-Ressource für mehrere Dienste verwenden. Wenn dies noch nicht erfolgt ist, erstellen Sie eine **Azure KI Services**-Ressource in Ihrem Azure-Abonnement.

1. Öffnen Sie auf einer anderen Browserregisterkarte das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com?azure-portal=true), und melden Sie sich mit dem Microsoft-Konto an, das Ihrem Azure-Abonnement zugeordnet ist.

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

1. Navigieren Sie auf einer anderen Browserregisterkarte zu [Vision Studio](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Melden Sie sich mit Ihrem Konto an, und stellen Sie sicher, dass Sie dasselbe Verzeichnis wie das Verzeichnis verwenden, in dem Sie Ihre Azure KI Services-Ressource erstellt haben.

1. Wählen Sie auf der Startseite von Vision Studio **Alle Ressourcen anzeigen** unter der Überschrift **Erste Schritte mit Vision** aus.

    ![Der Link „Alle Ressourcen anzeigen“ ist unter „Erste Schritte mit Vision in Vision Studio“ hervorgehoben.](./media/analyze-images-vision/vision-resources.png)

1. Zeigen Sie auf der Seite **Wählen Sie eine Ressource aus, mit der Sie arbeiten möchten** mit dem Mauszeiger in der Liste auf die Ressource, die Sie oben erstellt haben, aktivieren Sie dann das Kontrollkästchen links neben dem Ressourcennamen, und wählen Sie dann **Als Standardressource auswählen** aus.

    > **Hinweis**: Wenn Ihre Ressource nicht aufgeführt wird, müssen Sie die Seite unter Umständen **aktualisieren**.

    ![Das Dialogfeld „Wählen Sie eine Ressource aus, mit der Sie arbeiten möchten“ wird angezeigt, wobei die Ressource „cog-ms-learn-vision-SUFFIX Cognitive Services“ hervorgehoben und markiert ist. Die Schaltfläche „Als Standardressource auswählen“ ist hervorgehoben.](./media/analyze-images-vision/default-resource.png)

1. Schließen Sie die Einstellungsseite, indem Sie in der oberen rechten Bildschirmecke „x“ auswählen.

## Generieren von Beschriftungen für Bilder

Jetzt können Sie Vision Studio verwenden, um Bilder zu analysieren, die von einer Kamera im Store von *Northwind Traders* aufgenommen wurden.

Sehen wir uns die Bildbeschriftungsfunktion von Azure KI Vision an. Bildbeschriftungen sind über die Features **Caption** und **Dense Captions** von Image Analysis 4.0 verfügbar.

1. Navigieren Sie hierzu in einem Webbrowser zu [Vision Studio](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Wählen Sie auf der Landing Page **Getting started with Vision** die Registerkarte **Image analysis** aus, und wählen Sie dann die Kachel **Add captions to images** aus.

    ![Auf der Landing Page von Vision Studio ist die Registerkarte „Image analysis“ ausgewählt und hervorgehoben. Die Kachel „Add captions“ ist hervorgehoben.](./media/analyze-images-vision/add-captions.png)

1. Bestätigen Sie unter der Unterüberschrift **Try It Out** die Ressourcennutzungsrichtlinie, indem Sie diese lesen und das Kontrollkästchen aktivieren.  

1. Wählen Sie [**https://aka.ms/mslearn-images-for-analysis**](https://aka.ms/mslearn-images-for-analysis) aus, um **image-analysis.zip** herunterzuladen. Öffnen Sie den Ordner auf Ihrem Computer, und suchen Sie die Datei namens **store-camera-1.jpg**, die das folgende Bild enthält:

    ![Abbildung eines Elternteils, das die Kamera seines Mobiltelefons verwendet, um ein Bild eines Kinds in einem Geschäft aufzunehmen](./media/analyze-images-vision/store-camera-1.jpg)

1. Laden Sie das Bild **store-camera-1.jpg** hoch, indem Sie es auf das Feld **Drag and drop files here** ziehen oder indem Sie in ihrem Dateisystem zu dieser Datei navigieren.

1. Beobachten Sie den generierten Beschriftungstext, der im Bereich **Detected attributes** rechts neben dem Bild sichtbar ist.

    Die Funktion **Caption** liefert einen einzelnen, von Menschen lesbaren englischen Satz, der den Inhalt des Bildes beschreibt.

1. Verwenden Sie als Nächstes dasselbe Bild, um die Funktion **Dense captioning** auszuführen. Kehren Sie zur Startseite **Vision Studio** zurück, und wählen Sie wie zuvor die Registerkarte **Image analysis** aus. Wählen Sie dann die Kachel **Dense captioning** aus.

    Die Funktion **Dense Captions** unterscheidet sich von der Funktion **Caption** darin, dass sie mehrere lesbare Beschriftungen für ein Bild bereitstellt, von denen eine den Inhalt des Bildes beschreibt und die anderen jeweils die wichtigsten im Bild erkannten Objekte abdecken. Zu jedem erkannten Objekt gehört ein Begrenzungsrahmen, der die dem Objekt zugeordneten Pixelkoordinaten innerhalb des Bildes definiert.

1. Zeigen Sie mit der Maus auf eine der Beschriftungen in der Liste der **erkannten** Attribute, und beobachten Sie, was innerhalb des Bilds geschieht.

    ![Das Bild und seine Beschriftungen werden angezeigt.](./media/analyze-images-vision/dense-captioning.png)

    Bewegen Sie den Mauszeiger über die anderen Beschriftungen in der Liste, und beachten Sie, wie sich der Begrenzungsrahmen im Bild verschiebt, um den Teil des Bildes hervorzuheben, der zum Generieren der Beschriftung verwendet wurde.

## Taggen von Bildern

Das nächste Feature, das Sie ausprobieren werden, ist die Funktion **Extract Tags** zum Extrahieren von Tags. Das Extrahieren von Tags basiert auf Tausenden erkennbaren Objekten, einschließlich Lebewesen, Landschaften und Aktionen.

1. Kehren Sie zur Startseite von Vision Studio zurück, und wählen Sie dann die Kachel **Extract common tags from images** unter der Registerkarte **Image analysis** aus.

2. Lassen Sie unter **Choose the model you want to try out** die Option **Prebuilt product vs. gap model** ausgewählt. Wählen Sie unter **Choose your language** die Sprache **Englisch** oder eine Sprache Ihrer Wahl aus.

3. Öffnen Sie den Ordner, der die Bilder enthält, die Sie heruntergeladen haben, und suchen Sie die Datei **store-image-2.jpg**, die wie folgt aussieht:

    ![Abbildung einer Person mit Einkaufswagen in einem Supermarkt](./media/analyze-images-vision/store-camera-2.jpg)

4. Laden Sie die Datei **store-camera-2.jpg** hoch.

5. Überprüfen Sie die Liste der aus dem Bild extrahierten Tags und die Konfidenzwerte für die einzelnen Tags im Bereich der erkannten Attribute. Hier steht der Konfidenzwert für die Wahrscheinlichkeit, dass der Text für das erkannte Attribut das beschreibt, was tatsächlich auf dem Bild zu sehen ist. Beachten Sie in der Liste der Tags, dass sie nicht nur Objekte, sondern Aktionen wie *shopping*, *selling* und *standing* enthält.

    ![Screenshot des Bereichs „Detect attributes“ in Vision Studio mit Text und Konfidenzwerten neben dem Originalbild.](./media/analyze-images-vision/detect-attributes.png)

## Objekterkennung

In dieser Aufgabe verwenden Sie die Funktion **Object detection** der Bildanalyse. Die Objekterkennung erkennt und extrahiert Begrenzungsrahmen basierend auf Tausenden von erkennbaren Objekten und Lebewesen.

1. Kehren Sie zur Startseite von Vision Studio zurück, und wählen Sie dann die Kachel **Detect common objects in images** unter der Registerkarte **Image analysis** aus.

1. Lassen Sie unter **Choose the model you want to try out** die Option **Prebuilt product vs. gap model** ausgewählt.

1. Öffnen Sie den Ordner, der die heruntergeladenen Bilder enthält, und suchen Sie die Datei **store-camera-3.jpg**, die wie folgt aussieht:

    ![Abbildung einer Person mit Einkaufswagen](./media/analyze-images-vision/store-camera-3.jpg)

1. Laden Sie die Datei **store-camera-3.jpg** hoch.

1. Beobachten Sie im Feld **Detected attributes** die Liste erkannter Objekte und deren Konfidenzwerte.

1. Zeigen Sie mit dem Mauszeiger auf die Objekte in der Liste **Detected attributes**, um den Begrenzungsrahmen des Objekts im Bild hervorzuheben.

1. Verschieben Sie den Schieberegler **Threshold value**, bis der Wert 70 rechts neben dem Schieberegler angezeigt wird. Beobachten Sie, was mit den Objekten in der Liste geschieht. Der Schieberegler für den Schwellenwert legt fest, dass nur Objekte angezeigt werden sollen, deren Konfidenzwert oder Wahrscheinlichkeit größer als der Schwellenwert ist.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1.  Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben. 
1.  Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Azure KI Vision](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
