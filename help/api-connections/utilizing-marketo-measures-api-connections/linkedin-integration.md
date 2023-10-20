---
unique-page-id: 35586080
description: LinkedIn-Integration - [!DNL Marketo Measure] - Produktdokumentation
title: LinkedIn-Integration
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: 560ca558ae9ef4d2ef4da57eb9bfa672ed00e0fc
workflow-type: tm+mt
source-wordcount: '2653'
ht-degree: 2%

---

# LinkedIn-Integration {#linkedin-integration}

## Überblick {#overview}

Die [!DNL Marketo Measure] Die Integration mit LinkedIn erfolgt in zwei Komponenten:

Sponsored Content: Die Integration von gesponserten Inhalten ermöglicht [!DNL Marketo Measure] , um Ziel-URLs zu taggen [!DNL LinkedIn] Anzeigen, die letztendlich [!DNL Marketo Measure] , um einem Benutzer durch die gesamte Touchpoint-Journey zu folgen und die Aktivität wieder dem jeweiligen [!DNL LinkedIn] Kampagne und Kreativ. Dies bietet Kunden Einblicke in den ROI ihrer [!DNL LinkedIn] -Aktivität.

Lead Gen Forms: Durch die Integration mit der Lead Gen Forms von LinkedIn erhält Marketo Measure Einblicke in Formulare, die über die LinkedIn-Plattform übermittelt wurden. Diese Formulare werden mit Leads aus Ihrem CRM-System oder [!DNL Marketo Engage] -Instanz, damit sie für die Attribution berechtigt sind. Einblicke in die Kampagnen, Kreativelemente und Formulare, die zur Erstellung der Formulare beigetragen haben, ermöglichen es Teams nun, ihre LinkedIn-Marketing- und Anzeigenausgaben weiter zu optimieren.

## Verfügbarkeit {#availability}

Für alle Benutzer verfügbar.

## Anforderungen {#requirements}

**Rollen in Campaign Manager**

Für [!DNL Marketo Measure] Um Kostendaten für Anzeigen und Anzeigen herunterladen zu können, müssen Sie über eine der folgenden Rollen im Campaign Manager verfügen:

* Rechnungsadministrator
* Kundenbetreuer
* Kampagnen-Manager

Weitere Informationen: [Benutzerrollen und Funktionen in Campaign Manager](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Administratorrollen für gebührenpflichtige Medien**

Für [!DNL Marketo Measure] Um gesponserte Kreative erstellen/aktualisieren zu können, müssen Sie über eine der folgenden Paid Media-Admin-Rollen verfügen:

* Sponsored Content Poster
* Lead Gen Forms Manager

Weitere Informationen: [LinkedIn-Seitenadministratorrollen](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Es gibt andere [!DNL LinkedIn] Aufgaben, die wir ausführen **not** für unsere Integration erforderlich sind. Diese Rollen werden oft mit den erforderlichen Rollen verwechselt. Beachten Sie daher, dass es einen Unterschied gibt!

**Seitenadministratorrollen**

Für [!DNL Marketo Measure] Um Leads aus Lead-Generierungsformularen herunterladen/integrieren zu können, müssen Sie über die folgende Seitenadministratorrolle verfügen:

* Super Admin

Weitere Informationen: [LinkedIn-Seitenadministratorrollen](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## LinkedIn-Anzeigentypen {#linkedin-ad-types}

[!DNL Marketo Measure] unterstützt:

**Sponsored Content:** Gesponserte Inhalte ermöglichen es Ihnen, Inhalte für die [!DNL LinkedIn] Feed von Mitgliedern, die über diejenigen hinausgehen, die Ihrem Unternehmen folgen. Sponsored Content kann auf eine bestimmte Zielgruppe ausgerichtet sein und Werbetreibenden dabei helfen, [!DNL LinkedIn] Mitglieder, unabhängig davon, wo und wann sie sich in der [!DNL LinkedIn] Plattform für Desktop, Mobilgeräte und Tablets. Sponsored Content mit Lead Gen Forms wird unterstützt.

Die Arten von Sponsored Content und die Formate, die von [!DNL Marketo Measure] sind Einzelbild- und Videoanzeigen (über Lead Gen Forms). Aufgrund der Komplexität des Schemas unterstützen wir keine Karussellanzeigen.

[!DNL Marketo Measure] unterstützt keine gesponserten Nachrichten, Textanzeigen oder dynamischen Anzeigen.

![](assets/one.png)

>[!TIP]
>
>Für jede Ihrer Kampagnen/Ausgaben, die aus einer nicht gesponserten Inhaltsquelle stammen (z. B. Kampagnentyp &quot;Textanzeige&quot;oder &quot;Sponsored InMail&quot;), [!DNL Marketo Measure] does _not_ unterstützt grundsätzlich das Tracking dieser Kampagnentypen. Wenn Sie Ausgaben für Kampagnen wie diese zusammen mit Ihren Ausgaben für &quot;gesponserte Inhalte&quot;verfolgen möchten, sollten Sie unsere CSV für Marketingausgaben verwenden, um diese Ausgaben manuell zu protokollieren.

## Funktionsweise: gesponserte Inhalte {#how-it-works-sponsored-content}

>[!NOTE]
>
>Vor der ersten Verwendung muss diese Funktionseinstellung aktiviert werden, indem Sie zu [!DNL Marketo Measure] [!UICONTROL Einstellungen] > [!UICONTROL Integrationen] > [!UICONTROL Anzeigen] > [!UICONTROL LinkedIn Lead Gen Forms aktivieren].

**[!DNL LinkedIn's]Unique Auto-Tagging-Anforderungen**

[!DNL Marketo Measure] kann Ihnen dabei helfen, [!DNL LinkedIn] Kampagnenleistung durch automatisches Tagging Ihrer Landingpages.

[!DNL Marketo Measure] sucht nach Kreativen mit einer eindeutigen LinkedIn-Freigabe und fügt eine `?_bl={creativeId}` -Parameter an das Ende des Parameters an.

**Kopieren von Freigaben**

Mit diesem [!DNL Marketo Measure/LinkedIn] Für die Integration wird empfohlen, dass Kunden vorhandene Kreative nicht kopieren, klonen oder duplizieren. Wenn &quot;Teilen&quot;-Klicks gefunden werden, die nur auf einem Kreativ verwendet werden können, [!DNL Marketo Measure] kann die Freigabe so taggen, wie es ist, ohne dass kreative Inhalte oder &quot;Teilen&quot;-Klicks neu erstellt werden müssen. Alle Anzeigen-Verläufe (Impressionen, Klicks, &quot;Teilen&quot;-Klicks) bleiben erhalten.

Sobald eine Freigabe für mehrere Kreative freigegeben wurde, [!DNL Marketo Measure] muss einen Prozess zum Anhalten, Kopieren und erneuten Tagging durchlaufen, um einen eindeutigen Satz zu erstellen. [!DNL Marketo Measure] hält Live-Kreativinhalte an und archiviert sie, wodurch der Anzeigenverlauf einschließlich Impressionen, Klicks und Teilen in sozialen Netzwerken gelöscht wird, damit alles ordnungsgemäß mit einem Tag versehen werden kann.

Vorwärts, [!DNL Marketo Measure] empfiehlt, keine [!DNL LinkedIn] Teilt und bewahrt alle kreativen Inhalte und Freigaben so eindeutig wie möglich auf, sodass wir einfach unser Tracking hinzufügen können, ohne den Anzeigenverlauf löschen zu müssen.

**Kürzere URLs**

Der Grund für den zusätzlichen Schritt besteht darin, dass LinkedIn zulässt, dass Ziel-URLs eine gekürzte URL sind (bit.ly, goog.le usw.), was bedeutet, dass [!DNL Marketo Measure] sieht die lange, aufgelöste URL nicht und [!DNL Marketo Measure] muss Tracking-Parameter zu einer aufgelösten URL hinzufügen. Um dieses Problem zu umgehen, [!DNL Marketo Measure] sucht nach gekürzten URLs, bevor eine Anzeige neu erstellt wird, erweitert die URL und erstellt dann die neue Anzeige mit der aufgelösten URL und allen zugehörigen Parametern, sodass [!DNL Marketo Measure] , um Tags hinzuzufügen. Durch die Erstellung einer neuen Anzeige wird der Anzeigenverlauf (Impressionen, Klicks, Teilen-Klicks) gelöscht. Daher ist die Berechtigung zum Taggen gekürzter URLs erforderlich.

Wenn Sie die URLs erheblich gekürzt haben, kann es sich auf Ihre Kreativen auswirken. Wir empfehlen, keine verkürzten URLs mehr zu verwenden, damit [!DNL Marketo Measure] Sie können die Landingpages taggen, ohne neue Anzeigen erstellen und den Anzeigenverlauf löschen zu müssen.

**Der Prozess**

Fangen wir mit einigen Beispielen an. Angenommen, wir haben...

Kreativ A : Share 123\
Kreativ B : Share 234\
Creative C: Share 234\
Creative D : Share 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] werden zunächst alle Kampagnen, Kreative und &quot;Teilen&quot;-Klicks mit dem Status &quot;Aktiv&quot;durchsehen. [!DNL Marketo Measure] werden keine ausgesetzten, archivierten oder abgebrochenen Anzeigen mit Tags versehen. Wenn eine Anzeige angehalten wurde, setzen Sie [!UICONTROL active], werden wir ihn taggen, sobald er wieder aktiv ist. Wenn wir eine eindeutige Freigabe finden, d. h. sie wird nicht über mehrere Kreative oder Kampagnen hinweg verwendet (z. B. Creative A: Share 123), [!DNL Marketo Measure] fügt unseren benutzerdefinierten Parameter hinzu `>> ?_bl={creativeId}` zur Freigabe-URL.

`2)` Wenn die Freigabe nun freigegeben wurde und ihre Eindeutigkeit verloren hat (z. B. Creative B : Share 234 und Creative C: Share 234 und Creative D : Share 234), [!DNL Marketo Measure] hält alle ähnlichen kreativen Inhalte an und archiviert sie (Creative B, Creative C und Creative D).

`3)` [!DNL Marketo Measure] erstellt 3 neue Kreative, Creative E, Creative F und Creative G, die den archivierten Inhalt von Creative B kopieren.

`4)` [!DNL Marketo Measure] erstellt außerdem 3 neue Freigaben, Share 345, Share 456 und Share 567, die den Inhalt von Share 234 kopieren, bis auf die eigene eindeutige `?_bl` Tagging.

`5)` [!DNL Marketo Measure] müssen regelmäßig überprüfen, ob die Freigabe von &quot;Teilen&quot;-Klicks nicht erfolgt. Wenn dies der Fall ist, starten wir den Prozess in Schritt 2 neu.

>[!NOTE]
>
>Wenn Sie dies implementieren, verlieren unsere Kunden den Anzeigenverlauf von Creative B : Share 234, Creative C : Share 234 und Creative D : Share 234, da es jetzt mit Creative E neu erstellt wird: Share 345, Share F : Share 456 und Creative G : Share 567 .

![](assets/three.png)

## Funktionsweise: Lead Gen Forms {#how-it-works-lead-gen-forms}

**[!DNL LinkedIn's]Unique Auto-Tagging-Anforderungen**

[!DNL Marketo Measure] kann Ihnen dabei helfen, [!DNL LinkedIn] Kampagnenleistung durch automatisches Tagging Ihrer Landingpages.

[!DNL Marketo Measure] sucht nach Kreativen mit einer eindeutigen LinkedIn-Freigabe und fügt eine `?_bl={creativeId}` -Parameter an das Ende des Parameters an.

**Der Prozess**

bis [!DNL LinkedIn's] Ad Form API und Ad Form Response API können wir Daten zur Formularübermittlung für ein Anzeigenkonto erfassen und die E-Mail-Adresse mit einem Lead aus dem CRM oder Marketo verknüpfen.

LinkedIn-Formulare können mehrere E-Mail-Adressen enthalten. Wenn wir Formularantworten herunterladen, suchen wir nach E-Mail-Adressen mit der folgenden Priorität: Arbeits-E-Mail, E-Mail-Adresse (primäres Formularfeld) oder benutzerdefinierten Feldern mit einem gültigen E-Mail-Wert.

Unabhängig vom Status &quot;Kampagne&quot;oder &quot;Kreativ&quot;führen alle Formularantworten zu einem Touchpoint. [!DNL Marketo Measure] hat eine Lookback-Beschränkung von 90 Tagen, also [!DNL Marketo Measure] kann nicht auf Formularantworten zugreifen, die älter als 90 Tage sind, aber je länger die Variable [!DNL Marketo Measure] und [!DNL LinkedIn] Integration aktiviert ist, werden durch die [!DNL Marketo Measure].

>[!NOTE]
>
>LinkedIn-Kosten werden weiterhin als Teil von gesponserten Inhaltskampagnen heruntergeladen.

**Tracking von Lead Gen Forms in CRM oder Marketo**

Vor [!DNL Marketo Measure] und die LinkedIn Lead Gen Forms-Integration bestand, war es gängige Praxis für Kunden, ihre Formularübermittlungen an ein Marketo-Programm und/oder eine CRM-Kampagne zu senden, um die Formulare zu verfolgen und die Attribution für diese Aktivitäten zu erhalten. Sobald die Einstellung &quot;Lead Gen Forms&quot;aktiviert ist, möchten wir sicherstellen, dass diese Formularübermittlungen nicht doppelt gezählt werden. Überprüfen Sie Folgendes:

* Das Feld &quot;Käufer-Touchpoints aktivieren&quot;im CRM-Objekt ist auf &quot;Keine&quot;oder &quot;Alle Campaign-Mitglieder ausschließen&quot;gesetzt
* Alle zugehörigen Marketo-Programm- oder Marketo-Aktivitätsregeln aktualisieren
* Alle zugehörigen CRM-Kampagnenregeln aktualisieren

>[!NOTE]
>
>Die LinkedIn-API hat eine Lookback-Beschränkung von 90 Tagen. Wenn Sie also Marketo- oder CRM-Regeln verwenden, wird empfohlen, das Enddatum für die Regel auf 90 Tage vor dem Datum festzulegen, an dem Sie die Integration in [!DNL Marketo Measure].

## Touchpoint-Details ansehen {#touchpoint-details}

Einmal [!DNL Marketo Measure] Ihre Landingpage erfolgreich mit dem LinkedIn-Kreativ gekennzeichnet hat, können Sie die aufgelösten Anzeigendaten auf dem Touchpoint anzeigen. Hier finden Sie die Zuordnung von Datenwerten, die Sie erwarten sollten:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th style="width:30%">Touchpoint-Feld</th> 
   <th>Beispielwert</th> 
  </tr> 
  <tr> 
   <td>Anzeigen-ID</td>
   <td>84186224</td>
  </tr> 
  <tr> 
   <td>Anzeigeninhalt</td>
   <td>copy-1-image-2-man 95 % der #B2B-Marketer halten die Strategie zur Nachfrageerstellung für erfolgreich. Weitere Informationen: [!DNL https]://lnkd.in/jgdi50vKrgv</td>
  </tr> 
  <tr> 
   <td>Anzeigengruppen-ID</td>
   <td>(leer)</td>
  </tr> 
  <tr> 
   <td>Werbegruppenname</td>
   <td>(leer)</td>
  </tr> 
  <tr> 
   <td>Anzeigen-Kampagnen-ID</td>
   <td>138949954</td>
  </tr> 
  <tr> 
   <td>Name der Anzeigenkampagne</td>
   <td>SU - COM Accounts - Demand Skills</td>
  </tr> 
  <tr> 
   <td>Anzeigenziel-URL <b>*</b></td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td> 
  </tr> 
  <tr> 
   <td>Formular/URL</td> 
   <td>info.bizible.com/demo</td> 
  </tr> 
  <tr> 
   <td>Formular-URL - Roh</td> 
   <td>info.bizible.com/demo</td> 
  </tr> 
  <tr> 
   <td>Schlüsselwort-ID</td> 
   <td>(leer)</td> 
  </tr> 
  <tr> 
   <td>Suchbegriffübereinstimmungstyp</td> 
   <td>(leer)</td> 
  </tr> 
  <tr> 
   <td>Landingpage</td> 
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders</td> 
  </tr> 
  <tr> 
   <td>Landingpage - Roh</td> 
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td> 
  </tr> 
  <tr> 
   <td>Marketing-Kanal</td> 
   <td>Paid Social</td> 
  </tr> 
  <tr> 
   <td>Marketingkanal - Pfad</td> 
   <td>Paid Social.LinkedIn</td> 
  </tr> 
  <tr> 
   <td>Medium</td> 
   <td>"cpc"oder "Lead-Gen-Formular"</td> 
  </tr> 
  <tr> 
   <td>Referrer-Seite</td> 
   <td>www.linkedin.com/</td> 
  </tr> 
  <tr> 
   <td>Referrer Page - Roh</td> 
   <td>www.linkedin.com/</td> 
  </tr> 
  <tr> 
   <td>Suchbegriff</td> 
   <td>(leer)</td> 
  </tr> 
  <tr> 
   <td>Touchpoint-Typ</td> 
   <td>Webformular</td>
  </tr> 
  <tr> 
   <td>Touchpoint-Quelle</td>
   <td>LinkedIn</td>
  </tr> 
 </tbody> 
</table>

**&#42;** _Das Feld &quot;Anzeigenziel-URL&quot;wird nur für gesponserte Inhalte ausgefüllt. Für Lead Gen Forms sind keine Daten vorhanden._

<br>

## Kosten {#costs}

weil [!DNL Marketo Measure] verfügt über eine direkte Integration mit [!DNL LinkedIn], laden wir die aufgezeichneten Ausgaben für jede Kampagne und jeden Tag Creative herunter. Es ist nicht erforderlich, dass ein Kunde Berichte zu [!DNL LinkedIn] Ausgaben innerhalb der [!DNL Marketo Measure] nicht mehr verwenden.

Wie bei anderen Anzeigenintegrationen [!DNL Marketo Measure] hat eine Marketing-Kanalregel definiert, um alle [!DNL LinkedIn] Kampagnen, Kreativen und Kosten. Um die Regel zu verwenden, möchte der Kunde eine neue Zeile für seine gebührenpflichtige [!DNL LinkedIn] Anstrengungen. Es kann sich um einen neuen oder vorhandenen Kanal handeln. Verwenden Sie in der Spalte &quot;Referrer&quot;die Definition &quot;[[!DNL LinkedIn] Paid] [!DNL Marketo Measure] hat als jeden Touchpoint definiert, der über eine [!DNL Marketo Measure] -Tag.

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

Es wurden einige Verbesserungen an [!DNL Marketo Measure] Discover unterstützt die Berichterstellung von Lead Gen Forms.

**Paid Media Board**

Kachel &quot;Lead Gen Forms&quot;: Neue Kachel, die die Anzahl der LinkedIn-Formularausfüllungen enthält. Führen Sie einen Drilldown aus dieser Anzahl durch, um Aktivitäts-ID, Formular-Datum, Formular-Name und E-Mail-Adresse anzuzeigen.

**Interaktionspfad-Pinnwand**

Journey von Ereignissen: Enthält den Ereignistyp &quot;Aktivität&quot;und das Medium &quot;Lead-Gen-Formular&quot;für Formulare, die durch die Integration kommen. Die Drillthrough-Ansicht enthält Details zu Campaign, Creative und Formular.

## Häufig gestellte Fragen zu Sponsored Content {#sponsored-content-faq}

**Was ist eine dunkle Freigabe?**

Eine dunkle Freigabe ist ein Beitrag, bei dem er nie auf der Unternehmensseite veröffentlicht wird und sofort erstellt und direkt als Kreativ hinzugefügt wird. So [!DNL Marketo Measure]-erstellte Kreative erscheinen nicht oben auf der Seite eines Unternehmens und werden erneut beworben, dunkle Teilen werden verwendet, damit sie hinter den Kulissen starten können.

**Was macht Status? [!DNL Marketo Measure] tatsächlich taggen?**

Es gibt vier verschiedene Status auf einer [!DNL LinkedIn] Kampagne und Kreativ: Aktiv, Angehalten, Archiviert und Abgebrochen. Wir taggen nur aktive Kampagnen und Kreative. Beim Tagging anderer Status werden diese wieder auf &quot;Aktiv&quot;gesetzt. [!DNL Marketo Measure] markiert keine ausgesetzten, archivierten oder abgebrochenen Kampagnen oder kreativen Inhalte, setzt jedoch das Tagging fort, wenn sich der Status in &quot;Aktiv&quot;ändert.

**Was ist der Wert, der [!DNL Marketo Measure] verwendet zum Taggen?**

Am Ende der Ziel-URL [!DNL Marketo Measure] den Parameter hinzufügt `&_bl={creativeId}`, wobei `{creativeId}` ist die Creative ID aus LinkedIn. Mit der Creative-ID [!DNL Marketo Measure] kann auch die Kampagnen-ID bestimmen, da [!DNL LinkedIn] hat eine ziemlich einfache Anzeigenstruktur, da jede Kreativelement nur zu einer Kampagne gehören kann.

**Was passiert einmal mit meinem alten Kreativ? [!DNL Marketo Measure] erstellt eine neue Version davon?**

Wann [!DNL Marketo Measure] erstellt eine Freigabe neu und legt sie in einer neuen kreativen Komponente ab. Die alten Kreativelemente werden archiviert. Aus diesem Grund [!DNL Marketo Measure] werden keine archivierten Kampagnen oder kreativen Inhalte mit Tags versehen. Andernfalls würde es mit [!DNL Marketo Measure] zu versuchen, sie auf unbestimmte Zeit zu taggen.

**Warum stimmt die Ziel-URL der erstellten Anzeige nicht mit meiner ursprünglichen Anzeige überein?**

[!DNL Marketo Measure] muss die Tracking-Parameter zu einer aufgelösten URL hinzufügen, aber die in der API angezeigte URL kann möglicherweise eine gekürzte URL sein, ohne dass alle Parameter vorhanden sind. Um dieses Problem zu umgehen, [!DNL Marketo Measure] sucht nach gekürzten URLs, bevor er ein Hinzufügen neu erstellt, löst es auf und erstellt dann die neue Anzeige mit der aufgelösten URL und allen zugehörigen Parametern, wodurch [!DNL Marketo Measure] , um Tags hinzuzufügen.

**Markieren Sie alle meine Anzeigen? Ich sehe den Parameter bl nicht auf allen meinen Landingpages?**

Wir haben festgestellt, dass einige Marketingexperten einen Bild-Link in die Ziel-URL einfügen, die [!DNL Marketo Measure] kann nicht taggen, daher suchen wir innerhalb des Anzeigeninhalts nach der URL. Wenn [!DNL Marketo Measure] verfügt über die Berechtigung, gekürzte URLs mit Tags zu versehen. Wir erweitern die URL und das Tag, das jedoch aufgrund der Kopierstruktur von LinkedIn automatisch im Text gekürzt wird. Das Tag befindet sich in der verkürzten URL von LinkedIn, die im Feld Anzeigeninhalt des Touchpoints und nicht im Feld Landingpage - Roh angezeigt wird.

**Oh nein, jemand in meinem Team klonte versehentlich eine Aktie. Kann ich es anhalten?**

Keine Sorge. [!DNL Marketo Measure] sucht programmatisch nach nicht mehr eindeutigen Teilen, d. h. sie wurden seitdem in ein anderes Kreativ kopiert. Sobald diese Kopie erkannt wurde, [!DNL Marketo Measure] folgt dem üblichen Ablauf, um neue Anzeigen zu taggen und zu erstellen.

**Meine Anzeige stand noch vor der Überprüfung. Warum steht die Überprüfung nach [!DNL Marketo Measure] getaggt?**

LinkedIn erfordert, dass alle erstellten oder geänderten Anzeigen den normalen Sicherheitsprozess durchlaufen, bevor sie veröffentlicht werden. [!DNL Marketo Measure] versucht, die Anzeige so schnell wie möglich abzufangen, da sie alle 6 Stunden, jedoch mit [!DNL LinkedIn's] zusätzlichen Schritt hinzufügen, kann dies den Start um einige Stunden verzögern.

**Meine Anzeige enthält 2 URLs. Welche wird getaggt?**

Beide. Die [!DNL Marketo Measure] -Integration ermöglicht es uns, die Ziel-URL vom Clickthrough-Bild in der Anzeige zu taggen, aber auch die gekürzte URL in der Anzeigenbeschreibung automatisch zu aktualisieren.

![](assets/five.png)

**Ich habe meine [!DNL LinkedIn ads] -Konto. Warum nicht [!DNL Marketo Measure] Verknüpfungen taggen?**

Der verbundene [!DNL LinkedIn] Der Benutzer muss über einen ordnungsgemäßen Bearbeitungszugriff verfügen, d. h. er muss ein Kundenbetreuer, Campaign Manager oder Creative Manager sein.

**Woher weiß ich, ob mein Kreativ kopiert wird? Kann ich sehen, ob meine Kreativen dieselbe Freigabe verwenden?**

Die Freigabe-ID wird nicht in einer [!DNL LinkedIn] -Bericht erstellen, sodass es keine klare und naheliegende Möglichkeit gibt, nach Creative-to-Share-Zuordnungen zu suchen. Wenn Sie vermuten, dass es sich bei einem Kreativelement um eine Kopie handeln könnte, können Sie die Werbeanzeige in Ihrem [!DNL LinkedIn] Kampagnenverantwortlicher: Dadurch wird die Anzeige in einem neuen Tab geöffnet und Sie finden die Freigabe-ID in der URL.

![](assets/six.png)

## Häufig gestellte Fragen zu Lead Gen Forms {#lead-gen-forms-faq}

**Was kostet diese Verbesserung?**

Dieses Angebot ist bei allen gebührenpflichtigen [!DNL Marketo Measure] Abonnement.

**Ist die Integration rückwirkend?**

Ja, wir laden historische Anzeigenformularantworten aus LinkedIn herunter, obwohl wir auf das 90-Tage-Lookback-Fenster beschränkt sind. Die [!DNL Marketo Measure] und die LinkedIn-Integration aktiviert ist, werden die Touchpoints des Lead-Gen-Formulars durch [!DNL Marketo Measure].

Es gibt keine Option, ein bestimmtes Datum für den Download festzulegen. Sie können jedoch optional Touchpoint-Löschregeln festlegen, wenn Touchpoints vorhanden sind, die Sie unterdrücken müssen.

**Wird dies automatisch aktiviert, wenn ich bereits die [!DNL Marketo Measure] LinkedIn-Anzeigenintegration?**

Nein, wir werden nicht automatisch damit beginnen, sie für alle Kunden herunterzuladen, aber es ist ein sehr einfacher Wechsel, diese Funktion in den Einstellungen zu aktivieren.

**Sind Formulardaten verfügbar?**

Formulardaten sind verfügbar über [!DNL Marketo Measure] Entdecken Sie einschließlich Formular-ID und Formularname. Die Formulardetails sind noch nicht für die Touchpoint-Objekte im CRM verfügbar.

**Was geschieht mit jedem [!DNL LinkedIn] Leads, die bereits mit Marketo-Programmen oder CRM-Kampagnen synchronisiert wurden?**

Es wird empfohlen, alle [!DNL Marketo Measure] Regeln zum Generieren von Touchpoints aus diesen spezifischen Programmen oder Kampagnen, um Dopplungen zu vermeiden. Die LinkedIn-API hat eine Lookback-Beschränkung von 90 Tagen. Wenn Sie also Marketo- oder CRM-Regeln verwenden, wird empfohlen, das Enddatum für die Regel auf 90 Tage vor dem Datum festzulegen, an dem Sie die Integration in [!DNL Marketo Measure]. Ab diesem Zeitpunkt [!DNL Marketo Measure] können diese Leads mit größeren Einblicken und Details für Sie herunterladen.

**Ist automatisches Tagging oder Tracking erforderlich?**

Nein, dies unterscheidet sich von anderen [!DNL Marketo Measure] Integrationen. Anstatt die Landingpage zu ändern (da es keinen Klick durch die Landingpage gibt), laden wir nur die entsprechenden Informationen aus LinkedIn herunter und behandeln sie als Aktivitäten innerhalb von [!DNL Marketo Measure].
