---
unique-page-id: 18874698
description: Erstellen einer [!DNL Marketo Measure] Profil - [!DNL Marketo Measure] - Produktdokumentation
title: Erstellen einer [!DNL Marketo Measure] Profil
exl-id: dab2e2cb-fbd3-464a-9bd7-e9bf153d9848
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Erstellen einer [!DNL Marketo Measure] Profil {#creating-a-marketo-measure-profile}

Erfahren Sie, wie Sie eine [!DNL Marketo Measure] Profil. Erstellen einer [!DNL Marketo Measure] -Profil stellt sicher, dass beim Senden von Daten an Ihr CRM-System keine Validierungsfehler auftreten.

1. Erstellen eines spezifischen [!DNL Marketo Measure] profile:

   * Zuweisen der [!DNL Marketo Measure] Administratorberechtigungssatz
   * Berechtigung zum Anzeigen und Bearbeiten konvertierter Leads aktivieren

   >[!NOTE]
   >
   >Dieses Profil kann ein Klon einer [!DNL System Admin] profile

1. Erstellen Sie eine dedizierte [!DNL Marketo Measure] user:

   * Neu zuweisen [!DNL Marketo Measure] Profil für diesen Benutzer
   * &quot;Marketing-Benutzer&quot;als Benutzerberechtigung aktivieren

1. Schließen Sie dieses Profil aus allen Triggern, Workflows und Prozessen aus.
1. Melden Sie sich bei Ihrer [!DNL Marketo Measure] Konto erstellen und die [!DNL Salesforce] Verbindung zum neuen Benutzer:

   * Navigieren Sie zu [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;} und melden Sie sich mit den Salesforce-Anmeldeinformationen der neuen Benutzerproduktion an
   * Wählen Sie &quot;[!UICONTROL Einstellungen]&quot; innerhalb der &quot;[!UICONTROL Mein Konto]Dropdown
   * Wählen Sie &quot;[!UICONTROL Verbindungen]&quot; innerhalb der &quot;[!UICONTROL Integrationen]&quot; gruppieren
   * Klicken Sie auf das Schlüsselsymbol rechts neben dem aktuellen verbundenen [!DNL Salesforce] und wählen Sie die Option Mit Produktion erneut autorisieren aus. Melden Sie sich dann mit den neuen Benutzeranmeldeinformationen erneut an, wenn Sie dazu aufgefordert werden

   Abgeschlossen!

   Wenn Sie Fragen zur Erstellung eines dedizierten [!DNL Marketo Measure] Profil, wenden Sie sich an Ihren Kundenerfolgsmanager oder [Marketo-Support](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.
