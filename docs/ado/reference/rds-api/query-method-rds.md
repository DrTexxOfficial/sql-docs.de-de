---
title: Query-Methode (RDS) | Microsoft-Dokumentation
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Query method [ADO]
ms.assetid: 20f2480f-3758-405d-a379-05a0dce74796
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 59dff6a0af01fe55b6b542cfe494cd93ad73b943
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47616869"
---
# <a name="query-method-rds"></a>Query-Methode (RDS)
Eine gültige SQL-Abfragezeichenfolge verwendet, um zurückzugeben eine [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
> [!IMPORTANT]
>  Ab Windows 8 und Windows Server 2012, sind nicht mehr RDS-Server-Komponenten in das Windows-Betriebssystem enthalten (finden Sie unter Windows 8 und [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/en-us/download/details.aspx?id=27416) Einzelheiten). RDS-Client-Komponenten werden in einer zukünftigen Version von Windows entfernt werden. Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden. Anwendungen, die RDS zu migrieren sollten [WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
Set Recordset = DataFactory.Query(Connection, Query)  
```  
  
#### <a name="parameters"></a>Parameter  
 *Recordset*  
 Eine Objektvariable, steht ein **Recordset** Objekt.  
  
 *DataFactory*  
 Eine Objektvariable, steht ein [RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) Objekt.  
  
 *Verbindung*  
 Ein **Zeichenfolge** Wert, der die Verbindungsinformationen für Server enthält. Dies ist vergleichbar mit der [Connect](../../../ado/reference/rds-api/connect-property-rds.md) Eigenschaft.  
  
 *Dataseteigenschaften*  
 Ein **Zeichenfolge** , die die SQL-Abfrage enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die Abfrage sollte den SQL-Dialekt des Datenbankservers verwenden. Ein Status des wird zurückgegeben, wenn Fehler mit der Abfrage, die ausgeführt wurde. Die **Abfrage** Methode führt syntaxüberprüfung für keine der **Abfrage** Zeichenfolge.  
  
## <a name="applies-to"></a>Gilt für  
 [DataFactory-Objekt (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DataFactory-Objekt, Abfragemethode und CreateObject-Methode – Beispiel (VBScript)](../../../ado/reference/rds-api/datafactory-object-query-method-and-createobject-method-example-vbscript.md)


