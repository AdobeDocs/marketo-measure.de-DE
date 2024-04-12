---
unique-page-id: 18874554
description: Generierung und Zuordnung von Touchpoints – [!DNL Marketo Measure]
title: Generierung und Zuordnung von Touchpoints
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: ht
source-wordcount: '365'
ht-degree: 100%

---

# Generierung und Zuordnung von Touchpoints {#touchpoint-generation-and-mapping}

Attributions-Storys von [!DNL Marketo Measure] hängen von zwei Prozessen ab:

* Touchpoint-Generierung, die Touchpoints erstellt, welche die Interaktionen einer Person mit Ihren Marketing- und Verkaufsanstrengungen darstellen
* Touchpoint-Zuordnung, durch die Touchpoints dem passenden Kanal und Unterkanal zugeschrieben werden

Damit Sie [!DNL Marketo Measure] bestmöglich nutzen können, sollten Sie mit Ihrer [!DNL Marketo Measure]-Kontaktperson sprechen, um beide Prozesse an die Anforderungen Ihres Unternehmens anzupassen.

Methoden zur Touchpoint-Generierung

Der Prozess der Touchpoint-Generierung beantwortet die Frage „Wie weiß [!DNL Marketo Measure], dass dies passiert ist?“ Je nach Ihrem Funktionsumfang und den Interaktionstypen, die Ihre potenziellen Kundinnen und Kunden haben können, gibt es bis zu drei Möglichkeiten, wie [!DNL Marketo Measure] eine Interaktion erfassen und einen Touchpoint erstellen kann, um sie darzustellen.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] generiert nur einen Touchpoint pro Sitzung. Wenn mehr als ein Formular ausgefüllt wurde, wird nur das erste Ausfüllen des Formulars erfasst.

| **Interaktionstyp** | **Beispiel** | **Methode der Touchpoint-Generierung** |
|---|---|---|
| Online auf Ihren Sites | Formularausfüllung | JavaScript von [!DNL Marketo Measure]  |
| Offline oder Online auf anderen Sites | Handelsmessen; Partner für Content Syndication stellen eine Liste von Leads bereit, die mit Ihren Inhalten interagiert haben | CRM-Kampagnenzugehörigkeit, synchronisiert mit [!DNL Marketo Measure], entweder durch Festlegen des Kampagnensynchronisierungstyps direkt in der Kampagne oder durch Festlegen von Regeln auf der Kampagnenseite in [!DNL Marketo Measure] |
| Verkaufsaktivität | Ausgehender Aufruf von SDR | CRM-Aktivitätseintrag (Aufgabe oder Ereignis), synchronisiert mit [!DNL Marketo Measure] durch die Logik auf der Seite [!UICONTROL Aktivitäten] in [!DNL Marketo Measure] |

Methoden der Touchpoint-Zuordnung

Der Prozess der Touchpoint-Zuordnung beantwortet die Frage: „Wenn dieser Touchpoint erstellt ist, wie weiß [!DNL Marketo Measure], zu welchem Kanal und Unterkanal er gehört?“ Jede Methode der Touchpoint-Generierung verfügt über eine eigene Methode der Touchpoint-Zuordnung.

| **Interaktionstyp** | **Generierungsmethode** | **Zuordnungsmethode** |
|---|---|---|
| Online auf Ihren Sites | JavaScript von [!DNL Marketo Measure]  | Über die Seite [!DNL Online Channels] in [!DNL Marketo Measure], indem UTM-Werte und die Landingpage referenziert werden und auf Verweisseiteninformationen verwiesen wird |
| Offline oder Online auf anderen Sites | Synchronisierung der CRM-Kampagnenzugehörigkeit | Über die Seite [!UICONTROL Offline-Kanäle] in [!DNL Marketo Measure], durch Verweis auf den Kampagnentyp |
| Verkaufsaktivität | Synchronisierung von CRM-Aktivitäten | Über die Seite [!UICONTROL Online-Kanäle] in [!DNL Marketo Measure], indem auf den Kampagnennamen verwiesen wird, der auf der Seite [!UICONTROL Aktivitäten] zugewiesen ist |

>[!MORELIKETHIS]
>
>* [Zuordnen von Online-Touchpoints zu  [!DNL Marketo Measure] Kanälen/Unterkanälen](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Synchronisieren von CRM-Kampagnen in SFDC](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [Synchronisieren von CRM-Kampagnen innerhalb von  [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Zuordnen von CRM-Kampagnen zu  [!DNL Marketo Measure] Kanälen/Unterkanälen](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Erstellen von Touchpoints aus Verkaufsaktivitäten](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Häufig gestellte Fragen zu Aktivitäten und Zuordnen von Aktivitäten-Touchpoints zu Kanälen/Unterkanälen](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

