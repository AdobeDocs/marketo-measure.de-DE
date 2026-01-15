---
description: Anleitung zum Seitenlayout für Marketo Measure-Benutzer
title: Anweisungen zum Seiten-Layout
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 92%

---

# Anweisungen zum Seiten-Layout {#page-layout-instructions}

>[!NOTE]
>
>Möglicherweise werden Anweisungen zu „[!DNL Marketo Measure]“ in der Dokumentation angezeigt, obwohl Sie in Ihrem CRM weiterhin „Bizible“ sehen. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Zur einfachen Anzeige von [!DNL Marketo Measure]-Daten empfehlen wir, die Seiten-Layouts für [!UICONTROL Konto-], [!UICONTROL Kontakt-], [!UICONTROL Lead-], [!UICONTROL Gelegenheits-] und [!UICONTROL Kampagnen-]Objekte zu aktualisieren. Unten sind die Anweisungen zum Seiten-Layout für jedes Objekt aufgeschlüsselt.

Navigieren Sie zunächst zu Ihren [!DNL Salesforce]-Einstellungen und öffnen Sie die Registerkarte [!UICONTROL Anpassen].

## Kampagnenobjekt {#campaign-object}

Es wird empfohlen, dass Sie die [!DNL Marketo Measure]-Felder nur für Ihre Sandbox zu Ihrer SFDC-Kampagne hinzufügen. Mit diesem Feldern können Sie die Touchpoint-Generierung testen. In der Produktion wird empfohlen, nur die Schaltfläche [!DNL Marketo Measure] für die Massenaktualisierung des Touchpoint-Datums hinzuzufügen. Es wird davon abgeraten, die [!DNL Marketo Measure]-Felder in die Produktion aufzunehmen, da Sie Regeln zur Kampagnensynchronisierung erstellen können.

1. Wählen Sie innerhalb der Build-Option **[!UICONTROL Kampagnen]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

   ![1. Klicken Sie auf Seitenlayouts.](assets/marketo-salesforce-7.jpg)

1. Klicken Sie auf **[!UICONTROL Bearbeiten]** neben dem Seiten-Layout, das Sie aktualisieren möchten.

   ![1. Klicken Sie neben dem gewünschten Seiten-Layout auf Bearbeiten &#x200B;](assets/marketo-salesforce-1.jpg)

1. Wählen Sie unter der Option [!UICONTROL Felder] das Feld **[!UICONTROL Buyer Touchpoints aktivieren]** und ziehen Sie es an die gewünschten Stelle auf der Seite. Fügen Sie als Nächstes die Felder **[!UICONTROL Startdatum des Touchpoints]** und **[!UICONTROL Enddatum des Touchpoints]** hinzu.

   ![1. Wählen Sie in der Option Felder die Option Käufer-Touchpoints aktivieren aus](assets/bizible-full-1.png)

1. Klicken Sie dann oben auf der Seite auf die Option „[!UICONTROL Schaltflächen]“ im Schnellsuche-Menü.

1. Ziehen Sie die Schaltfläche **[!UICONTROL Massenaktualisierung Touchpoint-Datum]** in den Abschnitt mit den benutzerdefinierten Schaltflächen.

   ![1. Ziehen Sie die Schaltfläche Touchpoint-Datum Massenaktualisierung in Ihre benutzerdefinierte Ansicht](assets/bizible-taxonomy-1.png)

1. Klicken Sie auf **[!UICONTROL Speichern]**.

   >[!NOTE]
   >
   >Wenn Sie mehrere Kampagneneintragstypen verwenden, müssen Sie die Werte der Auswahlliste für das Feld **[!UICONTROL Buyer-Touchpoints aktivieren]** aktualisieren. Anweisungen dazu finden Sie in [diesem Artikel](/help/channel-tracking-and-setup/configurations-record-types.md).

## Leads {#leads}

1. Wählen Sie in Ihrer Build-Option **[!UICONTROL Leads]**.

1. Klicken Sie auf **[!UICONTROL Seiten-Layouts]**.

1. Klicken Sie auf **[!UICONTROL Bearbeiten]** neben dem Seiten-Layout, das Sie aktualisieren möchten. Beachten Sie, dass es mehrere Seiten-Layouts mit den Buyer-Touchpoint-Abschnitten geben kann.

1. Klicken Sie links in Ihrem Schnellsuchmenü auf die Seitenoption „VisualForce“.

1. Erstellen Sie einen Abschnitt und nennen Sie ihn „Buyer Touchpoints“.

1. Ziehen Sie die VisualForce-Seite aus der **[!UICONTROL Marketo Measure-Lead-bezogene Liste]** in den Abschnitt mit dem Seiten-Layout.

   ![1. Ziehen Sie die Seite Marketo Measure-Lead-Liste nach VisualForce](assets/connect-salesforce-1.png)

1. Klicken Sie auf den Schraubenschlüssel auf der [!DNL VisualForce]-Seite, ändern Sie die Höhe in 100 und aktivieren Sie Bildlaufleisten.

1. Wählen Sie im Menü die Option [!UICONTROL Arbeitsflächenanwendungen] und erstellen Sie unter dem gerade erstellten [!DNL VisualForce]-Abschnitt „Touchpoints“ einen neuen Abschnitt mit dem Namen „Marketo Measure Insights“.

1. Ziehen Sie die [!DNL Marketo Measure Insights]-Arbeitsflächenanwendung in den neu erstellten Abschnitt. Klicken Sie auf **Speichern**. Manchmal ist es erforderlich, das Seiten-Layout zuerst in der Arbeitsflächenanwendung zu speichern, bevor sie abgelegt wird, da Salesforce es nicht sofort erkennt. Nachdem Sie den Abschnitt erstellt haben, speichern Sie also das Seiten-Layout erst und bearbeiten Sie es dann erneut, um die Arbeitsflächenanwendung in diesen Abschnitt zu ziehen. Dies gilt für jedes Objekt.

   >[!NOTE]
   >
   >Damit die [!DNL Marketo Measure Insights]-Arbeitsflächenanwendung ordnungsgemäß funktioniert, müssen [Berechtigungen ordnungsgemäß konfiguriert werden](/help/configuration-and-setup/marketo-measure-insights-configuration.md).

Wenn Sie die ABM-Funktion von [!DNL Marketo Measure] verwenden, [klicken Sie hier für zusätzliche Anweisungen zum Seiten-Layout](/help/channel-tracking-and-setup/account-based-marketing-overview.md).

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

   ![1. Sortieren nach: Touchpoint-Datum, aufsteigend.](assets/marketo-salesforce-15.jpg)

1. Erweitern Sie die Option „Schaltflächen“ und deaktivieren Sie **[!UICONTROL Neu]**.

   ![1. Erweitern Sie die Option Schaltflächen und deaktivieren Sie Neu.](assets/marketo-salesforce-12.png)

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

Wenn Sie die ABM-Funktion von [!DNL Marketo Measure] verwenden, lesen Sie die [zusätzlichen Anweisungen für das Seiten-Layout](/help/channel-tracking-and-setup/account-based-marketing-overview.md).
