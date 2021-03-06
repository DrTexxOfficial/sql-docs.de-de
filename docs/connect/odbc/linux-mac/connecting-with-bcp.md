---
title: Herstellen einer Verbindung mit Bcp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- bcp
ms.assetid: 3eca5717-e50f-40db-be16-a1cebbdfee70
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: eff5cd89f349b3835eaace4d75c3a3a13655b4b0
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47682638"
---
# <a name="connecting-with-bcp"></a>Herstellen einer Verbindung mit bcp
[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]

Das Hilfsprogramm [bcp](http://go.microsoft.com/fwlink/?LinkID=190626) ist im [!INCLUDE[msCoName](../../../includes/msconame_md.md)] ODBC Driver for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unter Linux und macOS verfügbar. Diese Seite beschreibt die Unterschiede aus der Windows-Version von `bcp`.
  
- Das Feldabschlusszeichen ist ein Tabulator („\t“).  
  
- Das Zeilenabschlusszeichen ist ein Zeilenvorschub („\n“).  
  
- Zeichenmodus ist das bevorzugte Format für `bcp`-Formatdateien und -Datendateien, die keine Sonderzeichen enthalten.  
  
> [!NOTE]  
> Ein umgekehrter Schrägstrich „\\“ für ein Befehlszeilenargument muss entweder mit Anführungszeichen oder mit Escapezeichen versehen sein. Um z.B. einen Zeilenumbruch als benutzerdefiniertes Zeilenabschlusszeichen anzugeben, müssen Sie einen der folgenden Mechanismen verwenden:  
>   
> -   -R\\\n  
> -   -r"\n"  
> -   -r'\n'  
  
Der folgende Code ist ein Beispielbefehlsaufruf von `bcp` zum Kopieren von Tabellenzeilen in eine Textdatei:  
  
```  
bcp AdventureWorks2008R2.Person.Address out test.dat -Usa -Pxxxx -Sxxx.xxx.xxx.xxx  
```  
  
## <a name="available-options"></a>Verfügbare Optionen
In der aktuellen Version sind die folgende Syntax und die folgenden Optionen verfügbar:  

[_Datenbank_**.**] _Schema_**.** _Tabelle_ **in** _Daten\_Datei_ | **out** _Daten\_Datei_

- -a *packet_size*  
Gibt an, wie viele Bytes pro Netzwerkpaket an den Server bzw. vom Server gesendet werden.  
  
- -b *batch_size*  
Gibt die Anzahl von Zeilen pro importierten Datenbatch an.  
  
- -c  
Verwendet einen Zeichendatentyp.  
  
- -d *database_name*  
Gibt die Datenbank an, mit der eine Verbindung hergestellt werden soll.  
  
- -d  
Bewirkt, dass der Wert, der an die Option -S von `bcp` übergeben wird, als Datenquellenname (Data Source Name, DSN) interpretiert wird. Weitere Informationen finden Sie unter „DSN-Unterstützung in sqlcmd und bcp“ in [Herstellen einer Verbindung mit sqlcmd](../../../connect/odbc/linux-mac/connecting-with-sqlcmd.md).  
  
- -e *error_file* Gibt den vollständigen Pfad einer Fehlerdatei an, in der alle Zeilen gespeichert werden, die das Hilfsprogramm `bcp` nicht von der Datei in die Datenbank übertragen kann.  
  
- -E  
Verwendet für die Identitätsspalte in der importierten Datendatei einen Identitätswert oder -werte.  
  
- -f *format_file*  
Gibt den vollständigen Pfad einer Formatdatei an.  
  
- -F *first_row*  
Gibt die Nummer der ersten Zeile an, die aus einer Tabelle exportiert oder von einer Datendatei importiert werden soll.  
  
- -k  
Gibt an, dass während des Vorgangs keine Standardwerte in leere Spalten eingefügt werden, sondern ein NULL-Wert für diese Spalten beibehalten werden soll.  
  
- -l  
Gibt einen Anmeldungstimeout an. Die Option -I gibt an, wie viele Sekunden beim Herstellen einer Verbindung mit einem Server verstreichen dürfen, bevor für eine Anmeldung bei [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ein Timeout eintritt. Das Standardtimeout für die Anmeldung ist 15 Sekunden. Der Timeoutwert für den Anmeldungszeitraum muss eine Zahl zwischen 0 und 65534 sein. Wenn der angegebene Wert kein numerischer Wert ist oder außerhalb dieses Bereichs liegt, generiert `bcp` eine Fehlermeldung. Der Wert 0 gibt ein unendliches Timeout an.
  
- -L *last_row*  
Gibt die Nummer der letzten Zeile an, die aus einer Tabelle exportiert oder von einer Datendatei importiert werden soll.  
  
- -m *max_errors*  
Gibt an, wie viele Syntaxfehler maximal auftreten können, bevor der `bcp`-Vorgang abgebrochen wird.  
  
- -n  
Verwendet die systemeigenen (Datenbank-) Datentypen, um den Massenkopiervorgang auszuführen.  
  
- -P *password*  
Gibt das Kennwort für die Anmelde-ID an.  
  
- -Q  
Führt die SET QUOTED_IDENTIFIERS ON-Anweisung in der Verbindung zwischen dem Hilfsprogramm `bcp` und einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz aus.  
  
- -r *row_terminator*  
Gibt das Zeilenabschlusszeichen an.  
  
- -r  
Gibt an, dass beim Massenkopieren von Währungs-, Datums- und Zeitdaten in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] das Länderformat verwendet wird, das durch die Gebietsschemaeinstellung des Clientcomputers definiert wird.  
  
- -S *server*  
Gibt den Namen der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instanz herstellen oder wenn – D verwendet wird, einen DSN.  
  
- -t *field_terminator*  
Gibt das Feldabschlusszeichen an.  
  
- -T  
Gibt an, dass das Hilfsprogramm `bcp` die Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mithilfe einer vertrauenswürdigen Verbindung (integrierte Sicherheit) herstellt.  
  
- -U *login_id*  
Gibt die Anmelde-ID an, die zum Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet wird.  
  
- -V  
Meldet die Versionsnummer und das Copyright für das Hilfsprogramm `bcp`.  
  
- -w  
Verwendet Unicode-Zeichen, um den Massenkopiervorgang auszuführen.  
  
In dieser Version werden Latin-1- und UTF-16-Zeichen unterstützt.  
  
## <a name="unavailable-options"></a>Nicht verfügbare Optionen
In der aktuellen Version sind die folgende Syntax und die folgenden Optionen nicht verfügbar:  

- -c  
Gibt die Codepage für die in der Datendatei enthaltenen Daten an.  
  
- -h *hint*  
Gibt den oder die Hinweise an, die beim Massenimportieren von Daten in eine Tabelle oder Sicht verwendet werden.  
  
- -i *input_file*  
Gibt den Namen einer Antwortdatei an.  
  
- -n  
Verwendet die systemeigenen (Datenbank-) Datentypen für Daten, die keinen Zeichendatentyp haben, sowie Unicode-Zeichen für Zeichendaten.  
  
- -o *output_file*  
Gibt den Namen einer Datei an, in die die Ausgabe geschrieben wird, die von der Eingabeaufforderung umgeleitet wurde.  
  
- -V (80 | 90 | 100)  
Verwendet Datentypen aus einer früheren Version von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
- -X  
Bei Verwendung mit den Optionen Format und -f format_file wird anstelle der standardmäßigen Nicht-XML-Formatdatei eine XML-basierte Formatdatei generiert.  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter

[Herstellen einer Verbindung mit **sqlcmd**](../../../connect/odbc/linux-mac/connecting-with-sqlcmd.md)  
