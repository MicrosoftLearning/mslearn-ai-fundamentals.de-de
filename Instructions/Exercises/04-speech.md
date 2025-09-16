---
lab:
  title: Erkunden von Spracherkennung im Azure AI Foundry-Portal
---

# Erkunden von Spracherkennung im Azure AI Foundry-Portal

Der **Azure KI Speech** Dienst transkribiert Sprache in Text und wandelt Text in hörbare Sprache um. Sie könnten Azure KI Speech verwenden, um eine Anwendung zu erstellen, die Besprechungsnotizen transkribiert oder Text aus der Aufnahme von Interviews generiert.

In dieser Übung verwenden Sie Azure KI Speech im Azure AI Foundry-Portal, der Plattform von Microsoft zur Erstellung intelligenter Anwendungen, um Audio mithilfe der integrierten Testfunktionen zu transkribieren. 

Diese Übung dauert ca. **15** Minuten.

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartbereiche, die bei der ersten Anmeldung angezeigt werden. 

1. Navigieren Sie im Browser zu `https://ai.azure.com/managementCenter/allResources`, und wählen Sie **Neu erstellen** aus. Wählen Sie anschließend die Option zum Erstellen einer **Azure AI Foundry-Ressource** aus.

1. Geben Sie im Assistenten *Projekt erstellen* einen gültigen Namen für Ihr Projekt ein.

1. Erweitern Sie *Erweiterte Optionen*, um folgende Einstellungen vorzunehmen:
    - **Abonnement**: Ihr Azure-Abonnement
    - **Ressourcengruppe**: Erstellen oder wählen Sie eine Ressourcengruppe aus.
    - **Region**: Wählen Sie einen der folgenden Standorte aus:
        * East US
        * Frankreich, Mitte
        * Korea, Mitte
        * Europa, Westen
        * USA (Westen)

    Klicken Sie auf **Erstellen**. Warten Sie, bis Ihr Projekt erstellt wurde. Dies kann einige Minuten dauern.

1. Wenn das Projekt erstellt wird, gelangen Sie zu einer *Übersichtsseite* der Projektdetails.
 
1. Wählen Sie im Menü auf der linken Seite des Bildschirms **Playgrounds**.

    >*Hinweis:* Erweitern Sie zum Lesen des Inhalts das Menü, indem Sie oben auf das Symbol „Erweitern“ klicken.

1. Wählen Sie auf der Seite „Playgrounds“ von Azure AI Foundry die Option **Speech-Playground testen**. Der Speech-Playground ist eine Benutzeroberfläche, auf der Sie einige Azure KI Speech-Funktionen ausprobieren können.

## Erkunden von Spracherkennung im Speech-Playground von Azure AI Foundry

Probieren wir die *Spracherkennung* im Speech-Playground von Azure AI Foundry aus. 

1. Scrollen Sie auf der Seite *Sprache* nach unten und wählen Sie **Echtzeittranskription** aus.

1. Laden Sie **speech.zip** herunter, indem Sie die URL `https://aka.ms/mslearn-speech-files` auf einer neuen Browserregisterkarte öffnen. Die Verwendung der URL sollte automatisch einen Ordner auf Ihren Computer herunterladen. 

1. Navigieren Sie zum Ordner *Downloads* auf Ihrem Computer und suchen Sie dann den heruntergeladenen Ordner. Klicken Sie mit der rechten Maustaste auf den heruntergeladenen Ordner. Wählen Sie *Alle extrahieren…* aus. Wählen Sie dann *Extrahieren* aus, um den Inhalt zu entpacken. Der entpackte Ordner wird am Bildschirm angezeigt. Schließen Sie den entpackten Ordner. Beachten Sie, dass sich der entpackte Ordner jetzt auch im Ordner *Downloads* befindet.    

1. Wählen Sie im Azure AI Foundry Speech-Portal unter *Dateien hochladen* die Option **Dateien durchsuchen** aus. Navigieren Sie im entpackten Ordner. Wählen Sie **WhatAICanDo.m4a** und dann **Öffnen** aus.

    ![Dateien durchsuchen](media/recognize-synthesize-speech/browse-files-speech.png)

1. Der Speech-Dienst transkribiert und zeigt den Text in Echtzeit an. Wenn Ihr Computer Lautsprecher hat, können Sie die Aufzeichnung anhören, während der Text transkribiert wird.

1. Überprüfen Sie die Ausgabe. 

    >*Hinweis:* Um die vollständige Ausgabe anzuzeigen, müssen Sie möglicherweise den Bereich *Konfigurieren* minimieren. Um ihn zu minimieren, wählen Sie das Symbol rechts neben der Überschrift *Konfigurieren* aus.

1. Sie können in der Ausgabe unter *Text* das in Text transkribierte Audio sehen. 

In dieser Übung haben Sie Azure KI Speech-Dienste im Speech-Playground von Azure AI Foundry ausprobiert. Anschließend haben Sie die Echtzeittranskription verwendet, um eine Audioaufzeichnung zu transkribieren. Sie konnten sehen, wie die Texttranskription generiert wurde, während die Audiodatei wiedergegeben wurde.

## Bereinigen

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige von vielen Funktionen des Sprachdienstes veranschaulicht. Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Sprachdienste](https://azure.microsoft.com/services/cognitive-services/speech-services).
