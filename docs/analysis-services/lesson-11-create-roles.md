---
title: 'Lektion 12: Erstellen von Rollen | Microsoft-Dokumentation'
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: tutorial
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 7ec7afeddeeb4aae53f1368f55e2af5ec3ffcd0e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "37985884"
---
# <a name="lesson-11-create-roles"></a>Lektion 11: Erstellen von Rollen
[!INCLUDE[ssas-appliesto-sql2016-later-aas](../includes/ssas-appliesto-sql2016-later-aas.md)]

In dieser Lektion erstellen Sie Rollen. Rollen stellen Modelldatenbankobjekt- und Datensicherheit bereit, indem sie den Zugriff auf die Windows-Benutzer einschränken, die Rollenmitglieder sind. Jede Rolle wird mit einer einzelnen Berechtigung definiert: Keine, Lesen, Lesen und verarbeiten, Verarbeiten oder Administrator. Rollen können während der Modellerstellung mithilfe des Rollen-Manager definiert werden. Nachdem ein Modell bereitgestellt wurde, können Sie mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Rollen verwalten. Weitere Informationen finden Sie unter [Rollen](../analysis-services/tabular-models/roles-ssas-tabular.md)während der Modellerstellung im Dialogfeld Rollen-Manager definiert werden.  
  
> [!NOTE]  
> Das Erstellen von Rollen ist zum Abschließen dieses Lernprogramms nicht erforderlich. Das Konto, über das Sie derzeit angemeldet sind, verfügt standardmäßig über Administratorberechtigungen für das Modell. Um anderen Benutzern in Ihrer Organisation, die das Modell mit einem berichterstellungsclient durchsuchen können, müssen Sie allerdings mindestens eine Rolle mit Leseberechtigungen erstellen und diese Benutzer als Mitglieder hinzugefügt.  
  
Sie erstellen drei Rollen:  
  
-   **Vertriebsleiter** – diese Rolle kann Benutzer beinhalten, in Ihrer Organisation, die für die Leseberechtigungen für alle Modellobjekte und Daten haben sollen.  
  
-   **Sales Analyst US** – diese Rolle kann Benutzer beinhalten, in Ihrer Organisation, die für die Sie nur Daten zum Vertrieb in den Vereinigten Staaten wechseln können möchten. Für diese Rolle definieren Sie mit einer DAX-Formel einen *Zeilenfilter*, der Mitgliedern der Rolle lediglich das Durchsuchen von Daten in den USA ermöglicht.  
  
-   **Administrator** – diese Rolle kann Benutzer für die Administratorberechtigung, sind der unbegrenzten Zugriff und Berechtigungen zum Ausführen von administrativer Aufgaben für die Modelldatenbank beinhalten.  
  
Da Windows-Benutzer- und -Gruppenkonten in der Organisation eindeutig sind, können Sie Mitgliedern Konten aus Ihrer Organisation hinzufügen. In diesem Lernprogramm können Sie die Angaben zu den Mitgliedern auch weglassen. Sie können die Auswirkungen der einzelnen Rollen immer noch in "Lektion 12: Analysieren in Excel" testen.  
  
Geschätzte Zeit zum Bearbeiten dieser Lektion: **15 Minuten**  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
Dieses Thema ist Teil eines Lernprogramms zur Tabellenmodellierung, das in der entsprechenden Reihenfolge bearbeitet werden sollte. Vor dem Ausführen der Aufgaben in dieser Lektion an, Sie sollten die vorherige Lektion abgeschlossen haben: [Lektion 10: Erstellen von Partitionen](../analysis-services/lesson-10-create-partitions.md).  
  
## <a name="create-roles"></a>Erstellen von Rollen  
  
#### <a name="to-create-a-sales-manager-user-role"></a>So erstellen Sie die Benutzerrolle "Sales Manager"  
  
1.  Im tabellarischen Modell-Explorer mit der Maustaste **Rollen** > **Rollen**.  
  
2.  Klicken Sie im Rollen-Manager **neu**.  
  
3.  Klicken Sie auf die neue Rolle, und klicken Sie dann in der **Namen** Spalte benennen Sie die Rolle zum **Vertriebsleiter**.  
  
4.  Klicken Sie in der Spalte **Berechtigungen** auf die Dropdownliste, und wählen Sie anschließend die Berechtigung **Lesen** aus. 

    ![als-tabellarische-lesson11-neue-Rolle](../analysis-services/media/as-tabular-lesson11-new-role.png) 
  
5.  Optional: Klicken Sie auf die **Mitglieder** Registerkarte, und klicken Sie dann auf **hinzufügen**. Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** die Windows-Benutzer oder -Gruppen in Ihrer Organisation ein, die Sie der Rolle hinzufügen möchten.  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a>So erstellen Sie die Benutzerrolle "Sales Analyst US"  
  
1.  Klicken Sie im Rollen-Manager **neu**.    
  
2.  Benennen Sie die Rolle zum **Sales Analyst US**.  
  
3.  Erteilen Sie dieser Rolle **lesen** Berechtigung.  
  
4.  Klicken Sie auf der Registerkarte "Zeilenfilter", und klicken Sie dann für die **DimGeography** Tabelle nur in der Spalte DAX-Filter geben Sie die folgende Formel:  
  
    ```
    =DimGeography[CountryRegionCode] = "US" 
    ```
    
    Eine Zeilenfilterformel muss in einen booleschen Wert (TRUE/FALSE) aufgelöst werden. Mit dieser Formel legen Sie fest, dass nur Zeilen mit dem Länder-/Regionscode (Country Region Code) "US" für den Benutzer sichtbar sind.  
    ![als-tabellarische-lesson11-Rolle-filter](../analysis-services/media/as-tabular-lesson11-role-filter.png) 
  
6.  Optional: Klicken Sie auf die Registerkarte **Mitglieder** und anschließend auf **Hinzufügen**. Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** die Windows-Benutzer oder -Gruppen in Ihrer Organisation ein, die Sie der Rolle hinzufügen möchten.  
  
#### <a name="to-create-an-administrator-user-role"></a>Erstellen Sie eine Administrator-Benutzerrolle  
  
1.  Klicken Sie auf **Neu**.  
  
2.  Benennen Sie die Rolle zum **Administrator**.  
  
3.  Erteilen Sie dieser Rolle **Administrator** Berechtigung.  
  
4.  Optional: Klicken Sie auf die Registerkarte **Mitglieder** und anschließend auf **Hinzufügen**. Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** die Windows-Benutzer oder -Gruppen in Ihrer Organisation ein, die Sie der Rolle hinzufügen möchten. 
  
  
## <a name="whats-next"></a>Wie geht es weiter?
Wechseln Sie zur nächsten Lektion: [Lektion 12: Analysieren in Excel](../analysis-services/lesson-12-analyze-in-excel.md).

  
  
