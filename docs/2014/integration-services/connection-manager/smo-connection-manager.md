---
title: SMO-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMO
- SMO connection manager
- connection managers [Integration Services], SMO
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a095e6c0e7204bd74892156af4ddc05f3f383eb0
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48201062"
---
# <a name="smo-connection-manager"></a>SMO-Verbindungs-Manager
  Mit einem SMO-Verbindungs-Manager kann ein Paket eine Verbindung mit einem SMO-Server (SQL Management Object) herstellen. Die Übertragungstasks von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] verwenden einen SMO-Verbindungs-Manager. Beispielsweise verwendet der Task Anmeldungen übertragen, der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldungen überträgt, einen SMO-Verbindungs-Manager.  
  
 Wenn Sie einem Paket einen SMO-Verbindungs-Manager hinzufügen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, die in eine SMO-Verbindung zur Laufzeit aufgelöst wird, die Verbindungs-Manager-Eigenschaften festlegt und fügt den Verbindungs-Manager erstellt die `Connections` Auflistung auf der das Paket. Die `ConnectionManagerType` Eigenschaft des Verbindungs-Managers nastaven NA hodnotu `SMOServer`.  
  
 Es gibt folgende Möglichkeiten, um einen SMO-Verbindungs-Manager zu konfigurieren:  
  
-   Geben Sie den Namen eines Servers an, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist.  
  
-   Wählen Sie den Authentifizierungsmodus zum Herstellen einer Verbindung mit dem Server aus.  
  
## <a name="configuration-of-the-smo-connection-manager"></a>Konfiguration des SMO-Verbindungs-Managers  
 Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.  
  
 Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [SMO-Verbindungs-Manager-Editor](../smo-connection-manager-editor.md).  
  
 Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Integrationsdienste &#40;SSIS&#41; Verbindungen](integration-services-ssis-connections.md)  
  
  
