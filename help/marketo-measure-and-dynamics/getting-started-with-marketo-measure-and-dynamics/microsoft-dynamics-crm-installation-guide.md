---
unique-page-id: 18874763
description: "[!DNL Microsoft Dynamics] CRM-Installationsanleitung - Marketo-Maßnahme - Produktdokumentation"
title: "[!DNL Microsoft Dynamics] CRM-Installationsanleitung"
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] CRM-Installationsanleitung {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>Es werden möglicherweise Anweisungen angezeigt, die[!DNL Marketo Measure]&quot; in unserer Dokumentation, sehen aber immer noch &quot;Bizible&quot; in Ihrem CRM. Wir arbeiten daran, diese Aktualisierung durchzuführen, und das Rebranding wird sich in Kürze in Ihrem CRM widerspiegeln.

## Unterstützte Versionen {#supported-versions}

[!DNL Marketo Measure] unterstützt Folgendes [!DNL Microsoft Dynamics CRM] Versionen:

* [!DNL Microsoft Dynamics 2016] (Online und On-Premise)
* [!DNL Microsoft Dynamics 365] (Online und On-Premise)

Für Verbindung und Authentifizierung [!DNL Marketo Measure] unterstützt die folgenden Active Directory Federated Services (ADFS)-Versionen:

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## Installieren Sie die verwaltete Lösung {#install-the-managed-solution}

[Herunterladen und installieren](assets/marketo-measure-dynamics-extension.zip) die ZIP-Datei in Dynamics CRM.

**[!UICONTROL Einstellungen]** > **[!UICONTROL Anpassungen]** > **[!UICONTROL Lösungen]** > **[!UICONTROL Import]** (Schaltfläche) > **[!UICONTROL Datei auswählen]**.

![](assets/1.png)

>[!NOTE]
>
>Die folgenden beiden Screenshots können geringfügig von Ihren abweichen, da sie während einer Lösungsaktualisierung erstellt wurden.

![](assets/2.png)

![](assets/3.png)

## [!DNL Marketo Measure] Benutzerberechtigungen {#marketo-measure-user-permissions}

Es wird empfohlen, eine dedizierte [!DNL Marketo Measure] Verwenden Sie in Dynamics , damit wir Daten exportieren und importieren können, um Probleme mit anderen Benutzern in Ihrem CRM zu vermeiden. Beachten Sie den Benutzernamen und das Kennwort sowie die Endpunkt-URL, da diese bei der Erstellung der [!DNL Marketo Measure] -Konto.

## Sicherheitsrollen {#security-roles}

Wenn Ihr Unternehmen Dynamics-Sicherheitsrollen verwendet, stellen Sie sicher, dass der verbundene Benutzer oder der [!DNL Marketo Measure] Der Benutzer verfügt über ausreichende Lese-/Schreibberechtigungen für die erforderlichen Entitäten.

Sicherheitsrollen finden Sie hier: **[!UICONTROL Einstellungen]** > **[!UICONTROL Sicherheit]** > **[!UICONTROL Sicherheitsrollen]**.

Für [!DNL Marketo Measure] benutzerdefinierten Entitäten benötigen wir vollständige Berechtigungen für alle unsere Entitäten.

>[!NOTE]
>
>Benutzer, die Chancen schließen werden, benötigen auch die vollständigen Berechtigungen.

![](assets/4.png)

Informationen zu Dynamics-Standardentitäten finden Sie im Abschnitt [!DNL Marketo Measure] Dynamics-Schemadokument. Auf hoher Ebene [!DNL Marketo Measure] müssen nur in bestimmten Entitäten gelesen werden, um die entsprechenden Daten zu sammeln und in benutzerdefinierte Felder zu schreiben, die mit der verwalteten Lösung installiert werden. Wir werden keine neuen Standarddatensätze erstellen und auch keine Standardfelder aktualisieren.

## Touchpoints in Seitenlayouts einschließen: {#include-touchpoints-on-page-layouts}

1. Navigieren Sie für jede Entität zum Formular-Editor. Sie finden dies unter **[!UICONTROL Einstellungen]** > **[!UICONTROL Anpassungen]** > **[!UICONTROL System anpassen]** > `[Entity]` > **[!UICONTROL Forms]**. Oder Sie finden es in den Einstellungen, während Sie einen Datensatz anzeigen.

   * Die zu konfigurierenden Entitäten: Konto, Chancen, Kontakt, Lead und Kampagne.

   * Um Kampagnen zu konfigurieren, müssen Sie die Option &quot;Kampagnensynchronisierung&quot;in **[!UICONTROL CRM]** > **[!UICONTROL Kampagnen]**.

   ![](assets/5.png)

1. Seitenlayouts: Fügen Sie zunächst ein &quot;[!UICONTROL Eine Spalte]&quot; in dem Abschnitt, in dem die Touchpoints live geschaltet werden sollen. In dieser neuen Spalte benötigen wir ein Unterraster, das zu jedem Formular in Ihren Konto-, Opportunity-, Kontakt- und Lead-Entitäten hinzugefügt wird.

   ![](assets/6.png)

   ![](assets/7.png)

1. Wählen Sie das Objekt (Touchpoints der Käuferzuordnung oder Touchpoints der Käufer) aus, das im Unterraster dargestellt werden soll, was von der Objektbeziehung abhängt. Ändern Sie optional die anzuzeigenden Spalten, indem Sie auf die Schaltfläche Bearbeiten klicken. Die verwaltete Lösung hat ein Standardlayout festgelegt.

   Touchpoint-Subgrid für die Käuferzuordnung - Konten, Möglichkeiten und Kontakt\
   Käufer-Touchpoint-Subgrid - Leads und Kontakte

   ![](assets/8.png)

1. Nachdem Sie die Aktualisierung des Formulars abgeschlossen haben, veröffentlichen Sie die Änderungen und speichern Sie sie.

## Schema-bezogene Aspekte {#schema-related-considerations}

**Umsatz**

[!DNL Marketo Measure] verweist standardmäßig auf das Standardfeld &quot;Tatsächlicher Umsatz&quot;. Wenn Sie dies nicht verwenden, erläutern Sie bitte, wie Sie Ihren Lösungstechniker oder Success Manager über den Umsatz informieren, da ein benutzerdefinierter Workflow erforderlich ist.

**Abschlussdatum**

[!DNL Marketo Measure] verweist standardmäßig auf das Feld &quot;Datum der tatsächlichen Schließung&quot;. Wenn Sie dies nicht verwenden oder auch das Feld Geschätztes Schließdatum verwenden, erläutern Sie Ihren Prozess bitte Ihrem Solutions Engineer oder Success Manager. Möglicherweise müssen beide Felder in einem benutzerdefinierten Workflow berücksichtigt werden.

## Einrichten von Adobe Admin Console und Identitätsanbieter {#set-up-your-adobe-admin-console-and-identity-provider}

Der erste Schritt zur Verwendung von [!DNL Marketo Measure] ist das Erstellen und Anmelden bei Ihrem bereitgestellten Adobe Admin Console. Wenn Sie die E-Mail noch nicht mit Anweisungen zum Anmelden erhalten haben, wenden Sie sich an Ihren [!DNL Marketo Measure] Kundenbetreuer.

Als Produkt innerhalb der Adobe Suite [!DNL Marketo Measure] nutzt die volle Funktionalität von Adobe Admin Console für Identity Management. Mehr Ressourcen können [hier finden](https://helpx.adobe.com/de/enterprise/using/admin-console.html).

Wir empfehlen, alle Ressourcen, Best Practices und Optionen zu überprüfen, die Ihnen für [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Wenden Sie sich für Anleitungen und eine Übersicht über die Einrichtung Ihrer Identity Management in der Adobe Admin Console an Ihren [!DNL Marketo Measure] Kundenbetreuer.

Um die Benutzerauthentifizierung und -autorisierung mit Ihrer [!DNL Marketo Measure] -Instanz(en) müssen die folgenden Schritte in der Adobe Admin Console ausgeführt werden:

**Einrichten der [!DNL Marketo Measure] Produktkarte**

Beim Zugriff auf die Adobe Admin Console sehen Sie Ihre [!DNL Marketo Measure] Produktinstanz(en) im Abschnitt Überblick vorhanden.

![](assets/microsoft-dynamics-crm-installation-guide-8a.png)

Klicken Sie auf [!DNL Marketo Measure] Die Produktkarte zeigt Ihnen alle Ihre [!DNL Marketo Measure] Instanz(en). Standardmäßig wird jeder [!DNL Marketo Measure] Die Instanz hat ihr eigenes Profil mit dem Präfix &quot;[!DNL Marketo Measure]&quot;. Alle Administratoren oder Benutzer, die diesem oder einem anderen Profil in dieser Instanz hinzugefügt wurden, können sich bei anmelden. [!DNL Marketo Measure].

![](assets/microsoft-dynamics-crm-installation-guide-8b.png)

Es ist keine Aktion erforderlich, um ein neues Profil im [!DNL Marketo Measure] Produktinstanz(en).

So fügen Sie Benutzer hinzu, auf die [!DNL Marketo Measure], siehe Abschnitt [Hinzufügen [!DNL Marketo Measure] Administratoren und [!DNL Marketo Measure] Benutzer](#adding-marketo-measure-admins-and-marketo-measure-users) unten.

## Hinzufügen [!DNL Marketo Measure] Administratoren und [!DNL Marketo Measure] Benutzer {#adding-marketo-measure-admins-and-marketo-measure-users}

Der nächste Schritt besteht darin, Zugriff auf die [!DNL Marketo Measure] Anwendung durch Hinzufügen von Benutzern. Dies kann im Verzeichnis &quot;admins&quot;und &quot;users&quot;der [!DNL Marketo Measure] Produktkarte.

| Benutzertyp | Beschreibung |
|---|---|
| Administratoren | Dies sind Administratoren und Power-User der [!DNL Marketo Measure] Anwendung mit vollständiger Fähigkeit zur Aktualisierung und Verwaltung [!DNL Marketo Measure]-spezifische Konfigurationsoptionen |
| Benutzer | Dies sind Standardbenutzer von [!DNL Marketo Measure] Anwendung mit schreibgeschützten Berechtigungen innerhalb der [!DNL Marketo Measure] application |

Wenn Sie einen Benutzer zu seiner jeweiligen Gruppe hinzufügen, sehen Sie dessen [Identitätstyp aufgelistet](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/set-up-identity.ug.html).

>[!NOTE]
>
>Um [!DNL Marketo Measure] Administrator (in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}), muss ein Benutzer als Benutzer hinzugefügt werden. _und_ einem beliebigen [!DNL Marketo Measure] Produktprofil innerhalb der [!DNL Marketo Measure] Produktkarte.

**Anmelden bei[!DNL Marketo Measure]**

Nachdem ein Benutzer einem Produktprofil hinzugefügt wurde, kann er auf seine [!DNL Marketo Measure] Instanz(en) durch Auswahl der **Mit Adobe ID anmelden** Option bei [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}.

![](assets/microsoft-dynamics-crm-installation-guide-15.png)

## Konfigurieren von Verbindungen und Datenanbietern {#configuring-your-connections-and-data-providers}

Nachdem Sie sich bei der [!DNL Marketo Measure] und als Benutzer in der Adobe Admin Console eingerichtet wurden, besteht der nächste Schritt darin, Ihre verschiedenen Datenverbindungen einzurichten.

**CRM als Datenanbieter**

1. In [!DNL Marketo Measure] klicken Sie auf das **[!UICONTROL Mein Konto]** und wählen Sie **[!UICONTROL Einstellungen]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. under [!UICONTROL Integrationen] Klicken Sie im linken Navigationsbereich auf **[!UICONTROL Verbindungen]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. Klicken Sie auf **[!UICONTROL Einrichten einer neuen CRM-Verbindung]** Schaltfläche.

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. Weiter zu [!UICONTROL Microsoft Dynamics CRM], klicken Sie auf die **[!UICONTROL Verbinden]** Schaltfläche.

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. Auswählen [!UICONTROL Anmeldeinformationen] oder [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >Weitere Informationen zu OAuth finden Sie unter [diesem Artikel](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). Wenden Sie sich bei Fragen zum Prozess an Ihren [!DNL Marketo Measure] Kundenbetreuer.

1. In diesem Beispiel haben wir Anmeldedaten ausgewählt. Geben Sie Ihre Anmeldedaten ein und klicken Sie auf **[!UICONTROL Nächste]**.

Nach der Verbindung werden die Details Ihrer Dynamics-Verbindung in der Liste der CRM/MAP-Verbindungen angezeigt.

**Kontoverbindungen für Anzeigen**

So verbinden Sie Ihre Anzeigenkonten mit [!DNL Marketo Measure], indem Sie [!UICONTROL Verbindungen] innerhalb der [!DNL Marketo Measure] Anwendung.

1. Befolgen Sie die obigen Schritte 1 und 2 _CRM als Datenanbieter_ Abschnitt.

1. Klicken Sie auf **[!UICONTROL Einrichten einer neuen CRM-Verbindung]** Schaltfläche.

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. Wählen Sie die gewünschte Plattform aus.

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]JavaScript**

Zur [!DNL Marketo Measure] zur Verfolgung Ihrer Web-Aktivitäten gibt es mehrere Schritte für die Einrichtung.

1. Klicken Sie auf **[!UICONTROL Mein Konto]** und wählen Sie **[!UICONTROL Kontokonfiguration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. Geben Sie Ihre Telefonnummer ein. Geben Sie für Website Ihre primäre Stammdomäne ein, die für [!DNL Marketo Measure] Tracking auf Ihrer Website. Klicken **[!UICONTROL Speichern]** wann geschehen.

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >Wenden Sie sich zum Hinzufügen mehrerer Stammdomänen an Ihren [!DNL Marketo Measure] Kundenbetreuer.

1. Die [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) müssen dann auf der gesamten Site und Landingpages platziert werden. Es wird empfohlen, das Skript fest im Kopf Ihrer Landingpages zu codieren oder über ein Tag Management-System hinzuzufügen, z. B. [Google Tag Manager](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >Standardmäßig [!DNL Marketo Measure] exportiert jedes Mal 200 Datensätze pro API-Gutschrift, wenn ein Auftrag Daten an Ihr CRM sendet. Für die meisten Kunden bietet dies das optimale Gleichgewicht zwischen den API-Gutschriften, die von [!DNL Marketo Measure] und CPU-Ressourcenanforderungen im CRM-System. Bei Kunden mit komplexen CRM-Konfigurationen wie Workflows und Triggern kann eine kleinere Batch-Größe jedoch hilfreich sein, um die CRM-Leistung zu verbessern. Zu diesem Zweck [!DNL Marketo Measure] ermöglicht es Kunden, die Batch-Größe des CRM-Exports zu konfigurieren. Diese Einstellung ist auf der Seite Einstellungen > CRM > Allgemein in der Variablen [!DNL Marketo Measure] Webanwendung und Kunden können zwischen Batch-Größen von 200 (Standard), 100, 50 oder 25 wählen.
   >
   >Beachten Sie bei der Änderung dieser Einstellung, dass kleinere Batch-Größen mehr API-Gutschriften aus Ihrem CRM-System verbrauchen. Es wird empfohlen, die Batch-Größe nur zu reduzieren, wenn in Ihrem CRM-System CPU-Timeouts oder eine hohe CPU-Last auftreten.
