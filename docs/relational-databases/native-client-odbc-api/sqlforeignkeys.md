---
title: SQLForeignKeys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f0b720659980a072db9a22b4a3dfcaa2524f1676
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47665358"
---
# <a name="sqlforeignkeys"></a>SQLForeignKeys
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt Updateweitergaben und Löschungen über den Fremdschlüsseleinschränkungsmechanismus. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt SQL_CASCADE für UPDATE_RULE- und/oder DELETE_RULE-Spalten zurück, wenn die CASCADE-Option in der ON UPDATE-Klausel und/oder der ON DELETE-Klausel der FOREIGN KEY-Einschränkungen angegeben wird. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Gibt SQL_NO_ACTION für UPDATE_RULE- und/oder DELETE_RULE-Spalten zurück, wenn NO ACTION-Option in der ON UPDATE und/oder der ON DELETE-Klausel der FOREIGN KEY-Einschränkungen angegeben wird.  
  
 Wenn in einem beliebigen **SQLForeignKeys** -Parameter ungültige Werte vorhanden sind, gibt **SQLForeignKeys** bei der Ausführung SQL_SUCCESS zurück. **SQLFetch** gibt SQL_NO_DATA zurück, wenn in diesen Parametern ungültige Werte verwendet werden.  
  
 **SQLForeignKeys** kann in einem statischen Servercursor ausgeführt werden. Wenn **SQLForeignKeys** in einem aktualisierbaren Cursor (dynamischer Cursor oder Keysetcursor) ausgeführt wird, wird SQL_SUCCESS_WITH_INFO zurückgegeben. Das bedeutet, dass der Cursortyp geändert wurde.  
  
 Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt die Meldung von Informationen für Tabellen auf Verbindungsservern, indem er einen zweiteiligen Namen für die Parameter *FKCatalogName* und *PKCatalogName* akzeptiert: *Linked_Server_Name.Catalog_Name*.  
  
## <a name="see-also"></a>Siehe auch  
 [SQLForeignKeys-Funktion](http://go.microsoft.com/fwlink/?LinkId=59344)   
 [ODBC-API-Implementierungsdetails](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
