---
title: Einrichten des Auftragsverlaufsprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 0741180bb126d45ad99512a596fbab66c9a8047f
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48209120"
---
# <a name="set-up-the-job-history-log"></a>Set Up the Job History Log
  In diesem Thema wird beschrieben, wie Sie das Auftragsverlaufsprotokoll des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents einrichten.  
  
-   **Vorbereitungen:**  [Sicherheit](#Security)  
  
-   **Einrichten des Auftragsverlaufsprotokolls mit:**  [SQL Server Management Studio](#SSMS)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Security"></a> Sicherheit  
 Ausführliche Informationen finden Sie unter [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).  
  
##  <a name="SSMS"></a> Verwenden von SQL Server Management Studio  
 **So richten Sie das Auftragsverlaufsprotokoll ein**  
  
1.  Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.  
  
2.  Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.  
  
3.  Wählen Sie im Dialogfeld **Eigenschaften des SQL Server-Agents** die Seite **Verlauf** aus.  
  
4.  Nehmen Sie für die folgenden Optionen die gewünschten Einstellungen vor:  
  
    1.  Aktivieren Sie die Option **Größe des Auftragsverlaufsprotokolls beschränken**, und geben Sie dann die maximale Anzahl von Zeilen für das Auftragsverlaufsprotokoll sowie die maximale Anzahl von Zeilen je Auftrag ein.  
  
    2.  Aktivieren Sie die Option **Agentverlauf automatisch entfernen**, und geben Sie den Zeitraum an, nach dem ältere Verlaufsdaten aus dem Protokoll gelöscht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren von Aufträgen](implement-jobs.md)   
 [Überwachen der Auftragsaktivität](monitor-job-activity.md)   
 [Erstellen von Aufträgen](create-jobs.md)  
  
  
