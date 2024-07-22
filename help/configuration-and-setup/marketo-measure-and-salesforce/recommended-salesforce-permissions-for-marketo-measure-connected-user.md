---
unique-page-id: 18874696
description: Empfohlene [!DNL Salesforce] Berechtigungen für  [!DNL Marketo Measure] Connected User - [!DNL Marketo Measure]
title: Empfohlene [!DNL Salesforce] -Berechtigungen für [!DNL Marketo Measure] Connected User
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 23%

---

# Empfohlene [!DNL Salesforce] Berechtigungen für [!DNL Marketo Measure] Connected User {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] sendet und empfängt Daten über einen verbundenen [!DNL Salesforce]-Benutzer in der [!DNL Marketo Measure]-App.

Um Touchpoint-Daten an Ihre [!DNL Salesforce]-Instanz zu senden, muss der verbundene Benutzer Zugriff auf [!DNL Marketo Measure] benutzerdefinierte Objekte (d. h. Buyer Touchpoint und Buyer Attribution Touchpoint) sowie standardmäßige [!DNL Salesforce] Objekte wie Leads und Kontakte haben. Siehe [[!DNL Marketo Measure] in Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Administratorlizenzen können als verbundener Benutzer dienen, da sie häufig standardmäßig über die erforderlichen Datenberechtigungen verfügen. Ihr Team kann es jedoch vorziehen, einen Integrationsbenutzer oder eine dedizierte [!DNL Salesforce] -Benutzerlizenz zu verwenden, um die Auswirkungen von [!DNL Marketo Measure] auf Ihre Instanz zu verfolgen.

Wir empfehlen die folgenden Berechtigungen, um sicherzustellen, dass [!DNL Marketo Measure]-Daten korrekt fließen:

* [!DNL Marketo Measure] Administratorberechtigungen für dedizierte Benutzer festgelegt

Der verwaltete Berechtigungssatz bietet einem SFDC-Administrator die Möglichkeit, Datensätze von [!DNL Marketo Measure]-Objekten zu erstellen, zu lesen, zu schreiben und zu löschen.

* Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten

Dies ermöglicht [!DNL Marketo Measure], Leads zu dekorieren, nachdem sie in Kontakte umgewandelt wurden. Wenn dieser Berechtigungssatz nicht aktiviert ist, kann es zu erheblichen Datenverfolgungslücken kommen. Weitere Informationen finden Sie in der [[!DNL Salesforce Trailblazer] Community](https://help.salesforce.com/s/articleView?language=en_US&amp;id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] Kontrollkästchen für Marketing-Benutzer

Das Kontrollkästchen [!UICONTROL Marketing-Benutzer] ermöglicht es dem Benutzer, Kampagnen zu erstellen und die Assistenten zum Importieren von Kampagnen zu verwenden. Wenn diese Option nicht ausgewählt ist, können die Benutzenden nur Kampagnen und erweiterte Kampagneneinstellungen anzeigen, den Kampagnenverlauf für einen einzelnen Lead oder Kontakt bearbeiten und Kampagnenberichte ausführen. [!DNL Marketo Measure] muss in der Lage sein, das Kampagnenobjekt zu lesen und hineinzuschreiben.

**Zusätzliche Fehlerbehebung**

Wenn bei [!DNL Marketo Measure] weiterhin Probleme beim Lesen oder Schreiben von Daten auftreten, kann es hilfreich sein, Folgendes zu untersuchen:

* Zugriff auf [!DNL Salesforce] Warteschlangen

Wenn der dedizierte Benutzer keinen Zugriff auf Leads in Warteschlangen hat, kann er die Leads nicht mit [!DNL Marketo Measure] -Daten ändern. Sie können dies erreichen, indem Sie eine Rolle in der Hierarchie haben, die den Zugriff auf Warteschlangen ermöglicht oder Benutzern einzeln Zugriff gewährt.

* Sicherheit und Barrierefreiheit auf Feldebene

Die Sicherheit auf Feldebene und die Barrierefreiheit der Felder sind miteinander verbunden, weisen jedoch einige wesentliche Unterschiede auf. Die Sicherheit auf Feldebene definiert die Sichtbarkeit des Felds für ein bestimmtes Profil, während die Barrierefreiheit des Felds anhand der Sicherheitskonfiguration auf Feldebene und der Seitenlayoutkonfiguration bestimmt, ob ein Feld bearbeitbar ist. Mithilfe der Berechtigungssätze des [!DNL Marketo Measure]-Pakets erhalten Sie die erforderlichen Sicherheitseinstellungen für Feldobjekte. Manchmal muss der verbundene Benutzer die Felder [!DNL Marketo Measure] in den Seitenlayouts haben, um die richtige Barrierefreiheit zu erhalten. [!DNL Marketo Measure] -Felder im Layout ermöglichen die Zuordnung der [!DNL Marketo Measure] -Daten zu [!DNL Salesforce]. Dies hängt von Ihrer jeweiligen [!DNL Salesforce] -Umgebung ab.

Die [!DNL Salesforce] jedes Unternehmens hat individuelle Bedürfnisse, aber wir stellen Ihnen unsere Anforderungen zur Verfügung, um die [!DNL Marketo Measure] Zugriffsanforderungen mit Ihren Sicherheitsprotokollen abzugleichen. Zögern Sie nicht, bis [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} zu gelangen.
