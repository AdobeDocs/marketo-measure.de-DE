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

Die [!DNL Marketo Measure] Integration mit LinkedIn besteht aus zwei Teilen:

Gesponserte Inhalte: Die Integration gesponserter Inhalte ermöglicht es [!DNL Marketo Measure], Ziel-URLs in [!DNL LinkedIn]-Anzeigen zu taggen, was es [!DNL Marketo Measure] letztendlich ermöglicht, einen Benutzer durch die gesamte Touchpoint-Journey zu verfolgen und die Aktivität wieder den spezifischen [!DNL LinkedIn] Campaign und Creative zuzuordnen. Dadurch erhalten Kundinnen und Kunden Einblicke in den ROI ihrer [!DNL LinkedIn].

Lead Gen-Forms: Durch die Integration mit der Lead Gen-Forms von LinkedIn erhält Marketo Measure Einblick in Formulare, die über die LinkedIn-Plattform gesendet wurden. Diese Formularausfüllungen werden mit Leads aus Ihrer CRM- oder [!DNL Marketo Engage]-Instanz abgeglichen, sodass sie für die Attribution infrage kommen. Mit Einblicken in Campaign, Creative und Form, die beim Generieren der Formulare geholfen haben, können Teams ihr LinkedIn-Marketing und ihre Werbeausgaben weiter optimieren.

## Verfügbarkeit {#availability}

Verfügbar für alle Benutzer.

## Anforderungen {#requirements}

**Campaign Manager-Rollen**

Damit [!DNL Marketo Measure] Kostendaten für Anzeigen und Anzeigen herunterladen können, müssen Sie im Campaign Manager über eine der folgenden Rollen verfügen:

* Abrechnungs-Administrator
* Kundenbetreuer
* Kampagnen-Manager

Weitere Informationen: [Benutzerrollen und -funktionen in Campaign Manager](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Paid Media-Administratorrollen**

Damit [!DNL Marketo Measure] gesponserte Kreative erstellen/aktualisieren können, müssen Sie über eine der folgenden Paid-Media-Administratorrollen verfügen:

* Poster mit gesponserten Inhalten
* Lead Gen Forms Manager

Weitere Informationen: [LinkedIn-Seitenadministratorrollen](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Es gibt andere [!DNL LinkedIn] Rollen, die wir **für** Integration benötigen. Diese Rollen werden oft mit den erforderlichen Rollen verwechselt, also beachten Sie, dass es einen Unterschied gibt!

**Seiten-Admin-Rollen**

Damit [!DNL Marketo Measure] Leads aus Lead-Gen-Formularen herunterladen/integrieren können, müssen Sie über die folgende Seitenadministratorrolle verfügen:

* Superadmin

Weitere Informationen: [LinkedIn-Seitenadministratorrollen](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## LinkedIn-Anzeigentypen {#linkedin-ad-types}

[!DNL Marketo Measure] werden Folgendes unterstützen:

**Gesponserte Inhalte:** Gesponserte Inhalte ermöglichen es Ihnen, Inhalte für den [!DNL LinkedIn] Feed von Mitgliedern bereitzustellen, die über diejenigen hinausgehen, die Ihrem Unternehmen folgen. Gesponserte Inhalte können auf eine bestimmte Zielgruppe ausgerichtet werden und können Advertisern dabei helfen, [!DNL LinkedIn] Mitglieder zu erreichen, wo und wann immer sie auf der [!DNL LinkedIn]-Plattform über Desktop, Mobilgeräte und Tablet interagieren. Gesponserte Inhalte mit Lead Gen Forms werden unterstützt.

Die von [!DNL Marketo Measure] unterstützten Arten von gesponserten Inhalts-Anzeigenformaten sind Einzelbild-Anzeigen und Videoanzeigen (über Lead Gen Forms). Aufgrund der Komplexität des Schemas unterstützen wir keine Karussellanzeigen.

[!DNL Marketo Measure] unterstützt keine gesponserten Nachrichten, Textanzeigen oder dynamischen Anzeigen.

![](assets/one.png)

>[!TIP]
>
>Für alle Kampagnen/Ausgaben, die aus einer nicht gesponserten Inhaltsquelle stammen (z. B. Kampagnentyp „Textanzeige“ oder „Gesponsert inMail„), unterstützt [!DNL Marketo Measure] von _aus_ Tracking dieser Kampagnentypen. Wenn Sie die Ausgaben für Kampagnen wie diese zusammen mit Ihren Ausgaben für „gesponserte Inhalte“ verfolgen möchten, stellen Sie sicher, dass Sie unsere CSV-Datei mit den Marketingausgaben verwenden, um diese Ausgaben manuell zu protokollieren.

## Funktionsweise: Gesponserte Inhalte {#how-it-works-sponsored-content}

>[!NOTE]
>
>Vor der ersten Verwendung muss diese Funktionseinstellung aktiviert werden, indem Sie zu [!DNL Marketo Measure] [!UICONTROL Einstellungen] > [!UICONTROL Integrationen] > [!UICONTROL Anzeigen] > [!UICONTROL LinkedIn Lead Gen Forms aktivieren].

**[!DNL LinkedIn's]eindeutige Anforderungen an das automatische Tagging**

[!DNL Marketo Measure] können die Leistung Ihrer [!DNL LinkedIn]-Kampagnen verfolgen, indem Sie Ihre Landingpages automatisch taggen.

[!DNL Marketo Measure] werden nach Kreativen mit einer eindeutigen LinkedIn-Freigabe suchen und am Ende einen `?_bl={creativeId}` hinzufügen.

**Kopieren von Freigaben**

Bei dieser [!DNL Marketo Measure/LinkedIn]-Integration bitten wir Kunden, vorhandene Kreative nicht zu kopieren/klonen/duplizieren. Wenn Freigaben gefunden und nur für einen Kreativen verwendet werden, können [!DNL Marketo Measure] die Freigabe wie besehen taggen, ohne dass Kreative oder Freigaben neu erstellt werden müssen. Der gesamte Werbeverlauf (Impressionen, Klicks, Freigaben) bleibt erhalten.

Sobald festgestellt wird, dass eine Freigabe für mehrere Kreative freigegeben ist, müssen [!DNL Marketo Measure] einen Prozess zum Anhalten, Kopieren und erneuten Taggen durchlaufen, um einen eindeutigen Satz zu erstellen. [!DNL Marketo Measure] pausiert und archiviert Live-Kreative und löscht daher den Anzeigenverlauf einschließlich Impressionen, Klicks und Social Shares, um das automatische Tagging durchführen zu können.

Für die Zukunft empfiehlt [!DNL Marketo Measure], keine [!DNL LinkedIn]-Freigaben zu duplizieren und alle Kreativen und Freigaben so einzigartig wie möglich zu halten, damit wir einfach unser Tracking hinzufügen können, ohne den Anzeigenverlauf löschen zu müssen.

**gekürzte URLs**

Der Grund für diesen zusätzlichen Schritt besteht darin, dass LinkedIn es ermöglicht, Ziel-URLs als gekürzte URLs zu verwenden (bit.ly, goog.le usw.), was bedeutet, dass [!DNL Marketo Measure] die lange, aufgelöste URL nicht sieht und [!DNL Marketo Measure] Tracking-Parameter zu einer aufgelösten URL hinzufügen muss. Um dieses Problem zu umgehen, sucht [!DNL Marketo Measure] vor der erneuten Erstellung einer Anzeige nach gekürzten URLs, erweitert die URL und erstellt dann die neue Anzeige mit der aufgelösten URL und allen ihren Parametern, sodass [!DNL Marketo Measure] Tags hinzufügen können. Durch das Erstellen einer neuen Anzeige wird der Werbeverlauf (Impressionen, Klicks, Freigaben) gelöscht. Daher ist die Berechtigung zum Taggen gekürzter URLs erforderlich.

Wenn Sie stark gekürzte URLs verwenden, kann dies erhebliche Auswirkungen auf Ihre Kreativen haben. Es wird empfohlen, keine gekürzten URLs mehr zu verwenden, damit [!DNL Marketo Measure] die Landingpages taggen können, ohne neue Anzeigen erstellen und den Werbeverlauf löschen zu müssen.

**Der Prozess**

Beginnen wir mit einigen Beispielen. Nehmen wir an, wir haben….

Creative A : Freigabe 123\
Creative B : Freigabe 234\
Creative C : Freigabe 234\
Creative D : Freigabe 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] durchsucht zunächst alle Kampagnen, Kreativen und Freigaben mit dem Status „Aktiv“. [!DNL Marketo Measure] werden angehaltene, archivierte oder abgebrochene Anzeigen nicht mit Tags versehen. Wenn eine Anzeige angehalten und auf [!UICONTROL aktiv] gesetzt wurde, werden wir sie mit einem Tag versehen, sobald sie wieder aktiv ist. Wenn wir eine eindeutige Freigabe finden, d. h. sie wird nicht in mehreren Kreativen oder Kampagnen verwendet (z. B. Creative A : Freigabe 123), fügen [!DNL Marketo Measure] unseren benutzerdefinierten `>> ?_bl={creativeId}` zur Freigabe-URL hinzu.

`2)` Wenn die Freigabe jetzt freigegeben wurde und ihre Einzigartigkeit verloren gegangen ist (z. B. Creative B : Freigabe 234 und Creative C : Freigabe 234 und Creative D : Freigabe 234), hält [!DNL Marketo Measure] alle ähnlichen Kreativen (d. h. Creative B, Creative C und Creative D) an und archiviert sie.

`3)` [!DNL Marketo Measure] erstellt 3 neue Kreative, Creative E, Creative F und Creative G, die den Inhalt von Creative B kopieren, das archiviert wird.

`4)` [!DNL Marketo Measure] erstellt auch 3 neue Freigaben, nämlich Freigabe 345, Freigabe 456 und Freigabe 567, mit denen der Inhalt von Freigabe 234 kopiert wird, es sei denn, sie verfügt über ein eigenes eindeutiges `?_bl`-Tagging.

`5)` [!DNL Marketo Measure] müssen regelmäßig überprüfen, ob Freigaben nicht freigegeben werden. Falls dies der Fall ist, werden wir den Prozess in Schritt 2 oben neu starten.

>[!NOTE]
>
>Wenn Sie dies implementieren, verlieren unsere Kunden den Werbeverlauf von Creative B : Freigabe 234, Creative C : Freigabe 234 und Creative D : Freigabe 234, da es jetzt mit Creative E neu erstellt wird: Freigabe 345, Freigabe F : Freigabe 456 und Creative G : Freigabe 567 .

![](assets/three.png)

## Funktionsweise: Lead Gen Forms {#how-it-works-lead-gen-forms}

**[!DNL LinkedIn's]eindeutige Anforderungen an das automatische Tagging**

[!DNL Marketo Measure] können die Leistung Ihrer [!DNL LinkedIn]-Kampagnen verfolgen, indem Sie Ihre Landingpages automatisch taggen.

[!DNL Marketo Measure] werden nach Kreativen mit einer eindeutigen LinkedIn-Freigabe suchen und am Ende einen `?_bl={creativeId}` hinzufügen.

**Der Prozess**

Über [!DNL LinkedIn's] Anzeigenformular-API und die Antwort-API für Anzeigenformulare können wir Formulardaten für ein Anzeigenkonto erfassen und die E-Mail-Adresse mit einem Lead aus dem CRM oder Marketo verknüpfen.

LinkedIn-Formulare können mehrere E-Mail-Adressen enthalten. Beim Herunterladen von Formularantworten suchen wir nach E-Mail-Adressen mit der folgenden Priorität: geschäftliche E-Mail-Adresse, E-Mail-Adresse (Primärformularfeld) oder benutzerdefinierte Felder mit einem gültigen E-Mail-Wert.

Unabhängig vom Status Kampagne oder Creative führen alle Formularantworten zu einem Touchpoint. [!DNL Marketo Measure] verfügt über eine 90-tägige Lookback-Einschränkung. Daher kann [!DNL Marketo Measure] nicht auf Formularantworten zugreifen, die älter als 90 Tage sind. Je länger jedoch die [!DNL Marketo Measure]- und [!DNL LinkedIn]-Integration aktiviert ist, desto mehr Touchpoints für Lead-Gen-Formulare werden über [!DNL Marketo Measure] angezeigt.

>[!NOTE]
>
>LinkedIn-Kosten werden weiterhin im Rahmen von gesponserten Inhaltskampagnen heruntergeladen.

**Tracking von Lead Gen Forms in CRM oder Marketo**

Bevor die Integration von [!DNL Marketo Measure] und LinkedIn Lead Gen Forms existierte, war es gängige Praxis, dass Kundinnen und Kunden ihre Formularübermittlungen an ein Marketo-Programm und/oder eine CRM-Kampagne pushen, um die Formulare zu verfolgen und eine Attribution für diese Aktivitäten zu erhalten. Sobald die Einstellung für die Lead-Gen-Forms aktiviert ist, möchten wir sicherstellen, dass diese Formularübermittlungen nicht doppelt gezählt werden. Überprüfen Sie Folgendes:

* Das Feld „Käufer-Touchpoints aktivieren“ im CRM-Objekt ist auf „Keine“ oder „Alle Kampagnenmitglieder ausschließen“ festgelegt
* Aktualisieren aller zugehörigen Aktivitätsregeln für Marketo-Programme oder Marketo
* Aktualisieren aller zugehörigen CRM-Kampagnenregeln

>[!NOTE]
>
>Die LinkedIn-API unterliegt einer 90-tägigen Lookback-Beschränkung. Wenn Sie also Marketo- oder CRM-Regeln verwenden, wird empfohlen, das Enddatum für die Regel auf 90 Tage vor dem Datum festzulegen, an dem Sie die Integration in [!DNL Marketo Measure] aktiviert haben.

## Touchpoint-Details ansehen {#touchpoint-details}

Nachdem [!DNL Marketo Measure] Ihre Landingpage erfolgreich mit einem Tag auf dem LinkedIn-Kreativ versehen hat, können Sie die aufgelösten Anzeigendaten auf dem Touchpoint anzeigen. Hier finden Sie die Zuordnung der Datenwerte, die Sie erwarten sollten:

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
   <td>Werbe-ID</td>
   <td>84186224</td>
  </tr> 
  <tr> 
   <td>Anzeigeninhalt</td>
   <td>copy-1-image-2-man 95 % der #B2B Marketer halten die Strategie zur Nachfrageerstellung für erfolgreich. Weitere Informationen: [!DNL https]://lnkd.in/jgdi50vKrgv</td>
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
   <td>Anzeigenkampagnen-ID</td>
   <td>138949954</td>
  </tr> 
  <tr> 
   <td>Name der Anzeigenkampagne</td>
   <td>SU - COM Accounts - Demand Skills</td>
  </tr> 
  <tr> 
   <td>Werbeziel-URL <b>*</b></td>
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
   <td>Übereinstimmungstyp des Keywords</td> 
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
   <td>Marketing-Kanal - Pfad</td> 
   <td>Paid.social.LinkedIn</td> 
  </tr> 
  <tr> 
   <td>Medium</td> 
   <td>„CPC“ oder „Lead Gen-Formular“</td> 
  </tr> 
  <tr> 
   <td>Referrer-Seite</td> 
   <td>www.linkedin.com/</td> 
  </tr> 
  <tr> 
   <td>Empfehlungsseite - Roh</td> 
   <td>www.linkedin.com/</td> 
  </tr> 
  <tr> 
   <td>Suchausdruck</td> 
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

**&#42;** Feld _Anzeigenziel-URL“ wird nur für gesponserte Inhalte ausgefüllt. Es wird nicht für Lead Gen Forms ausgefüllt._

<br>

## Kosten {#costs}

Da [!DNL Marketo Measure] eine direkte Integration mit [!DNL LinkedIn] aufweist, laden wir die aufgezeichneten Ausgaben für jede Campaign und Creative jeden Tag herunter. Es ist nicht mehr erforderlich, dass ein Kunde über [!DNL LinkedIn] Ausgaben innerhalb des [!DNL Marketo Measure]-Programms berichtet.

Wie bei anderen Anzeigenintegrationen hat [!DNL Marketo Measure] eine Marketing-Kanal-Regel definiert, um alle [!DNL LinkedIn], Kreativen und Kosten zu platzieren. Um die Regel zu verwenden, sollte eine neue Zeile für die Paid-[!DNL LinkedIn]-Aktivitäten des Kunden eingefügt werden. Es kann sich um einen neuen oder vorhandenen Kanal handeln. Verwenden Sie in der Spalte „Referrer“ die Definition &quot;[[!DNL LinkedIn] Paid]&quot;, die [!DNL Marketo Measure] als Touchpoint mit einem [!DNL Marketo Measure]-Tag definiert hat.

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

An [!DNL Marketo Measure] Discover wurden einige Verbesserungen vorgenommen, um das Reporting über Lead-Gen-Forms zu unterstützen.

**Paid Media-Board**

Lead Gen Forms-Kachel: Neue Kachel, die die Anzahl der LinkedIn-Formularausfüllungen enthält. Bei einer Drill-down-Suche nach dieser Anzahl werden die Aktivitäts-ID, das Formulardatum, der Formularname und die E-Mail-Adresse angezeigt.

**Pfade für Interaktionen**

Journey von Ereignissen: Umfasst den Ereignistyp „Aktivität“ und Medium „Lead-Gen-Formular“ für Formulare, die durch die Integration kommen. Die Drill-Through-Ansicht enthält Details zu Campaign, Creative und Formular.

## Häufig gestellte Fragen zu Sponsored Content {#sponsored-content-faq}

**Was ist eine Dark Share?**

Eine Dark Share ist ein Beitrag, bei dem er nie auf der Firmenseite gepostet wird und sofort als Kreativer erstellt und direkt hinzugefügt wird. Damit [!DNL Marketo Measure] Kreative nicht oben auf der Unternehmensseite erscheinen und erneut beworben werden, werden dunkle Shares verwendet, damit sie hinter den Kulissen starten können.

**Welchen Status kennzeichnet [!DNL Marketo Measure] eigentlich?**

Es gibt vier verschiedene Status für [!DNL LinkedIn] Kampagne und Creative: Aktiv, Angehalten, Archiviert und Abgebrochen. Wir markieren nur Kampagnen und Kreative, die aktiv sind. Wenn Sie andere Status taggen, werden sie erneut auf „Aktiv“ gesetzt. [!DNL Marketo Measure] kennzeichnet keine pausierten, archivierten oder abgebrochenen Kampagnen oder Kreativen, setzt das Tagging jedoch fort, wenn sich der Status in „Aktiv“ ändert.

**Was ist der Wert, den [!DNL Marketo Measure] zum Taggen verwendet?**

Am Ende der Ziel-URL fügt [!DNL Marketo Measure] den `&_bl={creativeId}` hinzu, wobei der `{creativeId}` die Creative ID aus LinkedIn ist. Mit der Kreativ-ID können [!DNL Marketo Measure] auch die Kampagnen-ID bestimmen, da [!DNL LinkedIn] eine ziemlich einfache Anzeigenstruktur hat, da jeder Kreative nur zu einer Kampagne gehören kann.

**Was passiert mit meinem alten Kreativen, wenn [!DNL Marketo Measure] eine neue Version davon erstellt?**

Wenn [!DNL Marketo Measure] eine Freigabe neu erstellt und in einem neuen Kreativen platziert, wird der alte Kreative archiviert. Aus diesem Grund werden [!DNL Marketo Measure] auch keine archivierten Kampagnen oder Kreativen taggen. Andernfalls würden sie sich mit [!DNL Marketo Measure] schleifen, die versuchen, sie auf unbestimmte Zeit zu taggen.

**Warum stimmt die Ziel-URL der erstellten Anzeige nicht mit meiner ursprünglichen Anzeige überein?**

[!DNL Marketo Measure] muss die Tracking-Parameter zu einer aufgelösten URL hinzufügen, aber die URL, die in der API angezeigt wird, kann eine gekürzte URL sein, ohne dass alle Parameter vorhanden sind. Um dieses Problem zu umgehen, sucht [!DNL Marketo Measure] vor dem erneuten Erstellen einer Anzeige nach gekürzten URLs, löst sie auf und erstellt dann die neue Anzeige mit der aufgelösten URL und allen ihren Parametern, sodass [!DNL Marketo Measure] Tags hinzufügen können.

**Markierst du alle meine Werbeanzeigen? Ich sehe den bl-Parameter nicht auf allen Landingpages?**

Wir haben beobachtet, dass einige Marketer einen Bild-Link in die Ziel-URL einfügen, den [!DNL Marketo Measure] nicht taggen können, daher suchen wir nach der URL innerhalb des Anzeigeninhalts. Wenn [!DNL Marketo Measure] berechtigt ist, gekürzte URLs zu taggen, erweitern wir die URL und kennzeichnen sie, aber aufgrund der Kopierstruktur von LinkedIn wird sie automatisch im Text gekürzt. Das Tag befindet sich in der gekürzten LinkedIn-URL, die im Feld Anzeigeninhalt des Touchpoints statt im Feld Landingpage - Roh angezeigt wird.

**Oh nein, jemand aus meinem Team hat versehentlich eine Aktie geklont. Kann ich es anhalten?**

Keine Sorge. [!DNL Marketo Measure] wird programmgesteuert nach Freigaben suchen, die nicht mehr eindeutig sind, was bedeutet, dass sie seitdem in einen anderen Creative Manager kopiert wurden. Sobald diese Kopie erkannt wurde, folgen [!DNL Marketo Measure] dem üblichen Ablauf, um Anzeigen zu taggen und neu zu erstellen.

**Die Überprüfung meiner Anzeige stand noch aus. Warum steht die Überprüfung erneut aus, nachdem [!DNL Marketo Measure] es getaggt hat?**

LinkedIn verlangt, dass alle erstellten oder geänderten Anzeigen den normalen Sicherheitsprozess durchlaufen, bevor sie veröffentlicht werden. [!DNL Marketo Measure] versucht, die Anzeige so schnell wie möglich abzufangen, da sie alle 6 Stunden nach neuen Anzeigen sucht, aber mit [!DNL LinkedIn's] zusätzlichen Schritt kann sie den Start um einige Stunden verzögern.

**Meine Anzeige enthält zwei URLs. Welches wird getaggt?**

Beide. Die [!DNL Marketo Measure] Integration ermöglicht es uns, die Ziel-URL vom Clickthrough-Bild in der Anzeige zu taggen, aktualisiert aber auch automatisch die gekürzte URL in der Anzeigenbeschreibung.

![](assets/five.png)

**Ich habe mein [!DNL LinkedIn ads] Konto verbunden. Warum taggt [!DNL Marketo Measure] meine Links nicht?**

Der verbundene [!DNL LinkedIn]-Benutzer muss über angemessenen Bearbeitungszugriff verfügen, d. h. der Benutzer muss ein Account Manager, Campaign Manager oder Creative Manager sein.

**Woher weiß ich, ob mein Kreativ kopiert wird? Kann ich sehen, ob meine Kreativen dieselbe Freigabe verwenden?**

Die Freigabe-ID ist nicht in einem [!DNL LinkedIn]-Bericht angegeben, sodass es keine klare und naheliegende Möglichkeit gibt, nach Creative-to-Share-Zuordnungen zu suchen. Wenn Sie vermuten, dass es sich bei einem Kreativen um eine Kopie handelt, können Sie dies manuell überprüfen, indem Sie die Anzeige in Ihrem [!DNL LinkedIn] Campaign Manager öffnen. Dadurch wird die Anzeige in einer neuen Registerkarte geöffnet und Sie finden die Freigabe-ID in der URL.

![](assets/six.png)

## Häufig gestellte Fragen zu Lead Gen Forms {#lead-gen-forms-faq}

**Wie hoch sind die Kosten für diese Verbesserung?**

Dieses Angebot ist in jedem Paid [!DNL Marketo Measure]-Abonnement enthalten.

**Ist die Integration rückwirkend?**

Ja, wir laden historische Anzeigenformularantworten von LinkedIn herunter, obwohl wir auf das 90-tägige Lookback-Fenster beschränkt sind. Je länger die Integration von [!DNL Marketo Measure] und LinkedIn aktiviert ist, desto mehr Touchpoints für Lead-Gen-Formulare werden über [!DNL Marketo Measure] angezeigt.

Es gibt keine Option, um ein bestimmtes Datum für den Download festzulegen. Sie können jedoch optional Regeln für das Löschen von Touchpoints festlegen, wenn es Touchpoints gibt, die Sie unterdrücken müssen.

**Wird dies automatisch aktiviert, wenn ich bereits die [!DNL Marketo Measure] LinkedIn-Anzeigenintegration verwende?**

Nein, wir werden den Download nicht automatisch für alle Kunden starten, aber es ist ein sehr einfacher Wechsel, um diese Funktion in den Einstellungen zu aktivieren.

**Sind Formulardaten verfügbar?**

Formulardaten sind über [!DNL Marketo Measure] Discover verfügbar, einschließlich Formular-ID und Formularname. Formulardetails sind noch nicht für die Touchpoint-Objekte im CRM verfügbar.

**Was passiert mit allen [!DNL LinkedIn] Leads, die zuvor mit Marketo-Programmen oder CRM-Kampagnen synchronisiert wurden?**

Es wird empfohlen, alle [!DNL Marketo Measure] anzupassen, um Touchpoints aus diesen spezifischen Programmen oder Kampagnen zu generieren, um Duplizierungen zu vermeiden. Die LinkedIn-API unterliegt einer 90-tägigen Lookback-Beschränkung. Wenn Sie also Marketo- oder CRM-Regeln verwenden, wird empfohlen, das Enddatum für die Regel auf 90 Tage vor dem Datum festzulegen, an dem Sie die Integration in [!DNL Marketo Measure] aktiviert haben. Ab diesem Zeitpunkt können [!DNL Marketo Measure] diese Leads mit genaueren Einblicken und Details für Sie herunterladen.

**Ist ein automatisches Tagging oder Tracking erforderlich?**

Nein, dies unterscheidet sich von anderen [!DNL Marketo Measure]. Anstatt die Landingpage zu ändern (da kein Klick durch die Landingpage erfolgt), laden wir nur die entsprechenden Informationen von LinkedIn herunter und behandeln sie als Aktivitäten innerhalb von [!DNL Marketo Measure].
