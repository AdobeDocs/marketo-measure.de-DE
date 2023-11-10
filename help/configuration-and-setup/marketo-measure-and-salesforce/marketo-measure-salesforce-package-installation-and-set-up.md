---
description: "[!DNL Marketo Measure] Installation und Einrichtung von Salesforce-Paketen - [!DNL Marketo Measure] - Produktdokumentation"
title: "Installation und Einrichtung von [!DNL Marketo Measure] [!DNL Salesforce] -Paketen"
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: 68eb5bf83d589c9161490b1772551ed46a9ce444
workflow-type: ht
source-wordcount: '510'
ht-degree: 100%

---

# Installation und Einrichtung von [!DNL Marketo Measure] Salesforce-Paketen {#marketo-measure-salesforce-package-installation-and-set-up}

Vor der Installation des [!DNL Marketo Measure] [!DNL Salesforce] Basispakets müssen Sie ermitteln, ob Sie es zuerst in einer [!DNL Salesforce]-Sandbox installieren, bevor Sie zu Ihrer Salesforce-Betreibungsinstanz wechseln.

>[!NOTE]
>
>Wenn ihr [!DNL Marketo Measure]-Konto erst einmal mit einer [!DNL Salesforce]-Betreibungsinstanz verbunden ist, können Sie nicht mehr zurück gehen und eine Verbindung zu einer Sandbox herstellen. Außerdem kann ein [!DNL Marketo Measure]-Konto mit nur einer [!DNL Salesforce]-Betreibungsinstanz verbunden werden.

Das [!DNL Marketo Measure]-Basispaket enthält:

* 7 benutzerdefinierte [!DNL Marketo Measure]-Objekte
* Benutzerdefinierte [!DNL Marketo Measure]-Felder
* 25 [!DNL Stock]-Berichte

[!DNL Marketo Measure] kann Standard-Objekte, -Felder und -Datensätze von [!DNL Salesforce] lesen, jedoch wird [!DNL Marketo Measure] niemals Daten aktualisieren oder an sie übertragen. Alle von [!DNL Marketo Measure] Javascript erfassten Daten werden in den benutzerdefinierten Objekten und Feldern von [!DNL Marketo Measure] angezeigt.

Gehen Sie wie folgt vor, um das [!DNL Marketo Measure Salesforce]-Basispaket zu installieren.

1. Navigieren Sie mithilfe eines Inkognito-Browsers zum [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} und melden Sie sich an.

1. Installieren Sie das [!DNL Marketo Measure]-Paket in einer Sandbox oder in der Betreibung.

1. Melden Sie sich bei [!DNL Salesforce] als Administrator an.

1. Wählen Sie **[!UICONTROL Installieren] für alle Benutzer**. 

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. Sobald die Installation abgeschlossen ist, können Sie sie anzeigen.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

Nachdem Sie die Installation abgeschlossen haben, können Sie bei Bedarf Ihre [[!DNL Salesforce] Seitenlayouts](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} mit den Feldern von [!DNL Marketo Measure] aktualisieren.

>[!NOTE]
>
>Lesen Sie über für [!DNL Marketo Measure] erstellten Berechtigungssätze und darüber, [wie sie verwendet werden](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## Erstellen eines [!DNL Marketo Measure]-Profils und Benutzers {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] sendet und empfängt Daten über einen verbundenen [!DNL Salesforce]-Benutzer in der [!DNL Marketo Measure]-App.

Um Touchpoint-Daten an Ihre [!DNL Salesforce]-Instanz zu übertragen, muss der verbundene Benutzer Zugriff auf benutzerspezifische [!DNL Marketo Measure]-Objekte (z. B. Buyer Touchpoint und Buyer Attribution Touchpoint) sowie standardmäßige [!DNL Salesforce]-Objekte wie Leads und Kontakte haben.

Erstellen Sie ein [!DNL Marketo Measure]-Profil, um sicherzustellen, dass beim Übertragen von Daten an Salesforce keine Überprüfungsfehler auftreten.

Schritt 1: Erstellen eines spezifischen [!DNL Marketo Measure]-Profils

1. Weisen Sie die folgenden Berechtigungen zu:

* &quot;[!DNL Marketo Measure]-Administratorberechtigungssatz&quot;
   * Der verwaltete Berechtigungssatz bietet einem SFDC-Administrator die Möglichkeit, Datensätze von [!DNL Marketo Measure]-Objekten zu erstellen, zu lesen, zu schreiben und zu löschen.
* &quot;Berechtigungssatz für konvertierte Leads anzeigen und bearbeiten&quot;
   * Dies ermöglicht [!DNL Marketo Measure], Leads zu dekorieren, nachdem sie in Kontakte umgewandelt wurden. Wenn dieser Berechtigungssatz nicht aktiviert ist, kann es zu erheblichen Datenverfolgungslücken kommen.

>[!NOTE]
>
>Dieses Profil kann ein Klon eines Systemadministratorprofils sein.

Schritt 2: Erstellen Sie einen dedizierten [!DNL Marketo Measure]-Benutzer, damit Sie die Auswirkungen von [!DNL Marketo Measure] auf Ihre [!DNL Salesforce]-Instanz verfolgen können

1. Weisen Sie das [!DNL Marketo Measure]-Profil diesem Benutzer neu zu.

1. Aktivieren Sie &quot;Marketing-Benutzer“ als Berechtigung auf Benutzerebene.

* Das Kontrollkästchen [!UICONTROL Marketing-Benutzer] ermöglicht es dem Benutzer, Kampagnen zu erstellen und die Assistenten zum Importieren von Kampagnen zu verwenden. Wenn diese Option nicht ausgewählt ist, kann der Benutzer nur Kampagnen und erweiterte Kampagneneinstellungen anzeigen, den Kampagnenverlauf für einen einzelnen Lead oder Kontakt bearbeiten und Kampagnenberichte ausführen. [!DNL Marketo Measure] muss in der Lage sein, das Kampagnenobjekt zu lesen und hineinzuschreiben.

Schritt 3: Dieses Profil aus allen Triggern, Workflows und Prozessen ausschließen

Schritt 4: Melden Sie sich bei Ihrem [!DNL Marketo Measure]-Konto an und autorisieren Sie die [!DNL Salesforce]-Verbindung mit dem neuen Benutzer erneut

1. Gehen Sie zu apps.bizible.com und melden Sie sich mit den [!DNL Salesforce]-Anmeldedaten des neuen Benutzers für die Betreibung an.

1. Wählen Sie **[!UICONTROL Einstellungen]** in der Dropdown-Liste **[!UICONTROL Mein Konto]**.

1. Wählen Sie **[!UICONTROL Verbindungen]** in der Gruppierung **[!UICONTROL Integrationen]**.

1. Klicken Sie auf das Schlüsselsymbol rechts neben der aktuell verbundenen [!DNL Salesforce]-Verbindung und wählen Sie **Mit Betreibung erneut autorisieren**. Melden Sie sich mit den neuen Anmeldeinformationen erneut an (wenn Sie dazu aufgefordert werden).

>[!MORELIKETHIS]
>
>[Einrichten von Adobe Admin Console](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
