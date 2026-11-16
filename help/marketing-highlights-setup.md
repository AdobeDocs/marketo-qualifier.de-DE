---
title: Einrichten von Marketing-Highlights
description: Erfahren Sie, wie Sie mit einem Workflow-Schritt für intelligente Kampagnen Leads von Marketo Engage an Marketo Qualifier senden und erhalten Sie Empfehlungen zu Marketing-Highlights zur Überprüfung.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: da701e37-3227-4187-b68a-914277252a79
    internal-label: Integrations
subfeature_v2:
  - id: 7b0925d9-0dc0-5c75-a54d-2bcc31c6ebe4
    internal-label: Marketing highlights
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: adcfe279f38ca319589612820351c48af750bad9
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 2%
---

# Einrichten von Marketing-Highlights

Senden Sie Leads von [!DNL Adobe Marketo Engage] an [!DNL Adobe Marketo Qualifier], indem Sie den **[!UICONTROL An Marketo Qualifier senden]** zu einer Smart-Kampagne hinzufügen. Die Mitarbeiter sehen die Leads und die Aktivität, die sie an **[!UICONTROL Interessenten]** > **[!UICONTROL Marketing-Highlights]** gesendet haben.

Der Flussschritt funktioniert mit beiden Arten von Smart Campaign:

* **Trigger-Kampagnen** Versenden Sie Interaktionen sofort, z. B. E-Mail-Öffnungen und -Klicks, Link-Klicks, Ausfüllen von Formularen und Web-Seitenbesuche.
* **Batch-Kampagnen** Senden Sie bei jeder Ausführung der Kampagne die qualifizierenden Leads.

Wenn ein Lead den Targeting-Kriterien eines ausgehenden Workflows entspricht, empfiehlt Marketo Qualifier den Lead seinem Inhaber in Ihrem verbundenen CRM-System. Der Verantwortliche prüft und genehmigt den Lead vor der Registrierung und der Kontaktaufnahme. Leads werden nicht automatisch registriert.

Marketing-Highlights sind in allen Produktionsregionen verfügbar: Nordamerika, EMEA und Australien.

## Voraussetzungen {#before-you-begin}

Bestätigen Sie diese Voraussetzungen, bevor Sie den Flussschritt hinzufügen:

* Ein Marketo-Administrator hat &quot;**[!UICONTROL an Marketo Qualifier senden]** für Ihre Marketo Engage-Instanz in &quot;**[!UICONTROL &quot;]**.
* Marketo Qualifier ist [mit Salesforce oder Microsoft Dynamics 365 verbunden](getting-started.md#connect-your-crm) sodass jeder Lead seinem CRM-Besitzer zugeordnet werden kann.

>[!IMPORTANT]
>
>Für **[!UICONTROL Flussschritt „An Marketo Qualifier]**&quot; ist kein Webhook, keine Endpunkt-URL und keine API-Anmeldeinformationen erforderlich. Sie benötigen keinen Zugriff auf die Adobe Developer Console, um sie verwenden zu können. Wenn der Flussschritt nicht verfügbar ist, wenden Sie sich an den Marketo-Administrator.

## Senden von Leads mit einer intelligenten Kampagne {#send-leads-with-a-smart-campaign}

Verwenden Sie eine vorhandene Smart Campaign oder erstellen Sie eine für die Leads und Aktivitäten, die Sie senden möchten.

1. Öffnen Sie in Marketo Engage eine Smart Campaign oder wählen Sie **[!UICONTROL Marketing-Aktivitäten]** > **[!UICONTROL Neu]** > **[!UICONTROL Smart Campaign]** aus, um eine Smart Campaign zu erstellen.
1. Auf der Registerkarte **[!UICONTROL Smart List]** definieren Sie, welche Leads qualifiziert sind.

   * Fügen Sie für eine Trigger-Kampagne Trigger für die Aktivitäten hinzu, die Sie senden möchten, z. B. **[!UICONTROL Besuche auf]**, **[!UICONTROL Klicks auf Link auf]** oder **[!UICONTROL Klicks auf Link in E-Mail]**.
   * Fügen Sie für eine Batch-Kampagne Filter für die Leads hinzu, die Sie senden möchten.

1. Fügen Sie auf der **[!UICONTROL Fluss]** den **[!UICONTROL An Marketo Qualifier senden]** Flussschritt hinzu.
1. Aktivieren Sie die Trigger-Kampagne oder führen Sie die Batch-Kampagne aus bzw. planen Sie sie.
1. Öffnen Sie in Marketo Qualifier **[!UICONTROL Interessenten]** > **[!UICONTROL Marketing-]**), um die Leads und ihre Aktivitäten zu überprüfen.

   Die Aktivität zeigt an, wie ein Lead ankam, z. B. **[!UICONTROL aus Batch-Kampagne hinzugefügt]**.

Leads, die den Targeting-Kriterien eines ausgehenden Workflows entsprechen, werden nur dem CRM-Besitzer empfohlen. Um Empfehlungen zu überprüfen, öffnen Sie **[!UICONTROL Aufgaben]** > **[!UICONTROL Agentenvorschläge]**. Siehe [Empfehlungen aus Marketing-](outbound-workflows.md#automatically-enroll-prospects-from-marketing-highlights) abrufen“ und [Agentenvorschläge](tasks.md#agent-suggestions).

## Vorhandene Webhook-Setups {#existing-webhook-setups}

In den folgenden Anweisungen wird die frühere Webhook-Einrichtung beschrieben. Sie sind für den **[!UICONTROL An Marketo Qualifier senden]** nicht erforderlich. Wenn Ihr Unternehmen bereits einen Webhook verwendet, wenden Sie sich an Ihren Marketo-Administrator und Adobe-Ansprechpartner, bevor Sie dieses Setup ändern.

+++Webhook-Setup-Anweisungen

Diese Anweisungen erfordern Zugriff auf die Adobe Developer Console und auf **[!UICONTROL Admin]** in Marketo Engage.

### Teil A: Erstellen von API-Anmeldeinformationen {#part-a-create-api-credentials}

Mit diesen Anmeldeinformationen können [!DNL Marketo] sich sicher bei Marketo Qualifier authentifizieren.

So erstellen Sie die Anmeldeinformationen:

1. Wechseln Sie zur [Adobe-Entwicklerkonsole](https://developer.adobe.com/console/) und melden Sie sich mit Ihrer Adobe ID an.
1. Wählen Sie **[!UICONTROL Neues Projekt erstellen]** oder öffnen Sie ein vorhandenes Projekt.
1. Um das Projekt umzubenennen, wählen Sie **[!UICONTROL Projekt bearbeiten]**, geben Sie einen identifizierbaren Namen wie `Marketo Qualifier Marketing Highlights` ein und klicken Sie auf **[!UICONTROL Speichern]**.
1. Wählen Sie **[!UICONTROL API hinzufügen]**, wählen Sie **[!UICONTROL Experience Platform API]** und klicken Sie dann auf **[!UICONTROL Weiter]**.
1. Wählen Sie **[!UICONTROL Authentifizierungstyp OAuth Server-]** als aus und klicken Sie dann auf **[!UICONTROL Weiter]**.

   **[!UICONTROL OAuth Server-zu-Server]** ermöglicht es [!DNL Marketo], die Marketo Qualifier-API direkt von ihrem Server aus aufzurufen, ohne dass sich eine Person anmelden muss.

1. Geben Sie einen Berechtigungsnamen mit höchstens 45 Zeichen ein, z. B. `Marketo Qualifier Marketing Highlights Creds`.
1. Um das Produktprofil zu verknüpfen, wählen Sie es aus und klicken Sie auf **[!UICONTROL Konfigurierte API speichern]**.
1. Öffnen Sie **[!UICONTROL „Verbundene Anmeldeinformationen]** die **[!UICONTROL OAuth Server-zu-Server]**-Anmeldeinformationen. Wählen Sie **[!UICONTROL Client-Geheimnis abrufen]** und kopieren Sie dann die **[!UICONTROL Client-ID]** und **[!UICONTROL Client-Geheimnis]**. Sie verwenden diese Werte in [Teil C](#part-c-configure-the-marketo-webhook).

>[!WARNING]
>
>Den Client-Schlüssel privat halten. Behandeln Sie sie wie ein Passwort und senden Sie sie nicht per E-Mail. Verwenden Sie den genehmigten sicheren Kanal Ihrer Organisation, um ihn für die Person freizugeben, die den Webhook konfiguriert.

### Teil B: Erfassen Sie Ihren Endpunkt und Ihre Kennungen {#part-b-gather-your-endpoint-and-identifiers}

Sie benötigen drei Werte für [Teil C](#part-c-configure-the-marketo-webhook):

* **Endpunkt-URL** - Die Webhook-Adresse für Marketo Qualifier für Ihre Region.
* **imsOrg ID** - Die Kennung Ihres Unternehmens im Adobe Identity Management System (IMS) in der `{ORG_ID}@AdobeOrg`.
* **Sandbox-Name** - Der Name Ihrer AEP-Sandbox entspricht exakt der in der Marketo Qualifier-URL angezeigten Darstellung (dem `sname`), nicht dem in der Benutzeroberfläche angezeigten Anzeigenamen. Verwenden Sie den URL-Wert in Kleinbuchstaben, z. B. `prod`, nicht `Prod`.

| Region | Webhook-Endpunkt-URL |
| --- | --- |
| Nordamerika | `https://5r6xakp9k3.execute-api.us-east-1.amazonaws.com/prod/external/marketo/signals` |
| EMEA | `https://pc72i8q1k3.execute-api.eu-west-1.amazonaws.com/prod/external/marketo/signals` |
| APAC / Australien | `https://5cxxxyqlai.execute-api.ap-southeast-2.amazonaws.com/prod/external/marketo/signals` |

{style="table-layout:auto"}

Wenn Sie sich bezüglich Ihrer Region, IMS-Org-ID oder Ihres Sandbox-Namens nicht sicher sind, kann Ihr Adobe-Kontakt sie bestätigen.

### Teil C: Konfigurieren des Marketo-Webhooks {#part-c-configure-the-marketo-webhook}

So erstellen Sie den Webhook:

1. Wählen Sie in [!DNL Marketo] **[!UICONTROL Admin]** > **[!UICONTROL Webhooks]** aus.
1. Wählen Sie **[!UICONTROL Neuer Webhook]** aus.
1. Legen Sie **[!UICONTROL URL]** auf die Endpunkt-URL für Ihre Region von [Teil B](#part-b-gather-your-endpoint-and-identifiers) fest.
1. Legen Sie **[!UICONTROL Anfragetyp]** auf `POST` fest.
1. Setzen Sie **[!UICONTROL Request Token Encoding]** auf `JSON`. Diese Einstellung ist erforderlich.
1. Fügen Sie die unten stehende Payload-Vorlage in **[!UICONTROL Vorlage]** ein. Verwenden Sie das **[!UICONTROL Token einfügen]** von [!DNL Marketo], um die Feldnamen in Ihrer Instanz abzugleichen.

   >[!NOTE]
   >
   >Umschließen Sie bei JSON-Kodierung keine Zeichenfolgen-Token in Anführungszeichen. [!DNL Marketo] fügt sie automatisch hinzu.

   ```json
   {
     "leadId": {{lead.Id:default=0}},
     "email": {{lead.Email Address:default=}},
     "fullName": {{lead.Full Name:default=}},
     "company": {{company.Company Name:default=}},
     "title": {{lead.Job Title:default=}},
     "department": {{lead.Department:default=}},
     "country": {{lead.Country:default=}},
     "score": {{lead.Lead Score:default=0}},
     "rating": {{lead.Lead Rating:default=}},
     "leadStatus": {{lead.Lead Status:default=}},
     "leadSource": {{lead.Lead Source:default=}},
     "isCustomer": {{lead.Is Customer:default=false}},
     "industry": {{company.Industry:default=}},
     "annualRevenue": {{company.Annual Revenue:default=0}},
     "numEmployees": {{company.Num Employees:default=0}},
     "campaignId": {{campaign.id:default=0}},
     "campaignName": {{campaign.name:default=}},
     "programName": {{program.name:default=}},
     "occurredAt": {{system.dateTime:default=}},
     "munchkinId": {{system.munchkinId:default=}},
     "triggerName": {{trigger.Trigger Name:default=}},
     "crmId": {{lead.SFDC ID:default=}},
     "crmType": {{lead.SFDC Type:default=}},
     "crmOwnerEmail": {{lead.Lead Owner Email Address:default=}},
     "crmOwnerFirstName": {{lead.Lead Owner First Name:default=}},
     "crmOwnerLastName": {{lead.Lead Owner Last Name:default=}},
     "attributes": {
       "asset": {{trigger.Name:default=}},
       "link": {{trigger.Link:default=}},
       "subject": {{trigger.Subject:default=}},
       "webPage": {{trigger.Web Page:default=}},
       "category": {{trigger.Category:default=}},
       "details": {{trigger.Details:default=}},
       "sentBy": {{trigger.Sent By:default=}},
       "receivedBy": {{trigger.Received By:default=}},
       "referrer": {{trigger.Referrer:default=}},
       "searchEngine": {{trigger.Search Engine:default=}},
       "searchQuery": {{trigger.Search Query:default=}},
       "imDescription": {{lead.Last Interesting Moment Desc:default=}},
       "imType": {{lead.Last Interesting Moment Type:default=}},
       "imDate": {{lead.Last Interesting Moment Date:default=}},
       "imSource": {{lead.Last Interesting Moment Source:default=}},
       "chatAgentName": {{trigger.Agent Name:default=}},
       "chatAgentEmail": {{trigger.Agent Email:default=}},
       "chatConversationStatus": {{trigger.Conversation Status:default=}},
       "chatConversationSummary": {{trigger.Conversation Summary:default=}},
       "chatGoalName": {{trigger.Goal name:default=}},
       "chatMeetingStatus": {{trigger.meeting status:default=}},
       "chatScheduledFor": {{trigger.Scheduled For:default=}},
       "chatDocumentName": {{trigger.Document Name:default=}},
       "chatDocumentUrl": {{trigger.Document URL:default=}},
       "chatPageUrl": {{trigger.Page URL:default=}}
     }
   }
   ```

1. Wählen Sie **[!UICONTROL Webhook-]** > **[!UICONTROL Benutzerdefinierte Kopfzeile festlegen]** und fügen Sie dann die folgenden Kopfzeilen hinzu, indem Sie die Werte aus [Teil A](#part-a-create-api-credentials) und [Teil B](#part-b-gather-your-endpoint-and-identifiers):

   | Header | Wert |
   | --- | --- |
   | `Content-Type` | `application/json` |
   | `x-client-id` | Ihre Client-ID |
   | `x-client-secret` | Ihr Client-Geheimnis |
   | `x-gw-ims-org-id` | Ihre imsOrg-ID |
   | `x-sandbox-name` | Ihr Sandbox-Name |

   {style="table-layout:auto"}

1. Wählen Sie **[!UICONTROL Speichern]** aus.

### Teil D: Hinzufügen des Webhooks zu einer intelligenten Trigger-Kampagne {#part-d-add-the-webhook-to-a-trigger-smart-campaign}

Fügen Sie **[!UICONTROL Trigger-Smart]** Kampagne einen Flussschritt „Webhook aufrufen“ hinzu, entweder eine vorhandene oder eine neue. Die Trigger der Smart List für diese Kampagne entscheiden, welche Aktivitäten an Marketo Qualifier gesendet werden.

So fügen Sie den Webhook hinzu:

1. Öffnen Sie eine bestehende Smart Trigger-Kampagne oder erstellen Sie eine neue (**[!UICONTROL Marketing-Aktivitäten]** > **[!UICONTROL Neu]** > **[!UICONTROL Smart Campaign]**).
1. Fügen Sie auf der Registerkarte **[!UICONTROL Smart]** den Trigger oder die Trigger für die Aktivitäten hinzu, die Sie senden möchten, z. B. **[!UICONTROL Klicks auf Link in E-Mail]**, **[!UICONTROL Formular ausfüllen]** oder **[!UICONTROL Web-Seite besuchen]**.
1. Fügen Sie auf der Registerkarte **[!UICONTROL Fluss]** den Schritt **[!UICONTROL Webhook aufrufen]** hinzu und wählen Sie den Webhook aus, den Sie in [Teil C](#part-c-configure-the-marketo-webhook) erstellt haben.
1. Aktivieren Sie die Smart-Kampagne.

Die Aktivität dieser Smart Campaign fließt jetzt in Marketo Qualifier. Mitarbeiter können diese Aktivität unter „Interessenten **[!UICONTROL > „Marketing]** Highlights“ anzeigen **[!UICONTROL filtern]**.

+++

>[!MORELIKETHIS]
>
>* [Integrationen verwalten](integrations.md)
>* [Interessenten](prospects.md)
>* [Erste Schritte](getting-started.md)
