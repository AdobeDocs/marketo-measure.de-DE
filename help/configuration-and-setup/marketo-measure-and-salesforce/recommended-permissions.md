---
description: Recommended [!DNL Salesforce] Permissions for [!DNL Marketo Measure] Connected User - [!DNL Marketo Measure]
title: Empfohlene [!DNL Salesforce] -Berechtigungen für [!DNL Marketo Measure] Connected User
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 23%

---


# Empfohlene [!DNL Salesforce] für [!DNL Marketo Measure] Connected User {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] sendet und empfängt Daten über einen verbundenen [!DNL Salesforce]-Benutzer in der [!DNL Marketo Measure]-App.

Um Touchpoint-Daten an Ihre [!DNL Salesforce]-Instanz zu senden, muss der angemeldete Benutzer Zugriff auf [!DNL Marketo Measure] benutzerdefinierte Objekte (d. h. Buyer Touchpoint und Buyer Attribution Touchpoint) sowie auf standardmäßige [!DNL Salesforce] wie Leads und Kontakte haben. Siehe [[!DNL Marketo Measure] in Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Administratorbenutzerlizenzen können als verbundene Benutzer dienen, da sie standardmäßig oft über die erforderlichen Datenberechtigungen verfügen. Ihr Team zieht es jedoch möglicherweise vor, einen Integrationsbenutzer oder eine dedizierte [!DNL Salesforce]-Benutzerlizenz zu verwenden, um die Auswirkungen von [!DNL Marketo Measure] auf Ihre Instanz zu verfolgen.

Um sicherzustellen, dass [!DNL Marketo Measure] Daten korrekt fließen, empfehlen wir die folgenden Berechtigungen:

* Administratorberechtigungen für dedizierten Benutzer [!DNL Marketo Measure]

Der verwaltete Berechtigungssatz bietet einem SFDC-Administrator die Möglichkeit, Einträge von [!DNL Marketo Measure]-Objekten zu erstellen, zu lesen, zu schreiben und zu löschen.

* Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten

Dies ermöglicht [!DNL Marketo Measure], Leads zu dekorieren, nachdem sie in Kontakte umgewandelt wurden. Wenn dieser Berechtigungssatz nicht aktiviert ist, kann es zu erheblichen Lücken bei der Datenverfolgung kommen. Weitere Informationen finden Sie unter [[!DNL Salesforce Trailblazer] Community](https://help.salesforce.com/s/articleView?language=en_US&id=leads_view_edit_converted.htm&type=5).

* Checkbox „Marketing-Benutzer [!DNL Salesforce]&quot;

Das Kontrollkästchen [!UICONTROL Marketing-Benutzer] ermöglicht es dem Benutzer, Kampagnen zu erstellen und die Assistenten zum Importieren von Kampagnen zu verwenden. Wenn diese Option nicht ausgewählt ist, können die Benutzenden nur Kampagnen und erweiterte Kampagneneinstellungen anzeigen, den Kampagnenverlauf für einen einzelnen Lead oder Kontakt bearbeiten und Kampagnenberichte ausführen. [!DNL Marketo Measure] muss in der Lage sein, das Kampagnenobjekt zu lesen und hineinzuschreiben.

**Zusätzliche Fehlerbehebung**

Wenn [!DNL Marketo Measure] weiterhin Probleme beim Lesen oder Schreiben von Daten haben, kann es hilfreich sein, Folgendes zu untersuchen:

* Zugriff auf [!DNL Salesforce] Warteschlangen

Wenn der dedizierte Benutzer keinen Zugriff auf Leads in Warteschlangen hat, kann er die Leads nicht mit [!DNL Marketo Measure] Daten ändern. Sie können dies erreichen, indem Sie in der Hierarchie eine Rolle haben, die den Zugriff auf Warteschlangen ermöglicht oder Benutzern einzeln Zugriff gewährt.

* Sicherheit und Barrierefreiheit auf Feldebene

Sicherheit auf Feldebene und Barrierefreiheit im Feld hängen zusammen, haben aber einige wichtige Unterschiede. Die Sicherheit auf Feldebene definiert die Sichtbarkeit von Feldern für ein bestimmtes Profil, während die Barrierefreiheit von Feldern basierend auf der Sicherheit auf Feldebene und der Seitenlayoutkonfiguration bestimmt, ob ein Feld bearbeitbar ist. Mithilfe der Berechtigungssätze des [!DNL Marketo Measure]-Pakets erhalten Sie die erforderlichen Sicherheitseinstellungen für Feldobjekte. Manchmal muss ein verbundener Benutzer über die [!DNL Marketo Measure] Felder in den Seiten-Layouts verfügen, um die richtige Barrierefreiheit für Felder zu erzielen. [!DNL Marketo Measure] Felder im Layout ermöglichen die Zuordnung der [!DNL Marketo Measure] zu [!DNL Salesforce]. Dies hängt von Ihrer jeweiligen [!DNL Salesforce] ab.

Die [!DNL Salesforce] jedes Unternehmens hat individuelle Anforderungen, aber wir stellen Ihnen unsere Anforderungen, um die [!DNL Marketo Measure] Zugriffsanforderungen mit Ihren Sicherheitsprotokollen in Einklang zu bringen. Zögern Sie nicht, sich an [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} zu wenden.
