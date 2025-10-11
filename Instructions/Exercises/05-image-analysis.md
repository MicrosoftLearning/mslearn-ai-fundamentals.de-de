---
lab:
  title: Analysieren von Bildern im Azure AI Foundry-Portal
---

# Analysieren von Bildern im Azure AI Foundry-Portal

**Azure KI Vision** umfasst zahlreiche Funktionen zum Verständnis von Bildinhalten und Kontext sowie zum Extrahieren von Informationen aus Bildern. In dieser Übung verwenden Sie Azure KI Vision im Azure AI Foundry-Portal, die Plattform von Microsoft zum Erstellen intelligenter Anwendungen, um Bilder mithilfe der integrierten Try-it-out-Erfahrungen zu analysieren. 

Angenommen, das fiktive Einzelhandelsunternehmen *Northwind Traders* möchte einen „Smart Store“ implementieren, der von KI überwacht wird, um zu identifizieren, welche Kunden Unterstützung benötigen, und Mitarbeiter*innen zu diesen Kunden zu schicken. Mit Azure KI Vision können Bilder von den Kameras im Geschäft analysiert und aussagekräftige Beschreibungen der Bilder generiert werden.

Diese Übung dauert ca. **20** Minuten.

## Herunterladen und Extrahieren von Bilddateien

1. Laden Sie **[image-analysis.zip](https://aka.ms/mslearn-images-for-analysis)** unter `https://aka.ms/mslearn-images-for-analysis` herunter.
1. Extrahieren Sie die heruntergeladene ZIP-Datei in einen Ordner auf Ihrem Computer.

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot: Startseite des Azure AI Foundry-Portals](./media/ai-foundry-portal.png)

1. Scrollen Sie auf der Seite nach unten, und wählen Sie die Kachel **Azure KI Services erkunden** aus.

    ![Screenshot: Kachel „Azure KI Services erkunden“](./media/ai-services.png)

1. Wählen Sie auf der Seite „Azure KI Services“ die Kachel **Vision + Dokument** aus.

    ![Screenshot: Kachel „Vision + Dokument“](./media/vision-tile.png)

1. Zeigen Sie auf der Seite **Vision + Dokument** die Registerkarte **Bild** an, und wählen Sie die Kachel **Bildbeschriftung** aus.

    ![Screenshot: Kachel „Bildbeschriftung“](./media/image-captioning-tile.png)

1. Verwenden Sie im Bereich **Bildern Beschriftungen hinzufügen** die Schaltfläche **Hub auswählen**, um mit den folgenden Einstellungen **einen neuen Hub zu erstellen**:
    - **Hubname**: *Geben Sie einen gültigen Namen für den Hub ein.*
    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
    - **Speicherort:** *Wählen Sie einen der folgenden Standorte aus*/*:
        - East US
        - Frankreich, Mitte
        - Korea, Mitte
        - Europa, Westen
        - USA (Westen)
    - **Azure KI Services verbinden**: *Erstellen einer neuen Azure KI Services-Ressource mit einem gültigen Namen*
    - **Azure KI-Suche verbinden**: Verbindung überspringen

    \**Zum Zeitpunkt der Artikelerstellung wird Azure KI Vision in Hubs in diesem Regionen unterstützt.*

1. Wenn der Hub erstellt wird, werden Sie aufgefordert, ein Projekt zu erstellen. Geben Sie einen geeigneten Projektnamen ein, und wählen Sie **Projekt erstellen** aus.

## Generieren von Beschriftungen für Bilder

Lassen Sie uns die Bildbeschriftungsfunktion von Azure KI Vision nutzen, um Bilder zu analysieren, die von einer Kamera im Geschäft *Northwind Traders* aufgenommen wurden. Bildbeschriftungen sind über die Features **Caption** und **Dense Captions** von Image Analysis 4.0 verfügbar.

1. Wählen Sie im Aufgabenbereich auf der linken Seite **KI Services** aus.

    *Jetzt müssen Sie die zuvor ausgeführten Schritte wiederholen, um zur Oberfläche für die Bildbeschriftung zurückzukehren und Ihr neues hubbasiertes Projekt zu verwenden.*

1. Wählen Sie auf der Seite **KI Services** die Kachel **Vision + Dokument** aus. Wählen Sie dann auf der Seite **Vision + Dokument** auf der Registerkarte **Bild** die Kachel **Bildbeschriftung** aus.

1. Vergewissern Sie sich auf der Seite **Bildern Beschriftungen hinzufügen** im Auswahlmenü *Verbundene Azure KI Services*, dass die Azure KI Services-Ressource ausgewählt ist, die Sie in Ihrem Hub erstellt haben.

1. Laden Sie über den Link **Nach einer Datei suchen** das Bild **store-camera-1.jpg** aus dem Dateien hoch, die Sie zuvor heruntergeladen und extrahiert haben.

1. Beobachten Sie den generierten Beschriftungstext, der im Bereich **Detected attributes** rechts neben dem Bild sichtbar ist.

    ![Screenshot: Seite „Bildern Beschriftungen hinzufügen“ mit einem analysierten Bild](./media/image-captioning.png)

    Die Funktion **Caption** liefert einen einzelnen, von Menschen lesbaren englischen Satz, der den Inhalt des Bildes beschreibt.

1. Verwenden Sie als Nächstes dasselbe Bild, um die Funktion **Dense captioning** auszuführen. Kehren Sie zurück zur Seite **Vision + Dokument**, indem Sie oben auf der Seite den Pfeil **&larr;** *Zurück* und dann auf der Seite **Vision + Dokument** auf der Seite **Bild** die Kachel **Dichte Beschriftung** auswählen.

    Die Funktion **Dense Captions** unterscheidet sich von der Funktion **Caption** darin, dass sie mehrere lesbare Beschriftungen für ein Bild bereitstellt, von denen eine den Inhalt des Bildes beschreibt und die anderen jeweils die wichtigsten im Bild erkannten Objekte abdecken. Zu jedem erkannten Objekt gehört ein Begrenzungsrahmen, der die dem Objekt zugeordneten Pixelkoordinaten innerhalb des Bildes definiert.

1. Laden Sie das Bild **store-camera-1.jpg** erneut hoch, und zeigen Sie die Ergebnisse der dichten Beschriftung an.

    ![Screenshot: Ergebnisse der dichten Beschriftung](./media/dense-captioning.png)

    Zeigen Sie mit der Maus auf eine der Beschriftungen in der Liste **Erkannte Attribute**. Sie sehen, dass für jedes im Bild erkannte Objekt eine Beschriftung generiert wird.

## Taggen von Bildern 

Das nächste Feature, das Sie ausprobieren werden, ist die Funktion *Extract Tags* zum Extrahieren von Tags. Das Extrahieren von Tags basiert auf Tausenden erkennbaren Objekten, einschließlich Lebewesen, Landschaften und Aktionen.

1. Kehren Sie zur Seite **Vision + Dokument** zurück, indem Sie oben auf der Seite den Pfeil **&larr;** *Zurück* auswählen. Wählen Sie dann auf der Seite **Vision + Dokument** auf der Registerkarte **Bild** die Kachel **Gemeinsame Tag-Extraktion** aus.
1. Laden Sie die Datei **store-camera-2.jpg** aus dem Ordner hoch, den Sie zuvor extrahiert haben.
1. Überprüfen Sie die Liste der aus dem Bild extrahierten Tags und die Konfidenzwerte für die einzelnen Tags im Bereich der erkannten Attribute. Hier steht der Konfidenzwert für die Wahrscheinlichkeit, dass der Text für das erkannte Attribut das beschreibt, was tatsächlich auf dem Bild zu sehen ist. Beachten Sie in der Liste der Tags, dass sie nicht nur Objekte, sondern Aktionen wie *shopping*, *selling* und *standing* enthält.

    ![Screenshot des Bereichs „Detect attributes“ in Vision Studio mit Text und Konfidenzwerten neben dem Originalbild.](./media/analyze-images-vision/detect-attributes.png)

## Objekterkennung

In dieser Aufgabe verwenden Sie die Funktion **Object detection** der Bildanalyse. Die Objekterkennung erkennt und extrahiert Begrenzungsrahmen basierend auf Tausenden von erkennbaren Objekten und Lebewesen.

1. Kehren Sie zur Seite **Vision + Dokument** zurück, indem Sie oben auf der Seite den Pfeil **&larr;** *Zurück* auswählen. Wählen Sie dann auf der Registerkarte **Bild** die Kachel **Allgemeine Objekterkennung** aus.

1. Laden Sie die Datei **store-camera-3.jpg** hoch.

1. Beobachten Sie im Feld **Detected attributes** die Liste erkannter Objekte und deren Konfidenzwerte.

    ![Screenshot: Ergebnisse der dichten Beschriftung](./media/object-detection.png)

1. Versuchen Sie, die Objekte in **store-camera-4.jpg** zu erkennen.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressourcen enthält, die Sie erstellt haben. 
1. Wählen Sie **Ressourcengruppe löschen** aus, und geben Sie dann zur Bestätigung **den Namen der Ressourcengruppe** ein. Die Ressourcengruppe wird dann gelöscht.

## Weitere Informationen

Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Azure KI Vision](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
