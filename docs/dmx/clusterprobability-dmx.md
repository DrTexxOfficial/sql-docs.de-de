---
title: ClusterProbability (DMX) | Microsoft-Dokumentation
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: d4d8ce16bb07af07bd2bfd651cf5fc1ae15b7e08
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38030276"
---
# <a name="clusterprobability-dmx"></a>ClusterProbability (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Gibt die Wahrscheinlichkeit zurück, mit der der Eingabefall zum angegebenen Cluster gehört.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
ClusterProbability([<Node_Caption>])  
```  
  
## <a name="applies-to"></a>Gilt für  
 Diese Funktion kann nur verwendet werden, wenn das zugrunde liegende Data Mining-Modell Cluster unterstützt.  
  
## <a name="return-type"></a>Rückgabetyp  
 Ein Skalarwert.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Syntax wird das Schemarowset für den Inhalt eines Miningmodells verwendet, um die Knotenbeschriftungen zurückzugeben, die im Miningmodell vorhanden sind.  
  
```  
SELECT NODE_CAPTION FROM <model>.CONTENT  
```  
  
 Weitere Informationen zum Verwenden dieser Syntax finden Sie unter [SELECT FROM &#60;Modell&#62;. Inhalt &#40;DMX&#41;](../dmx/select-from-model-content-dmx.md). Weitere Informationen zu den Miningmodell-Schemarowset, finden Sie unter [DMSCHEMA_MINING_MODEL_CONTENT-Rowset](../analysis-services/schema-rowsets/data-mining/dmschema-mining-model-content-rowset.md).  
  
 Wenn eine \<knotenbeschriftung > nicht angegeben ist, wird die Funktion gibt die Wahrscheinlichkeit, dass die eingabefälle zum wahrscheinlichsten Cluster gehören. Verwenden der **Cluster** Funktion wahrscheinlichsten Clusters zurück.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird die Wahrscheinlichkeit dafür zurückgegeben, dass der angegebene Fall im Cluster mit der Bezeichnung Cluster 2 enthalten ist.  
  
```  
SELECT  
  ClusterProbability('Cluster 2')  
From  
  [TM Clustering]  
NATURAL PREDICTION JOIN  
(SELECT 28 AS [Age],  
  '2-5 Miles' AS [Commute Distance],  
  'Graduate Degree' AS [Education],  
  0 AS [Number Cars Owned],  
  0 AS [Number Children At Home]) AS t  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Cluster &#40;DMX&#41;](../dmx/cluster-dmx.md)   
 [Datamining-Erweiterungen &#40;DMX&#41; Funktionsreferenz](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Funktionen &#40;DMX&#41;](../dmx/functions-dmx.md)   
 [Allgemeine Vorhersagefunktionen &#40;DMX&#41;](../dmx/general-prediction-functions-dmx.md)  
  
  
