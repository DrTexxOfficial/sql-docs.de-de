---
title: TRIM (SSIS-Ausdruck) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- leading blanks
- TRIM function
- trailing blanks
ms.assetid: 7dd9081d-a3d4-483a-bf7e-bf2bd7692d39
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b66c351b52646dd363241ffc8562aa39be241f18
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47792418"
---
# <a name="trim-ssis-expression"></a>TRIM (SSIS-Ausdruck)
  Gibt einen Zeichenausdruck zurück, nachdem führende und nachfolgende Leerzeichen entfernt wurden.  
  
> [!NOTE]  
>  Mit TRIM werden keine Leerzeichen entfernt, wie z. B. Tabulatoren oder Zeilenvorschubzeichen. Unicode stellt Codeelemente für viele verschiedene Arten von Leerzeichen bereit, diese Funktion erkennt jedoch nur das Unicode-Codeelement 0x0020. DBCS-Zeichenfolgen, die in Unicode konvertiert werden, enthalten u. U. andere Leerzeichen als 0x0020. Diese Leerzeichen können von der Funktion nicht entfernt werden. Zum Entfernen aller Arten von Leerzeichen können Sie die Trim-Methode von Microsoft Visual Basic .NET in einem Skript verwenden, das aus der Skriptkomponente ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
TRIM(character_expression)  
```  
  
## <a name="arguments"></a>Argumente  
 *character_expression*  
 Ein Zeichenausdruck, aus dem Leerzeichen entfernt werden sollen.  
  
## <a name="result-types"></a>Ergebnistypen  
 DT_WSTR  
  
## <a name="remarks"></a>Remarks  
 TRIM gibt ein NULL-Ergebnis zurück, wenn das Element NULL ist.  
  
 TRIM kann nur mit dem DT_WSTR-Datentyp verwendet werden. Ein *character_expression* -Argument, das ein Zeichenfolgenliteral oder eine Datenspalte mit dem DT_STR-Datentyp ist, wird implizit in den DT_WSTR-Datentyp umgewandelt, bevor TRIM ausgeführt wird. Andere Datentypen müssen explizit in den DT_WSTR-Datentyp umgewandelt werden. Weitere Informationen finden Sie unter [Integration Services-Datentypen](../../integration-services/data-flow/integration-services-data-types.md) und [CAST &#40;SSIS-Ausdruck&#41;](../../integration-services/expressions/cast-ssis-expression.md).  
  
## <a name="expression-examples"></a>Beispiele für Ausdrücke  
 In diesem Beispiel werden führende und nachfolgende Leerzeichen aus einem Zeichenfolgenliteral entfernt. Als Ergebnis wird "New York" zurückgegeben.  
  
```  
TRIM("   New York   ")  
```  
  
 In diesem Beispiel werden führende und nachfolgende Leerzeichen aus dem Ergebnis der Verkettung der Spalten **FirstName** und **LastName** entfernt. Die leere Zeichenfolge zwischen **FirstName** und **LastName** wird nicht entfernt.  
  
```  
TRIM(FirstName + " "+ LastName)  
```  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [LTRIM &#40;SSIS-Ausdruck&#41;](../../integration-services/expressions/ltrim-ssis-expression.md)   
 [RTRIM &#40;SSIS-Ausdruck&#41;](../../integration-services/expressions/rtrim-ssis-expression.md)   
 [Funktionen &#40;SSIS-Ausdruck&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
