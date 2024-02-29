---
unique-page-id: 27656737
description: Marketing-Ausgaben für Berichte - [!DNL Marketo Measure]
title: Marketing-Ausgaben für Berichte
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 1%

---

# Marketing-Ausgaben für Berichte {#report-marketing-spend}

## Tabelle der Marketing-Ausgaben {#marketing-spend-table}

Die Tabelle Marketingausgaben enthält jetzt eine neue Spalte, in der die Währung für die einzelnen Zeilen Kanal, Unterkanal und Kampagne angezeigt wird. Diese neue Spalte wird für alle Kunden angezeigt, auch wenn nicht mehrere Währungen aktiviert sind.

Die Tabelle enthält nun eine Mischung verschiedener Währungen. Informationen zum Abrufen einer Summe aller Kanäle, Subkanäle oder Kampagnen in einer Währung finden Sie im Dashboard Marketingausgaben .

## Upload-Kosten {#upload-costs}

Wenn ein Benutzer die Kostendatei herunterlädt, enthält die Datei auch eine neue Spalte mit der Währung für jede Zeile. Die einzigen akzeptablen Währungen sind diejenigen, die im CRM festgelegt und gespeichert wurden. Sie müssen den aus drei Buchstaben bestehenden abgekürzten Code für Ihre Währung kennen (d. h. USD, CAD, JPY, EUR). Wenn eine Datei mit einer nicht erkannten Währung hochgeladen wird, schlägt der Datei-Upload fehl.

## Kosten von Anzeigenintegrationen {#costs-from-ad-integrations}

Wann [!DNL Marketo Measure] Importiert die Kosten von verbundenen Plattformen wie AdWords, Bing, Facebook oder Doubleclick. Wir verwenden auch die gemeldete Währung. Die Währung wird zusammen mit Kanal, Unterkanal und Kampagne angezeigt, wenn sie in der Tabelle Marketing-Ausgaben angezeigt wird.

Wenn die Währung des Anzeigen-Providers nicht mit einer Währung übereinstimmt, die aus dem CRM abgerufen wird, wird möglicherweise der Fehler &quot;Gemischte Währungen&quot;unter [!DNL Marketo Measure Discover] weil wir keine Umrechnung dieser Währung vornehmen konnten. Um dies zu beheben, muss Ihr CRM-Administrator eine Konversion für die unbekannte Währung hinzufügen.

## Migration zu konvertierten Marketingausgaben {#migrate-to-converted-marketing-spend}

Da unsere Marketing-Ausgaben historisch nur in einer einzigen (USD)-Währung getätigt wurden, ist ein kleiner Arbeitsaufwand erforderlich, um alle gemeldeten Ausgaben in die neue Währung umzuwandeln. Selbst wenn für Ihr Konto nicht die Option &quot;Mehrere Währungen&quot;aktiviert ist, sollten Sie diese Migration durchführen, wenn Sie eine einheitliche Unternehmenswährung außer USD haben.

1. Aktuelle Ausgabedatei in eine CSV-Datei herunterladen
1. In der Währungsspalte wird &quot;[!UICONTROL USD]&quot; als die angenommene Währung. Sie können entweder alle Vorkommen von[!UICONTROL USD]&quot; oder verwenden Sie Suchen+Ersetzen , um alle &quot;[!UICONTROL USD]&quot;-Instanzen in Ihre eigene Unternehmenskreditwährung, z. B. &quot;[!UICONTROL EUR]&quot; oder &quot;[!UICONTROL GBP]&quot;.
1. Speichern Sie die Datei und laden Sie sie dann erneut in hoch. [!DNL Marketo Measure].
1. Alle von Ihnen gemeldeten Kosten werden jetzt als neue Währung angezeigt.
