---
description: Berichtstyp für Kontakte ohne Opportunitys
title: Berichtstyp für Kontakte ohne Opportunitys
exl-id: 255048be-16ff-4964-85fd-cc07888a05af
feature: Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 18%

---


# Berichtstyp für Kontakte ohne Opportunitys {#report-type-for-contacts-without-opportunities}

>[!NOTE]
>Möglicherweise werden in der Dokumentation Anweisungen für &quot;[!DNL Marketo Measure]&quot; angezeigt, in Ihrem CRM-System wird jedoch weiterhin &quot;[!DNL Bizible]&quot; angezeigt. Wir arbeiten an dieser Aktualisierung, und das Rebranding sollte bald in Ihrem CRM zu sehen sein.

Um Berichte zu Kontakten mit Käufer-Touchpoints zu erstellen, die keiner Opportunity zugeordnet sind, müssen Sie einen benutzerdefinierten Berichtstyp erstellen.

1. Navigieren Sie **[!UICONTROL Setup]** > **[!UICONTROL Erstellen]** > **[!UICONTROL Berichtstypen]**.

   ![Seite „Berichtstypen“ im Salesforce-Setup](assets/1.jpg)

1. Wählen Sie **[!UICONTROL Neuer benutzerdefinierter Berichtstyp]**.

   ![Bildschirm zur Auswahl eines neuen benutzerdefinierten Berichtstyps](assets/2.jpg)

1. Legen Sie das [!UICONTROL Primäre Objekt] als &quot;[!UICONTROL Kontakte] fest. Benennen Sie die Bezeichnung Berichtstyp als „Kontakte mit Käufer-Touchpoints“. Verwenden Sie dieselbe Benennung für den Namen des Berichtstyps. Geben Sie in der Beschreibungseingabe „Kontakte mit Käufer-Touchpoints“ ein. Speichern Sie den Bericht im &quot;[!UICONTROL Andere] und setzen Sie den Bericht auf &quot;[!UICONTROL bereitgestellt].

   ![Berichttypdetails mit Kontakten als primäres Objekt](assets/3.jpg)

1. Von dort aus verknüpfen Sie das Objekt Kontakte mit dem Objekt Käufer-Touchpoints . Stellen Sie sicher, dass Sie die Schaltfläche „Jeder Datensatz mit „A“ muss mindestens einen zugehörigen Datensatz mit „B“ haben.“

   ![Konfiguration der Objektbeziehung, die Kontakte mit Käufer-Touchpoints verknüpft](assets/4.jpg)

1. Klicken Sie **[!UICONTROL Speichern]** und Sie sind fertig!
