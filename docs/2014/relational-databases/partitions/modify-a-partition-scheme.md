---
title: Ändern eines Partitionsschemas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 15118d2bec00582a22577230183b486c13bb031d
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48063230"
---
# <a name="modify-a-partition-scheme"></a>Ändern eines Partitionsschemas
  Sie können ein Partitionsschema in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ändern, indem Sie eine Dateigruppe zum Aufnehmen der nächsten Partition bestimmen, die der partitionierten Tabelle mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]hinzugefügt werden soll. Dies erreichen Sie, indem Sie einer Dateigruppe die NEXT USED-Eigenschaft zuweisen. Die NEXT USED-Eigenschaft können Sie einer leeren Dateigruppe zuweisen oder einer Dateigruppe, die bereits eine Partition besitzt. Eine Dateigruppe kann also mehr als eine Partition aufweisen.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Security](#Security)  
  
-   **Erstellen einer partitionierten Tabelle oder eines partitionierten Indexes mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungsmaßnahmen  
  
###  <a name="Restrictions"></a> Einschränkungen  
 Jede Dateigruppe, die von ALTER PARTITION SCHEME betroffen ist, muss online sein.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Die folgenden Berechtigungen können verwendet werden, um ALTER PARTITION SCHEME auszuführen:  
  
-   ALTER ANY DATASPACE-Berechtigung. Diese Berechtigung gilt standardmäßig für Mitglieder der festen Serverrolle **sysadmin** und für Mitglieder der festen Datenbankrollen **db_owner** und **db_ddladmin** .  
  
-   CONTROL- oder ALTER-Berechtigung für die Datenbank, in der das Partitionsschema erstellt wurde.  
  
-   Die CONTROL SERVER-Berechtigung oder ALTER ANY DATABASE-Berechtigung auf dem Server der Datenbank, in der das Partitionsschema erstellt wurde.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio  
 **So ändern Sie ein Partitionsschema**  
  
 Diese spezielle Aktion kann nicht mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ausgeführt werden. Um ein Partitionsschema zu ändern, müssen Sie zuerst das Schema löschen und dann mit dem Assistenten zum Erstellen von Partitionen eine neue Funktion mit den gewünschten Eigenschaften erstellen. Weitere Informationen finden Sie unter [Erstellen partitionierter Tabellen und Indizes mit SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) unter **Erstellen partitionierter Tabellen und Indizes**.  
  
#### <a name="to-delete-a-partition-scheme"></a>So löschen Sie ein Partitionsschema  
  
1.  Klicken Sie auf das Pluszeichen, um die Datenbank zu erweitern, die das zu löschende Partitionsschema enthält.  
  
2.  Klicken Sie auf das Pluszeichen, um den Ordner **Speicher** zu erweitern.  
  
3.  Klicken Sie auf das Pluszeichen, um den Ordner **Partitionsschemas** zu erweitern.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Partitionsschema, das Sie löschen möchten, und wählen Sie **Löschen**aus.  
  
5.  Stellen Sie im Dialogfeld **Objekt löschen** sicher, dass das richtige Partitionsschema ausgewählt ist, und klicken Sie dann auf **OK**.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
#### <a name="to-modify-a-partition-scheme"></a>So ändern Sie ein Partitionsschema  
  
1.  Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).  
  
  
