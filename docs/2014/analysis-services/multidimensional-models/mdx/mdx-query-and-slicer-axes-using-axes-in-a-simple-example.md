---
title: Verwenden von Abfrage- und Slicerachsen in einem einfachen Beispiel (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8001fe4357bc7e17ce915f3d2d38c5e2e0f9cbb1
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48114200"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a>Verwenden von Abfrage- und Slicerachsen in einem einfachen Beispiel (MDX)
  Anhand des einfachen Beispiels, das in diesem Thema vorgestellt wird, werden die Grundlagen zum Angeben und Verwenden von Abfrage- und Slicerachsen erläutert.  
  
## <a name="the-cube"></a>Der Cube  
 Ein Cube namens TestCube hat zwei einfache Dimensionen mit den Namen Route und Time. Jede Dimension hat nur eine Benutzerhierarchie, die den Namen Route bzw. Time hat. Da die Measures des Cubes Teil der Measures-Dimension sind, hat dieser Cube insgesamt drei Dimensionen.  
  
## <a name="the-query"></a>Die Abfrage  
 Die Abfrage muss eine Matrix bereitstellen, in der das Packages-Measure über Routen und Zeiten hinweg verglichen werden kann.  
  
 Im folgenden MDX-Abfragebeispiel sind die Hierarchien Route und Time die Abfrageachsen, und die Measures-Dimension ist die Slicerachse. Die [Members](/sql/mdx/members-set-mdx) -Funktion zeigt an, dass MDX die Elemente der Hierarchie oder der Ebene zum Erstellen einer Menge verwendet. Wird die `Members`-Funktion verwendet, ist es nicht erforderlich, dass Sie in der jeweiligen MDX-Abfrage explizit jedes Element einer bestimmten Hierarchie oder Ebene angeben.  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a>Das Ergebnis  
 Das Ergebnis ist ein Raster, das die Werte enthält, die das Packages-Measure in jedem Schnittpunkt der Achsendimensionen COLUMNS und ROWS hat. Die folgende Tabelle zeigt, wie dieses Raster aussehen würde:  
  
||air|sea|  
|-|---------|---------|  
|Erstes Quartal|60|50|  
|Zweites Quartal|45|45|  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben des Inhalts einer Abfrageachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md)   
 [Angeben des Inhalts einer slicerachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
