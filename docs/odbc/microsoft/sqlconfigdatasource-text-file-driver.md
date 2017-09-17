---
title: SQLConfigDataSource (Text-Datei-Treiber) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text file driver [ODBC], SQLConfigDataSource
- SQLConfigDataSource function [ODBC], Text File Driver
ms.assetid: c505d36e-1e72-47b2-a9e5-e4926b408468
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e781871cc8507d10617e1a147fa6d5a7c06ac756
ms.contentlocale: de-de
ms.lasthandoff: 09/09/2017

---
# <a name="sqlconfigdatasource-text-file-driver"></a>SQLConfigDataSource (Text-Datei-Treiber)
> [!NOTE]  
>  Dieses Thema enthält die Textdatei treiberspezifische Informationen. Allgemeine Informationen zu dieser Funktion finden Sie unter den entsprechenden Themen unter [ODBC API Reference](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Die **SQLConfigDataSource** -Funktion, die verwendet wird, hinzuzufügen, ändern oder Löschen einer Datenquelle verwendet, die dynamisch die folgenden Schlüsselwörter.  
  
|Schlüsselwort|Description|  
|-------------|-----------------|  
|CHARACTERSET|Für den Text-Treiber, OEM oder ANSI.|  
|COLNAMEHEADER|Gibt an, ob die Spaltennamen des ersten Datensatzes, der Daten angeben, für den Text-Treiber. "True" oder "false".|  
|WERT|Die Pfadangabe in das Verzeichnis.|  
|DESCRIPTION|Eine Beschreibung der Daten in der Datenquelle.<br /><br /> Dadurch wird die gleiche Option als **Beschreibung** im Dialogfeld "Setup".|  
|DRIVER|Die Pfadangabe an den Treiber-DLL.|  
|DRIVERID|Eine ganzzahlige ID für den Treiber. 27 (Text)|  
|ERWEITERUNGEN|Listet die Dateinamenerweiterungen der Textdateien in der Datenquelle an.<br /><br /> Dadurch wird die gleiche Option als **Erweiterungsliste** im Dialogfeld "Setup".|  
|FIL|Dateityp Text|  
|DATEITYP|Der Dateityp für den Text-Treiber (Text).|  
|FORMAT|Für den Text-Treiber kann FIXEDLENGTH TABDELIMITED, CSVDELIMITED (durch ein Komma) oder DELIMITED() (durch das Sonderzeichen in Klammern angegeben). Das Sonderzeichen kann ist ein Zeichen lang und im Zeichenformat, Dezimal oder hexadezimal vorliegen.|  
|MAXSCANROWS|Die Anzahl der Zeilen, die beim Festlegen des Datentyps einer Spalte, die basierend auf vorhandenen Daten geprüft werden.<br /><br /> Für den Text-Treiber können Sie eine Zahl zwischen 1 und 32767 für die Anzahl der Zeilen eingeben; Allerdings wird standardmäßig der Wert immer auf 25. (Eine Zahl außerhalb der Grenzwert wird einen Fehler zurückgegeben.)<br /><br /> Dadurch wird die gleiche Option als **zu scannende Zeilen** im Dialogfeld "Setup".|  
|READONLY|True, um die Datei schreibgeschützt machen. "False", um die Datei nicht schreibgeschützt sein.<br /><br /> Dadurch wird die gleiche Option als **Read Only** im Dialogfeld "Setup".|