---
description: "[!DNL Marketo Measure] Installation und Einrichtung von Salesforce-Paketen - [!DNL Marketo Measure] - Produktdokumentation"
title: "[!DNL Marketo Measure] [!DNL Salesforce] Package-Installation und -Einrichtung"
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# [!DNL Marketo Measure] Installation und Einrichtung von Salesforce-Paketen {#marketo-measure-salesforce-package-installation-and-set-up}

Vor der Installation [!DNL Marketo Measure] [!DNL Salesforce] Basispaket, müssen Sie ermitteln, ob Sie es zuerst in einem [!DNL Salesforce] Sandbox , bevor Sie zu Ihrer Salesforce-Produktionsinstanz wechseln.

>[!NOTE]
>
>Einmal [!DNL Marketo Measure] -Konto mit einer [!DNL Salesforce] Produktionsinstanz können Sie nicht rückwärts gehen und eine Verbindung zu einer Sandbox herstellen. Außerdem wird eine [!DNL Marketo Measure] -Konto kann nur mit einem [!DNL Salesforce] Produktionsinstanz.

Die [!DNL Marketo Measure] Das Basispaket enthält:

* 7 Benutzerdefiniert [!DNL Marketo Measure] Objekte
* Benutzerdefiniert [!DNL Marketo Measure] Felder
* 25 [!DNL Stock] Berichte

[!DNL Marketo Measure] kann Standard lesen [!DNL Salesforce] Objekte, Felder und Datensätze [!DNL Marketo Measure] aktualisiert oder pusst nie Daten. Alle von der [!DNL Marketo Measure] JavaScript wird im [!DNL Marketo Measure] Benutzerdefinierte Objekte und Felder.

Gehen Sie wie folgt vor, um die [!DNL Marketo Measure Salesforce] Basispaket.

1. Navigieren Sie mithilfe eines Inkognito-Browsers zum [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} und melden Sie sich an.

1. Installieren Sie im [!DNL Marketo Measure] -Paket in Sandbox oder Produktion.

1. Anmelden bei [!DNL Salesforce] als Administrator.

1. Auswählen **[!UICONTROL Installieren] für alle Benutzer**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. Sobald die Installation abgeschlossen ist, können Sie sie anzeigen.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

Nachdem Sie die Installation abgeschlossen haben, können Sie Ihre [[!DNL Salesforce] Seitenlayouts](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} mit dem [!DNL Marketo Measure] bei Bedarf.

>[!NOTE]
>
>Lesen Sie über [!DNL Marketo Measure] Erstellte Berechtigungssätze und [wie sie verwendet werden](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## Installieren [!DNL Marketo Measure] Dashboard-Paket {#install-marketo-measure-dashboard-package}

Die [!UICONTROL Dashboard] Das Erweiterungspaket enthält drei vordefinierte Dashboards. Wir empfehlen die Installation von [!UICONTROL Innerhalb] Produktion für alle Benutzer.

1. Installieren Sie das Paket aus dem [[!DNL Salesforce] Appexchange](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}.

1. Auswählen **[!UICONTROL Für alle Benutzer installieren]**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-3.png)

## Erstellen einer [!DNL Marketo Measure] Profil und Benutzer {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] sendet und empfängt Daten über eine verbundene [!DNL Salesforce] -Benutzer in [!DNL Marketo Measure] App.

Um Touchpoint-Daten an Ihre [!DNL Salesforce] -Instanz muss der verbundene Benutzer Zugriff auf [!DNL Marketo Measure] benutzerspezifische Objekte (z. B. Touchpoint der Käuferzuordnung und Touchpoint der Käuferzuordnung) sowie standardmäßige [!DNL Salesforce] Objekte wie Leads und Kontakte.

Erstellen Sie eine [!DNL Marketo Measure] Profil, um sicherzustellen, dass beim Pushen von Daten an Salesforce keine Überprüfungsfehler auftreten.

Schritt 1: Erstellen eines spezifischen [!DNL Marketo Measure] profile

1. Weisen Sie die folgenden Berechtigungen zu:

* &quot;[!DNL Marketo Measure] Administratorberechtigungssatz&quot;
   * Der verwaltete Berechtigungssatz bietet einem SFDC-Administrator die Möglichkeit, Datensätze zu erstellen, zu lesen, zu schreiben, zu löschen [!DNL Marketo Measure] Objekte.
* &quot;Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten&quot;
   * Dies ermöglicht Folgendes [!DNL Marketo Measure] um Leads zu dekorieren, nachdem sie in Kontakte umgewandelt wurden. Wenn dieser Berechtigungssatz nicht aktiviert ist, kann es zu erheblichen Datenverfolgungslücken kommen.

>[!NOTE]
>
>Dieses Profil kann ein Klon eines Systemadministratorprofils sein.

Schritt 2: Erstellen Sie eine dedizierte [!DNL Marketo Measure] -Benutzer, damit Sie die Auswirkungen von [!DNL Marketo Measure] auf [!DNL Salesforce] instance

1. Neu zuweisen [!DNL Marketo Measure] Profil für diesen Benutzer.

1. Aktivieren Sie &quot;Marketing-Benutzer&quot;als Berechtigung auf Benutzerebene.

* Die [!UICONTROL Marketing-Benutzer] Das Kontrollkästchen ermöglicht es dem Benutzer, Kampagnen zu erstellen und die Assistenten zum Importieren von Kampagnen zu verwenden. Wenn diese Option nicht ausgewählt ist, kann der Benutzer nur Kampagnen und erweiterte Kampagneneinstellungen anzeigen, den Kampagnenverlauf für einen einzelnen Lead oder Kontakt bearbeiten und Kampagnenberichte ausführen. [!DNL Marketo Measure] muss in der Lage sein, das Kampagnenobjekt zu lesen und zu schreiben.

Schritt 3: Dieses Profil aus allen Triggern, Workflows und Prozessen ausschließen

Schritt 4: Melden Sie sich bei Ihrer [!DNL Marketo Measure] Konto erstellen und die [!DNL Salesforce] Verbindung zum neuen Benutzer

1. Gehen Sie zu apps.bizible.com und melden Sie sich bei der neuen Benutzerproduktion an [!DNL Salesforce] Anmeldedaten.

1. Auswählen **[!UICONTROL Einstellungen]** innerhalb der **[!UICONTROL Mein Konto]** Dropdown-Liste.

1. Auswählen **[!UICONTROL Verbindungen]** innerhalb der **[!UICONTROL Integrationen]** Gruppierung.

1. Klicken Sie auf das Schlüsselsymbol rechts neben dem aktuellen verbundenen [!DNL Salesforce] Verbindung herstellen und auswählen, **Mit Produktion erneut autorisieren**. Melden Sie sich mit den neuen Benutzeranmeldeinformationen erneut an (wenn Sie dazu aufgefordert werden).
