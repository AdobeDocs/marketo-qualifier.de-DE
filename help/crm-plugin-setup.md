---
title: Einrichten des CRM-Plug-ins
description: Erfahren Sie, wie Sie das Marketo Qualifier CRM-Plug-in in Salesforce oder Microsoft Dynamics 365 installieren. Konfigurieren Sie Salesforce-Aktionen für Workflows und Marketo-Kampagnen.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
  - id: f8f8b877-7295-5853-989f-e21f73bc94c4
    internal-label: Administration
subfeature_v2:
  - id: d2fe5f36-5653-5902-937c-9d3026104284
    internal-label: CRM integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: df256cf271296b82fab2ed10725a0d6bd165e05b
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 0%
---

# Einrichten des CRM-Plug-ins

Installieren Sie das [!DNL Adobe Marketo Qualifier] CRM-Plug-in, damit die Kundenbetreuer [!DNL Marketo Sales Insights] und KI-generierte Einblicke auf den Datensatzseiten für Leads, Kontakte und Konten verwenden können, ohne Salesforce oder Microsoft Dynamics 365 verlassen zu müssen. Das Plug-in bietet auch eine Startansicht zum [Priorisieren von Leads in Ihrem CRM](admin-settings.md#prioritize-leads-in-the-crm-plugin).

In Salesforce können Mitarbeiter aus Lead- und Kontaktlistenansichten und einzelnen Datensatzseiten auch Interessenten zu ausgehenden Workflows oder Marketo-Kampagnen hinzufügen.

## Voraussetzungen

Stellen Sie sicher, dass die Personen, die das Plug-in installieren und verwenden, über den erforderlichen Zugriff verfügen:

* **Salesforce-Administrator**: Berechtigung zum Installieren von Paketen und Bearbeiten von Seiten-Layouts.
* **Microsoft Dynamics 365-**: Berechtigung zum Importieren von Lösungen in die Zielumgebung in Power Apps.
* **Repräsentanten**: Zugriff auf Marketo Qualifier und die entsprechenden CRM-Datensätze.

Die Installation des Plug-ins ist getrennt von [Verbinden des CRM-Systems mit Marketo Qualifier](getting-started.md#connect-your-crm).

## Installieren in Salesforce

Installieren Sie das Paket und fügen Sie dann seine Komponenten zu den Datensatzseiten hinzu, die von -Vertretern verwendet werden.

1. Öffnen Sie die [Salesforce-](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=salesforce) und melden Sie sich bei Salesforce als Administrator an.
1. Klicken Sie auf der Seite zur Paketinstallation auf **[!UICONTROL Für alle Benutzer installieren]** und klicken Sie dann auf **[!UICONTROL Installieren]**.

   Sie können den Zugriff einzelner Benutzer weiterhin über Salesforce-Berechtigungen steuern.

1. Wenn Sie aufgefordert werden, den Zugriff von Drittanbietern zu genehmigen, aktivieren Sie das Kontrollkästchen „Genehmigung“ und klicken Sie auf **[!UICONTROL Weiter]**.
1. Wählen Sie nach Abschluss der Installation **[!UICONTROL Fertig]** aus.

   Die Installation dauert einige Minuten. Vergewissern Sie sich, dass das Paket auf der Seite **[!UICONTROL Installierte Pakete]** angezeigt wird.

1. Bearbeiten Sie in Lightning App Builder die Datensatzseiten für Leads, Kontakte und Konten und fügen Sie die Marketo Qualifier-Komponenten hinzu.

### Aktionen zu Listenansichten hinzufügen

Konfigurieren Sie **[!UICONTROL Zu ausgehendem Workflow hinzufügen]** und **[!UICONTROL Zu Marketo Campaign hinzufügen]** separat für Lead- und Kontaktlistenansichten. Verwenden Sie die im Paket enthaltenen Schaltflächen, um Duplikate zu vermeiden.

1. Gehen Sie zu **[!UICONTROL Setup]** > **[!UICONTROL Objekt-Manager]** und wählen Sie **[!UICONTROL Lead]** oder **[!UICONTROL Kontakt]**.
1. Öffnen Sie **[!UICONTROL Schaltflächen, Links und Aktionen]** und suchen Sie die Listenschaltflächen **[!UICONTROL AMQ zu ausgehendem Workflow hinzufügen]** und **[!UICONTROL AMQ zu Marketo Campaign hinzufügen]**.
1. Öffnen Sie das Schaltflächen-Layout **[!UICONTROL Listenansicht“ des Objekts]** wählen Sie **[!UICONTROL Bearbeiten]** aus.

   Abhängig von Ihrer Salesforce-Einrichtung kann das Listenansichts-Layout unter **[!UICONTROL Suchlayouts]** > **[!UICONTROL Listenansicht]** angezeigt werden.

1. Verschieben Sie beide Listenschaltflächen auf **[!UICONTROL Ausgewählte Schaltflächen]** und speichern Sie sie.
1. Wiederholen Sie diesen Vorgang für das andere Objekt.

Vertreter wählen einen oder mehrere Datensätze in einer Listenansicht aus und wählen dann die Aktion aus.

### Aktionen zu Datensatzseiten hinzufügen

Datensatzseitenaktionen müssen getrennt von den Listenansichts-Schaltflächen konfiguriert werden. Fügen Sie beiden Aktionen zu jedem verwendeten Lead- und Kontaktseiten-Layout hinzu.

1. Gehen Sie zu **[!UICONTROL Setup]** > **[!UICONTROL Objekt-Manager]** und wählen Sie **[!UICONTROL Lead]** oder **[!UICONTROL Kontakt]**.
1. Öffnen Sie **[!UICONTROL Schaltflächen, Links und Aktionen]** und suchen Sie die Detailschaltflächen **[!UICONTROL AMQ zu ausgehendem Workflow hinzufügen]** und **[!UICONTROL AMQ zu Marketo Campaign hinzufügen]**.
1. Öffnen Sie **[!UICONTROL Seiten-Layouts]** und bearbeiten Sie ein Layout, das Ihren Mitarbeitern zugewiesen ist.
1. Fügen Sie beide Detailschaltflächen zu **[!UICONTROL Salesforce Mobile- und Lightning Experience-Aktionen]** und speichern Sie sie.
1. Wiederholen Sie diesen Vorgang für jedes anwendbare Layout und für das andere Objekt.

Die Aktionen werden in der Aktionsleiste oder im Menü des Datensatzes angezeigt und gelten für den angezeigten Datensatz.

>[!NOTE]
>
>Diese Aktionen funktionieren in Salesforce Lightning, dem Desktop-Programm, und nicht in der Salesforce-Mobile-App. Der Layout-Abschnitt **[!UICONTROL Salesforce Mobile- und Lightning-Erlebnisaktionen]** wird auch für Desktop-Aktionen verwendet.

### Fehlende Schaltfläche ersetzen

Wenn eine gepackte Schaltfläche fehlt, erstellen Sie eine Ersetzung unter den **[!UICONTROL Schaltflächen, Links und Aktionen“ des]**.

1. Wählen Sie **[!UICONTROL Neue Schaltfläche oder Link]** aus.
1. Geben Sie einen Titel für die Aktion ein, z. B. `Add to Outbound Workflow` oder `Add to Marketo Campaign`.
1. Wählen Sie **[!UICONTROL Listenschaltfläche]** für eine Listenansicht oder **[!UICONTROL Detailseitenschaltfläche]** für eine Datensatzseite aus.
1. Legen Sie **[!UICONTROL Content Source]** auf **[!UICONTROL VisualForce-]**) fest und wählen Sie die Aktionsseite des Pakets aus, die mit der Aktion, dem Objekt und der Platzierung übereinstimmt.

   Platzierungen von Lead-Listen, Lead-Details, Kontaktlisten und Kontaktdetails verwenden verschiedene Seiten. Vergewissern Sie sich, dass die ausgewählte Seite mit der Platzierung übereinstimmt, die Sie konfigurieren.

1. Klicken Sie für eine Listenschaltfläche auf **[!UICONTROL Zeilenauswahl erforderlich]**.
1. Speichern Sie die Schaltfläche und fügen Sie sie wie oben beschrieben dem entsprechenden Listenansichts-Schaltflächen-Layout oder den Aktionen für die Datensatzseite hinzu.

### Salesforce-Aktionen überprüfen

Nachdem Sie die Layouts gespeichert haben, prüfen Sie, ob beide Aktionen in den Lead- und Kontaktlistenansichten sowie auf den Datensatzseiten angezeigt werden. Testen Sie jede Listenaktion mit ausgewählten Datensätzen und jede Datensatzseitenaktion aus einem einzelnen Datensatz.

Wenn eine Aktion nicht verfügbar ist oder nicht geöffnet werden kann, verwenden Sie diese Prüfungen:

| Problem | Was zu überprüfen ist |
| --- | --- |
| Schaltfläche fehlt in einer Listenansicht | Vergewissern Sie sich, dass sich die Listenschaltfläche unter **[!UICONTROL Ausgewählte Schaltflächen]** im **[!UICONTROL Listenansicht-Schaltflächen-Layout) des richtigen Objekts befindet]** und speichern Sie das Layout. |
| Schaltfläche fehlt auf einer Datensatzseite | Vergewissern Sie sich, dass sich die Detailschaltfläche in **[!UICONTROL Salesforce Mobile- und Lightning-Erlebnisaktionen]** auf dem Layout befindet, das dem Benutzer zugewiesen wurde. Wenn Ihr Unternehmen dynamische Aktionen verwendet, überprüfen Sie auch die Sichtbarkeit der Aktion auf der Datensatzseite. |
| Erwartete Seitenoption beim Erstellen einer Schaltfläche nicht verfügbar | Überprüfen Sie, ob der Anzeigetyp **[!UICONTROL Listenschaltfläche]** für eine Listenansicht oder **[!UICONTROL Detailseitenschaltfläche]** für eine Datensatzseite ist. |
| Aktion wird nicht geöffnet oder zeigt einen Zugriffsfehler an | Vergewissern Sie sich, dass die Benutzenden Zugriff auf Marketo Qualifier und die ausgewählten Datensätze haben. |

## Installieren in Microsoft Dynamics 365

Importieren Sie das Plug-in-Paket in die Umgebung, in der Ihre Mitarbeiter arbeiten.

1. Öffnen Sie die [Microsoft Dynamics 365-](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=dynamics) und laden Sie die ZIP-Paketdatei herunter.
1. Melden Sie sich bei [Power Apps](https://make.powerapps.com/) als Administrator an und wählen Sie die Zielumgebung aus.
1. Öffnen Sie **[!UICONTROL Lösungen]** und wählen Sie **[!UICONTROL Lösung importieren]** aus.
1. Wählen Sie **[!UICONTROL Durchsuchen]**, wählen Sie die heruntergeladene ZIP-Datei aus und klicken Sie auf **[!UICONTROL Weiter]**.
1. Überprüfen Sie die Paketdetails und wählen Sie **[!UICONTROL Weiter]** aus.
1. Behalten Sie den Wert der vorbefüllten Umgebungsvariablen bei und wählen Sie **[!UICONTROL Importieren]**.
1. Warten Sie oben auf der Seite auf die Bestätigungsmeldung, dass die Lösung erfolgreich importiert wurde.

Der Import dauert einige Minuten.

>[!MORELIKETHIS]
>
>* [Priorisieren von Leads im CRM-Plug-in](admin-settings.md#prioritize-leads-in-the-crm-plugin)
>* [Integrationen](integrations.md)
>* [Erste Schritte](getting-started.md)
