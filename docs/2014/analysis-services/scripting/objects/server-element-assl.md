---
title: Server-Element (ASSL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.topic: reference
api_name:
- Server Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- server
helpviewer_keywords:
- Server element
ms.assetid: 92ca67f6-817e-4a75-9244-8f8bcf412190
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 39c4d780ade53dcb16d446237aa467f131614176
ms.sourcegitcommit: 3da2edf82763852cff6772a1a282ace3034b4936
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48106710"
---
# <a name="server-element-assl"></a>Server-Element (ASSL)
  Beschreibt eine Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Server>  
   <!—These elements are common to each major object -->  
   <Name>...</Name>  
   <ID>...</ID>  
   <CreatedTimestamp>...</CreatedTimestamp>  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   <Description>...</Description>  
   <Annotations>...</Annotations>  
   <!-- server elements or properties -->  
   <ProductName>...</ProductName>  
   <Edition>...</Edition>  
   <EditionId>...</Edition>  
   <Version>...</Version>  
   <ServerMode>...</ServerMode>  
   <ProductLevel>...</Databases>  
   <Databases>...</Databases>  
   <Assemblies>...</Assemblies>  
   <Traces>...</Traces>  
   <Roles>...</Roles>  
   <ServerProperties>...</ServerProperties>  
</Server>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|None|  
|Standardwert|None|  
|Cardinality|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|None|  
|Untergeordnete Elemente|[Namen](../properties/name-element-assl.md), [ID](../properties/id-element-assl.md), [CreatedTimestamp](../properties/createdtimestamp-element-assl.md), [LastSchemaUpdate](../properties/lastschemaupdate-element-assl.md), [Beschreibung](../properties/description-element-assl.md), [Anmerkungen](../collections/annotations-element-assl.md), [ProductName](../properties/productname-element-assl.md), [Edition](../properties/edition-element-assl.md), [EditionId](../../xmla/xml-elements-properties/editionid-element.md), [Version](../properties/version-element-assl.md), [ServerMode](../../xmla/xml-elements-properties/editionid-element.md), [ProductLevel](../../xmla/xml-elements-properties/productlabel-element.md), [Datenbanken](../collections/databases-element-assl.md), [Assemblys](../collections/assemblies-element-assl.md), [Ablaufverfolgungen](../collections/traces-element-assl.md), [Rollen](../collections/roles-element-assl.md), [ServerProperties](../collections/serverproperties-element-assl.md)>|  
  
## <a name="remarks"></a>Hinweise  
 Das `Server`-Element stellt eine Instanz von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] dar und dient als oberster Knoten in der ASSL-Knotenhierarchie (Analysis Services Scripting Language).  
  
 Das entsprechende Element im Analysis Management Objects (AMO)-Objektmodell ist <xref:Microsoft.AnalysisServices.Server>.  
  
## <a name="see-also"></a>Siehe auch  
 [Objekte &#40;ASSL&#41;](objects-assl.md)  
  
  
