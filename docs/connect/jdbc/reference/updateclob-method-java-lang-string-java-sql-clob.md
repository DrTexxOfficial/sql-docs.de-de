---
title: updateClob-Methode (java.lang.String, java.sql.Clob) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.updateClob (java.lang.String, java.sql.Clob)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 5da64915-1c13-44fd-90c0-52168889bae0
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 78a894683ec3d85012e96ac8e8378b17a9baceac
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47735058"
---
# <a name="updateclob-method-javalangstring-javasqlclob"></a>updateClob-Methode (java.lang.String, java.sql.Clob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Aktualisiert die angegebene Spalte unter Berücksichtigung des Spaltennamens mit einem java.sql.Clob-Wert.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public void updateClob(java.lang.String columnName,  
                       java.sql.Clob clobValue)  
```  
  
#### <a name="parameters"></a>Parameter  
 *columnName*  
  
 Eine **Zeichenfolge**, die den Spaltennamen enthält.  
  
 *clobValue*  
  
 Ein Clob-Objekt.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Diese UpdateClob-Methode wird von der UpdateClob-Methode in der java.sql.ResultSet-Schnittstelle angegeben.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [updateClob-Methode &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updateclob-method-sqlserverresultset.md)   
 [SQLServerResultSet-Elemente](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet-Klasse](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
