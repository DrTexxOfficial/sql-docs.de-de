---
title: Konfiguration des SQL Server Trusted Launchpad-Dienstkontos | Microsoft-Dokumentation
description: So ändern Sie das Trusted Launchpad für SQL Server-Dienstkonto für die Ausführung des externen Skripts für SQL Server verwendet werden.
ms.prod: sql
ms.technology: machine-learning
ms.date: 09/27/2018
ms.topic: conceptual
author: dphansen
ms.author: davidph
manager: cgronlun
ms.openlocfilehash: 85d96d758d2f363b3b4ec40131723ad10613b64c
ms.sourcegitcommit: 485e4e05d88813d2a8bb8e7296dbd721d125f940
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49100391"
---
# <a name="sql-server-launchpad-service-configuration"></a>Konfiguration von SQL Server Launchpad-Diensts
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Die [!INCLUDE[rsql_launchpad_md](../../includes/rsql-launchpad-md.md)] ist ein Dienst, der verwaltet und externer Skripts, ähnlich wie die, dass der Volltextsuchdienst indizierungs- und einen separaten Host startet, für die Verarbeitung von Volltextabfragen ausführt.

Eine Separate [!INCLUDE[rsql_launchpad_md](../../includes/rsql-launchpad-md.md)] Dienst erstellt und für jede Instanz der Datenbank-Engine, dem Sie SQL Server Machine learning (R oder Python) Integration hinzugefügt haben.

Weitere Informationen finden Sie unter den Launchpad-Abschnitten in [erweiterbarkeitsarchitektur in SQL Server Machine Learning Services](../../advanced-analytics/concepts/extensibility-framework.md#launchpad) und [Sicherheit: Übersicht für das Extensibility Framework in SQL Server-Machine Learning Dienste](../../advanced-analytics/concepts/security.md#launchpad).

## <a name="account-permissions"></a>Kontoberechtigungen

Standardmäßig ist SQL Server Launchpad für die Ausführung unter konfiguriert **NT Service\MSSQLLaunchpad**, die mit allen erforderlichen Berechtigungen zum Ausführen externer Skripts bereitgestellt wird. Entfernen von Berechtigungen, die dieses Konto kann dazu führen Launchpad, die Fehler bei der starten oder für den Zugriff auf SQL Server-Instanz, in dem externe Skripts ausgeführt werden soll.

Wenn Sie das Dienstkonto ändern, achten Sie darauf mit der **Local Security Policy** Anwendung (**alle apps** > **Windows-Verwaltung**  >  **Lokale Sicherheitsrichtlinie**).

Erforderliche Berechtigungen für dieses Konto sind in der folgenden Tabelle aufgeführt.

| Gruppenrichtlinieneinstellung | Konstantennamen |
|----------------------|---------------|
| [Anpassen des arbeitsspeicherkontingents für einen Prozess](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/adjust-memory-quotas-for-a-process) | SeIncreaseQuotaPrivilege | 
| [Auslassen der durchsuchenden Überprüfung](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/bypass-traverse-checking) | SeChangeNotifyPrivilege | 
| [Melden Sie sich als Dienst](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) | SeServiceLogonRight | 
| [Ersetzen von Token auf Prozessebene](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/replace-a-process-level-token) | SeAssignPrimaryTokenPrivilege | 

Weitere Informationen zu erforderlichen Berechtigungen für das Ausführen von SQL Server-Diensten finden Sie unter [Konfigurieren von Windows-Dienstkonten und -Berechtigungen](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).

<a name="bkmk_ChangingConfig"></a> 

## <a name="configuration-properties"></a>Konfigurationseigenschaften

Es gibt in der Regel keinen Grund zum Ändern der Dienstkonfiguration. Eigenschaften, die geändert werden können, gehören das Dienstkonto, die Anzahl von externen Prozessen (standardmäßig 20), oder das Kennwort zurückzusetzen, Richtlinien für Konten.

1. Öffnen Sie den [SQL Server-Konfigurations-Manager](../../relational-databases/sql-server-configuration-manager.md). 

  + Geben Sie auf der Startseite **MMC** zu Microsoft Management Console zu öffnen.

  + Auf **Datei** > **Snap-In hinzufügen/entfernen**, verschieben Sie **SQL Server-Konfigurations-Manager** aus ausgewählte-Snap-ins zur Verfügung.

2. In SQL Server Konfigurations-Manager unter SQL Server-Dienste mit der rechten Maustaste in SQL Server Launchpad, und wählen Sie **Eigenschaften**.

  + Um das Dienstkonto zu ändern, klicken Sie auf die **anmelden** Registerkarte.

  + Um die Anzahl von Benutzern zu erhöhen, klicken Sie auf die **erweitert** Registerkarte.

> [!Note]
> In frühen Versionen von SQL Server 2016 R Services, können Sie einige Eigenschaften des Diensts ändern, indem Sie die Bearbeitung der [!INCLUDE[rsql_productname](../../includes/rsql-productname-md.md)] Konfigurationsdatei. Diese Datei wird nicht mehr zum Ändern von Konfigurationen. SQL Server-Konfigurations-Manager ist der richtige Ansatz für Änderungen an der Dienstkonfiguration, wie z. B. das Dienstkonto und die Anzahl von Benutzern.

## <a name="debug-settings"></a>Debug-Einstellungen

Einige Eigenschaften können nur geändert werden, mithilfe Launchpads-Konfigurationsdatei, die sich in selteneren Fällen, z. B. Debuggen hilfreich sein kann. Die Konfigurationsdatei wird erstellt, während der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einrichten und in der Standardeinstellung als nur-Text-Datei am folgenden Speicherort gespeichert: `<instance path>\binn\rlauncher.config`

Sie müssen Administrator auf dem Computer sein, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird, um diese Datei ändern zu können. Für die Bearbeitung der Datei wird empfohlen, dass Sie eine Sicherungskopie erstellen, bevor Sie Änderungen speichern.

Die folgende Tabelle enthält die erweiterten Einstellungen für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], mit den zulässigen Werten. 

|**Einstellungsname**|**Typ**|**Beschreibung**|
|----|----|----|
|AUFTRAG\_BEREINIGUNG\_ON\_BEENDEN|Integer |Dies ist eine interne Einstellung – ändern Sie diesen Wert nicht. </br></br>Gibt an, ob es sich bei der temporären Arbeitsordner erstellt für jede externe Common Language Runtime-Sitzung bereinigt werden soll, nachdem die Sitzung abgeschlossen ist. Diese Einstellung ist beim Debuggen nützlich. </br></br>Unterstützte Werte sind **0** (deaktiviert) oder **1** (aktiviert). </br></br>Der Standardwert ist 1, die Bedeutung von Protokolldateien beim Beenden entfernt.|
|ABLAUFVERFOLGUNG\_EBENE|Integer |Konfiguriert den Ausführlichkeitsgrad der Ablaufverfolgung von MSSQLLAUNCHPAD zu Debugzwecken an. Dies wirkt sich die Ablaufverfolgungsdateien im Pfad durch die Einstellung LOG_DIRECTORY angegeben. </br></br>Unterstützte Werte sind: **1** (Fehler), **2** (Leistung), **3** (Warnung), **4** (Informationen). </br></br>Der Standardwert ist 1, d. h. nur Ausgabe von Warnungen.|

Alle Einstellungen haben die Form eines Schlüssel-Wert-Paars, bei dem jede Einstellung in einer separaten Zeile enthalten ist. Klicken Sie z. B., um das Level der Ablaufverfolgung zu ändern, hinzufügen die Zeile `Default: TRACE_LEVEL=4`.

## <a name="enforcing-password-policy"></a>Kennwortrichtlinie erzwingen

Wenn Ihre Organisation eine Richtlinie hat, die das regelmäßige Ändern von Kennwörtern erfordert, müssen Sie möglicherweise den Launchpad-Dienst zwingen, die verschlüsselten Kennwörter erneut zu generieren, die Launchpad für seine Workerkonten verwaltet.

Öffnen Sie den Bereich **Eigenschaften** für den Launchpad-Dienst in SQL Server Configuration Manager, klicken Sie auf **Erweitert**, und ändern Sie **Reset External Users Password** (Kennwörter externer Benutzer zurücksetzen) in **Yes** (Ja). Wenn Sie diese Änderung übernehmen, werden die Kennwörter sofort für alle Benutzerkonten erneut generiert. Sie müssen den Launchpad-Dienst neu starten, um R-Skripts nach dieser Änderungen verwenden zu können; nun werden auch die neu generierten Kennwörter gelesen.

Sie können dieses Flag entweder manuell festlegen oder dazu ein Skript verwenden.

## <a name="see-also"></a>Siehe auch

[Erweiterungsframework](../concepts/extensibility-framework.md)

[Sicherheitsübersicht](../concepts/security.md)
