---
title: Sqlsrv_client_info | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- sqlsrv_client_info
apitype: NA
helpviewer_keywords:
- API Reference, sqlsrv_client_info
- sqlsrv_client_info
ms.assetid: 3e2d3679-436a-45d8-8bdc-7c633b65a720
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 9feacf047b9c949bae25958a3030fce4661c1583
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47710445"
---
# <a name="sqlsrvclientinfo"></a>sqlsrv_client_info
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Gibt Informationen über die Liste der Verbindungen und den Client-Stack zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sqlsrv_client_info( resource $conn)  
```  
  
#### <a name="parameters"></a>Parameter  
*$conn*: Die Verbindungsressource, mit der der Client verbunden ist.  
  
## <a name="return-value"></a>Rückgabewert  
Ein assoziatives Array mit Schlüsseln, die in der folgenden Tabelle beschrieben werden, oder **false** , wenn die Verbindungsressource NULL ist.  
  
**Für PHP für SQL Server-Versionen 3.2 und 3.1**:  
  
|Key|und Beschreibung|  
|-------|---------------|  
|DriverDllName|MSODBCSQL11.DLL (ODBC Driver 11 für SQL Server)|  
|DriverODBCVer|ODBC-Version (xx.yy)|  
|DriverVer|ODBC Driver 11 for SQL Server DLL-Version:<br /><br />xx.yy.zzzz ([!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] Version 3.2 oder 3.1)|  
|ExtensionVer|php_sqlsrv.dll Version:<br /><br />3.2.xxxx.x (für [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] Version 3.2)<br /><br />3.1.xxxx.x (für [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] Version 3.1)|  
  
**Für PHP für SQL Server-Versionen 3.0 und 2.0**:  
  
|Key|und Beschreibung|  
|-------|---------------|  
|DriverDllName|SQLNCLI10.DLL ([!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] Version 2.0)|  
|DriverODBCVer|ODBC-Version (xx.yy)|  
|DriverVer|SQL Server Native Client DLL-Version<br /><br />10.50.xxx ([!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] Version 2.0)|  
|ExtensionVer|php_sqlsrv.dll Version:<br /><br />2.0.xxx ([!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] Version 2.0)|  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel schreibt Client-Informationen an die Konsole, wenn das Beispiel über die Befehlszeile ausgeführt wird. Das Beispiel setzt voraus, dass SQL Server auf dem lokalen Computer installiert ist. Wenn das Beispiel über die Befehlszeile ausgeführt wird, werden alle Ausgaben in die Konsole geschrieben.  
  
```  
<?php  
/*Connect to the local server using Windows Authentication and   
specify the AdventureWorks database as the database in use. */  
$serverName = "(local)";  
$conn = sqlsrv_connect( $serverName);  
  
if( $conn === false )  
{  
     echo "Could not connect.\n";  
     die( print_r( sqlsrv_errors(), true));  
}  
  
if( $client_info = sqlsrv_client_info( $conn))  
{  
       foreach( $client_info as $key => $value)  
      {  
              echo $key.": ".$value."\n";  
      }  
}  
else  
{  
       echo "Client info error.\n";  
}  
  
/* Close connection resources. */  
sqlsrv_close( $conn);  
?>  
```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
[API-Referenz für den SQLSRV-Treiber](../../connect/php/sqlsrv-driver-api-reference.md)

[Informationen zu den Codebeispielen in der Dokumentation](../../connect/php/about-code-examples-in-the-documentation.md)  
  
