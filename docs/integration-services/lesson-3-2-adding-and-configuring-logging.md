---
title: 'Schritt 2: Hinzufügen und Konfigurieren der Protokollierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: tutorial
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3d28fe017e3757b3f21d6d735911692708eb66c1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47726658"
---
# <a name="lesson-3-2---adding-and-configuring-logging"></a>Lektion 3-2: Hinzufügen und Konfigurieren der Protokollierung
In dieser Aufgabe aktivieren Sie die Protokollierung für den Datenfluss im Paket Lesson 3.dtsx. Sie konfigurieren dann einen Protokollanbieter für Textdateien, um die Ereignisse PipelineExecutionPlan und PipelineExecuteTrees zu protokollieren. Der Protokollanbieter für Textdateien erstellt Protokolle, die auf einfache Weise angezeigt werden können und portabel sind. Die Einfachheit dieser Protokolldateien ist besonders während der grundlegenden Testphase eines Pakets nützlich. Sie können die Protokolleinträge auch im Fenster Protokollereignisse des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers anzeigen.  
  
### <a name="to-add-logging-to-the-package"></a>So fügen Sie die Protokollierung zum Paket hinzu  
  
1.  Klicken Sie im Menü **SSIS** auf **Protokollierung**.  
  
2.  Stellen Sie im Dialogfeld **SSIS-Protokolle konfigurieren** im **Container** -Bereich sicher, dass das oberste Objekt, das das Paket aus Lektion 3 darstellt, ausgewählt ist.  
  
3.  Wählen Sie auf der Registerkarte **Anbieter und Protokolle** im Feld **Anbietertyp** die Option **SSIS-Protokollanbieter für Textdateien**aus, und klicken Sie anschließend auf **Hinzufügen**.  
  
    Von Integration Services wird ein neuer Protokollanbieter für Textdateien mit dem Standardnamen **SSIS-Protokollanbieter für Textdateien**zum Paket hinzugefügt. Sie können jetzt den neuen Protokollanbieter konfigurieren.  
  
4.  Geben Sie in der **Name** -Spalte **Lesson 3 Log File**ein.  
  
5.  Ändern Sie optional **Beschreibung**.  
  
6.  Klicken Sie in der Spalte **Konfiguration** auf **<New Connection>** , um das Ziel anzugeben, wohin die Protokollinformationen geschrieben werden.  
  
    Wählen Sie im Dialogfeld **Dateiverbindungs-Manager-Editor** für **Verwendungstyp**die Option **Datei erstellen**aus, und klicken Sie anschließend auf **Durchsuchen**. Standardmäßig wird vom Dialogfeld **Dateien auswählen** der Projektordner geöffnet, aber Sie können Protokollinformationen an beliebiger Stelle speichern.  
  
7.  Geben Sie im Dialogfeld **Datei auswählen** im Feld **Dateiname** **TutorialLog.log**ein, und klicken Sie auf **Öffnen**.  
  
8.  Klicken Sie auf **OK** , um das Dialogfeld **Dateiverbindungs-Manager-Editor** zu schließen.  
  
9. Erweitern Sie im **Container** -Bereich alle Knoten der Paketcontainerhierarchie, und deaktivieren Sie anschließend alle Kontrollkästchen, einschließlich des Kontrollkästchens für **Extract Sample Currency Data** . Aktivieren Sie jetzt das Kontrollkästchen für **Extract Sample Currency Data** , um nur die Ereignisse für diesen Knoten abzurufen.  
  
    > [!IMPORTANT]  
    > Wenn der Status des Kontrollkästchens **Extract Sample Currency Data** abgeblendet anstatt ausgewählt ist, verwendet der Task die Protokolleinstellungen des übergeordneten Containers. In diesem Fall können Sie die taskspezifischen Protokollereignisse nicht aktivieren.  
  
10. Wählen Sie auf der Registerkarte **Details** in der Spalte **Ereignisse** die Ereignisse **PipelineExecutionPlan** und **PipelineExecutionTrees** aus.  
  
11. Klicken Sie auf **Erweitert** , um die Details zu überprüfen, die vom Protokollanbieter für jedes Ereignis in das Protokoll geschrieben werden. Standardmäßig werden alle Informationskategorien für die Ereignisse ausgewählt, die Sie angeben.  
  
12. Klicken Sie auf **Standard** , um die Informationskategorien auszublenden.  
  
13. Wählen Sie auf der Registerkarte **Anbieter und Protokolle** in der **Name** -Spalte **Lesson 3 Log File**aus. Nach dem Erstellen eines Protokollanbieters für Ihr Paket können Sie diesen optional deaktivieren, um die Protokollierung zeitweise zu deaktivieren, ohne dass Sie einen Protokollanbieter löschen und dann erneut erstellen müssen.  
  
14. Klicken Sie auf **OK**.  
  
## <a name="next-steps"></a>Next Steps  
[Schritt 3: Testen des Tutorialpakets aus Lektion 3](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
