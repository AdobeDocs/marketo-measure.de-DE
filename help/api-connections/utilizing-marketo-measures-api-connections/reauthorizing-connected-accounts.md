---
unique-page-id: 18874690
description: Erneutes Autorisieren von Connected Accounts - [!DNL Marketo Measure] - Produktdokumentation
title: Erneutes Autorisieren von Connected Accounts
exl-id: 7abd1d67-5bed-45bb-844f-0ffd23c3d7f8
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Erneutes Autorisieren von Connected Accounts {#reauthorizing-connected-accounts}

Wenn die Verbindung zu einem Konto getrennt wird [!DNL Marketo Measure] -Konto, ändert sich der Status der Plattform in &quot;Autorisierung erforderlich&quot;und zeigt ein rotes Symbol an.

Wenn Ihre Anzeigenplattform getrennt wird, [!DNL Marketo Measure] können keine Kostendaten herunterladen oder, wenn Sie die automatische Tagging-Funktion aktiviert haben, hängen Sie die [!DNL Marketo Measure] UTM-Parameter für alle neu erstellten Anzeigen. [!DNL Marketo Measure] kann die UTM-Parameter nicht rückwirkend an Touchpoints anhängen, die von der Anzeigen-Plattform aus erstellt wurden, während das Konto getrennt wurde.

Wenn die Verbindung zwischen Ihrer CRM-Plattform getrennt wird, [!DNL Marketo Measure] kann nicht aktualisiert werden [!DNL Marketo Measure] Daten speichern oder neue Touchpoints in Ihre Organisation übertragen. Sobald die CRM-Verbindung wieder hergestellt wurde, [!DNL Marketo Measure] sendet alle Daten, die bei der Trennung des Kontos verpasst wurden.

![](assets/1-1.png)

## Erneutes Autorisieren von getrennten Konten {#re-authorizing-disconnected-accounts}

1. Navigieren Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} und melden Sie sich an.
1. Auswählen **[!UICONTROL Einstellungen]** unter [!UICONTROL Mein Konto] in der oberen linken Ecke.
1. Suchen Sie links den Abschnitt Integrationen und klicken Sie auf **[!UICONTROL Verbindungen]**.
1. Wählen Sie neben dem Konto, das neu verbunden werden soll, das Symbol für den roten Schlüssel aus.
1. Daraufhin wird ein Popup-Fenster angezeigt, in dem Sie aufgefordert werden, die Anmeldedaten für das Konto anzugeben.
