---
lab:
  title: Erkunden von Speech im Azure AI Foundry-Portal
---

# Erkunden von Speech im Azure AI Foundry-Portal

Der **Azure KI Speech** Dienst transkribiert Sprache in Text und wandelt Text in hörbare Sprache um. Sie könnten Azure KI Speech verwenden, um eine Anwendung zu erstellen, die Besprechungsnotizen transkribiert oder Text aus der Aufnahme von Interviews generiert.

In dieser Übung verwenden Sie Azure KI Speech im Azure AI Foundry-Portal, der Plattform von Microsoft zur Erstellung intelligenter Anwendungen, um Audio mithilfe der integrierten Testfunktionen zu transkribieren. 

## Erstellen eines Projekts im Azure KI Foundry-Portal

Beginnen wir mit dem Erstellen eines Azure AI Foundry-Projekts.

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot der Azure AI Foundry-Startseite mit ausgewählter Option „Agent erstellen“.](./media/azure-ai-foundry-home-page.png)

1. Wählen Sie auf der Startseite **+ Agent erstellen**.

1. Geben Sie im Assistenten **Agent erstellen** einen gültigen Namen für Ihr Projekt ein. 

1. Wählen Sie **Erweiterte Optionen** und nehmen Sie die folgenden Einstellungen vor:
    - **Azure AI Foundry-Ressource**: *Behalten Sie den Standardnamen bei.*
    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
    - **Region**: Wählen Sie einen der folgenden Standorte aus:
        * East US
        * Frankreich, Mitte
        * Korea, Mitte
        * Europa, Westen
        * USA (Westen)

1. Wählen Sie **Erstellen** und überprüfen Sie Ihre Konfiguration. Warten Sie, bis der Einrichtungsvorgang abgeschlossen ist.

    >**Hinweis**: Wenn Sie eine Berechtigungsfehlermeldung erhalten, klicken Sie auf die Schaltfläche **Korrigieren**, um die erforderlichen Berechtigungen hinzuzufügen und fortzufahren.

1. Nach der Erstellung Ihres Projekts werden Sie standardmäßig zum Agents-Playground im Azure AI Foundry-Portal weitergeleitet, der in etwa wie folgt aussieht:

    ![Screenshot eines Azure KI-Projekts im Azure AI Foundry-Portal.](./media/ai-foundry-project-2.png)
 
1. Wählen Sie im Menü auf der linken Seite des Bildschirms **Playgrounds**.

1. Wählen Sie auf der Seite *Playgrounds* die Kachel **Speech-Playground** aus, um einige Azure KI Speech-Funktionen auszuprobieren.

## Erkunden von Spracherkennung im Speech-Playground von Azure AI Foundry

Probieren wir die *Spracherkennung* im Speech-Playground von Azure AI Foundry aus. 

1. Scrollen Sie auf der Seite *Speech* nach unten und wählen Sie **Echtzeit-Transkription** unter *Sprachfunktionen ausprobieren*. Sie werden zum *Speech-Playground* weitergeleitet. 

1. Wählen Sie [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) aus, um **speech.zip** herunterzuladen. Öffnen Sie den Ordner . 

1. Wählen Sie unter *Dateien hochladen* die Option **Dateien durchsuchen** und navigieren Sie zu dem Ordner, in dem Sie die Datei gespeichert haben. Wählen Sie **WhatAICanDo.m4a** und dann **Öffnen** aus.

    ![Dateien durchsuchen](media/recognize-synthesize-speech/browse-files-speech.png)

1. Der Speech-Dienst transkribiert und zeigt den Text in Echtzeit an. Wenn Ihr Computer Lautsprecher hat, können Sie die Aufzeichnung anhören, während der Text transkribiert wird.

1. Überprüfen Sie die Ausgabe. Der Text sollte erfolgreich erkannt und transkribiert worden sein.

In dieser Übung haben Sie Azure KI Speech-Dienste im Speech-Playground von Azure AI Foundry ausprobiert. Anschließend haben Sie die Echtzeittranskription verwendet, um eine Audioaufzeichnung zu transkribieren. Sie konnten sehen, wie die Texttranskription generiert wurde, während die Audiodatei wiedergegeben wurde.

## Bereinigen

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige von vielen Funktionen des Sprachdienstes veranschaulicht. Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Sprachdienste](https://azure.microsoft.com/services/cognitive-services/speech-services).
