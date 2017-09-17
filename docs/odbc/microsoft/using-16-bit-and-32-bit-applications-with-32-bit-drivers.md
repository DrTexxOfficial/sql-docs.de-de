---
title: Verwenden von 16-Bit- und 32-Bit-Anwendungen mit 32-Bit-Treibern | Microsoft Docs
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
- ODBC drivers [ODBC], 16-bit applications
- ODBC drivers [ODBC], 32-bit applications
- 32-bit applications with 32-bit drivers [ODBC]
- 16-bit applications with 32-bit drivers [ODBC]
ms.assetid: fc65c988-b31f-4cc9-851f-30d2119604fd
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 802b09dd83ce3671edbff33ff2be447c6279621f
ms.contentlocale: de-de
ms.lasthandoff: 09/09/2017

---
# <a name="using-16-bit-and-32-bit-applications-with-32-bit-drivers"></a>Verwenden von 16-Bit- und 32-Bit-Anwendungen mit 32-Bit-Treiber
> [!IMPORTANT]  
>  16-Bit-Anwendung-Unterstützung wird in einer zukünftigen Version von Windows entfernt werden. Verwenden Sie diese Funktion beim Entwickeln neuer Anwendungen nicht, und planen Sie das Ändern von Anwendungen, in denen es zurzeit verwendet wird. Entwickeln Sie stattdessen 32-Bit oder 64-Bit-Anwendungen.  
  
 Mit der ODBC-Komponente können Sie die 16-Bit- und 32-Bit-Anwendungen mit 32-Bit-Treiber verwenden. Microsoft® Windows® 95 und Windows 98 und Microsoft Windows/Windows 2000-Betriebssysteme unterstützen die folgenden Kombinationen von Anwendungen und-Treiber:  
  
-   16-Bit-Anwendungen mit 32-Bit-Treibern  
  
-   32-Bit-Anwendungen mit 32-Bit-Treibern  
  
 Verwendung von 32-Bit-Anwendung mit einem 16-Bit-Treiber wird nicht unterstützt.  
  
> [!NOTE]  
>  Beginnen mit der Version von ODBC, Version 3.0, Windows NT 4.0 unterstützt.  
  
 ODBC umfasst die ODBC-Komponenten, die erforderlich sind, um die oben genannten Konfigurationen "thunking" Dynamic Link Libraries (DLLs), um 16-Bit-Adressen in 32-Bit-Adressen zu konvertieren und umgekehrt zu unterstützen. Das Setup-Programm bestimmt, welches Betriebssystem Sie verwenden, und ODBC-Komponenten, die erforderlich sind, von diesem System installiert. Sie könne auch die von allen Systemen verwendet ODBC-Komponenten zu installieren.  
  
 In den meisten Fällen portieren Sie eine Anwendung oder ein aus 16-Bit-Treiber in 32-Bit umfasst fünf Arten von Änderungen:  
  
-   Änderungen an Meldungsbehandlung code  
  
-   Wechselt, da ganze Zahlen und Handles 32-Bit sind  
  
-   Änderungen in Aufrufen von Windows für Anwendungsprogrammierschnittstellen (APIs)  
  
-   Änderungen an den Treiber threadsicher  
  
-   Änderungen an ODBC-Komponenten  
  
 Von einer Anwendung oder Treiber programmiersicht ist der Hauptunterschied zwischen 16-Bit- und 32-Bit-ODBC-Komponenten an, dass sie unterschiedliche Namen aufweisen. Aus Sicht der System unterscheidet sich die Architektur von jeder Anwendung oder Treiber Verbindung und die Tools zum Verwalten von Datenquellen sind unterschiedlich.  
  
 Dieser Abschnitt enthält die folgenden Themen.  
  
-   [Verwenden von 16-Bit-Anwendungen mit 32-Bit-Treiber](../../odbc/microsoft/using-16-bit-applications-with-32-bit-drivers.md)  
  
-   [Verwenden 32-Bit-Anwendungen mit 32-Bit-Treiber](../../odbc/microsoft/using-32-bit-applications-with-32-bit-drivers.md)