---
title: 'Lektion 2: Erstellen Sie eine Richtlinie für Container und Generieren eines Shared Access Signature (SAS)-Schlüssels | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 7ddcef5d5e0695041742784151103c358a973d55
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48124080"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a>Lektion 2: Erstellen einer Richtlinie für einen Container und Generieren eines Shared Access Signature (SAS)-Schlüssels
  In dieser Lektion erfahren Sie, wie Sie eine Richtlinie für den BLOB-Container erstellen und auch einen SAS-Schlüssel generieren.  
  
 Eine gespeicherte Zugriffsrichtlinie stellt eine zusätzliche Steuerungsebene für Shared Access Signatures auf Serverseite bereit. Eine Shared Access Signature ist ein URI, der eingeschränkte Zugriffsrechte für Container, BLOBs, Warteschlangen und Tabellen gewährt. Wenn Sie diese neue Erweiterung verwenden, müssen Sie eine Richtlinie für einen Container mit Lese-, Schreib- und Auflistungsrechten erstellen.  
  
 Sie können eine Richtlinie und eine Shared Access Signature erstellen, indem Sie eine der folgenden Methoden verwenden:  
  
-   Windows Azure-REST-API-Vorgänge: [-Container erstellen](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), und [Container-ACL abrufen](https://msdn.microsoft.com/library/azure/dd179469.aspx).  
  
-   [CloudBlobContainer.GetSharedAccessSignature-Methode](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.storageclient.cloudblobcontainer.getsharedaccesssignature.aspx) in Windows Azure SDK.  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   Eine Drittanbieter-Windows Azure Explorertool, wie z. B. [Azure Storage-Explorer](http://azurestorageexplorer.codeplex.com/).  
  
 **Nächste Lektion:**  
  
 [Lektion 3: Erstellen von SQL Server-Anmeldeinformationen](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  
  
