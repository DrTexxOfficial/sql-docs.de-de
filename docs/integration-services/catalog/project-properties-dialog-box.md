---
title: Projekteigenschaften (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.ssis.ssms.isprojectprop.general.f1
- sql13.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 25a88ea18cb9bd6741dfab89a0bd3ed4cd04861a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47611328"
---
# <a name="project-properties-dialog-box"></a>Projekteigenschaften (Dialogfeld)
  Ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekt entspricht einer Bereitstellungseinheit. Jedes Projekt kann Pakete, Parameter und Umgebungsverweise enthalten. Ein Projekt ist ein sicherungsfähiges Objekt, mit dem Berechtigungen für Datenbankprinzipale definiert werden können. Wenn ein Projekt erneut bereitgestellt wird, kann die frühere Version des Projekts im [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Katalog gespeichert werden.  
  
 Mit Projekt- und Paketparametern können Sie Eigenschaften in Paketen zur Zeit der Ausführung Werte zuweisen. Einige Parameter erfordern Werte, bevor das Paket ausgeführt werden kann. Parameterwerte, die auf Umgebungsvariablen verweisen, erfordern einen entsprechenden Umgebungsverweis im Projekt, damit die Ausführung erfolgen kann.  
  
 **Was möchten Sie tun?**  
  
-   [Öffnen des Dialogfelds "Projekteigenschaften"](#open_dialog)  
  
-   [Festlegen der Optionen auf der Seite "Allgemein"](#general)  
  
-   [Festlegen der Optionen auf der Seite "Berechtigungen"](#permissions)  
  
##  <a name="open_dialog"></a> Öffnen des Dialogfelds "Projekteigenschaften"  
  
1.  Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Server her.  
  
     Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Instanz her, die die SSISDB-Datenbank hostet.  
  
2.  Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.  
  
3.  Erweitern Sie den **SSISDB** -Knoten.  
  
4.  Erweitern Sie den Ordner mit dem Projekt, für das Sie die Eigenschaften festlegen möchten.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften**.  
  
##  <a name="general"></a> Festlegen der Optionen auf der Seite "Allgemein"  
 Verwenden Sie die Seite "Allgemein", um Projekteigenschaften anzuzeigen.  
  
 **Name**  
 Listet den Projektnamen auf.  
  
 **Bezeichner**  
 Listet die Projekt-ID auf.  
  
 **Beschreibung**  
 Zeigt die optionale Beschreibung des Projekts an.  
  
 **Projektversion**  
 Listet die Projektversion auf.  
  
 **Bereitstellungsdatum**  
 Listet das Datum und die Uhrzeit der Bereitstellung oder erneuten Bereitstellung des Projekts auf.  
  
##  <a name="permissions"></a> Festlegen der Optionen auf der Seite "Berechtigungen"  
 Auf der Seite **Berechtigungen** können die expliziten Berechtigungen für das Projekt angezeigt oder festgelegt werden.  
  
 Durchsuchen  
 Klicken Sie auf **Durchsuchen** , um mithilfe des Dialogfelds **Alle Prinzipale durchsuchen** die Benutzer und Rollen auszuwählen, deren Berechtigungen Sie festlegen möchten.  
  
 **Name**  
 Listet den Namen des Benutzers oder der Rolle auf.  
  
 **Typ**  
 Listet den Benutzer- oder Rollentyp auf.  
  
 **Berechtigung**  
 Listet die Berechtigungen auf.  
  
 **Grantor**  
 Listet den Benutzer oder die Rolle auf, die die Berechtigung gewährt.  
  
 **Erteilen**  
 Wenn **Erteilen** ausgewählt wird, wird die Berechtigung für den ausgewählten Benutzer oder die Rolle gewährt.  
  
 **Verweigern**  
 Wenn **Verweigern** ausgewählt wird, wird die Berechtigung für den ausgewählten Benutzer oder die Rolle verweigert.  
  
  
