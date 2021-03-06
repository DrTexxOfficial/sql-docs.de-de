---
title: Setup-Programm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/31/2016
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- installing ODBC components [ODBC], setup program
ms.assetid: 9cc5d75d-b293-41e5-927c-10f4af2e7af1
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: f64eda5ad640e50afd25db111de74141e41e652d
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47722148"
---
# <a name="setup-program"></a>Setupprogramm
> **Hinweis:** ab Windows XP und Windows Server 2003, **ODBC ist in der Windows-Betriebssystem enthalten**. Sie sollten nur explizit ODBC in früheren Versionen von Windows installieren.  
  
 Der Benutzer führt das Setup-Programm, um den Installationsvorgang zu starten. Das Setup-Programm wird von der Anwendung oder den Treiber Entwickler geschrieben. Zusätzlich zur Installation der ODBC-Komponenten können sie andere Software zu installieren. Z. B. können Anwendungsentwickler dasselbe Installationsprogramm sowohl ODBC-Komponenten zu installieren und ihren Anwendungen installieren.  
  
 Entwickler können das Setup-Programm von Grund auf neu, schreiben, mit dem Microsoft® Windows® SDK-Setup-Hilfsprogramme oder Setup-Software anderer Hersteller. Dadurch werden Entwickler vollständige Kontrolle über das Setup-Programm Aussehen und Verhalten. Das Setup-Programm kann geschrieben werden, um zusätzliche Software, z. B. eine ODBC-Anwendung zu installieren. Weitere Informationen zu den Windows SDK-Setup-Hilfsprogramme finden Sie unter der Windows SDK-Dokumentation.  
  
 Wie viel von der Installation tatsächlich vom Setupprogramm abgeschlossen ist, hängt davon ab, was sie Aufrufe in die Installationsprogramm-DLL fungiert. Das Installationsprogramm-DLL enthält Funktionen für die einzelnen ODBC-Komponenten zu installieren. Ruft das Setup-Programm einfach **SQLInstallDriverManager**, **SQLInstallDriverEx**, oder **SQLInstallTranslatorEx** im Installationsprogramm-DLL für das Abrufen des Pfads, der die Verzeichnis, in dem die Komponente installiert werden und Informationen über die Komponente in der Registrierung hinzugefügt ist. Diese Funktionen sind tatsächlich Dateien nicht kopiert werden; das Setup-Programm wird anhand der Informationen in den Argumenten dieser Funktionen.  
  
 Das Installationsprogramm-DLL enthält auch Funktionen zum Entfernen von ODBC-Komponenten. Der Setup-Programm ruft **SQLRemoveDriverManager**, **SQLRemoveDriver**, oder **SQLRemoveTranslator** im Installationsprogramm-DLL für die Nutzung von einer Komponente zu dekrementieren Anzahl der in der Registrierung und, wenn neue Verwendungsanzahl in der Komponente auf 0 fällt, entfernen Sie alle Informationen über die Komponente aus der Registrierung. Diese Funktionen entfernen Sie die Dateien für die Komponente nicht tatsächlich; das Setup-Programm wird auf 0 fällt die Verwendungsanzahl der neuen.
