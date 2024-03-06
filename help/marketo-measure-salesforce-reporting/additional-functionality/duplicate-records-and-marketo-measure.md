---
unique-page-id: 18874572
description: Datensätze duplizieren und [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Doppelte Datensätze und  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 7%

---

# Datensätze duplizieren und [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen mit den folgenden Eigenschaften angezeigt:[!DNL Marketo Measure]&quot; in der Dokumentation, sehen aber trotzdem &quot;Bizible&quot;in Ihrem CRM. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

[!DNL Marketo Measure] verwendet die E-Mail-Adresse als eindeutige Kennung bei der Zuordnung von Daten zu einem zugehörigen Lead oder Kontakt im CRM. Wann [!DNL Marketo Measure] findet mehrere Leads oder Kontakte mit derselben E-Mail-Adresse, wir decken die gleichen Daten auf allen Datensätzen auf. Die Auswirkungen sind zu erwarten, wenn Sie über Leads oder Kontakte mit [!DNL Marketo Measure] und kann die Anzahl der Einzelanwender mit Touchpoints für Käufer fälschlicherweise erhöhen.

Wie sieht dies aus in [!DNL Marketo Measure] Reporting?

_Beispielbericht: [!DNL Marketo Measure] Personen mit Touchpoints für Käufer._

![](assets/1-1.png)

Sie können die [!DNL Marketo Measure] Personen-ID von kelsey@adobe.com , dass es sowohl eine Lead- als auch eine Kontaktperson mit dieser E-Mail-Adresse gibt. In diesem Bericht werden 2 Erstkontakt-Ereignisse, zwei Lead-Erstellungskontakt-Touches und zwei PostLC-Interaktionen gemeldet. Diese doppelten Datensätze enthalten Touchpoint-Datums- und Touchpoint-Informationen, die zu dem Schluss führen können, dass es sich um zwei verschiedene Personen handelt, obwohl es sich um dieselbe Person handelt.

**Empfehlung**

* Um die Rendite Ihrer Berichte zu maximieren, empfehlen wir die Verwendung eines Deduplizierungs-Tools in Ihrem CRM-System, um sicherzustellen, dass Sie nur netto neue, eindeutige Datensätze erstellen. Dies kann mit Ihrem Marketing-Automatisierungs-Tool oder einer separaten Software erfolgen, die in Ihrem CRM-System installiert ist. [!DNL Marketo Measure] dedupliziert keine Datensätze automatisch und bietet diesen Service nicht über unsere Software an.
* Eine alternative Option wäre das manuelle Zusammenführen von Datensätzen bei der Identifizierung von Duplikaten. Dieser Prozess kann zeitaufwendig und mühsam sein, aber die Ausgabe präziser Berichte ist die Zeitinvestition wert.
