---
unique-page-id: 18874554
description: Touchpoint-Generierung und -Zuordnung - [!DNL Marketo Measure] - Produktdokumentation
title: Erstellung und Zuordnung von Touchpoints
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 2%

---

# Erstellung und Zuordnung von Touchpoints {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] Attributionsverläufe hängen von zwei Prozessen ab:

* Touchpoint-Generierung, die Touchpoints erstellt, die die Interaktionen einer Person mit Ihren Marketing- und Verkaufsbemühungen darstellen
* Touchpoint-Zuordnung, durch die Touchpoints dem entsprechenden Kanal und dem entsprechenden Unterkanal gutgeschrieben werden

Damit Sie das Beste aus [!DNL Marketo Measure], sollten Sie [!DNL Marketo Measure] rep , um beide Prozesse an die Anforderungen Ihres Unternehmens anzupassen.

Methoden zur Touchpoint-Generierung

Der Prozess der Touchpoint-Generierung beantwortet die Frage &quot;Wie ist es? [!DNL Marketo Measure] Wird er wissen, dass dies geschehen ist?&quot; Je nach Funktionssatz und den Interaktionstypen, die Ihre potenziellen Kunden haben können, gibt es bis zu drei Möglichkeiten [!DNL Marketo Measure] kann eine Interaktion aufnehmen und einen Touchpoint erstellen, um sie darzustellen.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] Pro Sitzung wird nur ein Touchpoint generiert. Wenn mehr als ein Formular ausgefüllt wurde, wird nur das erste Ausfüllen des Formulars erfasst.

| **Interaktionstyp** | **Beispiel** | **Touchpoint-Generierungsmethode** |
|---|---|---|
| Online auf Ihrer Site(n) | Ausfüllen des Formulars | [!DNL Marketo Measure] JavaScript |
| Offline; Online nicht auf Ihrer Site/Ihren Sites | Messen; Content-Syndikations-Partner stellt eine Liste von Leads bereit, die mit Ihren Inhalten interagiert haben | CRM-Campaign-Mitgliedschaft synchronisiert mit [!DNL Marketo Measure], indem Sie entweder den Kampagnensynchronisierungstyp direkt in der Kampagne festlegen oder Regeln auf der Kampagnenseite in [!DNL Marketo Measure] |
| Verkaufsaktivität | Ausgehender Aufruf von SDR | CRM-Aktivitäts-Datensatz (Aufgabe oder Ereignis), der mit synchronisiert wird [!DNL Marketo Measure], durch die Logik in [!UICONTROL Tätigkeiten] Seite in [!DNL Marketo Measure] |

Touchpoint-Zuordnungsmethoden

Der Prozess der Touchpoint-Zuordnung beantwortet die Frage: &quot;Wie ist es nach der Erstellung dieses Touchpoints? [!DNL Marketo Measure] Werden Sie wissen, zu welchem Kanal und Subkanal er gehört?&quot; Jede Methode der Touchpoint-Generierung verfügt über eine eigene Methode der Touchpoint-Zuordnung.

| **Interaktionstyp** | **Erzeugungsmethode** | **Zuordnungsmethode** |
|---|---|---|
| Online auf Ihrer Site(n) | [!DNL Marketo Measure] JavaScript | Durch die [!DNL Online Channels] Seite in [!DNL Marketo Measure], indem auf UTM-Werte, Landingpage- und Verweisinformationen verwiesen wird |
| Offline; Online, nicht auf Ihren Sites | Synchronisation der CRM-Campaign-Mitgliedschaft | Durch die [!UICONTROL Offline-Kanäle] Seite in [!DNL Marketo Measure]durch Verweis auf den Kampagnentyp |
| Verkaufsaktivität | Synchronisation von CRM-Aktivitäten | Durch die [!UICONTROL Online-Kanäle] Seite in [!DNL Marketo Measure], indem auf den Kampagnennamen verwiesen wird, der der [!UICONTROL Tätigkeiten] page |

>[!MORELIKETHIS]
>
>* [Online-Touchpoints zuordnen zu [!DNL Marketo Measure] Kanäle/Subkanäle](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [Synchronisieren von CRM-Kampagnen in SFDC](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [Synchronisieren von CRM-Kampagnen in [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Zuordnen von CRM-Kampagnen zu [!DNL Marketo Measure] Kanäle/Subkanäle](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Erstellen von Touchpoints aus Verkaufsaktivitäten](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Häufig gestellte Fragen zu Aktivitäten und Zuordnen von Touchpoints zu Kanälen/Subkanälen](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

