---
title: Einige Verfügbarkeitsreplikate synchronisieren keine Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.agp4synchronizing.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 3db6a569-e942-4321-a0dd-c4ab002087c8
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 03554319ea3bb9d8ae66bde44e7e4c5026c9da39
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48146530"
---
# <a name="some-availability-replicas-are-not-synchronizing-data"></a>Einige Verfügbarkeitsreplikate synchronisieren keine Daten
    
## <a name="introduction"></a>Einführung  
  
|||  
|-|-|  
|**Richtlinienname**|Datensynchronisierungsstatus der Verfügbarkeitsreplikate|  
|**Problem**|Einige Verfügbarkeitsreplikate synchronisieren keine Daten.|  
|**Kategorie**|**Warnung**|  
|**Facet**|Verfügbarkeitsgruppe|  
  
## <a name="description"></a>Description  
 Diese Richtlinie führt ein Rollup des Datensynchronisierungsstatus aller Verfügbarkeitsreplikate in der Verfügbarkeitsgruppe aus und überprüft, ob die Synchronisierung der Verfügbarkeitsreplikate ggf. nicht betriebsbereit ist. Die Richtlinie befindet sich in einem fehlerhaften Zustand, wenn einer der Datensynchronisierungsstatus des Verfügbarkeitsreplikats NOT SYNCHRONIZING lautet.  
  
 Diese Richtlinie befindet sich in einem ordnungsgemäßen Zustand, wenn keiner der Datensynchronisierungsstatus des Verfügbarkeitsreplikats NOT SYNCHRONIZING lautet.  
  
> [!NOTE]  
>  Für diese Version von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]finden Sie Informationen zu möglichen Ursachen und Lösungen im TechNet Wiki unter [Einige Verfügbarkeitsreplikate synchronisieren keine Daten](http://go.microsoft.com/fwlink/p/?LinkId=220852) .  
  
## <a name="possible-causes"></a>Mögliche Ursachen  
 In dieser Verfügbarkeitsgruppe weist mindestens ein sekundäres Replikat den Synchronisierungsstatus NOT SYNCHRONIZING auf und empfängt keine Daten vom primären Replikat.  
  
## <a name="possible-solution"></a>Mögliche Lösung  
 Verwenden Sie den Verfügbarkeitsreplikat-Richtlinienstatus, um das Verfügbarkeitsreplikat mit dem Status NOT SYNCHRONIZING zu ermitteln, und beheben Sie dann das Problem des Verfügbarkeitsreplikats.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQLServer&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Verwenden des AlwaysOn-Dashboards &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
