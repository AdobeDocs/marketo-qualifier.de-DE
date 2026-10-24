---
title: '[!DNL Adobe Marketo Qualifier] – Versionshinweise'
description: Erfahren Sie mehr über die neuen Funktionen in [!DNL Adobe Marketo Qualifier].
feature: Agentic AI, Sales Insights, Account Journeys
role: User
source-git-commit: bf94a2d28913093923f446025405339e4e64919c
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 11%
---
# [!DNL Adobe Marketo Qualifier] – Versionshinweise

## Bevorstehende Version

* Finden und priorisieren Sie die richtigen Accounts und Leads mit Smart Audience (Beta). Beschreiben Sie die gewünschten Konten in verständlicher Sprache, fügen Sie CRM-Daten und Wachstumssignale hinzu, prüfen Sie bewertete Leads und fügen Sie sie einem ausgehenden Workflow hinzu. [Weitere Informationen](smart-audience.md).
* Filtern Sie Kontakte nach Account-Feldern neben Kontakt- und Opportunity-Feldern, um die richtigen Kontakte zu finden und Outbound-Workflows genauer anzusprechen. [Weitere Informationen](prospects.md#filter-and-find-prospects).
* Kontakte zeigen den zugehörigen Konto- und Eigentümernamen an, und die Seite eines Interessenten zeigt jetzt 90 Tage Marketing-Aktivität an, von 30 Tagen. [Weitere Informationen](prospects.md#review-prospect-details).

## 10-08-2026

Diese Version umfasst:

* Verwenden Sie einen ausgehenden Workflow erneut oder ändern Sie die Touchpoints eines laufenden Workflows, duplizieren Sie ihn und bearbeiten Sie die Kopie. Die Kopie beginnt als privater Entwurf ohne Interessenten, und der ursprüngliche Workflow bleibt unverändert. [Weitere Informationen](outbound-workflows.md#duplicate-an-outbound-workflow).
* Konfigurieren Sie ausgehende Workflows in einem kompakten Layout mit Navigation zwischen Ziel, Targeting, Touchpoints und Einstellungen. [Weitere Informationen](outbound-workflows.md#create-an-outbound-workflow).
* Anfragen zum Löschen von Opt-outs in E-Mail-Antworten werden automatisch erkannt. Der Interessent wird als „Opt-out“ markiert und es werden keine weiteren Touchpoints gesendet. [Weitere Informationen](outbound-workflows.md#opt-out-requests-in-replies).
* Bereiten Sie sich auf Meetings mit einem einzigen Brief vor, der Web-Recherche und produktspezifische Fallstudien mit Gesprächspunkten kombiniert, die nach Relevanz und Quellen sortiert sind. [Weitere Informationen](prospects.md#generate-meeting-prep).
* Generierte E-Mails werden anhand von Qualitätsrichtlinien geprüft und bei Bedarf neu geschrieben, bevor Sie sie überprüfen. Sie überprüfen, bearbeiten und genehmigen weiterhin jede E-Mail, bevor sie gesendet wird. [Weitere Informationen](outbound-workflows.md#review-and-refine-generated-emails).

## 09-22-2026

Diese Version umfasst:

* Zeigen Sie [!DNL Marketo Sales Insights]- und Agentendaten im eingebetteten CRM-Plug-in an und fügen Sie Interessenten zu [!DNL Marketo Qualifier] hinzu. [Weitere Informationen](admin-settings.md#crm-mcp-and-the-embedded-plugin).
* Priorisieren Sie CRM-Leads mit Best Bets, „Meine Merkliste“, Web-Aktivität, E-Mail-Interaktion und Webinar-Aktivität. [Weitere Informationen](admin-settings.md#prioritize-leads-in-the-crm-plugin).
* Interessenten automatisch für ausgehende Workflows registrieren, wenn ihre Live-[!DNL Marketo] den Workflow-Kriterien entspricht. [Weitere Informationen](home.md#automatically-enroll-prospects-from-marketing-highlights).
* Überprüfen Sie den Interessentenkontext, exportieren Sie die Liste der Interessenten, und zeigen Sie Zusammenfassungen der KI-Personen in [!DNL Marketo Optimizer] Prime- und Ultimate-Instanzen an. [Weitere Informationen](prospects.md#review-prospect-context-and-export-the-list).
* Überprüfen und validieren Sie generierte E-Mails potenzieller Kundinnen und Kunden aus der Aufgabenwarteschlange und antworten Sie während eines ausgehenden Workflows mit Agentenvorschlägen. [Weitere Informationen](tasks.md).

## 09-08-2026

Diese Version umfasst:

* Legen Sie Ihren eigenen E-Mail-Zeichnungsstil einmal in den Profileinstellungen fest, und jede generierte E-Mail folgt ihm. [Weitere Informationen](profile-settings.md#email-drafting-context).
* Generieren Sie eine zielbasierte oder benutzerdefinierte Besprechungsvorbereitung auf der Seite eines potenziellen Kunden auf einer neuen Registerkarte für Besprechungsforschung . [Weitere Informationen](prospects.md#generate-meeting-prep).
* Administratoren können einen ausgehenden Workflow einem Teamkollegen zuweisen und die Workflow-Einstellungen auf ihre Standardeinstellungen zurücksetzen. [Weitere Informationen](outbound-workflows.md#create-an-outbound-workflow).
* Beim Importieren von potenziellen Kunden aus einer CSV-Datei benutzerdefinierte Felder zuordnen und diese Werte in generierten E-Mails verwenden. [Weitere Informationen](prospects.md#build-your-prospect-list).
* Die generierten E-Mails verwenden alle zusätzlichen Daten potenzieller Kunden, die Sie importieren, und können nativ in der Sprache des potenziellen Kunden geschrieben werden. [Weitere Informationen](outbound-workflows.md#step-5-add-prospects-and-start-email-generation).
* Die ausgehende Leistung zeigt standardmäßig die Öffnungs- und Klickrate an, mit einem Umschalter für die Rohanzahl und für die Gesamtzahl der potenziellen Kunden auf Organisationsebene. [Weitere Informationen](performance.md).
* CRM-Synchronisierungsregeln aktualisieren den CRM-Status automatisch, wenn ein Interessent einen ausgehenden Workflow durchläuft. [Weitere Informationen](admin-settings.md#configure-crm-sync-rules).
* Stellen Sie KI-Chat-Fragen in Ihren [!DNL Marketo Qualifier]-, CRM-, [!DNL Marketo]- und [!DNL Marketo Optimizer]. [Weitere Informationen](ai-assistant.md#ask-ai-chat-across-your-connected-data).

## 08-17-2026

[!DNL Marketo Qualifier] ist jetzt als eigenständige App verfügbar. Es unterstützt [!DNL Marketo Engage] und [!DNL Marketo Optimizer].

Diese Version umfasst:

* Priorisierung von Interessenten und Konten mit KI-generierten Aktivitätszusammenfassungen und signalbasierter Bewertung. [Weitere Informationen](prospects.md#review-prospect-details) über Interessenten oder [Konten](accounts.md#account-insights).
* Zielgesteuerte ausgehende Workflows mit von KI vorgeschlagenen Kadenzen und entworfenen E-Mails. [Weitere Informationen](outbound-workflows.md).
* Eine einheitliche Aufgabenwarteschlange für Telefonanrufe, LinkedInMails und E-Mail-Überprüfungen. [Weitere Informationen](tasks.md).
* Automatische Besprechungsbuchung über Kalenderintegration. [Weitere Informationen](outbound-workflows.md#meeting-booking).
* Ein Wissenszentrum für die Einführung von KI-Outreach in eigenen Playbook-Materialien. [Weitere Informationen](admin-settings.md#knowledge-center).
* KI-Chat für Fragen in natürlicher Sprache, die auf CRM-, Interaktions- und Wissenscenter-Daten basieren. [Weitere Informationen](ai-assistant.md).
* E-Mail- und Besprechungsbuchungs-Leistungsberichte. [Weitere Informationen](performance.md).
* Browser- und E-Mail-Plug-ins für den Zugriff innerhalb Ihres CRM oder Outlook. [Weitere Informationen](admin-settings.md#crm-mcp-and-the-embedded-plugin).
* Unterstützung für Salesforce- und Microsoft Dynamics 365-Integrationen. [Weitere Informationen](integrations.md).
