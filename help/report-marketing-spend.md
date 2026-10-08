---
description: Berichte zu Marketing-Ausgaben für Marketo Measure-Benutzer
title: Marketing-Ausgaben für Berichte
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
    internal-label: Marketo Measure
feature_v2:
  - id: d24e0b99-7796-5c7d-831d-d71a1d725f01
    internal-label: Reporting
  - id: e3b4b95f-0bb9-5cb3-a479-9dcb943dca3f
    internal-label: Spend Management
source-git-commit: 940fee4abd0e09b6bf513b5e7526d3c242bd31c7
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 1%
---
# Marketing-Ausgaben für Berichte {#report-marketing-spend}

## Marketing-Ausgabentabelle {#marketing-spend-table}

Die Tabelle Marketingausgaben enthält eine neue Spalte, in der die Währung für jeden Kanal, Unterkanal und jede Kampagnenzeile angezeigt wird. Diese neue Spalte wird für alle Kunden angezeigt, auch wenn für sie nicht mehrere Währungen aktiviert sind.

Die Tabelle enthält eine Mischung verschiedener Währungen. Siehe das Dashboard Marketingausgaben , um eine Summe aller Kanäle, Unterkanäle oder Kampagnen in einer einzigen Währung zu erhalten.

## Upload-Kosten {#upload-costs}

Wenn ein Benutzer die Kostendatei herunterlädt, enthält die Datei auch eine neue Spalte mit der Währung für jede Zeile. Die einzigen zulässigen Währungen sind diejenigen, die im CRM festgelegt und gespeichert wurden. Sie müssen den abgekürzten dreistelligen Code für Ihre Währung kennen (USD, CAD, JPY, EUR). Wenn eine Datei mit einer nicht erkannten Währung hochgeladen wird, schlägt der Datei-Upload fehl.

## Kosten aus Anzeigenintegrationen {#costs-from-ad-integrations}

Wenn [!DNL Marketo Measure] die Kosten von verbundenen Plattformen wie AdWords, Bing, Facebook oder Doubleclick importiert, verwenden wir auch die angegebene Währung. Die Währung wird neben dem Kanal, Unterkanal und der Kampagne angezeigt, wenn sie in der Tabelle „Marketing-Ausgaben“ angezeigt werden.

Wenn die Währung vom Werbeanbieter nicht mit einer Währung übereinstimmt, die vom CRM abgerufen wird, wird in [!DNL Marketo Measure Discover] möglicherweise der Fehler „Gemischte Währungen“ angezeigt. Um dies zu beheben, muss der CRM-Administrator eine Konversion für die unbekannte Währung hinzufügen.

## Zu konvertierten Marketingausgaben migrieren {#migrate-to-converted-marketing-spend}

Da die Marketingausgaben in der Vergangenheit nur in einer einzigen Währung (USD) getätigt wurden, ist ein geringer Arbeitsaufwand erforderlich, um alle gemeldeten Ausgaben in die neue Währung zu ändern. Auch wenn für Ihr Konto mehrere Währungen nicht aktiviert sind, sollten Sie diese Migration durchführen, wenn Sie eine einzige Unternehmenswährung außer USD haben.

1. Aktuelle Ausgabedatei als CSV herunterladen
1. In der Währungsspalte wird &quot;[!UICONTROL USD]&quot; als angenommene Währung angezeigt. Sie können entweder alle Vorkommen von &quot;[!UICONTROL USD]&quot; manuell ersetzen oder mit Suchen+Ersetzen alle &quot;[!UICONTROL USD]&quot;-Instanzen in Ihre eigene Unternehmenswährung ändern, z. B. &quot;[!UICONTROL EUR]&quot; oder &quot;[!UICONTROL GBP].
1. Speichern Sie die Datei und laden Sie sie wieder in [!DNL Marketo Measure] hoch.
1. Alle gemeldeten Kosten werden jetzt in der neuen Währung angezeigt.
