---
title: Beispiel für eine XML-Eingabedatei mit Inlinearbeitsauslastung (DTA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d031b9042ef1a3ca4d6c7200cce4f6966e61ab02
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48121450"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a>Beispiel für eine XML-Eingabedatei mit Inlinearbeitsauslastung (DTA)
  Kopieren Sie dieses Beispiel für eine XML-Eingabedatei, die eine Arbeitsauslastung mit dem **EventString** -Element angibt, und fügen Sie sie in Ihren XML-Editor oder Text-Editor ein. Mit dem **EventString** -Element können Sie eine auf einem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript basierende Arbeitsauslastung in der XML-Eingabedatei angeben, anstatt eine separate Arbeitsauslastungsdatei zu verwenden. Nach dem Kopieren dieses Beispiels in Ihr Bearbeitungstool ersetzen Sie die Werte für das **Server**-, **Database**-, **Schema**-, **Table**-, **Workload**-, **EventString**- und **TuningOptions** -Element durch die Werte für Ihre Optimierungssitzung. Weitere Informationen zu sämtlichen Attributen und untergeordneten Elementen, die Sie zusammen mit diesen Elementen verwenden können, finden Sie unter [XML-Eingabedateireferenz &#40;Datenbankoptimierungsratgeber&#41;](xml-input-file-reference-database-engine-tuning-advisor.md) Im folgenden Beispiel wird nur eine Teilmenge der verfügbaren Optionen für Attribute und untergeordnete Elemente verwendet.  
  
## <a name="code"></a>Code  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a>Kommentare  
 `USE database_name` -Anweisungen können in der Inlinearbeitsauslastung angegeben werden, die im **EventString** -Element enthalten ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Starten und Verwenden des Datenbankoptimierungsratgebers](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md)   
 [Anzeigen und Verwenden der Ausgabe des Datenbankoptimierungsratgebers](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md)   
 [XML-Eingabedateireferenz &amp;#40;Datenbankoptimierungsratgeber&amp;#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
