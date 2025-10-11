---
lab:
  title: Erkunden von Spracherkennung im Azure AI Foundry-Portal
---

# Erkunden von Spracherkennung im Azure AI Foundry-Portal

Azure KI Speech transkribiert Sprache in Text und wandelt Text in hörbare Sprache um. Sie können KI Speech verwenden, um eine Anwendung zu erstellen, die Besprechungsnotizen transkribieren oder Text aus Gesprächsaufzeichnungen generieren kann, oder um einen interaktiven KI-Assistenten zu unterstützen, der auf gesprochene Befehle und Fragen reagieren kann.

In dieser Übung verwenden Sie Azure KI Speech im Azure AI Foundry-Portal, der Plattform von Microsoft zum Erstellen intelligenter Anwendungen, um die wichtigsten Funktionen von Azure KI Speech zu erkunden. 

Diese Übung dauert ca. **15** Minuten.

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Öffnen Sie in einem Webbrowser unter `https://ai.azure.com` das [Azure KI Foundry-Portal](https://ai.azure.com) und melden Sie sich mit Ihren Azure-Anmeldeinformationen an. Schließen Sie alle Tipps oder Schnellstartfenster, die bei der ersten Anmeldung geöffnet werden, und verwenden Sie gegebenenfalls das Logo **Azure AI Foundry** oben links, um zur Startseite zu navigieren, die ähnlich wie die folgende Abbildung aussieht (schließen Sie das **Hilfe**-Fenster, falls es geöffnet ist):

    ![Screenshot: Startseite des Azure AI Foundry-Portals](./media/ai-foundry-portal.png)

1. Scrollen Sie auf der Seite nach unten, und wählen Sie die Kachel **Azure KI Services erkunden** aus.

    ![Screenshot: Kachel „Azure KI Services erkunden“](./media/ai-services.png)

1. Wählen Sie auf der Seite „Azure KI Services“ die Kachel **Speech** aus.

    ![Screenshot: Kachel „Speech“](./media/speech.png)

1. Wählen Sie auf der Seite **Speech** die Option **Zum Speech-Playground wechseln** aus. Erstellen Sie dann ein neues Projekt mit den folgenden Einstellungen, wenn Sie dazu aufgefordert werden:
    - **Projektname:** *Geben Sie einen gültigen Namen für Ihr Projekt ein.*
    - **Erweiterte Einstellungen**:
        - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
        - **Ressourcengruppe**: *Erstellen Sie eine Ressourcengruppe, oder wählen Sie eine Ressourcengruppe aus*.
        - **Region:** *Wählen Sie eine **empfohlene AI Foundry**-Region aus.*
        - **AI Foundry oder Azure OpenAI** *Erstellen Sie eine neue Azure AI Foundry-Ressource mit einem gültigen Namen.*

1. Klicken Sie auf **Erstellen**. Warten Sie, bis Ihr Projekt erstellt wurde. Dies kann einige Minuten dauern.

1. Wenn das Projekt erstellt wird, gelangen Sie zu einem **Speech**-Playground (falls nicht, wählen Sie im Aufgabenbereich auf der linken Seite **Playgrounds** aus, und öffnen Sie den Speech-Playground von dort aus.)

    Der Speech-Playground ist eine Benutzeroberfläche, auf der Sie einige Azure KI Speech-Funktionen ausprobieren können.  

## Erkunden von Spracherkennung im Speech-Playground von Azure AI Foundry

Probieren wir die *Spracherkennung* im Speech-Playground von Azure AI Foundry aus.

1. Laden Sie auf einer neuen Browserregisterkarte die Datei **[speech.zip](https://aka.ms/mslearn-speech-files)** von `https://aka.ms/mslearn-speech-files` herunter. Extrahieren Sie die heruntergeladene Datei in einen lokalen Ordner. 

1. Kehren Sie zum Azure AI Foundry-Portal zurück, und wählen Sie auf der Registerkarte **Spracherkennung** der Seite „Speech“ die Option **Echtzeittranskription** aus.

1. Wählen Sie unter **Dateien hochladen** die Option **Dateien durchsuchen** aus, und laden Sie die Datei **WhatAICanDo.m4a** aus dem Ordner hoch, den Sie zuvor zum Herunterladen und Extrahieren verwendet haben.

    Der Speech-Dienst transkribiert und zeigt den Text in Echtzeit an. Wenn Ihr Computer Lautsprecher hat, können Sie die Aufzeichnung anhören, während der Text transkribiert wird.

    ![Screenshot: Benutzeroberfläche „Echtzeittranskription“ im Speech-Playground](./media/real-time-transcription.png)

1. Überprüfen Sie die Ausgabe. 

    >*Tipp*: Um die vollständige Ausgabe anzuzeigen, müssen Sie möglicherweise den Bereich *Konfigurieren* minimieren. Um ihn zu minimieren, wählen Sie das Symbol rechts neben der Überschrift *Konfigurieren* aus.

    Sie können in der Ausgabe unter **Text** das in Text transkribierte Audio sehen.

## Erkunden der Sprachsynthese im Speech-Playground von Azure AI Foundry

Sehen wir uns nun an, wie Azure KI Speech hörbare Sprache aus Text generieren kann.

1. Wählen Sie im Speech-Playground die Registerkarte **Sprachsynthese** aus, und stellen Sie sicher, dass **Voice-Katalog** ausgewählt ist.
1. Zeigen Sie die verfügbaren Stimmen an, und wählen Sie eine aus (z. B. *Ava Multilingual*).
1. Wählen Sie im Bereich **Stimmdetails** die Registerkarte **Ausprobieren** aus. Geben Sie anschließend einen Text ein (z. B. `The rain in Spain stays mainly in the plain`), und verwenden Sie die Schaltfläche **Wiedergeben**, um Sprache aus dem Text zu synthetisieren.

    ![Screenshot: Benutzeroberfläche „Voice-Katalog“ im Speech-Playground](./media/voice-gallery.png)

    Der Text wird mit der ausgewählten Stimme gesprochen. Sie können andere Stimmen ausprobieren, um die gesprochene Ausgabe zu vergleichen.

## Bereinigen

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie **Ressourcengruppe löschen** aus, und **geben Sie zur Bestätigung den Namen der Ressourcengruppe ein**. Die Ressourcengruppe wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige von vielen Funktionen des Sprachdienstes veranschaulicht. Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Sprachdienste](https://azure.microsoft.com/services/cognitive-services/speech-services).
