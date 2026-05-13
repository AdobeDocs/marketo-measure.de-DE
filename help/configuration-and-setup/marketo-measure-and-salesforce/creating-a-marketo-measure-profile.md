---
unique-page-id: 18874698
description: Erstellen eines  [!DNL Marketo Measure] -Profils - [!DNL Marketo Measure]
title: Erstellen eines [!DNL Marketo Measure] -Profils
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
TQID: https://experienceleague.adobe.com/7LvGF-KnE-FAkp1eLwawZUbFqac4cWAH9YmPKXaqKsM
product_v2:
  - id: e6fc4016-a972-4f36-8c30-a6a5f82ad0c8
feature_v2:
  - id: c8f57308-7e33-4e41-a385-b55041c78939
source-git-commit: 9ceb54139bfa9b6ce7c2c5fbb4e25e649f5708a3
workflow-type: tm+mt
source-wordcount: 190
ht-degree: 7%

---

# Erstellen eines [!DNL Marketo Measure] Profils {#creating-a-marketo-measure-profile}

Erfahren Sie, wie Sie ein [!DNL Marketo Measure] erstellen. Durch die Erstellung eines [!DNL Marketo Measure] Profils wird sichergestellt, dass beim Pushen von Daten an Ihr CRM keine Validierungsfehler auftreten.

1. Erstellen Sie ein bestimmtes [!DNL Marketo Measure]:

   * Zuweisen des [!DNL Marketo Measure]-Administratorberechtigungssatzes
   * Berechtigung zum Anzeigen und Bearbeiten konvertierter Leads aktivieren

   >[!NOTE]
   >
   >Dieses Profil kann ein Klon eines [!DNL System Admin] sein

1. hat einen dedizierten [!DNL Marketo Measure] erstellt:

   * Weisen Sie diesem Benutzer das neue [!DNL Marketo Measure] zu
   * „Marketing-Benutzer“ als Berechtigung auf Benutzerebene aktivieren

1. Dieses Profil aus allen Triggern, Workflows und Prozessen ausschließen.
1. Melden Sie sich bei Ihrem [!DNL Marketo Measure]-Konto an und autorisieren Sie die [!DNL Salesforce] erneut mit dem neuen Benutzer:

   * Wechseln Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und melden Sie sich mit den neuen Produktions-Salesforce-Anmeldeinformationen an
   * Wählen Sie [!UICONTROL Einstellungen] in der Dropdown-Liste [!UICONTROL Mein Konto] aus.
   * Wählen Sie [!UICONTROL Verbindungen] innerhalb der Gruppierung [!UICONTROL Integrationen] aus.
   * Klicken Sie auf das Symbol Schlüssel rechts neben der aktuellen verbundenen [!DNL Salesforce]-Verbindung und wählen Sie die Option Erneute Autorisierung für Produktion aus. Melden Sie sich dann bei Aufforderung erneut mit den neuen Benutzeranmeldeinformationen an

   Fertig!

   Wenn Sie Fragen zur Erstellung eines dedizierten [!DNL Marketo Measure] haben, wenden Sie sich an das Adobe Account Team (Ihren Account Manager) oder an den [Marketo Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
