---
title: Sys. xml_indexes (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.xml_indexes_TSQL
- xml_indexes_TSQL
- sys.xml_indexes
- xml_indexes
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_indexes catalog view
ms.assetid: 3408de72-b067-4fda-b5d5-8e856dfd9db3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 69e6102d6d74604c59a6dc6e827dfd0226170987
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47777978"
---
# <a name="sysxmlindexes-transact-sql"></a>sys.xml_indexes (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt eine Zeile pro XML-Index zurück.  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**\<geerbte Spalten >**||Erbt Spalten von [sys.indexes](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md).|  
|**using_xml_index_id**|**int**|NULL = Primärer XML-Index.<br /><br /> Nonnull = Sekundärer XML-Index.<br /><br /> Nonnull ist ein Selbstjoinhinweis auf den primären XML-Index.|  
|**secondary_type**|**char(1)**|Typbeschreibung des sekundären Indexes:<br /><br /> P = sekundärer XML-Index vom Typ PATH<br /><br /> V = sekundärer XML-Index vom Typ VALUE<br /><br /> R = sekundärer XML-Index vom Typ PROPERTY<br /><br /> NULL = Primärer XML-Index|  
|**secondary_type_desc**|**nvarchar(60)**|Typbeschreibung des sekundären Indexes:<br /><br /> PATH = sekundärer XML-Index vom Typ PATH<br /><br /> VALUE = sekundärer XML-Index vom Typ VALUE<br /><br /> PROPERTY = sekundäre XML-Indizes vom Typ PROPERTY<br /><br /> NULL = Primärer XML-Index|  
|**xml_index_type**|**tinyint**|Indextyp:<br /><br /> 0 = Primärer XML-Index<br /><br /> 1 = Sekundärer XML-Index<br /><br /> 2 = Selektiver XML-Index<br /><br /> 3 = Sekundärer, selektiver XML-Index|  
|**xml_index_type_description**|**nvarchar(60)**|Beschreibung des Typs des Index:<br /><br /> PRIMARY_XML<br /><br /> Sekundärer XML-Index<br /><br /> Selektiver XML-Index<br /><br /> Sekundärer, selektiver XML-Index|  
|**path_id**|**int**|NULL für alle XML-Indizes, mit Ausnahme sekundärer, selektiver XML-Indizes.<br /><br /> Andernfalls die ID des höher gestuften Pfads, über den der sekundäre, selektive XML-Index erstellt wird. Dieser Wert entspricht dem Wert von Dieser Wert entspricht dem Wert von path_idpath_id aus der sys.selective_xml_index_paths-Systemsicht.|  
  
## <a name="permissions"></a>Berechtigungen  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Weitere Informationen finden Sie unter [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Katalogsichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Objekt-Katalogsichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)  
  
  
