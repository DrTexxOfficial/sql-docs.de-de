---
title: Erstellen und Bereitstellen eine leere Datenbank (Analysis Services AMO-TOM) | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: afacae6ab8fc6f5a4f592e87758cca3142579c0a
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "34038563"
---
# <a name="create-and-deploy-an-empty-database-analysis-services-amo-tom"></a>Erstellen und Bereitstellen einer leeren Datenbank (Analysis Services AMO-TOM)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
Ein gängiges Programmiermodells Szenario für AMO-TOM besteht darin Datenbanken und -Modelle im Handumdrehen zu generieren. Dieser Artikel führt Sie durch die Schritte zum Erstellen einer Datenbank. 

Für tabellarische Lösungen besteht eine 1: 1-Entsprechung zwischen einer Datenbank- und modellsicherheitseinstellungen, mit der ein Modell pro Datenbank zur Verfügung. Sie können einen oder anderen in der Regel angeben, und das Modul wird das fehlende Objekt ableiten. 

Erstellen und Bereitstellen einer neuen Datenbank ist eine dreiteilige Aufgabe: 

* Instanziieren einer **Datenbank** Objekt, und legen Sie die Eigenschaften, einschließlich eines Namens. 

* Hinzufügen der **Datenbank** -Objekt an eine **Server.Databases** Auflistung. 

* Rufen Sie die **Update** Methode für die **Datenbank** Objekt zum Speichern der **Server**. 

## <a name="code-example-create-empty-database"></a>Codebeispiel: leere Datenbank erstellen 

```
using System; 
using Microsoft.AnalysisServices; 
using Microsoft.AnalysisServices.Tabular; 
 
namespace TOMSamples 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // 
            // Connect to the local default instance of Analysis Services 
            // 
            string ConnectionString = "DataSource=localhost"; 
 
            // 
            // The using syntax ensures the correct use of the 
            // Microsoft.AnalysisServices.Tabular.Server object. 
            // 
            using (Server server = new Server()) 
            { 
                server.Connect(ConnectionString); 
 
                // 
                // Generate a new database name and use GetNewName 
                // to ensure the database name is unique. 
                // 
                string newDatabaseName = 
                    server.Databases.GetNewName("New Empty Database"); 
 
                // 
                // Instantiate a new  
                // Microsoft.AnalysisServices.Tabular.Database object. 
                // 
                var blankDatabase = new Database() 
                { 
                    Name = newDatabaseName, 
                    ID = newDatabaseName, 
                    CompatibilityLevel = 1200, 
                    StorageEngineUsed = StorageEngineUsed.TabularMetadata, 
                }; 
                // 
                // Add the new database object to the server's  
                // Databases connection and submit the changes 
                // with full expansion to the server. 
                // 
                server.Databases.Add(blankDatabase); 
                blankDatabase.Update(UpdateOptions.ExpandFull); 

                Console.Write("Database "); 
                Console.ForegroundColor = ConsoleColor.Yellow; 
                Console.Write(blankDatabase.Name); 
                Console.ResetColor(); 
                Console.WriteLine(" created successfully."); 
                Console.WriteLine(); 
            } 
            Console.WriteLine("Press Enter to close this console window."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="next-steps"></a>Nächste Schritte 

Sobald eine Datenbank erstellt wurde, können Sie Modellobjekte hinzufügen: 

- [Hinzufügen einer Datenquelle mit einem tabellarischen Modell](../../analysis-services/tabular-model-programming-compatibility-level-1200/add-a-data-source-to-tabular-model-analysis-services-amo-tom.md)
- [Erstellen von Tabellen, Partitionen und Spalten in einem tabellarischen Modell](../../analysis-services/tabular-model-programming-compatibility-level-1200/create-tables-partitions-and-columns-in-a-tabular-model.md)
 
