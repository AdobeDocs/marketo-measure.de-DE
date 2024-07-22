---
unique-page-id: 35586080
description: LinkedIn-Integration - [!DNL Marketo Measure]
title: LinkedIn-Integration
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '2653'
ht-degree: 1%

---

# LinkedIn-Integration {#linkedin-integration}

## Überblick {#overview}

Die [!DNL Marketo Measure] -Integration mit LinkedIn besteht aus zwei Komponenten:

Gesponserte Inhalte: Durch die Integration von gesponserten Inhalten kann [!DNL Marketo Measure] Ziel-URLs für [!DNL LinkedIn] Anzeigen taggen. Dadurch kann [!DNL Marketo Measure] einem Benutzer letztendlich durch die gesamte Touchpoint-Journey folgen und die Aktivität wieder einer bestimmten [!DNL LinkedIn]-Kampagne und Creative zuordnen. Dies bietet Kunden Einblicke in den ROI ihrer [!DNL LinkedIn] -Aktivität.

Lead Gen Forms: Durch die Integration mit der Lead Gen Forms von LinkedIn erhält Marketo Measure Einblicke in Formulare, die über die LinkedIn-Plattform übermittelt wurden. Diese Formularausfüllungen werden mit Leads aus Ihrem CRM-System oder Ihrer [!DNL Marketo Engage]-Instanz abgeglichen, sodass sie für die Zuordnung infrage kommen. Einblicke in die Kampagnen, Kreativelemente und Formulare, die zur Erstellung der Formulare beigetragen haben, ermöglichen es Teams nun, ihre LinkedIn-Marketing- und Anzeigenausgaben weiter zu optimieren.

## Verfügbarkeit {#availability}

Für alle Benutzer verfügbar.

## Anforderungen {#requirements}

**Kampagnen-Manager-Rollen**

Damit Sie Daten zu Anzeigendaten und Anzeigen-Kosten von [!DNL Marketo Measure] herunterladen können, müssen Sie über eine der folgenden Rollen im Campaign Manager verfügen:

* Rechnungsadministrator
* Kundenbetreuer
* Kampagnen-Manager

Weitere Informationen: [Benutzerrollen und -funktionen in Campaign Manager](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Paid Media-Administratorrollen**

Damit [!DNL Marketo Measure] gesponserte Kreativinhalte erstellen/aktualisieren kann, müssen Sie über eine der folgenden Paid Media-Admin-Rollen verfügen:

* Sponsored Content Poster
* Lead Gen Forms Manager

Weitere Informationen: [LinkedIn-Seitenadministratorrollen](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Es gibt weitere [!DNL LinkedIn] Rollen, die wir für unsere Integration **nicht** benötigen. Diese Rollen werden oft mit den erforderlichen Rollen verwechselt. Beachten Sie daher, dass es einen Unterschied gibt!

**Seitenadministratorrollen**

Damit [!DNL Marketo Measure] Leads aus Lead-Generierungsformularen herunterladen/integrieren kann, müssen Sie über die folgende Seitenadministratorrolle verfügen:

* Super Admin

Weitere Informationen: [LinkedIn-Seitenadministratorrollen](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## LinkedIn-Anzeigentypen {#linkedin-ad-types}

[!DNL Marketo Measure] unterstützt Folgendes:

**Sponsored Content:** Sponsored Content ermöglicht es Ihnen, Inhalte für den [!DNL LinkedIn] -Feed von Mitgliedern bereitzustellen, die über diejenigen hinausgehen, die Ihrem Unternehmen folgen. Sponsored Content kann auf eine bestimmte Zielgruppe ausgerichtet werden und Werbetreibenden dabei helfen, [!DNL LinkedIn]-Mitglieder überall und immer dann zu erreichen, wenn sie auf der [!DNL LinkedIn] -Plattform auf Desktop-, Mobil- und Tablet-Geräten tätig sind. Sponsored Content mit Lead Gen Forms wird unterstützt.

Die von [!DNL Marketo Measure] unterstützten Arten von gesponserten Inhalts-Anzeigenformaten sind Einzelbildanzeigen und Videoanzeigen (über Lead Gen Forms). Aufgrund der Komplexität des Schemas unterstützen wir keine Karussellanzeigen.

[!DNL Marketo Measure] unterstützt keine gesponserten Nachrichten, Textanzeigen oder dynamischen Anzeigen.

![](assets/one.png)

>[!TIP]
>
>Für jede Ihrer Kampagnen/Ausgaben, die aus einer nicht gesponserten Inhaltsquelle stammen (z. B. Kampagnentyp &quot;Textanzeige&quot;oder &quot;Sponsored InMail&quot;), unterstützt [!DNL Marketo Measure] nicht _grundsätzlich das Tracking dieser Kampagnentypen._ Wenn Sie Ausgaben für Kampagnen wie diese zusammen mit Ihren Ausgaben für &quot;gesponserte Inhalte&quot;verfolgen möchten, sollten Sie unsere CSV für Marketingausgaben verwenden, um diese Ausgaben manuell zu protokollieren.

## Funktionsweise: gesponserte Inhalte {#how-it-works-sponsored-content}

>[!NOTE]
>
>Vor der ersten Verwendung muss diese Funktionseinstellung aktiviert werden, indem Sie zu &quot;[!DNL Marketo Measure] [!UICONTROL Einstellungen]&quot;> &quot;[!UICONTROL Integrationen]&quot;> &quot;[!UICONTROL Anzeigen]&quot;> &quot;[!UICONTROL LinkedIn Lead Gen Forms aktivieren]&quot;navigieren.

**[!DNL LinkedIn's]Eindeutige Anforderungen an das automatische Tagging**

[!DNL Marketo Measure] kann Ihnen dabei helfen, die Leistung Ihrer [!DNL LinkedIn]-Kampagne zu verfolgen, indem Sie Ihre Landingpages automatisch mit Tags versehen.

[!DNL Marketo Measure] sucht nach Kreativen mit einer eindeutigen LinkedIn-Freigabe und fügt am Ende einen Parameter `?_bl={creativeId}` hinzu.

**Kopieren von Teilen**

Mit dieser [!DNL Marketo Measure/LinkedIn] -Integration bitten wir Kunden, vorhandene Kreative nicht zu kopieren/zu klonen/zu duplizieren. Wenn &quot;Teilen&quot;-Klicks gefunden werden und erkannt werden, dass sie nur auf einem Kreativelement verwendet werden, kann [!DNL Marketo Measure] die Freigabe so taggen, wie es ist, ohne dass kreative Inhalte oder &quot;Teilen&quot;-Klicks neu erstellt werden müssen. Außerdem bleiben alle Anzeigen-Verläufe (Impressionen, Klicks, &quot;Teilen&quot;-Klicks) erhalten.

Sobald festgestellt wird, dass eine Freigabe für mehrere Kreative freigegeben ist, muss [!DNL Marketo Measure] den Prozess zum Anhalten, Kopieren und erneuten Taggen durchlaufen, um einen eindeutigen Satz zu erstellen. [!DNL Marketo Measure] hält Live-Kreativinhalte an und archiviert sie, löscht sie daher den Anzeigenverlauf einschließlich Impressionen, Klicks und Teilen-Klicks, um alles automatisch mit Tags zu versehen.

In Zukunft empfiehlt [!DNL Marketo Measure], keine [!DNL LinkedIn]-Freigaben zu duplizieren und alle kreativen Inhalte und &quot;Teilen&quot;-Klicks so eindeutig wie möglich zu halten, damit wir einfach unser Tracking hinzufügen können, ohne den Anzeigenverlauf löschen zu müssen.

**Reduzierte URLs**

Der Grund für den zusätzlichen Schritt besteht darin, dass LinkedIn zulässt, dass Ziel-URLs eine gekürzte URL sind (bit.ly, goog.le usw.), was bedeutet, dass [!DNL Marketo Measure] die lange, aufgelöste URL nicht sieht und [!DNL Marketo Measure] Tracking-Parameter zu einer aufgelösten URL hinzufügen muss. Um dieses Problem zu umgehen, sucht [!DNL Marketo Measure] vor der Neuerstellung einer Anzeige nach gekürzten URLs, erweitert die URL, erstellt dann die neue Anzeige mit der aufgelösten URL und allen zugehörigen Parametern, sodass [!DNL Marketo Measure] Tags hinzufügen kann. Durch die Erstellung einer neuen Anzeige wird der Anzeigenverlauf (Impressionen, Klicks, Teilen-Klicks) gelöscht. Daher ist die Berechtigung zum Taggen gekürzter URLs erforderlich.

Wenn Sie häufig gekürzte URLs verwenden, kann dies schwerwiegende Auswirkungen auf Ihre kreativen Inhalte haben. Wir empfehlen, keine verkürzten URLs mehr zu verwenden, damit [!DNL Marketo Measure] die Landingpages mit Tags versehen kann, ohne neue Anzeigen erstellen und den Anzeigenverlauf löschen zu müssen.

**Der Prozess**

Fangen wir mit einigen Beispielen an. Angenommen, wir haben...

Kreativ A : Share 123\
Kreativ B : Share 234\
Creative C: Share 234\
Creative D : Share 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] durchsucht zunächst alle Kampagnen, Kreativen und &quot;Teilen&quot;-Klicks mit dem Status &quot;Aktiv&quot;. [!DNL Marketo Measure] markiert keine ausgesetzten, archivierten oder abgebrochenen Anzeigen. Wenn eine Anzeige angehalten und dann auf [!UICONTROL aktiv] gesetzt wurde, wird sie mit einem Tag versehen, sobald sie wieder aktiv ist. Wenn wir eine eindeutige Freigabe finden, d. h. sie nicht für mehrere Kreative oder Kampagnen verwendet wird (z. B. Creative A: Share 123), fügt [!DNL Marketo Measure] unseren benutzerdefinierten Parameter `>> ?_bl={creativeId}` zur Freigabe-URL hinzu.

`2)` Wenn die Freigabe nun freigegeben wurde und ihre Eindeutigkeit verloren hat (z. B. Creative B : Share 234 and Creative C : Share 234 and Creative D : Share 234), hält [!DNL Marketo Measure] alle ähnlichen Kreative an und archiviert sie (d. h. Creative B, Creative C und Creative D).

`3)` [!DNL Marketo Measure] erstellt 3 neue Kreative, Creative E, Creative F und Creative G, die den archivierten Inhalt von Creative B kopieren.

`4)` [!DNL Marketo Measure] erstellt außerdem 3 neue &quot;Teilen&quot;-Klicks, 345 teilen, 456 teilen und 567 teilen, die den Inhalt von Share 234 kopieren, mit der Ausnahme, dass sie über ein eigenes eindeutiges `?_bl`-Tagging verfügen.

`5)` [!DNL Marketo Measure] muss regelmäßig überprüfen, ob die &quot;Teilen&quot;-Klicks nicht freigegeben werden, und wenn dies der Fall ist, starten wir den Prozess in Schritt 2 weiter oben.

>[!NOTE]
>
>Wenn Sie dies implementieren, verlieren unsere Kunden den Anzeigenverlauf von Creative B : Share 234, Creative C : Share 234 und Creative D : Share 234, da es jetzt mit Creative E neu erstellt wird: Share 345, Share F : Share 456 und Creative G : Share 567 .

![](assets/three.png)

## Funktionsweise: Lead Gen Forms {#how-it-works-lead-gen-forms}

**[!DNL LinkedIn's]Eindeutige Anforderungen an das automatische Tagging**

[!DNL Marketo Measure] kann Ihnen dabei helfen, die Leistung Ihrer [!DNL LinkedIn]-Kampagne zu verfolgen, indem Sie Ihre Landingpages automatisch mit Tags versehen.

[!DNL Marketo Measure] sucht nach Kreativen mit einer eindeutigen LinkedIn-Freigabe und fügt am Ende einen Parameter `?_bl={creativeId}` hinzu.

**Der Prozess**

Über [!DNL LinkedIn's] Ad Form API und Ad Form Response API können wir Formulardaten für ein Anzeigenkonto erfassen und die E-Mail-Adresse mit einem Lead aus dem CRM oder Marketo verknüpfen.

LinkedIn-Formulare können mehrere E-Mail-Adressen enthalten. Wenn wir Formularantworten herunterladen, suchen wir nach E-Mail-Adressen mit der folgenden Priorität: Arbeits-E-Mail, E-Mail-Adresse (primäres Formularfeld) oder benutzerdefinierten Feldern mit einem gültigen E-Mail-Wert.

Unabhängig vom Status &quot;Kampagne&quot;oder &quot;Kreativ&quot;führen alle Formularantworten zu einem Touchpoint. [!DNL Marketo Measure] hat eine Lookback-Beschränkung von 90 Tagen, sodass [!DNL Marketo Measure] nicht auf Formularantworten zugreifen kann, die älter als 90 Tage sind. Je länger die Integration von [!DNL Marketo Measure] und [!DNL LinkedIn] aktiviert ist, desto mehr Touchpoints des Lead Gen-Formulars werden über [!DNL Marketo Measure] sichtbar.

>[!NOTE]
>
>LinkedIn-Kosten werden weiterhin als Teil von gesponserten Inhaltskampagnen heruntergeladen.

**Tracking von Lead Gen Forms in CRM oder Marketo**

Vor der Integration von [!DNL Marketo Measure] und LinkedIn Lead Gen Forms war es gängige Praxis, dass Kunden ihre Formularübermittlungen an ein Marketo-Programm und/oder eine CRM-Kampagne senden, um die Formulare zu verfolgen und die Attribution für diese Aktivitäten zu erhalten. Sobald die Einstellung &quot;Lead Gen Forms&quot;aktiviert ist, möchten wir sicherstellen, dass diese Formularübermittlungen nicht doppelt gezählt werden. Überprüfen Sie Folgendes:

* Das Feld &quot;Käufer-Touchpoints aktivieren&quot;im CRM-Objekt ist auf &quot;Keine&quot;oder &quot;Alle Campaign-Mitglieder ausschließen&quot;gesetzt
* Alle zugehörigen Marketo-Programm- oder Marketo-Aktivitätsregeln aktualisieren
* Alle zugehörigen CRM-Kampagnenregeln aktualisieren

>[!NOTE]
>
>Die LinkedIn-API hat eine Lookback-Beschränkung von 90 Tagen. Wenn Sie Marketo- oder CRM-Regeln verwenden, wird daher empfohlen, das Enddatum für die Regel auf 90 Tage vor dem Datum festzulegen, an dem Sie die Integration in [!DNL Marketo Measure] aktiviert haben.

## Touchpoint-Details ansehen {#touchpoint-details}

Nachdem [!DNL Marketo Measure] Ihre Landingpage erfolgreich mit dem LinkedIn-Kreativ gekennzeichnet hat, können Sie die aufgelösten Anzeigendaten auf dem Touchpoint anzeigen. Hier finden Sie die Zuordnung von Datenwerten, die Sie erwarten sollten:

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

**&#42;** _Das Feld &quot;Anzeigenziel-URL&quot;wird nur für gesponserte Inhalte ausgefüllt. Sie wird nicht für Lead Gen Forms ausgefüllt._

<br>

## Kosten {#costs}

Da [!DNL Marketo Measure] eine direkte Integration mit [!DNL LinkedIn] aufweist, laden wir die aufgezeichneten Ausgaben für jede Kampagne und jeden Tag für jeden Kreativ herunter. Es ist nicht mehr erforderlich, dass ein Kunde über [!DNL LinkedIn] Ausgaben innerhalb der [!DNL Marketo Measure] -Anwendung berichtet.

Wie bei anderen Anzeigenintegrationen hat [!DNL Marketo Measure] eine Marketing-Kanalregel definiert, um alle [!DNL LinkedIn] -Kampagnen, Kreativinhalte und Kosten zu platzieren. Um die Regel zu verwenden, möchte der Kunde eine neue Zeile für seine gebührenpflichtigen [!DNL LinkedIn] Bemühungen einfügen. Es kann sich um einen neuen oder vorhandenen Kanal handeln. Verwenden Sie in der Spalte &quot;Referrer&quot;die Definition &quot;[[!DNL LinkedIn] bezahlt]&quot;, die [!DNL Marketo Measure] als Touchpoint mit dem Tag [!DNL Marketo Measure] definiert hat.

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

Es wurden einige Verbesserungen an [!DNL Marketo Measure] Discover vorgenommen, um Lead Gen Forms Reporting zu unterstützen.

**Paid-Media-Pinnwand**

Kachel &quot;Lead Gen Forms&quot;: Neue Kachel, die die Anzahl der LinkedIn-Formularausfüllungen enthält. Führen Sie einen Drilldown aus dieser Anzahl durch, um Aktivitäts-ID, Formular-Datum, Formular-Name und E-Mail-Adresse anzuzeigen.

**Einsatzpfad-Pinnwand**

Journey von Ereignissen: Enthält den Ereignistyp &quot;Aktivität&quot;und das Medium &quot;Lead-Gen-Formular&quot;für Formulare, die durch die Integration kommen. Die Drillthrough-Ansicht enthält Details zu Campaign, Creative und Formular.

## Häufig gestellte Fragen zu Sponsored Content {#sponsored-content-faq}

**Was ist eine dunkle Freigabe?**

Eine dunkle Freigabe ist ein Beitrag, bei dem er nie auf der Unternehmensseite veröffentlicht wird und sofort erstellt und direkt als Kreativ hinzugefügt wird. Damit [!DNL Marketo Measure]-erstellte Kreative nicht oben auf der Seite eines Unternehmens erscheinen und wieder beworben werden, werden dunkle Freigaben verwendet, damit sie hinter den Kulissen starten können.

**Welche Status taggt [!DNL Marketo Measure] tatsächlich?**

Es gibt vier verschiedene Status für eine [!DNL LinkedIn]-Kampagne und eine kreative Kampagne: Aktiv, Angehalten, Archiviert und Abgebrochen. Wir taggen nur aktive Kampagnen und Kreative. Beim Tagging anderer Status werden diese wieder auf &quot;Aktiv&quot;gesetzt. [!DNL Marketo Measure] taggt keine angehaltenen, archivierten oder abgebrochenen Kampagnen oder kreativen Inhalte, setzt jedoch das Tagging fort, wenn sich der Status in &quot;Aktiv&quot;ändert.

**Welchen Wert verwendet [!DNL Marketo Measure] für das Tag**?

Am Ende der Ziel-URL fügt [!DNL Marketo Measure] den Parameter `&_bl={creativeId}` hinzu, wobei `{creativeId}` die Creative-ID aus LinkedIn ist. Mit der Creative-ID kann [!DNL Marketo Measure] auch die Kampagnen-ID bestimmen, da [!DNL LinkedIn] eine ziemlich einfache Anzeigenstruktur aufweist, da jede Kreativelement-Kampagne nur zu einer Kampagne gehören kann.

**Was passiert mit meinem alten Kreativ, wenn [!DNL Marketo Measure] eine neue Version erstellt?**

Wenn [!DNL Marketo Measure] eine Freigabe neu erstellt und in einem neuen Kreativ platziert, wird der alte Kreativ archiviert. Aus diesem Grund wird [!DNL Marketo Measure] auch keine archivierten Kampagnen oder Kreativinhalte taggen - andernfalls würde [!DNL Marketo Measure] versuchen, sie auf unbestimmte Zeit zu taggen.

**Warum stimmt die Ziel-URL der erstellten Anzeige nicht mit meiner ursprünglichen Anzeige überein?**

[!DNL Marketo Measure] muss die Tracking-Parameter zu einer aufgelösten URL hinzufügen, aber die in der API angezeigte URL kann möglicherweise eine gekürzte URL sein, ohne dass alle Parameter vorhanden sind. Um dieses Problem zu umgehen, sucht [!DNL Marketo Measure] vor der Neuerstellung und dem Hinzufügen nach verkürzten URLs, löst sie aus, erstellt dann die neue Anzeige mit der aufgelösten URL und allen zugehörigen Parametern, sodass [!DNL Marketo Measure] Tags hinzufügen kann.

**Taggen Sie alle meine Anzeigen? Ich kann den Parameter bl nicht auf allen meinen Landingpages sehen?**

Wir haben festgestellt, dass einige Marketing-Experten einen Bild-Link in die Ziel-URL einfügen, die [!DNL Marketo Measure] nicht taggen kann. Daher suchen wir innerhalb des Anzeigeninhalts nach der URL. Wenn [!DNL Marketo Measure] berechtigt ist, gekürzte URLs mit Tags zu versehen, erweitern wir die URL und das Tag, die jedoch aufgrund der Kopierstruktur von LinkedIn automatisch im Text gekürzt werden. Das Tag befindet sich in der verkürzten URL von LinkedIn, die im Feld Anzeigeninhalt des Touchpoints und nicht im Feld Landingpage - Roh angezeigt wird.

**Nein, jemand in meinem Team klonte versehentlich eine Aktie. Kann ich es anhalten?**

Keine Sorge. [!DNL Marketo Measure] sucht programmgesteuert nach nicht mehr eindeutigen Teilen, d. h., sie wurde seitdem in eine andere Kreative kopiert. Sobald diese Kopie erkannt wurde, folgt [!DNL Marketo Measure] dem üblichen Fluss, um neue Anzeigen zu taggen und zu erstellen.

**Meine Anzeige stand vor der Überprüfung. Warum steht eine erneute Überprüfung aus, nachdem [!DNL Marketo Measure] sie mit Tags versehen hat?**

LinkedIn erfordert, dass alle erstellten oder geänderten Anzeigen den normalen Sicherheitsprozess durchlaufen, bevor sie veröffentlicht werden. [!DNL Marketo Measure] versucht, die Anzeige so schnell wie möglich abzufangen, da alle 6 Stunden nach neuen Anzeigen gesucht wird, aber mit dem zusätzlichen Schritt [!DNL LinkedIn's] der Start um einige Stunden verzögert werden kann.

**Meine Anzeige enthält zwei URLs. Welche wird getaggt?**

Beide. Durch die Integration von [!DNL Marketo Measure] können wir die Ziel-URL vom Clickthrough-Bild in der Anzeige mit Tags versehen, aber auch die gekürzte URL in der Anzeigenbeschreibung automatisch aktualisieren.

![](assets/five.png)

**Ich habe mein [!DNL LinkedIn ads]-Konto verbunden. Warum werden meine Links nicht mit [!DNL Marketo Measure] getaggt?**

Der verbundene Benutzer [!DNL LinkedIn] muss über einen ordnungsgemäßen Bearbeitungszugriff verfügen, d. h. der Benutzer muss ein Kundenbetreuer, ein Kampagnen-Manager oder Creative Manager sein.

**Woher weiß ich, ob mein kreatives Element kopiert wird? Kann ich sehen, ob meine Kreativen dieselbe Freigabe verwenden?**

Die Freigabe-ID wird in einem [!DNL LinkedIn] -Bericht nicht angegeben. Daher gibt es keine klare und naheliegende Möglichkeit, nach Zuordnungen zu kreativen Assets zu suchen. Wenn Sie vermuten, dass ein Kreativelement eine Kopie sein könnte, können Sie die Anzeige manuell überprüfen, indem Sie sie in Ihrem [!DNL LinkedIn] Campaign Manager öffnen. Dadurch wird die Anzeige in einer neuen Registerkarte geöffnet und Sie können die Freigabe-ID in der URL finden.

![](assets/six.png)

## Häufig gestellte Fragen zu Lead Gen Forms {#lead-gen-forms-faq}

**Was kostet diese Verbesserung?**

Dieses Angebot ist in jedem zahlungspflichtigen [!DNL Marketo Measure]-Abonnement enthalten.

**Ist die Integration rückwirkend?**

Ja, wir laden historische Anzeigenformularantworten aus LinkedIn herunter, obwohl wir auf das 90-Tage-Lookback-Fenster beschränkt sind. Je länger die Integration von [!DNL Marketo Measure] und LinkedIn aktiviert ist, desto mehr Touchpoints des Lead-Gen-Formulars werden über [!DNL Marketo Measure] angezeigt.

Es gibt keine Option, ein bestimmtes Datum für den Download festzulegen. Sie können jedoch optional Touchpoint-Löschregeln festlegen, wenn Touchpoints vorhanden sind, die Sie unterdrücken müssen.

**Wird dies automatisch aktiviert, wenn ich bereits die [!DNL Marketo Measure] LinkedIn-Anzeigenintegration verwende?**

Nein, wir werden nicht automatisch damit beginnen, sie für alle Kunden herunterzuladen, aber es ist ein sehr einfacher Wechsel, diese Funktion in den Einstellungen zu aktivieren.

**Sind Formulardaten verfügbar?**

Formulardaten sind über [!DNL Marketo Measure] Discover verfügbar, einschließlich Formular-ID und Formularname. Die Formulardetails sind noch nicht für die Touchpoint-Objekte im CRM verfügbar.

**Was passiert mit [!DNL LinkedIn] Leads, die zuvor mit Marketo-Programmen oder CRM-Kampagnen synchronisiert wurden?**

Es wird empfohlen, alle [!DNL Marketo Measure] -Regeln anzupassen, um Touchpoints aus diesen spezifischen Programmen oder Kampagnen zu generieren, um Dopplungen zu vermeiden. Die LinkedIn-API hat eine Lookback-Beschränkung von 90 Tagen. Wenn Sie Marketo- oder CRM-Regeln verwenden, wird daher empfohlen, das Enddatum für die Regel auf 90 Tage vor dem Datum festzulegen, an dem Sie die Integration in [!DNL Marketo Measure] aktiviert haben. Ab diesem Zeitpunkt kann [!DNL Marketo Measure] diese Leads mit besseren Einblicken und Details für Sie herunterladen.

**Ist automatisches Tagging oder Tracking beteiligt?**

Nein, dies unterscheidet sich von anderen [!DNL Marketo Measure] -Integrationen. Anstatt die Landingpage zu ändern (da es keinen Klick durch die Landingpage gibt), laden wir nur die entsprechenden Informationen aus LinkedIn herunter und behandeln sie als Aktivitäten innerhalb von [!DNL Marketo Measure].
