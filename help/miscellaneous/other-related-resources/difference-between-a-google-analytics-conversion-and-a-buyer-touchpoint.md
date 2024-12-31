---
unique-page-id: 18874648
description: Unterschied zwischen einer Google Analytics-Konversion und einer Buyer Touchpoint - [!DNL Marketo Measure]
title: Unterschied zwischen einer Google Analytics-Konversion und einem Buyer Touchpoint
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 5%

---

# Unterschied zwischen einer Google Analytics-Konversion und einem Buyer Touchpoint {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Erfahren Sie, was ein [!DNL Google Analytics (GA)] ist und wie es sich von einem Buyer Touchpoint unterscheidet.

**Was sind die Konversionen der Google Analytics?**

[!UICONTROL Google Analytics]-Konversionen werden dadurch bestimmt, wie ein Marketer oder ein Web-Entwickler „Ziel“-Abschlüsse auf einer bestimmten Website codiert. Google zufolge könnte man sich Ziele wie „einen Kauf (für eine E-Commerce-Site) tätigen, eine Spielebene ausfüllen (für eine mobile Gaming-App) oder ein Kontaktinformationsformular einreichen (für eine Marketing- oder Lead-Generation-Site)“ vorstellen. Meistens sehen Marketing-Fachleute Ziele/Konversionen als jemanden, der ein Informationsformular ausfüllt.

Ziele können jedoch nicht codiert werden, um ein bestimmtes Verhalten zu verwalten. Stattdessen gibt es Zieltypen, die ein Web-Entwickler konfigurieren kann. Im Folgenden finden Sie einige dieser Beispiele:

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>Zieltyp</strong></td> 
   <td><p><strong>Beschreibung</strong></p></td> 
   <td><strong>Beispiel</strong></td> 
  </tr> 
  <tr> 
   <td><p>Ziel</p></td> 
   <td>Ein bestimmter Speicherort wird geladen</td> 
   <td><em>Vielen Dank für Ihre Registrierung!Bildschirm </em> Web-Seite oder App</td> 
  </tr> 
  <tr> 
   <td>Dauer</td> 
   <td>Sitzungen, die eine bestimmte Zeit oder länger dauern</td> 
   <td>10 Minuten oder länger auf einer Support-Site</td> 
  </tr> 
  <tr> 
   <td>Pages/Screens pro Sitzung</td> 
   <td>Ein Benutzer kann eine bestimmte Anzahl von Seiten oder Bildschirmen anzeigen</td> 
   <td>Es wurden 5 Seiten oder Bildschirme geladen</td> 
  </tr> 
  <tr> 
   <td>Veranstaltung</td> 
   <td>Eine als Ereignis definierte Aktion wird ausgelöst</td> 
   <td>Social-Media-Empfehlung, Videowiedergabe und Klick</td> 
  </tr> 
 </tbody> 
</table>

Die meisten Marketing-Fachleute konfigurieren ihre Konversionen als „Ziel-Ziele“, d. h. sie erstellen normalerweise eine Dankeseite nach einem Formular, um dies als formale Konversion zu betrachten.

Das bedeutet, dass Google Dankeseitenansichten als Konversion betrachtet. Aus Sicht der Google Analytics ist dies eine Erkenntnis, mit der die meisten Marketer einverstanden sind.

Käufer-Touchpoints verhalten sich jedoch anders.

**Wie unterscheiden sich Käufer-Touchpoints?**

[!DNL Marketo Measure] JavaScript verfolgt Sitzungsdaten und Formularübermittlungen auf allen Formularen einer bestimmten Site. Es ist nicht notwendig, Ziele aus einem [!DNL Marketo Measure] Blickwinkel zu codieren. Dieser Vorgang läuft automatisch ab. Bei Formularübermittlungen meldet [!DNL Marketo Measure] jedes Mal den Abschluss eines Formulars, wenn ein anonymer Benutzer Informationsfelder in einem bestimmten Formular ausfüllt und auch auf die Schaltfläche „Formularübermittlung“ klickt. [!DNL Marketo Measure] benötigt keine Dankeseite, um die Formularübermittlung aufzuzeichnen.

[!DNL Marketo Measure] erstellt einen Formular-Touchpoint, wenn:

* Ein Lead/Kontakt, der mit diesen Konversionen verknüpft ist, wird in Ihrem CRM angezeigt.
* Das [!DNL Marketo Measure] JS ist auf den Web-Seiten vorhanden, die das Formular enthalten.
* Ein Formular wird innerhalb einer 30-minütigen Sitzung übermittelt.

[!DNL Marketo Measure] ignoriert Destination Google Analytics-Konversionen, wenn:

* Ein Bot sendet Formulare auf einer Website (diese Bots schaffen es normalerweise nicht in das CRM eines Kunden).
* Ein Benutzer sendet weitere Formulare nach der ersten Übermittlung des Formulars. [!DNL Marketo Measure] überträgt nur die erste Konvertierung aus dieser Sitzung.
* Der Benutzer klickt mehrmals auf die Formularübermittlung. [!DNL Marketo Measure] wird nur die erste Formularübermittlung berücksichtigt.
* Der Benutzer lädt die Dankeseite mehrmals neu.
* Der Benutzer verwendet alle Tools zum Blockieren von Anzeigen.

Wie Sie sehen, gibt es grundlegende Unterschiede zwischen dem, was GA und [!DNL Marketo Measure] als Konversion betrachten. Daher ist es wahrscheinlich, dass die Anzahl der Konversionen und die Anzahl der Formular-Touchpoints unterschiedlich sind.
