---
unique-page-id: 18874572
description: Duplizierte Datensätze und  [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Doppelte Datensätze und  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 12%

---

# Datensätze duplizieren und [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

[!DNL Marketo Measure] verwendet die E-Mail-Adresse als eindeutige Kennung bei der Zuordnung von Daten zu einem zugehörigen Lead oder Kontakt im CRM. Wenn [!DNL Marketo Measure] mehrere Leads oder Kontakte mit derselben E-Mail-Adresse findet, werden dieselben Daten für alle Datensätze angezeigt. Die Auswirkung davon liegt darin, dass Sie über Leads oder Kontakte mit [!DNL Marketo Measure] berichten und die Anzahl der Unique People, die Touchpoints des Käufers haben, fälschlicherweise erhöhen können.

Wie sieht dies in der [!DNL Marketo Measure] -Berichterstellung aus?

_Beispielbericht: [!DNL Marketo Measure] Personen mit Touchpoints für Käufer._

![](assets/1-1.png)

Sie können für die [!DNL Marketo Measure] Personen-ID von kelsey@adobe.com sehen, dass mit dieser E-Mail-Adresse sowohl ein Lead als auch ein Kontakt vorhanden sind. In diesem Bericht werden 2 Erstkontakt-Ereignisse, zwei Lead-Erstellungskontakt-Touches und zwei PostLC-Interaktionen gemeldet. Diese doppelten Datensätze enthalten Touchpoint-Datums- und Touchpoint-Informationen, die zu dem Schluss führen können, dass es sich um zwei verschiedene Personen handelt, obwohl es sich um dieselbe Person handelt.

**Empfehlung**

* Um die Rendite Ihrer Berichte zu maximieren, empfehlen wir die Verwendung eines Deduplizierungs-Tools in Ihrem CRM-System, um sicherzustellen, dass Sie nur netto neue, eindeutige Datensätze erstellen. Dies kann mit Ihrem Marketing-Automatisierungs-Tool oder einer separaten Software erfolgen, die in Ihrem CRM-System installiert ist. [!DNL Marketo Measure] dedupliziert Datensätze nicht automatisch und bietet diesen Dienst nicht über unsere Software an.
* Eine alternative Option wäre das manuelle Zusammenführen von Datensätzen bei der Identifizierung von Duplikaten. Dieser Prozess kann zeitaufwendig und mühsam sein, aber die Ausgabe präziser Berichte ist die Zeitinvestition wert.
