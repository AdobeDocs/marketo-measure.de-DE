---
unique-page-id: 18874698
description: Erstellen einer [!DNL Marketo Measure] Profil - [!DNL Marketo Measure]
title: Erstellen eines [!DNL Marketo Measure] -Profils
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 3%

---

# Erstellen einer [!DNL Marketo Measure] Profil {#creating-a-marketo-measure-profile}

Erfahren Sie, wie Sie eine [!DNL Marketo Measure] Profil. Erstellen einer [!DNL Marketo Measure] -Profil stellt sicher, dass beim Senden von Daten an Ihr CRM-System keine Validierungsfehler auftreten.

1. Erstellen eines spezifischen [!DNL Marketo Measure] profile:

   * Zuweisen der [!DNL Marketo Measure] Administratorberechtigungssatz
   * Berechtigung zum Anzeigen und Bearbeiten konvertierter Leads aktivieren

   >[!NOTE]
   >
   >Dieses Profil kann ein Klon einer [!DNL System Admin] profile

1. Erstellung eines dedizierten [!DNL Marketo Measure] user:

   * Neu zuweisen [!DNL Marketo Measure] Profil für diesen Benutzer
   * Aktivieren Sie &quot;Marketing-Benutzer&quot;als Berechtigung auf Benutzerebene

1. Schließen Sie dieses Profil aus allen Triggern, Workflows und Prozessen aus.
1. Melden Sie sich bei Ihrer [!DNL Marketo Measure] Konto erstellen und die [!DNL Salesforce] Verbindung zum neuen Benutzer:

   * Navigieren Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} und melden Sie sich mit den Salesforce-Anmeldeinformationen der neuen Benutzerproduktion an
   * Wählen Sie &quot;[!UICONTROL Einstellungen]&quot; innerhalb der &quot;[!UICONTROL Mein Konto]Dropdown
   * Wählen Sie &quot;[!UICONTROL Verbindungen]&quot; innerhalb der &quot;[!UICONTROL Integrationen]&quot; gruppieren
   * Klicken Sie auf das Schlüsselsymbol rechts neben dem aktuellen verbundenen [!DNL Salesforce] Verbindung herzustellen und wählen Sie die Option Neu autorisieren mit Produktion aus. Melden Sie sich dann bei Aufforderung mit den neuen Benutzeranmeldeinformationen erneut an.

   Fertig!

   Wenn Sie Fragen zur Erstellung eines dedizierten [!DNL Marketo Measure] Profil, wenden Sie sich an das Adobe Account Team (Ihren Kundenbetreuer) oder [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
