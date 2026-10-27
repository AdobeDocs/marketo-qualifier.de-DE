---
title: Profileinstellungen konfigurieren
description: Erfahren Sie, wie Sie Ihre E-Mail-Verbindung, Signatur und Kalenderverfügbarkeit in den Profileinstellungen von Adobe Marketo Qualifier konfigurieren.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
TQID: 'https://experienceleague.adobe.com/YsrBduYA7jKhgxttexqMBBpgDIq23s6wUb4Wp6y6h3g'
product_v2:
  - id: d98caee2-fd67-486e-9513-36435358ebff
    internal-label: Marketo Qualifier
feature_v2:
  - id: f8c781b4-253f-436e-b9f1-a71172814e41
    internal-label: Profile Settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
source-git-commit: ab54d20ccc80d88c3592d89c9f43feeb062ed82c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 3%
---

# Profileinstellungen

Erweitern Sie in der linken Navigation **[!UICONTROL Konfiguration]** und wählen Sie **[!UICONTROL Profileinstellungen]** aus. Verwenden Sie diese Einstellungen, um Ihre persönlichen Daten, E-Mail-Verbindung, Kalender und Chat-Verfügbarkeit zu verwalten.

![Profileinstellungen](assets/profile-email-config.png)

## E-Mail-Einstellungen

Richten Sie auf **[!UICONTROL Registerkarte]** E-Mail-Einstellungen“ Ihre E-Mail-Verbindungen ein.

* **[!UICONTROL E-Mail-Verbindungen]** - Wählen Sie Microsoft Outlook oder Google aus und folgen Sie dem Anmeldevorgang. Unter [Outlook verbinden](integrations.md#connect-outlook) finden Sie den von Ihnen genehmigten Zugriff und ggf. den Genehmigungspfad des Administrators.
* **[!UICONTROL E-Mail-Signatur]** - Fügen Sie die in generierten E-Mails verwendete Signatur hinzu oder aktualisieren Sie sie. Fügen Sie Ihren [Meeting-Buchungs](outbound-workflows.md#meeting-booking)-Link ein, damit potenzielle Kunden Zeit mit Ihnen planen können.
* **[!UICONTROL Meeting-Buchungslink]** - Senden Sie eine Besprechungseinladung in Ihre E-Mails. Verwendet die Besprechungs-URL.

### E-Mail-Zeichnungskontext

![E-Mail-Kontext](assets/profile-email-instructions.png)

Verwenden Sie **[!UICONTROL E-Mail]** Zeichnungskontext, um den E-Mail-Ton, die Struktur und den Stil festzulegen, sodass E-Mails konsistent sind.

Schreiben Sie Ihren Kontext im Bereich **[!UICONTROL E-Mail-Zeichnungskontext]** als Markdown.
Damit können Sie Folgendes definieren:

* Ton und Stimme
* Struktur und Länge
* Personalization und Grußregeln
* Betreffzeilenstil
* Verwendung von Interaktionssignalen
* So werden Metriken, Korrekturpunkte und Kundengeschichten dargestellt

Standardmäßig verwenden Entwürfe einen Kontext im Hausstil, sodass sich Ihre vorhandenen Entwürfe erst ändern, wenn Sie Ihren eigenen Kontext hinzufügen.

## Kalenderkonfiguration

Legen Sie auf **[!UICONTROL Registerkarte]** Kalenderkonfiguration“ Ihre Zeitzone und Verfügbarkeit fest.

* **[!UICONTROL Kalenderverbindung]** - Wählen Sie **[!UICONTROL Verbinden]** und folgen Sie dem Microsoft-Anmeldeprozess.
* **[!UICONTROL E-Mail zur Besprechungsbestätigung]** - Definieren Sie den Betreff und Text der Bestätigungs-E-Mail, die ein Interessent nach der Buchung eines Meetings erhält.
* **[!UICONTROL Voreinstellungen]** - Legt die standardmäßige Länge der Besprechung und den Puffer zwischen den Besprechungen fest.

Wenn Sie den Kalender trennen:

* Aktive Buchungslinks funktionieren nicht mehr.
* Auf der Buchungsseite wird eine Meldung über die vorübergehende Nichtverfügbarkeit angezeigt.
* Ihre Einstellungen bleiben beim erneuten Herstellen der Verbindung erhalten.

## Kalenderverfügbarkeit

Die Kalenderverfügbarkeit in Adobe Marketo Qualifier basiert auf zwei Eingaben:

* Ihr verbundener Arbeitskalender, z. B. Outlook oder Gmail
* Die Verfügbarkeits- und Zeitschlitzregeln in **[!UICONTROL Kalenderkonfiguration]**

Marketo Qualifier liest den Frei/Belegt-Status, nicht die Ereignisdetails, aus dem verbundenen Kalender. Er kombiniert diesen Status mit Ihren Regeln, um die Zeitfenster zu bestimmen, die potenzielle Kunden buchen können.

Sie können Folgendes konfigurieren:

* Arbeitszeit nach Wochentag
* Mehrere Blöcke pro Tag, z. B. 9:00 Uhr bis 13:00 Uhr bis 17:00 Uhr.
* Ihre Zeitzone
* Meeting-Dauer
* Puffer vor und nach Besprechungen
* Mindestkündigungsfrist
* Buchungsfenster

>[!MORELIKETHIS]
>
>* [Ausgehende Workflows](outbound-workflows.md)
>* [Integrationen](integrations.md)
>* [Aufgaben](tasks.md)
