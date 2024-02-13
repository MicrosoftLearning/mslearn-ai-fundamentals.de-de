---
lab:
  title: Erkunden von Speech Studio
---

# Erkunden von Speech Studio

Der **Azure KI Speech** Dienst transkribiert Sprache in Text und wandelt Text in hörbare Sprache um. Sie könnten Azure KI Speech verwenden, um eine Anwendung zu erstellen, die Besprechungsnotizen transkribiert oder Text aus der Aufnahme von Interviews generiert.

In dieser Übung testen Sie die Funktionen von Azure KI Speech mit Azure KI Speech Studio. 

## Erstellen einer *Azure KI Speech*-Ressource

Sie können den Speech-Dienst nutzen, indem Sie entweder eine Ressource **Speech** oder eine Ressource für **Azure KI Services** erstellen.

In dieser Übung erstellen Sie eine Azure KI Speech-Ressource, es sei denn, Sie verfügen bereits über eine Ressource, die Sie verwenden können.

1. Öffnen Sie in einem anderen Browsertab [Azure KI Speech Studio](https://speech.microsoft.com/) und melden Sie sich mit Ihrem Microsoft-Konto an.

1. Wählen Sie **Einstellungen** und dann **Ressource erstellen** aus. Konfigurieren Sie sie mit den folgenden Einstellungen:
    - **Name der neuen Ressource**: *Geben Sie einen eindeutigen Namen ein.*
    - **Abonnement**: *Ihr Azure-Abonnement*.
    - **Region:** *Wählen Sie eine [unterstützte Region](https://learn.microsoft.com/azure/ai-services/speech-service/regions) aus*.
    - **Tarif**: *Free FO (falls verfügbar, andernfalls Standard S0)*.
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine Ressourcengruppe mit einem eindeutigen Namen*.
1. Klicken Sie auf **Ressource erstellen**. Warten Sie, bis die Ressource erstellt wurde, und wählen Sie dann **Ressource verwenden** aus. Die Seite „Erste Schritte mit Speech“ wird angezeigt.

## Erkunden der Spracherkennung in Speech Studio

1. Wählen Sie [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) aus, um **speech.zip** herunterzuladen. Öffnen Sie den Ordner . 

1. Suchen Sie auf der Seite „Erste Schritte mit Speech“ unter *Spracherkennung* nach *Echtzeit-Spracherkennung*. Wählen Sie **Erkunden der Echtzeit-Spracherkennung** aus.

    ![Erste Schritte mit Speech](media/recognize-synthesize-speech/try-out-speech-to-text.png)

1. Wählen Sie unter *Audiodateien auswählen* **Dateien durchsuchen** aus und navigieren Sie zu dem Ordner, in dem Sie die Datei gespeichert haben. Wählen Sie **WhatAICanDo.m4a** und dann **Öffnen** aus.

    ![Dateien durchsuchen](media/recognize-synthesize-speech/browse-files-speech.png)

1. Der Speech-Dienst transkribiert und zeigt den Text in Echtzeit an. Wenn Ihr Computer Lautsprecher hat, können Sie die Aufzeichnung anhören, während der Text transkribiert wird.
1. Überprüfen Sie die Ausgabe. Der Text sollte erfolgreich erkannt und transkribiert worden sein.

    > **Hinweis**: Wenn eine Fehlermeldung angezeigt wird, warten Sie einige Minuten, bevor Sie es erneut versuchen. Es dauert etwas, bis die Speech-Ressource für die erste Verwendung verfügbar ist.

In dieser Übung haben Sie eine Azure KI Speech-Ressource in Speech Studio erstellt. Anschließend haben Sie die Echtzeit-Spracherkennung verwendet, um eine Audioaufzeichnung zu transkribieren. Sie konnten sehen, wie die Texttranskription generiert wurde, während die Audiodatei wiedergegeben wurde.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

In dieser Übung wurden nur einige der Funktionen von Azure KI Speech Service veranschaulicht. Weitere Informationen über die Möglichkeiten dieses Diensts finden Sie auf der Seite [Sprachdienste](https://azure.microsoft.com/services/cognitive-services/speech-services).
