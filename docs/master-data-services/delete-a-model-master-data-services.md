---
title: Löschen eines Modells (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology:
- master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting models [Master Data Services]
- models [Master Data Services], deleting models
ms.assetid: f0ad3cc4-aed7-47c8-94bc-2971fe9fe871
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: bf09705d0ccec2707d19a89af7321ff86d861ee1
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47755428"
---
# <a name="delete-a-model-master-data-services"></a>Löschen eines Modells (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Löschen Sie ein Modell, um das Modell und alle zugehörigen Daten aus [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]zu entfernen.  
  
> [!NOTE]  
>  Nach Abschluss dieser Prozedur sind alle Objekte und alle Daten aus allen Versionen des Modells permanent gelöscht.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Systemverwaltung** zuzugreifen.  
  
-   Sie müssen ein Modelladministrator sein. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)zuzugreifen.  
  
### <a name="to-delete-a-model"></a>So löschen Sie ein Modell  
  
1.  Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.  
  
2.  Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Modelle**.  
  
3.  Wählen Sie auf der Seite **Modelle verwalten** im Raster die Zeile des Modells aus, das Sie löschen möchten.  
  
4.  Klicken Sie auf **Löschen**.  
  
5.  Klicken Sie im Bestätigungsdialogfeld auf **OK**.  
  
6.  Klicken Sie im zusätzlichen Bestätigungsdialogfeld auf **OK**.  
  
 Die Spalte **Status** im Raster zeigt den Status des Vorgangs für das Modell. Beim Klicken auf die Schaltfläche **Modell speichern** wird das Bild ![Aktualisieren](../master-data-services/media/mds-model-status-updating.png "Updating") angezeigt, das angibt, dass das Modell aktualisiert wird. Wenn beim Erstellen oder Bearbeiten eines Modells Fehler auftreten, wird das Bild ![Fehler](../master-data-services/media/mds-model-status-error.png "Error") angezeigt. Andernfalls lautet der Status „OK“, und das Bild ![OK](../master-data-services/media/mds-model-status-ok.png "OK") angezeigt.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Modelle &#40;Master Data Services&#41;](../master-data-services/models-master-data-services.md)   
 [Erstellen eines Modells &#40;Master Data Services&#41;](../master-data-services/create-a-model-master-data-services.md)  
  
  
