---
title: CubeHierarchy-Datentyp (ASSL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- CubeHierarchy Data Type
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- CubeHierarchy
helpviewer_keywords:
- CubeHierarchy data type
ms.assetid: cd633409-0c14-4dd9-97cc-3d30e25df24f
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ba39d031f8760a82232f4f276c46d04101cc6438
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48209645"
---
# <a name="cubehierarchy-data-type-assl"></a>CubeHierarchy-Datentyp (ASSL)
  Definiert einen Grunddatentyp ab, die Informationen über eine [Hierarchie](../objects/hierarchy-element-assl.md) Element in einer [Cube](../objects/cube-element-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```  
<CubeHierarchy>   <HierarchyID>...</HierarchyID>   <Name>...</Name>   <OptimizedState>...</OptimizedState>   <Visible>...</Visible>   <Enabled>...</Enabled>   <Annotations>...</Annotations></CubeHierarchy>  
```  
  
## <a name="data-type-characteristics"></a>Datentypmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Basisdatentypen|None|  
|Abgeleitete Datentypen|None|  
  
## <a name="data-type-relationships"></a>Datentypbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|None|  
|Untergeordnete Elemente|[Anmerkungen](../collections/annotations-element-assl.md), [aktiviert](../properties/enabled-element-assl.md), [HierarchyID](../properties/id-element-assl.md), [Namen](../properties/name-element-assl.md), [OptimizedState](../properties/state-element-assl.md), [sichtbar](../properties/visible-element-assl.md)|  
|Abgeleitete Elemente|[Hierarchie](../objects/hierarchy-element-assl.md) ([Hierarchien](../collections/hierarchies-element-assl.md) Auflistung von [CubeDimension](dimension-data-type-assl.md))|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Datentyp unterliegt in keinem Bereitstellungsmodus Einschränkungen und kann in jedem dieser Modi verwendet werden: 0 - Mehrdimensional und Data Mining, 1 - SharePoint und 2 - Tabellarisch.  
  
 In [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)], *aktiviert* Eigenschaft nicht festgelegt werden, um `False` für *CubeHierarchy*.  
  
 Das entsprechende Element im Analysis Management Objects (AMO)-Objektmodell ist <xref:Microsoft.AnalysisServices.CubeHierarchy>.  
  
## <a name="see-also"></a>Siehe auch  
 [Discover-Methode &#40;XMLA&#41;](../../xmla/xml-elements-methods-discover.md)   
 [Analysis Services Scripting Language-XML-Datentypen &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
