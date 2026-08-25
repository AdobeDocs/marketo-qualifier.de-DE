---
title: Admin-Einstellungen
description: Erfahren Sie, wie Sie CRM-Felder, Aktivitätssynchronisierung, E-Mail-Opt-out und andere Sales Qualifier-Administrationseinstellungen verwalten.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/vbtO6I67ZEaZz3oio9InNErvq5D0wjbRxyDZpTq8Lzo'
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4bid: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
internal-label: Administration
source-git-commit: 08dd05e1d13b501d43d457e6217a43aaabdb1d0d
workflow-type: tm+mt
source-wordcount: 670
ht-degree: 0%

---


# Admin-Einstellungen

Verwenden Sie **[!UICONTROL Admin-Einstellungen]** um CRM-Integrationen zu konfigurieren, das Wissenscenter zu verwalten und E-Mail-Opt-outs zu konfigurieren.

Sales Qualifier stellt eine Verbindung zu Salesforce oder Microsoft Dynamics 365 her. Durch diese Verbindung erhält die Account Qualification Agent (AQA) eine konsistente Ansicht von Leads, Konten, Kontakten, Aktivitäten und Eigentümern. Sales Qualifier kann auch Outreach-Aktivitäten und den Opt-out-Status zurück in das CRM schreiben und Outreach-Aktivitäten mit Marketo synchronisieren.

Die CRM-Verbindungen, die Feldzuordnung und die Aktivitätssynchronisierung konfigurieren Sie unter **[!UICONTROL Administration]** > **[!UICONTROL Admin-Einstellungen]** > **[!UICONTROL CRM-Verbindungen]**. Standardbenutzer können die konfigurierten CRM-Daten und -Filter verwenden, diese Einstellungen jedoch nicht ändern. Informationen zum erstmaligen Verbinden eines CRM-Systems finden Sie unter [Erste Schritte](getting-started.md#connect-your-crm).

>[!IMPORTANT]
>
>Der Zugriff auf **[!UICONTROL Admin]** Einstellungen erfordert die Mitgliedschaft in den Benutzergruppen `Sales Qualifier` und `Sales Qualifier Admins`. Siehe [Benutzerrollen und Berechtigungen](user-roles-permissions.md).

## CRM MCP und das eingebettete Plug-in

Sales Qualifier arbeitet auf folgende Weise mit Ihrem CRM-System:

* **CRM-MCP** Abfragen: Live-CRM-Daten von Account Qualification Agent werden abgefragt, damit Antworten und Einblicke den aktuellen Status Ihrer Datensätze widerspiegeln.
* **Eingebettetes Plug-in** - Das CRM-Plug-in zeigt [!DNL Marketo Sales Insights] (MSI)-Einblicke und agentische Daten in Ihrem CRM an. Verwenden Sie das Plug-in, um einen potenziellen Kunden zu Sales Qualifier hinzuzufügen.
* **Aktivitätssynchronisierung** Wenn ein Administrator die Option **[!UICONTROL Aktivitätssynchronisierung]** aktiviert, werden die Outreach-Aktivitäten mit dem CRM und Marketo synchronisiert.

## CRM-Zugriffsbereich

Sales Qualifier liest Benutzer, Kontakte, Besitzerzuordnungen, Leads, Konten, Chancen und Aktivitäten aus dem CRM. Es werden nur protokollierte Outreach-Aktivitäten und der Opt-out-Status in das CRM geschrieben und Outreach-Aktivitäten werden mit Marketo synchronisiert. Ihr CRM-Administrator bereitet den API-Zugriff in Salesforce oder Dynamics vor. Ein Sales Qualifier-Administrator verbindet dann das CRM, ordnet eingehende Felder zu und entscheidet, ob die Aktivitäten synchronisiert werden sollen.

>[!NOTE]
>
>Die Schritte zur Anmeldung in [Erste Schritte](getting-started.md#connect-your-crm) beschreiben den Lesezugriff auf CRM-Objekte. Wenn Sie die Aktivitätssynchronisierung oder das Opt-out-Writeback aktivieren, wenden Sie sich an Ihren CRM-Administrator, um ihm den entsprechenden für Ihre CRM-Konfiguration erforderlichen Schreibzugriff zu gewähren.

## CRM-Felder zuordnen (eingehende Zuordnung)

Nachdem das CRM verbunden ist, wählen Sie **[!UICONTROL Verwalten]** für die Verbindung aus und öffnen Sie **[!UICONTROL Eingehende Zuordnung]**. Eingehende Zuordnungen steuern, welche CRM-Felder Sales Qualifier in die Anwendung holt.

1. Wählen Sie **[!UICONTROL Abschnitt hinzufügen]** aus.
1. Geben Sie einen Namen und eine Beschreibung für den Abschnitt ein.
1. Einen Entitätstyp auswählen. **[!UICONTROL Interessenten]** ist standardmäßig ausgewählt. **[!UICONTROL Kontakte]**, **[!UICONTROL Konten]** und **[!UICONTROL Opportunities]** sind ebenfalls verfügbar.
1. CRM-Felder zum Importieren auswählen.

   Jede Feldzeile zeigt ihren **[!UICONTROL Anzeigenamen]**, **[!UICONTROL Feldname]** und **[!UICONTROL Datentyp]** an.

1. Aktivieren **[!UICONTROL Filterbar]** für jedes Feld eines Interessenten, Kontakts oder einer Opportunity, das bzw. die Sie als Filter in der Liste **[!UICONTROL Interessenten]** verfügbar machen möchten.
1. Zeigen Sie eine Vorschau des Abschnitts an und wählen Sie **[!UICONTROL Hinzufügen]**.

Zugeordnete Felder werden in den entsprechenden Bereichen von Sales Qualifier angezeigt:

* Felder für Interessenten werden auf der Registerkarte **[!UICONTROL Person]** angezeigt.
* Kontofelder werden auf der Registerkarte **[!UICONTROL Konto]** angezeigt.
* Die Felder für die Opportunity werden im Abschnitt **[!UICONTROL Account-Opportunity]** angezeigt. Filterbare Opportunity-Felder werden auch als eigene Spalten in **[!UICONTROL Meine Opportunity-Kontakte]** mit Bezeichnungen wie **[!UICONTROL Phase (Opportunity)]** angezeigt, um sie von Kontaktfeldern zu unterscheiden.

## Aktivitätssynchronisierung konfigurieren (ausgehende Zuordnung)

1. Wählen Sie **[!UICONTROL CRM-Verbindungen]** die Option **[!UICONTROL Verwalten]** für das verbundene CRM aus.
1. Öffnen Sie **[!UICONTROL Ausgehende Zuordnung]**.
1. Aktivieren Sie **[!UICONTROL Aktivitätssynchronisierung]** um Sales Qualifier-Outreach-Aktivitäten mit dem CRM und Marketo zu synchronisieren. Die Aktivitäten „Gesendet“, „Geöffnet“, „Klickt“ und „Antwort“ enthalten den Namen des Interaktionsplans.

Wenn die Aktivitätssynchronisierung deaktiviert ist, verwendet Sales Qualifier weiterhin eingehende CRM-Daten, synchronisiert jedoch keine Outreach-Aktivitäten mit dem CRM oder Marketo.

## Konfigurieren des globalen E-Mail-Opt-outs

1. Erweitern Sie in der linken Navigation **[!UICONTROL Administration]** und wählen Sie **[!UICONTROL Admin-Einstellungen]** aus.
1. Wählen Sie **[!UICONTROL E-Mail]** Einstellungen unter **[!UICONTROL Compliance]** aus.
1. Aktivieren Sie **[!UICONTROL Ausschluss-Link in jeder E-Mail einschließen]** um eine Fußzeile zur Abmeldung an ausgehende E-Mails anzuhängen.
1. Geben **[!UICONTROL in der Opt]** out-Nachrichtenvorlage den Fußzeilentext ein. Fügen Sie das `{opt_out_link}`-Token ein, in dem der Abmelde-Link angezeigt werden soll.

Die Einstellungen werden automatisch gespeichert.

Wenn ein Interessent den Link auswählt, sendet Sales Qualifier keine E-Mails mehr an diesen Interessenten und synchronisiert den Opt-out-Status mit dem verbundenen CRM.

## Referenz: Beispiel-API-Parameter

Ihr CRM-Team kann diese Beispiele verwenden, um zu bestätigen, dass der Lesezugriff die erwarteten Lead-Felder zurückgibt.

### Dynamics OData-Beispiel

```text
$select=fullname,_ownerid_value,leadid,emailaddress1,jobtitle,statuscode,createdon,modifiedon,statecode
$filter=_ownerid_value eq '<crmUserId>' [AND additional filters]
$expand=Lead_ActivityPointers(...),parentaccountid(...)
$orderby=modifiedon desc
```

### Salesforce SOQL-Beispiel

```sql
SELECT Id, Salutation, FirstName, LastName, Name, Title, Company, Email,
  LeadSource, Status, OwnerId, LastModifiedDate, LastActivityDate, CreatedDate,
  (SELECT Id, Subject, ActivityDate, Status FROM Tasks ORDER BY ActivityDate DESC LIMIT 1),
  (SELECT Id, Subject, ActivityDateTime FROM Events ORDER BY ActivityDateTime DESC LIMIT 1)
FROM Lead
WHERE OwnerId = '<crmUserId>' AND IsDeleted = false
ORDER BY LastModifiedDate DESC
```

>[!MORELIKETHIS]
>
>* [Erste Schritte](getting-started.md)
>* [Benutzerrollen und -berechtigungen](user-roles-permissions.md)
>* [Interessenten](prospects.md)
