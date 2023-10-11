---
unique-page-id: 18874799
description: Anweisungen zum Seiten-Layout - [!DNL Marketo Measure] - Produktdokumentation
title: Anweisungen zum Seiten-Layout
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: ht
source-wordcount: '836'
ht-degree: 100%

---

# Anweisungen zum Seiten-Layout {#page-layout-instructions}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in unserer Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding wird bald in Ihrem CRM zu sehen sein.

Zur einfachen Anzeige von [!DNL Marketo Measure]-Daten empfehlen wir, die Seiten-Layouts für [!UICONTROL Konto-], [!UICONTROL Kontakt-], [!UICONTROL Lead-], [!UICONTROL Gelegenheits-] und [!UICONTROL Kampagnen-]Objekte zu aktualisieren. Unten sind die Anweisungen zum Seiten-Layout für jedes Objekt aufgeschlüsselt.

Navigieren Sie zunächst zu Ihren [!DNL Salesforce]-Einstellungen und öffnen Sie die Registerkarte [!UICONTROL Anpassen].

## Kampagnenobjekt {#campaign-object}

Wir empfehlen, [!DNL Marketo Measure]-Felder nur für Ihre Sandbox zu Ihrer SFDC-Kampagne hinzuzufügen. Mit diesem Feldern können Sie die Touchpoint-Generierung testen. In der Produktion wird empfohlen, nur die [!DNL Marketo Measure]-Schaltfläche für die Massenaktualisierung der Touchpoint-Daten hinzuzufügen. Wir raten davon ab, die [!DNL Marketo Measure]-Felder zur Produktion hinzuzufügen, da Sie Regeln zur Kampagnensynchronisierung erstellen können.

1. Wählen Sie innerhalb der Build-Option **[!UICONTROL Kampagnen]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

   ![](assets/1-1.jpg)

1. Klicken Sie auf **[!UICONTROL Bearbeiten]** neben dem Seiten-Layout, das Sie aktualisieren möchten.

   ![](assets/2-1.jpg)

1. Wählen Sie unter der Option [!UICONTROL Felder] das Feld **[!UICONTROL Buyer Touchpoints aktivieren]** und ziehen Sie es an die gewünschten Stelle auf der Seite. Fügen Sie als Nächstes die Felder **[!UICONTROL Startdatum des Touchpoints]** und **[!UICONTROL Enddatum des Touchpoints]** hinzu.

   ![](assets/3-2.png)

1. Klicken Sie dann oben auf der Seite auf die Option „[!UICONTROL Schaltflächen]“ im Schnellsuche-Menü.

1. Ziehen Sie die Schaltfläche **[!UICONTROL Massenaktualisierung Touchpoint-Datum]** in den Abschnitt mit den benutzerdefinierten Schaltflächen.

   ![](assets/4-1.jpg)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   >[!NOTE]
   >
   >Wenn Sie mehrere Kampagneneintragstypen verwenden, müssen die Werte der Auswahlliste für das Feld **[!UICONTROL Buyer Touchpoints aktivieren]** aktualisiert werden. Anweisungen dazu finden Sie in [diesem Artikel](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md).

## Leads {#leads}

1. Wählen Sie in Ihrer Build-Option **[!UICONTROL Leads]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

1. Klicken Sie auf **[!UICONTROL Bearbeiten]** neben dem Seiten-Layout, das Sie aktualisieren möchten. Beachten Sie, dass es mehrere Seiten-Layouts mit den Buyer Touchpoint-Abschnitten geben kann.

1. Klicken Sie links in Ihrem Schnellsuchmenü auf die Seitenoption „VisualForce“.

1. Erstellen Sie einen neuen Abschnitt und nennen Sie ihn „Buyer Touchpoints“.

   >[!NOTE]
   >
   >Wählen Sie für jeden dieser Abschnitte das Format „Einspaltig“ aus.

1. Ziehen Sie die VisualForce-Seite aus der **[!UICONTROL Marketo Measure-Lead-bezogene Liste]** in den Abschnitt mit dem Seiten-Layout.

   ![](assets/5-1.png)

1. Klicken Sie auf den Schraubenschlüssel auf der [!DNL VisualForce]-Seite, ändern Sie die Höhe in 100 und aktivieren Sie Bildlaufleisten.

1. Wählen Sie im Menü die Option [!UICONTROL Arbeitsflächenanwendungen] und erstellen Sie einen neuen Abschnitt mit dem Namen „Marketo Measure Insights“ unter dem gerade erstellten [!DNL VisualForce]-Abschnitt „Touchpoints“.

   >[!NOTE]
   >
   >Wählen Sie für jeden dieser Abschnitte das Format „Einspaltig“ aus.

1. Ziehen Sie die [!DNL Marketo Measure Insights]-Arbeitsflächenanwendung in den neu erstellten Abschnitt. Klicken Sie auf **Speichern**. Manchmal ist es erforderlich, das Seiten-Layout zuerst in der Arbeitsflächenanwendung zu speichern, bevor sie abgelegt wird, da Salesforce es nicht sofort erkennt. Nachdem Sie den neuen Abschnitt erstellt haben, speichern Sie also das Seiten-Layout erst und bearbeiten Sie es dann erneut, um die Arbeitsflächenanwendung in diesen Abschnitt zu ziehen. Dies gilt für jedes Objekt.

   >[!NOTE]
   >
   >Damit die [!DNL Marketo Measure Insights]-Arbeitsflächenanwendung ordnungsgemäß funktioniert, müssen [Berechtigungen ordnungsgemäß konfiguriert werden](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >Die meisten Kundinnen und Kunden verwenden keine Felder, die mit (FT) oder (LC) enden, da es sich um veraltete Felder handelt, die genutzt wurden, bevor der [!DNL Marketo Measure]-Touchpoint zu einem Objekt wurde.

Klicken Sie bei Verwendung der ABM-Funktion von [!DNL Marketo Measure] [hier](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md), um weitere Anweisungen zum Seiten-Layout zu erhalten.

## Kontakte {#contacts}

1. Wählen Sie in der Build-Option **[!UICONTROL Kontakte]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

1. Wählen Sie dann das Seiten-Layout aus, das Sie bearbeiten möchten.

   Gehen Sie zur Option „Zugehörige Listen“ im Schnellsuchmenü und fügen Sie die zugehörige Liste **[!UICONTROL Buyer Touchpoints]** hinzu.

1. Klicken Sie auf das Schraubenschlüsselsymbol und fügen Sie folgenden Spalten in dieser Reihenfolge hinzu:

   * Buyer Touchpoint
   * Marketing-Kanal
   * Touchpoint-Quelle
   * Name der Anzeigenkampagne
   * Touchpoint-Position
   * Touchpoint-Datum

1. Sortieren nach: Touchpoint-Datum, aufsteigend.

   ![](assets/6.jpg)

1. Erweitern Sie die Option „Schaltflächen“ und deaktivieren Sie **[!UICONTROL Neu]**.

   ![](assets/7.png)

1. Gehen Sie zurück zur Option [!UICONTROL Zugehörige Liste] im Menü und fügen Sie die zum **[!UICONTROL Buyer Attribution Touchpoint]** zugehörige Liste hinzu.

1. Klicken Sie auf das Schraubenschlüsselsymbol und fügen Sie folgenden Spalten in dieser Reihenfolge hinzu:

   * Attribution Touchpoint
   * Marketing-Kanal
   * Opportunity
   * Name der Anzeigenkampagne
   * Touchpoint-Typ
   * Touchpoint-Position
   * Attribution % W-förmig (_oder das stabilste Attributionsmodell wie „Vollständiger Pfad“ oder „Benutzerdefiniert“_)
   * Umsatz W-förmig (_oder das stabilste Attributionsmodell wie „Vollständiger Pfad“ oder „Benutzerdefiniert“_)
   * Touchpoint-Datum

1. Sortieren Sie die Touchpoints nach [!UICONTROL Datum] > [!UICONTROL Aufsteigend].

1. Erweitern Sie den Abschnitt „Schaltflächen“ und deaktivieren Sie **[!UICONTROL Neu]**.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Opportunitys {#opportunities}

1. Wählen Sie in der Build-Option **[!UICONTROL Opportunitys]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

1. Wählen Sie dann das Seiten-Layout aus, das Sie bearbeiten möchten.

1. Fügen Sie die zum **[!UICONTROL Buyer Attribution Touchpoint]** zugehörige Liste hinzu und klicken Sie auf das Schraubenschlüsselsymbol, um die folgenden Spalten für Opportunitys hinzuzufügen:

   * Attribution Touchpoint
   * Marketing-Kanal
   * Kontakt
   * Name der Anzeigenkampagne
   * Touchpoint-Typ
   * Touchpoint-Position
   * Attribution % W-förmig (_oder das stabilste Attributionsmodell wie „Vollständiger Pfad“ oder „Benutzerdefiniert“_)
   * Umsatz W-förmig (_oder das stabilste Attributionsmodell wie „Vollständiger Pfad“ oder „Benutzerdefiniert“_)
   * Touchpoint-Datum

1. Sortieren Sie nach [!UICONTROL Touchpoint-Datum] > [!UICONTROL Aufsteigend].

1. Deaktivieren Sie die Option **[!UICONTROL Neu]** im Abschnitt [!UICONTROL Schaltflächen].

1. Klicken Sie auf **[!UICONTROL Speichern]**.

## Konten {#accounts}

1. Wählen Sie in der Build-Option **[!UICONTROL Konten]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

1. Wählen Sie dann das Seiten-Layout aus, das Sie bearbeiten möchten.

1. Fügen Sie die zum **[!UICONTROL Buyer Attribution Touchpoint]** zugehörige Liste hinzu und klicken Sie auf das Schraubenschlüsselsymbol, um folgende Spalten hinzuzufügen:

   * Attribution Touchpoint
   * Marketing-Kanal
   * Opportunity
   * Name der Anzeigenkampagne
   * Touchpoint-Typ
   * Touchpoint-Position
   * Attribution % W-förmig (_oder das stabilste Attributionsmodell wie „Vollständiger Pfad“ oder „Benutzerdefiniert“_)
   * Umsatz W-förmig (_oder das stabilste Attributionsmodell wie „Vollständiger Pfad“ oder „Benutzerdefiniert“_)
   * Touchpoint-Datum

1. Sortieren Sie nach „Touchpoint-Datum“ > „Aufsteigend“.

1. Deaktivieren Sie die Option **[!UICONTROL Neu]** im Abschnitt [!UICONTROL Schaltflächen].

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Klicken Sie bei Verwendung der ABM-Funktion von [!DNL Marketo Measure] [hier](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md), um weitere Anweisungen zum Seiten-Layout zu erhalten.
