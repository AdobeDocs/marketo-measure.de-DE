---
unique-page-id: 27656737
description: Marketing-Ausgaben für Berichte - [!DNL Marketo Measure]
title: Marketing-Ausgaben für Berichte
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Marketing-Ausgaben für Berichte {#report-marketing-spend}

## Tabelle der Marketing-Ausgaben {#marketing-spend-table}

Die Tabelle Marketingausgaben enthält eine neue Spalte, in der die Währung für die einzelnen Zeilen Kanal, Unterkanal und Kampagne angezeigt wird. Diese neue Spalte wird für alle Kunden angezeigt, auch wenn nicht mehrere Währungen aktiviert sind.

Die Tabelle enthält eine Mischung verschiedener Währungen. Im Dashboard Marketing-Ausgaben erhalten Sie eine Summe aller Kanäle, Unterkanäle oder Kampagnen in einer Währung.

## Upload-Kosten {#upload-costs}

Wenn ein Benutzer die Kostendatei herunterlädt, enthält die Datei auch eine neue Spalte mit der Währung für jede Zeile. Die einzigen akzeptablen Währungen sind diejenigen, die im CRM festgelegt und gespeichert wurden. Sie müssen den aus drei Buchstaben bestehenden abgekürzten Code für Ihre Währung kennen (USD, CAD, JPY, EUR). Wenn eine Datei mit einer nicht anerkannten Währung hochgeladen wird, schlägt der Datei-Upload fehl.

## Kosten von Anzeigenintegrationen {#costs-from-ad-integrations}

Wann [!DNL Marketo Measure] Importiert die Kosten von verbundenen Plattformen wie AdWords, Bing, Facebook oder Doubleclick. Wir verwenden auch die gemeldete Währung. Die Währung wird neben Kanal, Unterkanal und Kampagne angezeigt, wenn sie in der Tabelle Marketing-Ausgaben angezeigt wird.

Wenn die Währung des Anzeigen-Providers nicht mit einer Währung übereinstimmt, die aus dem CRM abgerufen wird, wird möglicherweise der Fehler &quot;Gemischte Währungen&quot;unter [!DNL Marketo Measure Discover]. Um dies zu beheben, muss der CRM-Administrator eine Konversion für die unbekannte Währung hinzufügen.

## Migration zu konvertierten Marketingausgaben {#migrate-to-converted-marketing-spend}

Da die Marketing-Ausgaben historisch nur in einer einzigen (USD)-Währung getätigt wurden, ist ein kleiner Arbeitsaufwand erforderlich, um alle gemeldeten Ausgaben in die neue Währung zu ändern. Selbst wenn für Ihr Konto nicht die Option &quot;Mehrere Währungen&quot;aktiviert ist, sollten Sie diese Migration vornehmen, wenn Sie eine einheitliche Unternehmenswährung außer USD haben.

1. Aktuelle Ausgabedatei in eine CSV-Datei herunterladen
1. Die Spalte &quot;Währung&quot;zeigt &quot;[!UICONTROL USD]&quot; als die angenommene Währung. Sie können entweder alle Vorkommen von[!UICONTROL USD]&quot; oder verwenden Sie Suchen+Ersetzen , um alle &quot;[!UICONTROL USD]&quot;-Instanzen in Ihre eigene Unternehmenskreditwährung, z. B. &quot;[!UICONTROL EUR]&quot; oder &quot;[!UICONTROL GBP]&quot;.
1. Speichern Sie die Datei und laden Sie sie dann erneut in hoch. [!DNL Marketo Measure].
1. Alle von Ihnen gemeldeten Kosten werden jetzt als neue Währung angezeigt.
