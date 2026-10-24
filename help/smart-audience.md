---
title: Intelligente Zielgruppe (Beta)
description: Erfahren Sie, wie Sie mit Smart Audience (Beta) Account-Listen erstellen, CRM-Daten und Wachstumssignale hinzufügen, Leads priorisieren und sie einem ausgehenden Workflow hinzufügen.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
badgeBeta: label="Beta" type="Informative"
source-git-commit: bf94a2d28913093923f446025405339e4e64919c
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 1%
---

# Intelligente Zielgruppe (Beta)

Smart Audience (Beta) hilft Ihnen, die Konten und Personen zu finden, die als Nächstes in [!DNL Adobe Marketo Qualifier] arbeiten. Beschreiben Sie Ihre Audience in verständlicher Sprache, verfeinern Sie die Kontenliste mit CRM-Daten und Wachstumssignalen, finden Sie relevante Leads und fügen Sie ausgewählte Leads zu einem ausgehenden Workflow hinzu.

Arbeiten Sie in der Listenansicht mit dem Raster, den Filtern und den Schaltflächen oder verwenden Sie den Chat, um zu beschreiben, was Sie möchten. Beide arbeiten auf derselben Liste: Änderungen in einer Liste werden in der anderen angezeigt. Wenn eine Änderung nicht sofort angezeigt wird, wählen Sie **[!UICONTROL Aktualisieren]**.

Die Fortschrittsverfolgung am Anfang jeder Liste zeigt drei Schritte an: **[!UICONTROL Smart-Audience-Liste erstellen]**, **[!UICONTROL Leads priorisieren]** und **[!UICONTROL Zum ausgehenden Workflow hinzufügen]**.

## Voraussetzungen

Für die intelligente Zielgruppe ist eine Salesforce- oder Microsoft Dynamics 365 CRM-Verbindung erforderlich. Er liest CRM-Daten live und schreibt nicht in das CRM. Anweisungen zur Verbindung finden Sie unter [Erste Schritte](getting-started.md#connect-your-crm).

Sie können bis zu 100 Listen erstellen. Jede Liste enthält bis zu 500 Accounts und 2.000 Leads. Konten oder Leads, die diese Limits überschreiten, werden nicht hinzugefügt. Grenzen Sie Ihre Kriterien ein oder unterteilen Sie die Zielgruppe in mehrere Listen, z. B. nach Region oder Segment.

## Beschreiben und Vorschau von Konten

Beginnen Sie mit einer Beschreibung der Konten, die Sie erreichen möchten. In der Vorschau wird keine Liste gespeichert.

1. Öffnen Sie **[!UICONTROL Intelligente Zielgruppe]** und wählen Sie **[!UICONTROL Neue intelligente Zielgruppe]** oder **[!UICONTROL Liste erstellen]** aus.
1. Beschreiben Sie im Chat die gewünschten Konten. Geben Sie beispielsweise `Find healthcare accounts with revenue over $50M` ein.
1. Überprüfen Sie die Anzahl der übereinstimmenden Konten und die Stichprobe in der Vorschau.

Ihre Anfrage kann die folgenden Kriterien enthalten:

| Kriterien | Beispiele |
| --- | --- |
| Firmenbezogene Daten | Branche, Anzahl der Mitarbeiter, Jahresumsatz, Kontotyp und Bewertung |
| Speicherort | Region, Land, Bundesland oder Stadt |
| Eigentum | Konten oder Konten, die einem benannten Eigentümer zugewiesen sind |
| Vertriebskette | Konten mit oder ohne offene Opportunity, die den [Salesforce-Beschränkungen unterliegen](#current-scope-and-limits) |
| Kontodetails | Name, Website oder Domain und Kontonummer |

Andere Beispielanfragen umfassen:

* `Accounts in the US with more than 1000 employees`
* `My accounts in Germany or France`
* `Accounts with no open opportunity`

Wenn ein Teil einer Anfrage nicht auf Ihre CRM-Daten angewendet werden kann, identifiziert der Chat die übersprungene Bedingung. Die Vorschau enthält nur die angewendeten Bedingungen. Überprüfen Sie diese Auslassungen, bevor Sie speichern.

## Speichern oder Verfeinern der Vorschau

Speichern Sie die Vorschau, wenn sie Ihrer gewünschten Zielgruppe entspricht.

1. Um die Vorschau zu ändern, senden Sie eine neue Anfrage mit den gewünschten Bedingungen. Nichts wird gespeichert, bis Sie bestätigen.
1. Wenn die Vorschau fertig ist, bitten Sie den Chat, sie als Liste zu speichern und der Liste einen Namen zu geben.
1. Überprüfen Sie die gespeicherten Konten auf der Registerkarte **[!UICONTROL Konten]** .

Sie können eine Liste auf der zugehörigen Seite umbenennen. Um eine Liste zu löschen, öffnen Sie sie und wählen Sie **[!UICONTROL Smart-Audience-Liste löschen]** aus.

>[!CAUTION]
>
>Wenn Sie eine Liste löschen, werden ihre Konten, Leads und Spalten dauerhaft aus der Smart-Zielgruppe entfernt. CRM-Einträge werden nicht gelöscht.

## Konten anreichern und in die engere Wahl ziehen

Fügen Sie Informationsspalten hinzu, um zu entscheiden, welche Konten funktionieren sollen. Eine Spalte oder ein Signal pro Anfrage anfordern.

Um CRM-Informationen hinzuzufügen, geben Sie eine Anfrage wie `Add a column showing which accounts have an open opportunity` ein. Siehe [Aktueller Umfang und Einschränkungen](#current-scope-and-limits) für Salesforce-Einschränkungen.

Um Wachstumssignale hinzuzufügen, wählen Sie **[!UICONTROL Konten anreichern]** in der Listenansicht aus oder fragen Sie im Chat nach. Zu den verfügbaren Signalen gehören:

| Signal | Was angezeigt wird |
| --- | --- |
| Finanzierung | Jüngste Finanzierungs- und Finanzierungsveranstaltungen |
| Anstellung | Jüngste Stellenangebote und Personalbedarf |
| Dehnungssignale | Neue Niederlassungen, neue Märkte und Expansionsankündigungen |
| Technologieänderungen | Ergänzungen und Änderungen am Technologie-Stack eines Unternehmens |
| Entlassungen | Über Chat angeforderte Informationen zur Entlassung |

Geben Sie beispielsweise `Which of these accounts have raised funding recently?` oder `Which of these accounts have had layoffs?` ein.

Bei großen Listen kann das Hinzufügen eines Signals einige Minuten dauern. Folgen Sie dem in der Liste angezeigten Fortschritt, überprüfen Sie jede neue Spalte und behalten oder verwerfen Sie sie.

So grenzen Sie die Konten ein und haben Prioritäten:

1. Öffnen Sie auf der **[!UICONTROL Konten]** die Option **[!UICONTROL Filter]**.
1. Filtern Sie nach Konto, Domain, Branche, Eigentümer, minimalen oder maximalen Mitarbeitern, minimalem oder maximalem Umsatz oder benutzerdefinierten Spalten. Benutzerdefinierte Spalten sind die hinzugefügten CRM- und Signalspalten. Filtern Sie beispielsweise nach Konten, für die die Spalte „Einstellungen“ auf &quot;`Yes`&quot; festgelegt ist.
1. Wählen Sie optional **[!UICONTROL Konten priorisieren]** aus, um die Konten nach Bewertung zu sortieren.
1. Entfernen Sie alle Konten, die nicht funktionieren sollen.

Filter werden mit der Liste gespeichert. Leads werden nur für die gefilterten Konten gefunden. Legen Sie daher Kontofilter fest, bevor Sie Leads priorisieren.

## Suchen und Priorisieren von Leads

Finden Sie relevante Personen in den Accounts, die Sie in die engere Wahl gezogen haben. Wählen **[!UICONTROL unter „Leads priorisieren]** eine Voreinstellung aus oder beschreiben Sie die Personen, die Sie im Chat haben möchten.

| Voreinstellung | Gefundene Kontakte |
| --- | --- |
| **[!UICONTROL Vertriebskontakte]** | Ansprechpartner für Vertriebs- und Vertriebsleiter |
| **[!UICONTROL Marketing-Kontakte]** | VP Marketing und Marketing Manager Kontakte |
| **[!UICONTROL Produktkontakte]** | SVP-Produkt- und Produkt-Manager-Kontakte |
| **[!UICONTROL Technologiekontakte]** | Leiter IT und VP Engineering Kontakte |
| **[!UICONTROL Alle CRM-Kontakte]** | Jeder verfügbare Kontakt bei den Accounts bis zum Limit von 2.000 Leads |

Geben Sie für eine Chat-Anfrage `Find VP and Director level people at these accounts`, `Find C-level executives (CEO, CTO, CFO) at these accounts` oder `Find managers at these accounts` ein.

Überprüfen Sie die Ergebnisse auf der Registerkarte **[!UICONTROL Leads]** . Jeder Lead zeigt seinen Namen, Titel, Konto, E-Mail-Adresse, Inhaber und Score an. Filtern Sie nach der Priorität, ob eine E-Mail-Adresse verfügbar ist, die Mindest- oder Höchstpunktzahl oder ob sich der Lead in einem Workflow befindet. In **[!UICONTROL Spalte &quot;]**&quot; wird erläutert, warum jeder Lead dort eingestuft wird, wo er sich befindet.

### Funktionsweise von Scores

Die Scores reichen von 0 bis 100. Eine höhere Punktzahl bedeutet eine bessere Passform und mehr Bereitschaft, sich zu engagieren. Dieselben Daten erzeugen denselben Wert.

Eine Punktzahl kombiniert:

* **Anpassen**: Wie gut der Account Ihrem idealen Kundenprofil entspricht, z. B. Branche und Größe.
* **Kauf- und Wachstumssignale** Signale wie Einstellungen, Finanzierung und Führungswechsel. Die jüngsten Signale zählen mehr.
* **Verkaufskontext**: Kontext wie ein bestehender Kunde mit einer Expansionsmöglichkeit.

Lesen Sie die Begründung und die verfügbaren Daten, bevor Sie entscheiden, an wen Sie sich wenden möchten.

## Hinzufügen von Leads zu einem ausgehenden Workflow

Fügen Sie nach der Überprüfung der Leads die Leads, die Sie einem vorhandenen ausgehenden Workflow hinzufügen möchten, hinzu.

1. Filtern **[!UICONTROL auf der Registerkarte]** Leads“ die gewünschten Leads und wählen Sie sie aus. Wählen Sie beispielsweise Leads mit einer E-Mail-Adresse und einer Mindestpunktzahl von 70 aus.
1. Wählen Sie **[!UICONTROL Zu ausgehendem Workflow hinzufügen]** aus.
1. Wählen Sie den Workflow aus und bestätigen Sie.
1. Überprüfen Sie die Bestätigung. Die Spalte **[!UICONTROL Workflow]** zeigt **[!UICONTROL Zugewiesen]** für die hinzugefügten Leads an.

Sie können auch den Chat bitten, die Leads anhand des Namens zu einem Workflow hinzuzufügen. Wenn Sie den Namen nicht kennen, bitten Sie Chat, Ihre verfügbaren Workflows aufzulisten. Überprüfen Sie den Namen des Workflows und die Anzahl der Leads in der Antwort.

Das Hinzufügen von Leads ersetzt nicht die Überprüfung und Genehmigung von E-Mails. Führen Sie die Schritte aus[&#x200B; um generierte E](outbound-workflows.md#review-and-refine-generated-emails)Mails zu überprüfen und [Interessenten zu genehmigen und &#x200B;](outbound-workflows.md#approve-and-enroll-prospects) registrieren), bevor die Kontaktaufnahme gesendet wird.

## Derzeitiger Umfang und Einschränkungen

Beachten Sie während der Beta die folgenden Einschränkungen:

* Eine Spalte oder ein Signal pro Anfrage anfordern.
* Intelligente Zielgruppe verwendet standardmäßige CRM-Kontofelder. Benutzerdefinierte CRM-Felder werden nicht unterstützt.
* Das Filtern nach den Produkten, deren Besitzer ein Konto ist, wird nicht unterstützt.
* Für Salesforce ist es nicht möglich, Konten zu finden, die eine offene Opportunity haben. Die Suche nach Konten ohne offene Opportunity funktioniert mit beiden CRMs.
* Für Salesforce sind keine Anfragen zur Einstellung für eine bestimmte Rolle verfügbar, z. B. für Vertriebsmitarbeiter.

>[!MORELIKETHIS]
>
>* [Konten](accounts.md)
>* [Interessenten](prospects.md)
>* [Ausgehende Workflows](outbound-workflows.md)
>* [AI-Chat](ai-assistant.md)
