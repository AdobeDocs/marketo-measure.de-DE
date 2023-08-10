---
unique-page-id: 18874696
description: Empfohlen [!DNL Salesforce] Berechtigungen für [!DNL Marketo Measure] Connected User - [!DNL Marketo Measure] - Produktdokumentation
title: Empfohlene [!DNL Salesforce] -Berechtigungen für [!DNL Marketo Measure] Connected User
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 29%

---

# Empfohlene[!DNL Salesforce]-Berechtigungen für[!DNL Marketo Measure]Connected User {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] sendet und empfängt Daten über einen verbundenen [!DNL Salesforce]-Benutzer in der [!DNL Marketo Measure]-App.

Um Touchpoint-Daten an Ihre [!DNL Salesforce] -Instanz muss der verbundene Benutzer Zugriff auf [!DNL Marketo Measure] benutzerspezifische Objekte (d. h. Touchpoint der Käufer- und Käuferzuordnung) sowie standardmäßige [!DNL Salesforce] Objekte wie Leads und Kontakte (siehe [[!DNL Marketo Measure] in Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Administratorbenutzerlizenzen können als verbundener Benutzer dienen, da sie häufig standardmäßig über die erforderlichen Datenberechtigungen verfügen. Ihr Team kann jedoch einen Integrationsbenutzer oder einen dedizierten [!DNL Salesforce] Anwenderlizenz, um die Auswirkungen von [!DNL Marketo Measure] auf Ihrer Instanz.

Wir empfehlen die folgenden Berechtigungen, um sicherzustellen, dass [!DNL Marketo Measure] Daten fließen genau:

* [!DNL Marketo Measure] Administratorberechtigungen für dedizierte Benutzer festgelegt

Der verwaltete Berechtigungssatz bietet einem SFDC-Administrator die Möglichkeit, Datensätze von [!DNL Marketo Measure]-Objekten zu erstellen, zu lesen, zu schreiben und zu löschen.

* Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten

Dies ermöglicht [!DNL Marketo Measure], Leads zu dekorieren, nachdem sie in Kontakte umgewandelt wurden. Wenn dieser Berechtigungssatz nicht aktiviert ist, kann es zu erheblichen Datenverfolgungslücken kommen. Weitere Informationen finden Sie unter [[!DNL Salesforce Trailblazer] Community](https://help.salesforce.com/articleView?id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] Kontrollkästchen für Marketing-Benutzer

Das Kontrollkästchen [!UICONTROL Marketing-Benutzer] ermöglicht es dem Benutzer, Kampagnen zu erstellen und die Assistenten zum Importieren von Kampagnen zu verwenden. Wenn diese Option nicht ausgewählt ist, kann der Benutzer nur Kampagnen und erweiterte Kampagneneinstellungen anzeigen, den Kampagnenverlauf für einen einzelnen Lead oder Kontakt bearbeiten und Kampagnenberichte ausführen. [!DNL Marketo Measure] muss in der Lage sein, das Kampagnenobjekt zu lesen und hineinzuschreiben.

**Zusätzliche Fehlerbehebung**

Wenn [!DNL Marketo Measure] weiterhin Probleme beim Lesen oder Schreiben von Daten auftreten, kann es hilfreich sein, Folgendes zu untersuchen:

* Zugriff auf [!DNL Salesforce] Warteschlangen

Wenn der dedizierte Benutzer keinen Zugriff auf Leads in Warteschlangen hat, kann er die Leads mit [!DNL Marketo Measure] Daten. Sie können dies erreichen, indem Sie eine Rolle in der Hierarchie haben, die den Zugriff auf Warteschlangen ermöglicht oder Benutzern einzeln Zugriff gewährt.

* Sicherheit und Barrierefreiheit auf Feldebene

Die Sicherheit auf Feldebene und die Barrierefreiheit der Felder sind miteinander verbunden, weisen jedoch einige wesentliche Unterschiede auf. Die Sicherheit auf Feldebene definiert die Sichtbarkeit des Felds für ein bestimmtes Profil, während die Barrierefreiheit des Felds anhand der Sicherheitskonfiguration auf Feldebene und der Seitenlayoutkonfiguration bestimmt, ob ein Feld bearbeitbar ist. Verwenden der [!DNL Marketo Measure] -Berechtigungssätze des Pakets erhalten Sie die erforderlichen Sicherheitseinstellungen für Feldobjekte. In einigen Fällen muss der verbundene Benutzer über die [!DNL Marketo Measure] -Felder in den Seitenlayouts. [!DNL Marketo Measure] -Felder im Layout ermöglichen die [!DNL Marketo Measure] Daten, die zugeordnet werden sollen [!DNL Salesforce]. Dies hängt von Ihrem jeweiligen [!DNL Salesforce] Umgebung.

Die [!DNL Salesforce] hat individuelle Bedürfnisse, aber wir stellen Ihnen unsere Anforderungen, um [!DNL Marketo Measure] Zugriffsanforderungen mit Ihren Sicherheitsprotokollen. Zögern Sie nicht, Kontakt aufzunehmen zu [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
