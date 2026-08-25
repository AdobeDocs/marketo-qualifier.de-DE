---
title: Benutzerrollen und -berechtigungen
description: Erfahren Sie, wie Sales Qualifier-Benutzergruppen den Zugriff auf Programme und Administratoren steuern.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
TQID: 'https://experienceleague.adobe.com/9X9DYGMvLGcPG--G6rHcDEk91hdT9-XYc9wbiL2Qoww'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
  - id: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: d6a8091bd893ea80a26edfc1526646aec037223f
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 4%

---


# Benutzerrollen und -berechtigungen

Sales Qualifier verwendet zwei erforderliche Benutzergruppen, um Vertriebsaufgaben von der organisationsweiten Konfiguration zu trennen.

## Erforderliche Benutzergruppen

| Gruppe | Wer gehört | Was sie gewährt |
| --- | --- | --- |
| `Sales Qualifier` | Jeder Benutzer, einschließlich Administratoren | Zugriff auf die Anwendung: Interessenten, Konten, Interaktionspläne, Aufgaben, Leistung und Profileinstellungen. |
| `Sales Qualifier Admins` | Nur Administratoren zusätzlich zur `Sales Qualifier` | Zugriff auf **[!UICONTROL Admin-]**), die CRM-Verbindungen, das Wissenscenter und Compliance-Einstellungen für die gesamte Organisation steuert. |

Standardbenutzer benötigen nur die `Sales Qualifier`. Administratoren benötigen die Mitgliedschaft in beiden Gruppen. Siehe [Erste Schritte](getting-started.md) um diese Gruppen zu erstellen.

Organisationen können auch eine optionale `Sales Qualifier BDR managers` erstellen. Mitglieder können auf E-Mail-Leistungsberichte zugreifen.

## Administratorzugriff

**[!UICONTROL Admin-Einstellungen]** wird unter **[!UICONTROL Administration]** nur für Benutzer angezeigt, die beiden erforderlichen Gruppen angehören. Änderungen an diesen Einstellungen gelten für die gesamte Organisation.

## Was Administratoren steuern

| Einstellung | Konfigurieren der Konfiguration | Ergebnis |
| --- | --- | --- |
| CRM-Verbindung und Feldzuordnung | [Integrationen](integrations.md#map-crm-fields-inbound-mapping) | Bestimmt, welche CRM-Felder für einen Interessenten oder ein Konto angezeigt werden und welche Felder als Filter verfügbar sind. |
| Globales E-Mail-Opt-out | [Integrationen](integrations.md#configure-global-email-opt-out) | Fügt jeder ausgehenden E-Mail eine Fußzeile zum Abmelden hinzu. |
| Wissenszentrum und Playbook | [Wissenszentrum](knowledge-center.md) | Stellt das Playbook für das Unternehmen in ausgehenden Eingabeaufforderungen und [KI-Chat](ai-assistant.md) zur Verfügung. |
| Aktivitäten-Synchronisierung | [Integrationen](integrations.md#configure-activity-sync-outbound-mapping) | Legt fest, ob Sales Qualifier Outreach-Aktivitäten im CRM angezeigt werden. |

Standardbenutzer können diese Einstellungen verwenden, sie jedoch nicht ändern. Wenn ein erwarteter Filter, eine Playbook-Referenz oder ein CRM-Feld fehlt, wenden Sie sich an einen Administrator.

>[!MORELIKETHIS]
>
>* [Erste Schritte](getting-started.md)
>* [Integrationen](integrations.md)
>* [Wissenszentrum](knowledge-center.md)
