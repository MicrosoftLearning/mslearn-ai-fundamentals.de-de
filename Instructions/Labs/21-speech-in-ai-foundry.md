---
lab:
  title: Erkunden von Speech im Azure AI Foundry-Portal
---

# Erkunden von Speech im Azure AI Foundry-Portal

Der **Azure KI Speech** Dienst transkribiert Sprache in Text und wandelt Text in hörbare Sprache um. Sie könnten Azure KI Speech verwenden, um eine Anwendung zu erstellen, die Besprechungsnotizen transkribiert oder Text aus der Aufnahme von Interviews generiert.

In dieser Übung verwenden Sie Azure KI Speech im Azure AI Foundry-Portal, der Plattform von Microsoft zur Erstellung intelligenter Anwendungen, um Audio mithilfe der integrierten Testfunktionen zu transkribieren. 

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Navigieren Sie auf einer Browserregisterkarte zu [Azure AI Foundry](https://ai.azure.com?azure-portal=true).

1. Melden Sie sich mit Ihrem Konto an. 

1. Wählen Sie auf der Startseite des Azure AI Foundry-Portals die Option **Projekt erstellen** aus. In Azure AI Foundry sind Projekte Container, die Ihnen beim Organisieren Ihrer Arbeit helfen.  

    ![Screenshot der Startseite von Azure AI Foundry mit ausgewähltem „Projekt erstellen“.](./media/azure-ai-foundry-home-page.png)

1. Im Bereich *Projekt erstellen* sehen Sie einen generierten Projektnamen, den Sie so beibehalten können. Je nachdem, ob Sie in der Vergangenheit einen Hub erstellt haben, wird entweder eine Liste der zu erstellenden *neuen* Azure-Ressourcen oder eine Dropdownliste vorhandener Hubs angezeigt. Wenn Sie die Dropdown-Liste der vorhandenen Hubs sehen, wählen Sie *Neuen Hub erstellen*, erstellen Sie einen eindeutigen Namen für Ihren Hub und wählen Sie *Weiter*.  
 
    ![Screenshot des Erstellens eines Projektbereichs mit automatisch generierten Namen für Hub und Projekt.](./media/azure-ai-foundry-create-project.png)

> **Wichtig**: Sie benötigen eine Azure KI Services-Ressource, die an einem bestimmten Ort bereitgestellt wird, um den Rest des Labs durchzuführen.

1. Wählen Sie im gleichen Fenster *Projekt erstellen* die Option **Anpassen** und wählen Sie einen der folgenden **Standorte**: USA, Osten, Frankreich, Mitte, Südkorea, Mitte, Europa, Westen oder USA, Westen, um den Rest des Labs zu vervollständigen. Wählen Sie dann **Erstellen** aus. 

1. Notieren Sie sich die erstellten Ressourcen: 
- Azure KI Services
- Azure KI-Hub
- Azure KI-Projekt
- Speicherkonto
- Key vault
- Ressourcengruppe  
 
1. Nachdem die Ressourcen erstellt wurden, gelangen Sie auf die Seite *Übersicht* Ihres Projekts. Wählen Sie im Menü auf der linken Seite des Bildschirms **KI Services**.
 
    ![Screenshot des linken Menüs auf dem Projektbildschirm, auf dem „KI Services“ ausgewählt ist.](./media/azure-ai-foundry-ai-services.png)  

1. Wählen Sie auf der Seite *KI Services* die Kachel *Speech*, um die Azure KI Speech-Funktionen zu testen.

    ![Screenshot mit ausgewählter Kachel „Speech“ auf der KI Services-Seite.](./media/speech-tile.png)

## Erkunden von Spracherkennung im Speech-Playground von Azure AI Foundry

Probieren wir die *Echtzeit-Spracherkennung* im Speech-Playground von Azure AI Foundry aus. 

1. Scrollen Sie auf der Seite *Speech* nach unten und wählen Sie **Echtzeit-Spracherkennung** unter *Sprachfunktionen ausprobieren*. Sie werden zum *Speech-Playground* weitergeleitet. 

1. Wählen Sie [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) aus, um **speech.zip** herunterzuladen. Öffnen Sie den Ordner . 

1. Wählen Sie unter *Dateien hochladen* die Option **Dateien durchsuchen** und navigieren Sie zu dem Ordner, in dem Sie die Datei gespeichert haben. Wählen Sie **WhatAICanDo.m4a** und dann **Öffnen** aus.

    ![Dateien durchsuchen](media/recognize-synthesize-speech/browse-files-speech.png)

1. Der Speech-Dienst transkribiert und zeigt den Text in Echtzeit an. Wenn Ihr Computer Lautsprecher hat, können Sie die Aufzeichnung anhören, während der Text transkribiert wird.

1. Überprüfen Sie die Ausgabe. Der Text sollte erfolgreich erkannt und transkribiert worden sein.

In dieser Übung haben Sie Azure KI Speech-Dienste im Speech-Playground von Azure AI Foundry ausprobiert. Anschließend haben Sie die Echtzeit-Spracherkennung verwendet, um eine Audioaufzeichnung zu transkribieren. Sie konnten sehen, wie die Texttranskription generiert wurde, während die Audiodatei wiedergegeben wurde.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige der Funktionen von Azure KI Speech Service veranschaulicht. Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Sprachdienste](https://azure.microsoft.com/services/cognitive-services/speech-services).
