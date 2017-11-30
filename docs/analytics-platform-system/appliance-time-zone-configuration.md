---
title: Appliance-Zeitzonenkonfiguration (Analytics Platform System)
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cea9eeb9-fe05-4e65-b229-539de02ab20a
caps.latest.revision: "18"
ms.openlocfilehash: 05cf2811dad14a6a7d53752893f363b061b86843
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="appliance-time-zone-configuration"></a>Die Zeitzonenkonfiguration Appliance
Die **Zeitzone** auf der Seite können Sie die Zeitzone für alle Knoten in der SQL Server PDW Appliance festlegen.  
  
## <a name="to-set-the-time-zone"></a>Festlegen der Zeitzone  
  
1.  Starten Sie den Konfigurations-Manager. Weitere Informationen finden Sie unter [starten Sie den Konfigurations-Manager & #40; Analyseplattformsystem & #41; ](launch-the-configuration-manager.md).  
  
2.  Beenden Sie die Anwendung Dienste mithilfe der **Dienststatus** Seite im Konfigurations-Manager. Finden Sie unter [PDW Services Status & #40; Analyseplattformsystem & #41; ](pdw-services-status.md) Anweisungen.  
  
3.  Klicken Sie im linken Bereich des Konfigurations-Managers auf **Zeitzone**. Wählen Sie die gewünschte Zeitzone aus der **Zeitzone** Dropdown-Menü. Je nach Position, Sie können auch auswählen, wählen Sie das Kontrollkästchen neben **automatisch für die Sommerzeit angepasst Uhr**.  
  
4.  Klicken Sie auf **übernehmen** zum Speichern der Änderungen.  
  
5.  Die Appliance-Dienste neu, mithilfe der **Dienststatus** Seite im Konfigurations-Manager. Wenn Sie auch planen, die Berechtigungen zu ändern, können Sie dies tun, vor dem Neustart der Anwendung.  
  
![DWConfig, Anwendungszeit](./media/appliance-time-zone-configuration/SQL_Server_PDW_DWConfig_ApplTopTime.png "SQL_Server_PDW_DWConfig_ApplTopTime")  
  
## <a name="see-also"></a>Siehe auch  
[Starten Sie den Konfigurations-Manager & #40; Analyseplattformsystem & #41;](launch-the-configuration-manager.md)  
  