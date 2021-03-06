---
title: Neugestalten | Microsoft-Dokumentation
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- reshaping previously shaped Recordset [ADO]
- data shaping [ADO], reshaping
ms.assetid: b1c965b7-3dad-4de6-9e0e-502ca8785be3
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 324801cbfc97db4e2a1137fa04df0c74dc1897a1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47714528"
---
# <a name="reshaping"></a>Neustrukturierung
Ein **Recordset** erstellt von einer Klausel in einer Form Befehl zugewiesen werden kann ein *Alias* Name (in der Regel mit dem AS-Schlüsselwort). Der Alias des eine geformten **Recordset** in einem völlig anderen Befehl verwiesen werden kann. D. h. Sie können wieder verwenden, oder *umformen*, eine zuvor geformten **Recordset** in einem neuen Shape-Befehl. Um dieses Feature zu unterstützen, stellt ADO eine Eigenschaft bereit, mit denen [Reshape Name](../../../ado/reference/ado-api/reshape-name-property-dynamic-ado.md).  
  
 Neu gestaltet werden, verfügt über zwei Hauptfunktionen aus. Die erste besteht darin, ordnen Sie einer vorhandenen **Recordset** mit einem neuen übergeordneten **Recordset**.  
  
## <a name="example"></a>Beispiel  
  
```  
rs1.Open "SHAPE {select * from Customers} " & _  
         "APPEND ({select * from Orders} AS chapOrders " & _  
         "RELATE CustomerID to CustomerID)", cn  
  
rs2.Open "SHAPE {select * from Employees} " & _  
         "APPEND (chapOrders RELATE EmployeeID to EmployeeID)", cn  
```  
  
 Die zweite Funktion ist nicht in Kapitel unterteilten Zugriff auf vorhandene untergeordnete ermöglichen **Recordset** Objekte, mit der Syntax "Form \<Recordset reshape Name >".  
  
> [!NOTE]
>  Spalten kann nicht angefügt werden, zu einem vorhandenen **Recordset**, strukturieren einer parametrisierten **Recordset** oder **Recordset** Objekte in der alle dazwischen liegenden COMPUTE-Klausel, oder führen aggregieren Sie Vorgänge für alle **Recordset** Nachfolger der **Recordset** Clientszenarios wird. Die **Recordset** Clientszenarios wird und die neue Form-Befehl müssen beide verwenden Sie den gleichen [Verbindung](../../../ado/reference/ado-api/connection-object-ado.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Data Shaping Example (Beispiele der Datenstrukturierung)](../../../ado/guide/data/data-shaping-example.md)
