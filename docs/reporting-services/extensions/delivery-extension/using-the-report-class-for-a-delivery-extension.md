---
title: Verwenden der Report-Klasse für eine Übermittlungserweiterung | Microsoft-Dokumentation
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: extensions
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 5fbbc345461cfe0a036897e277837190f46f7fe1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47685269"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a>Verwenden der Report-Klasse für eine Übermittlungserweiterung
  Die <xref:Microsoft.ReportingServices.Interfaces.Report>-Klasse stellt einen Bericht in der Berichtsserver-Datenbank dar. Jedes Abonnement wird einem bestimmten Bericht zugeordnet. Der Bericht ist in der Benachrichtigung enthalten. Die Übermittlungserweiterung kann das <xref:Microsoft.ReportingServices.Interfaces.Report>-Objekt verwenden, das Bestandteil der Benachrichtigung zum Rendern des Berichts ist. Das <xref:Microsoft.ReportingServices.Interfaces.Report>-Objekt enthält auch berichtsspezifische Eigenschaften, wie die URL zum Bericht auf dem Server und den Namen des Berichts. Diese Eigenschaften können alle als Teil des Übermittlungsanbieters verwendet werden.  
  
 Die <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A>-Methode der <xref:Microsoft.ReportingServices.Interfaces.Report>-Klasse kann zum Rendern eines Berichts verwendet werden. Die <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A>-Methode gibt ein Array von einem oder mehreren <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekten zurück, die zusammen einen gerenderten Bericht ausmachen. Das erste <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekt ist der gerenderte Bericht. Alle anderen <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekte sind Ressourcen, die zusammen mit den Berichtsdaten geliefert werden müssen (z. B. eine HTML-Datei und zugehörige Bilder). Renderingerweiterungen mit einem einzigen Datenstrom (IMAGE, PDF, MHTML und Excel) geben nur ein <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekt im Array zurück.  
  
 Das <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>-Objekt, das den Berichtsdatenstrom enthält, kann als Teil einer Übermittlung enthalten sein.  
  
 Ein Beispiel zur Verwendungsweise der <xref:Microsoft.ReportingServices.Interfaces.Report>-Klasse finden Sie unter [SQL Server Reporting Services-Produktbeispiele](http://go.microsoft.com/fwlink/?LinkId=177889)  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Implementieren von Übermittlungserweiterungen](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Reporting Services-Erweiterungsbibliothek](../../../reporting-services/extensions/reporting-services-extension-library.md)   
 [Using the RenderedOutputFile Class for a Delivery Extension (Verwenden der RenderedOutputFile-Klasse für eine Übermittlungserweiterung)](../../../reporting-services/extensions/delivery-extension/using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
