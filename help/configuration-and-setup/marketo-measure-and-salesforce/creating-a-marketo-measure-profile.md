---
unique-page-id: 18874698
description: Erstellen eines [!DNL Marketo Measure] Profils - [!DNL Marketo Measure]
title: Erstellen eines [!DNL Marketo Measure] -Profils
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 3%

---

# Erstellen eines [!DNL Marketo Measure]-Profils {#creating-a-marketo-measure-profile}

Erfahren Sie, wie Sie ein [!DNL Marketo Measure] -Profil erstellen. Durch das Erstellen eines [!DNL Marketo Measure] -Profils werden beim Senden von Daten an Ihr CRM-System keine Überprüfungsfehler ausgegeben.

1. Erstellen Sie ein bestimmtes [!DNL Marketo Measure] -Profil:

   * Zuweisen des [!DNL Marketo Measure] Administratorberechtigungssatzes
   * Berechtigung zum Anzeigen und Bearbeiten konvertierter Leads aktivieren

   >[!NOTE]
   >
   >Dieses Profil kann ein Klon eines [!DNL System Admin] -Profils sein

1. Es wurde ein dedizierter [!DNL Marketo Measure] Benutzer erstellt:

   * Weisen Sie dem Benutzer das neue [!DNL Marketo Measure] Profil zu.
   * Aktivieren Sie &quot;Marketing-Benutzer&quot;als Berechtigung auf Benutzerebene

1. Schließen Sie dieses Profil aus allen Triggern, Workflows und Prozessen aus.
1. Melden Sie sich bei Ihrem [!DNL Marketo Measure]-Konto an und autorisieren Sie die [!DNL Salesforce]-Verbindung mit dem neuen Benutzer erneut:

   * Wechseln Sie zu &quot;[experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}&quot;und melden Sie sich mit den Salesforce-Anmeldeinformationen der neuen Benutzerproduktion an
   * Wählen Sie &quot;[!UICONTROL Einstellungen]&quot;in der Dropdown-Liste &quot;[!UICONTROL Mein Konto]&quot;aus.
   * Wählen Sie &quot;[!UICONTROL Verbindungen]&quot;innerhalb der Gruppe &quot;[!UICONTROL Integrationen]&quot;aus.
   * Klicken Sie auf das Schlüsselsymbol rechts neben der aktuellen verbundenen [!DNL Salesforce]-Verbindung und wählen Sie die Option Mit Produktion neu autorisieren aus. Melden Sie sich dann bei Aufforderung mit den neuen Benutzeranmeldeinformationen erneut an.

   Fertig!

   Wenden Sie sich bei Fragen zum Erstellen eines dedizierten [!DNL Marketo Measure] -Profils an das Adobe Account Team (Ihren Kundenbetreuer) oder an den [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
