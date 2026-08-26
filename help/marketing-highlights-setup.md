---
title: Einrichten von Marketing-Highlights
description: Erfahren Sie, wie Sie Marketo mit Sales Qualifier verbinden, damit Kundenbetreuer in den Marketing-Highlights Interessenten nach Marketo-Live-Aktivitäten anzeigen und filtern können.
feature: Agentic AI, Sales Insights, Account Journeys
role: Admin
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4bid: fdbb8fc9-ffa3-4b86-88fe-aa4c5a3e1bc6
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8573d3891d5c8ec8a05637f160f120f933b0ec61
workflow-type: tm+mt
source-wordcount: 686
ht-degree: 3%

---


# Einrichten von Marketing-Highlights

Die Marketing-Highlights zeigen die Live-[!DNL Marketo]-Aktivität jedes Interessenten, wie z. B. Öffnungen und Klicks, Web-Besuche und Formularausfüllungen, auf der Registerkarte **[!UICONTROL Marketing-]**) eines Interessenten in Sales Qualifier an. In diesem Artikel wird erläutert, wie Sie Ihre [!DNL Marketo]-Instanz verbinden, damit Aktivitäten in fließen.

>[!IMPORTANT]
>
>Für den Abschluss dieses Setups ist der Zugriff auf die Adobe Developer Console und auf **[!UICONTROL Admin]** in [!DNL Marketo] erforderlich. Arbeiten Sie mit Ihrem Adobe-Ansprechpartner und Ihrem [!DNL Marketo]-Administrator zusammen, um die vier folgenden Teile auszufüllen.

Das Setup besteht aus vier Teilen:

* Teil A: Erstellen von API-Anmeldeinformationen in der Adobe Developer Console.
* Teil B: Erfassen Sie Ihren Sales Qualifier-Endpunkt und Ihre Kennungen.
* Teil C: Konfigurieren eines Webhooks in [!DNL Marketo Engage].
* Teil D: Hinzufügen des Webhooks zu einer Smart Trigger-Kampagne.

Nach Abschluss des Setups können Benutzer diese Aktivität unter **[!UICONTROL Interessenten]** > **[!UICONTROL Marketing-Highlights]** anzeigen und filtern.

## Teil A: Erstellen von API-Anmeldeinformationen {#part-a-create-api-credentials}

Mit diesen Anmeldeinformationen können [!DNL Marketo] sich sicher bei Sales Qualifier authentifizieren.

So erstellen Sie die Anmeldeinformationen:

1. Wechseln Sie zur [Adobe-Entwicklerkonsole](https://developer.adobe.com/console/) und melden Sie sich mit Ihrer Adobe ID an.
1. Wählen Sie **[!UICONTROL Neues Projekt erstellen]** oder öffnen Sie ein vorhandenes Projekt.
1. Wählen Sie **[!UICONTROL Projekt bearbeiten]**, benennen Sie das Projekt in einen identifizierbaren Namen um, z. B. `Sales Qualifier Marketing Highlights`, und wählen Sie **[!UICONTROL Speichern]**.
1. Wählen Sie **[!UICONTROL API hinzufügen]**, wählen Sie **[!UICONTROL Experience Platform API]** und klicken Sie dann auf **[!UICONTROL Weiter]**.
1. Wählen Sie **[!UICONTROL Authentifizierungstyp OAuth Server-]** als aus und klicken Sie dann auf **[!UICONTROL Weiter]**.

   **[!UICONTROL OAuth Server-zu-Server]** ermöglicht es [!DNL Marketo], die Sales Qualifier-API direkt von ihrem Server aus aufzurufen, ohne dass sich eine Person anmelden muss.

1. Geben Sie einen Berechtigungsnamen mit höchstens 45 Zeichen ein, z. B. `Sales Qualifier Marketing Highlights Creds`.
1. Wählen Sie das zu verknüpfende Produktprofil und dann **[!UICONTROL Konfigurierte API speichern]** aus.
1. Öffnen Sie **[!UICONTROL „Verbundene Anmeldeinformationen]** die **[!UICONTROL OAuth Server-zu-Server]**-Anmeldeinformationen. Wählen Sie **[!UICONTROL Client-Geheimnis abrufen]** und kopieren Sie dann die **[!UICONTROL Client-ID]** und **[!UICONTROL Client-Geheimnis]**. Sie verwenden diese Werte in [Teil C](#part-c-configure-the-marketo-webhook).

>[!WARNING]
>
>Den Client-Schlüssel privat halten. Behandeln Sie sie wie ein Passwort und senden Sie sie nicht per E-Mail. Verwenden Sie den genehmigten sicheren Kanal Ihrer Organisation, um ihn für die Person freizugeben, die den Webhook konfiguriert.

## Teil B: Erfassen Sie Ihren Endpunkt und Ihre Kennungen {#part-b-gather-your-endpoint-and-identifiers}

Sie benötigen drei Werte für [Teil C](#part-c-configure-the-marketo-webhook):

* **Endpunkt-URL** - Die Webhook-Adresse für Sales Qualifier für Ihre Region.
* **imsOrg ID** - Die Kennung Ihres Unternehmens im Adobe Identity Management System (IMS) in der `{ORG_ID}@AdobeOrg`.
* **Sandbox-Name** - Der Name Ihrer AEP-Sandbox entspricht exakt der in der Sales Qualifier-URL angezeigten Darstellung (dem `sname`), nicht dem in der Benutzeroberfläche angezeigten Anzeigenamen. Verwenden Sie den URL-Wert in Kleinbuchstaben, z. B. `prod`, nicht `Prod`.

| Region | Webhook-Endpunkt-URL |
| --- | --- |
| Nordamerika | `https://5r6xakp9k3.execute-api.us-east-1.amazonaws.com/prod/external/marketo/signals` |
| EMEA | `https://pc72i8q1k3.execute-api.eu-west-1.amazonaws.com/prod/external/marketo/signals` |
| APAC / Australien | `https://5cxxxyqlai.execute-api.ap-southeast-2.amazonaws.com/prod/external/marketo/signals` |

{style="table-layout:auto"}

Wenn Sie sich bezüglich Ihrer Region, IMS-Org-ID oder Ihres Sandbox-Namens nicht sicher sind, kann Ihr Adobe-Kontakt sie bestätigen.

## Teil C: Konfigurieren des Marketo-Webhooks {#part-c-configure-the-marketo-webhook}

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

## Teil D: Hinzufügen des Webhooks zu einer intelligenten Trigger-Kampagne {#part-d-add-the-webhook-to-a-trigger-smart-campaign}

Fügen Sie **[!UICONTROL Trigger-Smart]** Kampagne einen Flussschritt „Webhook aufrufen“ hinzu, entweder eine vorhandene oder eine neue. Die Trigger der Smart List für diese Kampagne entscheiden, welche Aktivitäten an Sales Qualifier gesendet werden.

So fügen Sie den Webhook hinzu:

1. Öffnen Sie eine bestehende Smart Trigger-Kampagne oder erstellen Sie eine neue (**[!UICONTROL Marketing-Aktivitäten]** > **[!UICONTROL Neu]** > **[!UICONTROL Smart Campaign]**).
1. Fügen Sie auf der Registerkarte **[!UICONTROL Smart]** den Trigger oder die Trigger für die Aktivitäten hinzu, die Sie senden möchten, z. B. **[!UICONTROL Klicks auf Link in E-Mail]**, **[!UICONTROL Formular ausfüllen]** oder **[!UICONTROL Web-Seite besuchen]**.
1. Fügen Sie auf der Registerkarte **[!UICONTROL Fluss]** den Schritt **[!UICONTROL Webhook aufrufen]** hinzu und wählen Sie den Webhook aus, den Sie in [Teil C](#part-c-configure-the-marketo-webhook) erstellt haben.
1. Aktivieren Sie die Smart-Kampagne.

Die Aktivität dieser Smart Campaign fließt jetzt in Sales Qualifier. Mitarbeiter können diese Aktivität unter „Interessenten **[!UICONTROL > „Marketing]** Highlights“ anzeigen **[!UICONTROL filtern]**.

>[!MORELIKETHIS]
>
>* [Integrationen verwalten](integrations.md)
>* [Interessenten](prospects.md)
>* [Erste Schritte](getting-started.md)
