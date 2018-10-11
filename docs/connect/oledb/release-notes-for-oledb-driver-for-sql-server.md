---
title: Anmerkungen zu dieser Version (OLE DB-Treiber für SQL Server) | Microsoft-Dokumentation
ms.date: 07/03/2018
ms.prod: sql
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daveng
ms.openlocfilehash: 01ea0242637f4dd5c813808b3b840d3a5a86df9a
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47789118"
---
# <a name="release-notes-for-the-microsoft-ole-db-driver-for-sql-server"></a>Anmerkungen zu dieser Version vom OLE DB-Treiber für SQL Server
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../includes/driver_oledb_download.md)]

Auf dieser Seite wird erläutert, was in den einzelnen Versionen des Microsoft OLE DB-Treibers für SQL Server hinzugefügt wurde.

## <a name="whats-new-in-version-1810"></a>Neues in Version 18.1.0

**Funktionen, die hinzugefügt werden:**

* Unterstützung für `UseFMTONLY` Schlüsselwort für Verbindungszeichenfolgen und `SSPROP_INIT_USEFMTONLY` -Eigenschaft zur datenquelleninitialisierung.
`UseFMTONLY` Steuert, wie die Metadaten abgerufen werden, bei der Verbindung [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] und höher.  
Weitere Informationen finden Sie in den folgenden Themen:
  * [Verwenden von Verbindungszeichenfolgen-Schlüsselwörtern mit dem OLE DB-Treiber für SQL Server](applications/using-connection-string-keywords-with-oledb-driver-for-sql-server.md)

**Behobene Probleme:**

* Feste falsche Version von der BCP-Formatdatei. OLE DB-Treiber-18.0 wird fälschlicherweise die Version der BCP-Formatdatei, auf 18.0 statt 11.0. Formatdateien, die vom OLE DB-Treiber-18.0 können nicht von der OLE DB-Treiber 18.1. gelesen werden. Wenn Sie Dateien im Format generiert, indem Sie die vorherige Version des Treibers durch den neuen Treiber verwenden müssen, können Sie die Dateien, um die Version 11.0 ändern manuell bearbeiten.

## <a name="whats-new-in-version-1802"></a>Neues in Version 18.0.2

**Funktionen, die hinzugefügt**:

* Unterstützung für `MultiSubnetFailover` Schlüsselwort für Verbindungszeichenfolgen und `SSPROP_INIT_MULTISUBNETFAILOVER` -Eigenschaft zur datenquelleninitialisierung.  
Weitere Informationen finden Sie in den folgenden Themen:  
  * [OLE DB-Treiber für SQL Server-Unterstützung für Hochverfügbarkeit, Notfallwiederherstellung](features/oledb-driver-for-sql-server-support-for-high-availability-disaster-recovery.md)  
  * [Verwenden von Verbindungszeichenfolgen-Schlüsselwörtern mit dem OLE DB-Treiber für SQL Server](applications/using-connection-string-keywords-with-oledb-driver-for-sql-server.md)

## <a name="see-also"></a>Siehe auch
[Microsoft OLE DB-Treiber für SQL Server](oledb-driver-for-sql-server.md)
