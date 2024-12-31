---
unique-page-id: 18874572
description: Duplizieren von Datensätzen und [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Doppelte Datensätze und  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 12%

---

# Duplizieren von Datensätzen und [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

[!DNL Marketo Measure] verwendet die E-Mail-Adresse als eindeutige Kennung, wenn Daten mit einem zugehörigen Lead oder Kontakt im CRM abgeglichen werden. Wenn [!DNL Marketo Measure] mehrere Leads oder Kontakte mit derselben E-Mail-Adresse findet, werden dieselben Daten in allen Datensätzen angezeigt. Dies wirkt sich aus, wenn Sie Berichte zu Leads oder Kontakten mit [!DNL Marketo Measure] erstellen, und kann fälschlicherweise die Anzahl der Einzelpersonen mit Käufer-Touchpoints in die Höhe treiben.

Wie sieht dies in [!DNL Marketo Measure] Reporting aus?

_Beispielbericht: [!DNL Marketo Measure] Personen mit Käufer-Touchpoints._

![](assets/1-1.png)

Für die [!DNL Marketo Measure] Personen-ID von kelsey@adobe.com können Sie sehen, dass es sowohl einen Lead als auch einen Kontakt mit dieser E-Mail-Adresse gibt. In diesem Bericht werden zwei Erstkontakte, zwei Lead-Erstellungs-Kontakte und zwei PostLC-Interaktionen gemeldet. Diese doppelten Datensätze enthalten dasselbe Touchpoint-Datum und dieselbe Touchpoint-Information, was zu dem Schluss führen könnte, dass es sich um zwei verschiedene Personen handelt, obwohl sie dieselbe Person sind.

**Empfehlung**

* Um eine maximale Rendite in Ihren Berichten zu erzielen, empfehlen wir die Verwendung eines Deduplizierungs-Tools in Ihrem CRM, um sicherzustellen, dass Sie nur neue, eindeutige Datensätze erstellen. Dies kann mit Ihrem Marketing-Automatisierungs-Tool oder einer separaten Software, die in Ihrem CRM installiert ist, erfolgen. [!DNL Marketo Measure] dedupliziert Einträge nicht automatisch und bietet diesen Service nicht über unsere Software an.
* Eine alternative Option besteht darin, Datensätze beim Identifizieren von Duplikaten manuell zusammenzuführen. Dieser Prozess kann zeitaufwendig und mühsam sein, aber das Ergebnis genauer Berichte lohnt sich.
