---
title: ID-Element (XMLA) | Microsoft-Dokumentation
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 18c0a9e1db03ef30b54b788d16223e70bc9e9059
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38037028"
---
# <a name="id-element-xmla"></a>ID-Element (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Identifiziert eine Sperre auf dem das übergeordnete [Sperre](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md) oder [Unlock](../../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Lock> <!-- or Unlock>  
   ...  
   <ID>...</ID>  
   ...  
</Lock>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Description|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge|  
|Standardwert|InclusionThresholdSetting|  
|Cardinality|1-1: Erforderliches Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Sperre](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md), [nicht entsperren](../../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)|  
|Untergeordnete Elemente|InclusionThresholdSetting|  
  
## <a name="remarks"></a>Hinweise  
 Das **ID** -Element enthält einen Globally Unique Identifier (GUID), der verwendet wird, um eine Sperre zu identifizieren.  
  
## <a name="see-also"></a>Siehe auch
 [Objekt-Element &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/object-element-xmla.md)   
 [Mode-Element &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/mode-element-xmla.md)   
 [Eigenschaften &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
