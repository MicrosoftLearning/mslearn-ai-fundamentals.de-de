---
lab:
  title: "Erkunden von Inhaltssicherheit in Azure\_AI Foundry"
---

# Erkunden von Inhaltssicherheit in Azure AI Foundry

Mit Azure KI Services können Benutzer*innen KI-Anwendungen mit sofort einsatzbereiten, vorgefertigten und anpassbaren APIs und Modellen erstellen. In dieser Übung werfen Sie einen Blick auf einen der Dienste, Azure KI Inhaltssicherheit, mit dem Sie Text- und Bildinhalte moderieren können. Im Azure AI Foundry-Portal, der Plattform von Microsoft zur Erstellung intelligenter Anwendungen, verwenden Sie Azure KI Inhaltssicherheit, um Text zu kategorisieren und ihm eine Schweregradbewertung zuzuweisen. 

> **Hinweis**: Das Ziel dieser Übung besteht darin, ein allgemeines Verständnis dafür zu gewinnen, wie Azure KI Services bereitgestellt und verwendet werden. Content Safety wird als Beispiel verwendet, aber es wird nicht erwartet, dass Sie in dieser Übung ein umfassendes Wissen über Content Safety erwerben!

## Erstellen eines Projekts im Azure KI Foundry-Portal

1. Navigieren Sie in einem Browserregisterkarte zum [Azure AI Foundry-Portal](https://ai.azure.com?azure-portal=true).

2. Melden Sie sich mit Ihrem Konto an. 

3. Wählen Sie auf der Startseite des Azure AI Foundry-Portals die Option **Projekt erstellen** aus. In Azure AI Foundry sind Projekte Container, die Ihnen beim Organisieren Ihrer Arbeit helfen.  

    ![Screenshot der Startseite von Azure AI Foundry mit ausgewähltem „Projekt erstellen“.](./media/azure-ai-foundry-home-page.png)

4. Im Bereich *Projekt erstellen* sehen Sie einen generierten Projektnamen, den Sie so beibehalten können. Je nachdem, ob Sie in der Vergangenheit einen Hub erstellt haben, wird entweder eine Liste der zu erstellenden *neuen* Azure-Ressourcen oder eine Dropdownliste vorhandener Hubs angezeigt. Wenn Sie die Dropdown-Liste der vorhandenen Hubs sehen, wählen Sie *Neuen Hub erstellen*, erstellen Sie einen eindeutigen Namen für Ihren Hub und wählen Sie *Weiter*.  
 
    ![Screenshot des Erstellens eines Projektbereichs mit automatisch generierten Namen für Hub und Projekt.](./media/azure-ai-foundry-create-project.png)

> **Wichtig**: Sie benötigen eine Azure KI Services-Ressource, die an einem bestimmten Ort bereitgestellt wird, um den Rest des Labs durchzuführen.

5. Wählen Sie im gleichen Fenster *Projekt erstellen* die Option **Anpassen** und wählen Sie einen der folgenden **Standorte**: USA, Osten, Frankreich, Mitte, Südkorea, Mitte, Europa, Westen oder USA, Westen, um den Rest des Labs zu vervollständigen. Wählen Sie dann **Erstellen** aus. 

1. Notieren Sie sich die erstellten Ressourcen: 
- Azure KI Services
- Azure KI-Hub
- Azure KI-Projekt
- Speicherkonto
- Key vault
- Ressourcengruppe  

6. Nachdem die Ressourcen erstellt wurden, gelangen Sie auf die Seite *Übersicht* Ihres Projekts. 

7. Um Inhaltssicherheit zu verwenden, müssen Sie eine Berechtigungsaktualisierung für Ihre *Azure KI-Hubressource* vornehmen. Öffnen Sie dazu die [Azure-Portal](https://portal.azure.com?portal-azure=true), und melden Sie sich mit demselben Abonnement an, mit dem Sie Ihre AI Foundry-Ressourcen erstellt haben.  

8. Verwenden Sie im Azure-Portal die Suchleiste oben auf der Seite, um nach **Azure AI Foundry** zu suchen und diese auszuwählen. Wählen Sie auf der Ressourcenseite die Ressource aus, die Sie gerade erstellt haben und die vom *Typ*** Azure KI-Hub** ist.  

9. Wählen Sie im Azure-Portal auf der linken Seite **Zugriffssteuerung (IAM)** aus. Wählen Sie dann im geöffneten Bereich neben dem Pluszeichen **Hinzufügen** und anschließend **Rollenzuweisung hinzufügen** aus. 

![Screenshot: Auswählen von „Rollenzuweisung hinzufügen“ im Access Control-Bereich](./media/content-safety/access-control-step-one.png)

10. Suchen Sie in der Liste der Rollen nach **Azure AI Safety Evaluator** und wählen Sie diese aus. Wählen Sie **Weiter**aus. 

11. Verwenden Sie die folgenden Einstellungen, um sich die Rolle zuzuweisen: 
    - **Zugriff zuweisen auf**: Wählen Sie *Benutzer, Gruppe oder Dienstprinzipal* aus.
    - **Mitglieder**: Klicken Sie auf *Mitglieder auswählen*.
        - Suchen Sie im geöffneten Bereich *Mitglieder auswählen* nach Ihrem Namen. Klicken Sie neben Ihrem Namen auf das Pluszeichen. Klicken Sie dann auf **Auswählen**.
    - **Beschreibung**: *Lassen Sie dieses Feld frei.*

12. Wählen Sie **Überprüfen und Zuweisen** und dann erneut **Überprüfen und Zuweisen** aus, um die Rollenzuweisung hinzuzufügen.    

13. Kehren Sie in Ihrem Browser zum [Azure AI Foundry-Portal](https://ai.azure.com?azure-portal=true) zurück. Wählen Sie Ihr Projekt aus. 

14. Wählen Sie im Menü auf der linken Seite des Bildschirms **KI Services**.
 
    ![Screenshot des linken Menüs auf dem Projektbildschirm, auf dem „KI Services“ ausgewählt ist.](./media/azure-ai-foundry-ai-services.png)  

15. Wählen Sie auf der Seite *KI Services* die Kachel *Vision + Dokument*, um die Azure KI Vision- und Dokument-Funktionen zu testen.
    
    ![Screenshot der Kachel „Inhaltssicherheit“.](./media/content-safety-tile.png)

## Testen der Textmoderation mit Inhaltssicherheit im Azure AI Foundry-Portal 

1. Wählen Sie auf der Seite *Inhaltssicherheit* unter *Textinhalt filtern* die Option **Textinhalt moderieren**.

2. Wählen Sie auf der Seite *Textinhalt moderieren* unter der Überschrift *Ausprobieren* die soeben erstellte Azure KI Services-Ressource aus dem Dropdownmenü.   

3. Wählen Sie unter *Einfachen Test durchführen* die Kachel **Sichere Inhalte**. Beachten Sie, dass im Feld darunter Text angezeigt wird. 

4. Klicken Sie auf **Run test**. Wenn Sie einen Test ausführen, wird das Deep Learning-Modell des Content Safety-Diensts aufgerufen. Das Deep Learning-Modell wurde bereits darauf trainiert, unsichere Inhalte zu erkennen.

5. Überprüfen Sie im Bereich *Ergebnisse* die Ergebnisse. Es gibt vier Schweregrade von sicher bis hoch und vier Arten von schädlichen Inhalten. Stuft der Content Safety KI-Dienst dieses Beispiel als akzeptabel ein oder nicht? Wichtig ist, dass die Ergebnisse innerhalb eines Konfidenzintervalls liegen. Ein gut trainiertes Modell, wie eines der vordefinierten Modelle von Azure KI, kann Ergebnisse zurückgeben, die mit hoher Wahrscheinlichkeit dem entsprechen, wie ein Mensch das Ergebnis bezeichnen würde. Jedes Mal, wenn Sie einen Test ausführen, rufen Sie das Modell erneut auf. 

6. Versuchen Sie es mit einem anderen Beispiel. Wählen Sie den Text unter Gewalttätiger Inhalt mit Schreibfehlern aus. Überprüfen Sie, ob der Inhalt im Feld darunter angezeigt wird.

7. Klicken Sie auf **Test ausführen** und überprüfen Sie die Ergebnisse im Ergebnisbereich erneut. 

Sie können Tests für alle bereitgestellten Beispiele ausführen und dann die Ergebnisse überprüfen.

## Bereinigung

Wenn Sie nicht vorhaben, weitere Übungen zu machen, löschen Sie alle Ressourcen, die Sie nicht mehr benötigen. Dadurch werden unnötige Kosten vermieden.

1. Öffnen Sie das [Azure-Portal]( https://portal.azure.com) und wählen Sie die Ressourcengruppe aus, die die Ressource enthält, die Sie erstellt haben.
1. Wählen Sie die Ressource, dann **Löschen** und anschließend **Ja** aus, um den Löschvorgang zu bestätigen. Die Ressource wird dann gelöscht.

## Weitere Informationen

Diese Übung hat nur einen Teil der Möglichkeiten des Inhaltssicherheitsdienstes gezeigt. Weitere Informationen darüber, was Sie mit diesem Dienst tun können, erfahren Sie auf der Seite [Inhaltssicherheit](https://learn.microsoft.com/azure/ai-services/content-safety/overview).