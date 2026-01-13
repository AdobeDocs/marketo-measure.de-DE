---
description: Glossar der Marketo Measure-Felder
title: Glossar der Marketo Measure-Felder
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
feature: Fundamentals
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '3210'
ht-degree: 99%

---


# Glossar der Marketo Measure-Felder {#glossary}

Dieser Artikel enthält ein Glossar aller Marketo Measure-Felder, die Ihrem Salesforce aus dem Marketo Measure-Basispaket hinzugefügt werden. Sie finden außerdem Informationen darüber, auf welchem Objekt das Feld zu finden ist und wie jedes Feld mit Informationen gefüllt wird.

Für eine Zuordnung, auf welches Objekt sich jedes Marketo Measure-Feld bezieht, [klicken Sie hier](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[A](#a) ・ [B](#b) ・ [C](#c) ・ [D](#d) ・ [E](#e) ・ [F](#f) ・ [G](#g) ・ H ・ I ・ J ・ [K](#k) ・ [L](#l) ・ [M](#m) ・ N ・ [O](#o) ・ [P](#p) ・ Q ・ [R](#r) ・ [S](#s) ・ [T](#t) ・ [U](#u) ・ [V](#v) ・ W ・ X ・ Y ・ Z

## A {#a}

**Konto** | Auf dem Buyer Attribution Touchpoint gefunden

Dieses Feld enthält den Kontonamen, der mit dem BAT verknüpft ist.

**Anzeigen-Kampagnen-ID** | Auf dem Buyer Touchpoint und Buyer Attribution Touchpoint gefunden

Es gibt drei Möglichkeiten, dieses Feld auszufüllen:

`1)` Wenn der Touchpoint aus einer Paid Search stammt (entweder AdWords oder BingAds), wird hier die Anzeigen-Kampagnen-ID aus der Anzeigenplattform angezeigt.

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt, wird das Feld mit dem Wert von utm_campaign aus der Landingpage-URL ausgefüllt.

Z. B. `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

In diesem Beispiel würde die Anzeigen-Kampagnen-ID Folgendes anzeigen: __GAId__ Virtuelles Marketing-Ereignis - September 2014

`3)` Wenn der Touchpoint von einer Offline-Salesforce-Kampagne stammt (eine Konferenz, ein Abendessen usw.), wird die Salesforce-Kampagnen-ID durch die Anzeigen-Kampagnen-ID ersetzt.

Wenn keines der oben genannten zutrifft, ist dieses Feld leer.

**Anzeigenkampagnenname** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search (AdWords/Bing Ads) stammt, wird hier der Name der Anzeigenkampagne aus der Anzeigenplattform angezeigt.

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt und die Landingpage-URL einen Wert für utm_campaign enthält, wird dieser Wert hier eingetragen.

`3)` Wenn der Touchpoint aus einer Salesforce-Kampagne stammt, wird hier der Name der Salesforce-Kampagne angezeigt.

`4)` Hier wird der Kampagnenname eingetragen, der für Touchpoints definiert ist, die aus Aktivitäten generiert wurden, wie er in Ihrem Marketo Measure-Konto erstellt wurde.

Wenn keines der oben genannten zutrifft, ist dieses Feld leer.

**Anzeigenkampagnenname (FT)** | Buyer Touchpoint

Dieses Feld wird auf die gleiche Weise wie der Name der Anzeigenkampagne ausgefüllt. In diesem Feld wird jedoch speziell der Name der Anzeigenkampagne angezeigt, die den Erstkontakt-Touchpoint generiert hat.

**Anzeigenkampagnenname (LC)** | Buyer Touchpoint

Dieses Feld wird auf die gleiche Weise wie der Name der Anzeigenkampagne ausgefüllt. In diesem Feld wird jedoch speziell der Name der Anzeigenkampagne angezeigt, die den Touchpoint &quot;Lead-Erstellung&quot;generiert hat.

**Anzeigeninhalt** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search (AdWords/Bing Ads) stammt, wird im Feld die vollständige Anzeigenkopie von der Anzeigenplattform angezeigt.

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt, zeigt dieses Feld den Wert von utm_content in der Landingpage-URL an.

`3)` Dies wird mit dem Wert &quot;Betreff&quot; aus der verwandten Aktivität gefüllt, die den Touchpoint generiert hat.

Wenn keines der oben genannten zutrifft, ist dieses Feld leer.

**Anzeigenziel-URL** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search stammt, zeigt dieses Feld das URL-Ziel an, zu dem Sie weitergeleitet werden, nachdem Sie in der Suchmaschine auf die Anzeige geklickt haben.

Wenn der Touchpoint nicht aus einer Paid Search stammt, ist das Feld leer.

**Anzeigengruppen-ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search stammt, wird hier die ID der Anzeigengruppe aus AdWords/Bing Ads angezeigt.

Wenn der Touchpoint nicht aus einer Paid Search stammt, ist das Feld leer.

**Anzeigengruppenname** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, wird hier der Anzeigengruppenname von AdWords/Bing Ads angezeigt.

Wenn der Touchpoint nicht aus einer Paid Search stammt, ist das Feld leer.

**Anzeigen-ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, wird hier die Anzeigen-ID von AdWords/Bing Ads angezeigt.

`2)` Dies wird mit der externen Aktivitäts-ID ausgefüllt, wenn der Touchpoint von einer CRM-Aktivität generiert wird.

Wenn der Touchpoint nicht aus einer Paid Search stammt, ist das Feld leer.

**Attribution % Benutzerdefiniertes Modell** | Buyer Attribution Touchpoint

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld den Prozentsatz des Umsatzes an, der einem Touchpoint zugeordnet ist, entsprechend den Werten, die in Ihrem benutzerspezifischen Modell festgelegt sind.

Wenn Sie kein benutzerdefiniertes Modell verwenden, ist dieses Feld leer.

**Attribution % Erstkontakt** | Buyer Attribution Touchpoint

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem Erstkontakt-Modell zugeordnet ist.

**Attribution % Vollständig** | Buyer Attribution Touchpoint

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem vollständigen Pfadmodell zugeordnet wurde.

**Attribution % Lead-Erstellung** | Buyer Attribution Touchpoint

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint zugeordnet ist, gemäß einem Lead-Erstellungsmodell.

**Attribution % U-förmig** | Buyer Attribution Touchpoint

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem U-förmigen Modell zugeordnet wurde.

**Attribution % W-förmig** | Buyer Attribution Touchpoint

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem W-förmigen Modell zugeordnet ist.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## B {#b}

**Marketo Measure Opportunity Amount** | Salesforce Opportunity 

Wenn Sie ein benutzerdefiniertes Feld &quot;Betrag&quot;verwenden, um den Opportunity-Umsatz zu melden, kann Marketo Measure diese benutzerdefinierten Felder nicht lesen. Der Marketo Measure Opportunity Amount ist ein ausgeblendetes Feld, das zum Erstellen eines Workflows verwendet wird, mit dem Marketo Measure benutzerdefinierte Amount-Felder für die Opportunity lesen kann.

**Browser** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird der Typ des Webbrowsers angezeigt, der während der Websitzung verwendet wird (Chrome, Safari, Firefox usw.).

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## C {#c}

**Kontakt** | Buyer Touchpoint, Buyer Attribution Touchpoint

Im Feld wird der Kontakt angezeigt, zu dem der Touchpoint gehört.

**Zählung - Benutzerdefiniertes Modell** | Buyer Attribution Touchpoint

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld im Dezimalformat den Prozentsatz der Umsatzgutschriften an einen Touchpoint entsprechend den Werten, die in Ihrem benutzerspezifischen Modell festgelegt sind.

Wenn Sie kein benutzerdefiniertes Modell verwenden, ist dieses Feld leer.

**Zählung - Benutzerdefiniertes Modell** | Buyer Touchpoint

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld im Dezimalformat den Prozentsatz der einem Touchpoint zugewiesenen Attribution an, der den in Ihrem benutzerspezifischen Modell festgelegten Werten entspricht. Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, spiegelt es nicht die Umsatzgutschriften wider, sondern lediglich die Attributionsgutschriften.

Wenn Sie kein benutzerdefiniertes Modell verwenden, ist dieses Feld leer.

**Zählung - Erstkontakt** | Buyer Attribution Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Umsatzgutschriften an einen Touchpoint gemäß einem Erstkontakt-Modell an.

**Zählung - Erstkontakt** | Buyer Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Attributionen, die einem Touchpoint gemäß einem Erstkontakt-Modell gewährt werden. Wenn es sich bei dem Touchpoint um den Erstkontakt handelt, ist dieses Feld immer 1,0 (d. h. 100 % Attributionsgutschriften). Wenn der Touchpoint nicht der Erstkontakt ist, ist dieses Feld immer 0 (d. h. 0 % Attributionsgutschriften).

Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, spiegelt es nicht die Umsatzgutschriften wider, sondern lediglich die Attributionsgutschriften.

**Zählung - Vollständiger Pfad** | Buyer Attribution Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz des Umsatzes an, der einem Touchpoint gemäß einem vollständigen Pfadmodell zugewiesen wurde.

**Zählung - Touch bei Lead-Erstellung** | Buyer Attribution Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Umsatzgutschriften an einen Touchpoint gemäß einem Lead-Erstellungsmodell.

**Zählung - Touch bei Lead-Erstellung** | Buyer Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der einem Touchpoint gemäß einem Lead-Erstellungsmodell zugewiesenen Attribution. Wenn es sich bei dem Touchpoint um den Touchpoint der Lead-Erstellung handelt, ist dieses Feld immer 1,0 (d. h. 100 % Attributionsgutschriften). Wenn es sich bei dem Touchpoint nicht um den Touchpoint der Lead-Erstellung handelt, ist dieses Feld immer 0 (d. h. 0 % Attributionsgutschriften).

Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, spiegelt es nicht die Umsatzgutschriften wider, sondern lediglich die Attributionsgutschriften.

**Anzahl - U-förmig** | Buyer Attribution Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Umsatzgutschriften an einen Touchpoint gemäß einem U-förmigen Modell.

**Anzahl - U-förmig** | Buyer Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Attributionsgutschriften an, der einem Touchpoint gemäß einem U-förmigen Modell gewährt wird. Im U-förmigen Modell wird die Gewichtung zwischen Erstkontakt, Lead-Erstellungs-Touch und allen zwischengeschalteten Formularübermittlungen zwischen Erstkontakt und Lead-Erstellungskontakt aufgeteilt.

Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, spiegelt es nicht die Umsatzgutschriften wider, sondern lediglich die Attributionsgutschriften.

**Zählung - W-förmig** | Buyer Attribution Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Gutschriften an einen Touchpoint gemäß einem W-förmigen Modell.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## D {#d}

Datum gemeldet | Marketo Measure ABTest, Marketo Measure-Ereignis

Marketo Measure-Ereignis - das Datum, an dem ein Benutzer auf Ihrer Website eine bestimmte Aktion ausgeführt und ein Ereignis aktiviert hat

Marketo Measure ABTest - das Datum, an dem ein Benutzer an einem A/B-Test auf Ihrer Website teilgenommen hat

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## E {#e}

**Ereignisname** | Marketo Measure-Ereignis

In diesem Feld wird der Name der Aktion angezeigt, die das Ereignis ausgelöst hat (d. h. Seitenansicht).

**Ereigniswert** | Marketo Measure-Ereignis

Beschreibung des Ereignisses (d. h. Homepage)

**Experimentname** | Marketo Measure ABTest

In diesem Feld wird der Name des Experiments (d. h. die Testschaltfläche) angezeigt.

**Experiment-ID** | Marketo Measure AB-Test

Der eindeutige Identifikationscode für jedes Experiment

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## F {#f}

Formular-URL | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird eine gekürzte Version der URL einer Seite angezeigt, in der das Ausfüllen des Formulars erfolgte (keine UTM-Parameter)

Formular-URL - Roh | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die gesamte Seiten-URL angezeigt, in der das Formular ausgefüllt wurde, einschließlich UTM-Parameter

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## G {#g}

Geo-Stadt | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird der Name der Stadt angezeigt, in der der Lead/Kontakt Ihre Website besucht hat. Dies erfolgt über die Reverse-IP-Suche.

Geo-Land | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt an, wo das Land, in dem der Lead/Kontakt Ihre Website besucht hat, liegt. Dies erfolgt über die Reverse-IP-Suche.

Geo-Region | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die Region oder der Bundesstaat angezeigt, in der der Lead/Kontakt Ihre Website besucht hat. Dies erfolgt über die Reverse-IP-Suche.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## K {#k}

**Keyword-ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

Wenn der Touchpoint aus einer Paid Search stammt, zeigt dieses Feld die Keyword-ID aus der Anzeigenplattform (Adwords/BingAds) an.

Wenn dieser Touchpoint nicht aus einer Paid Search stammt, ist dieses Feld leer.

**Keyword MatchType** | Buyer Touchpoint, Buyer Attribution Touchpoint

Wenn der Touchpoint aus einer Paid Search stammt, zeigt dieses Feld den Matchtyp aus der Anzeigenplattform (Adwords/Bing) an.

**Keyword-Text** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search stammt, zeigt dieses Feld den Suchbegrifftext aus der Anzeigenplattform (Adwords/BingAds) ODER den Wert aus dem Parameter _bk in der Landingpage-URL an.

Z. B. `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt, zeigt dieses Feld den Wert von utm_term aus der Landingpage-URL an.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

Wenn der Touchpoint nicht aus einer Paid Search stammt oder kein utm_term-Wert vorhanden ist, ist dieses Feld leer.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## L {#l}

**Landingpage** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die gekürzte Version der URL (keine UTM-Parameter) der ersten Web-Seite angezeigt, die während einer Web-Sitzung besucht wurde.

**Landingpage - Roh** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die gesamte URL (einschließlich UTM-Parameter) der ersten Web-Seite angezeigt, die während einer Web-Sitzung besucht wurde.

**Lead** | Buyer Touchpoint, Marketo Measure Person

Dieses Feld zeigt den Namen des Leads an, zu dem ein Touchpoint gehört.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## M {#m}

**Marketingkanal** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt die allgemeine Gruppe von Marketing-Aktivitäten oder Marketingkanälen an, zu denen der Touchpoint gehört (d. h. Paid Search, Direkt, Social Media usw.). Touchpoints werden nach der Einrichtung Ihrer Kanäle in der Marketo Measure App gruppiert. Weitere Informationen über Marketing-Kanäle und dazu, wie Sie Ihre Kanäle einrichten können, finden Sie [hier](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**Marketingkanal - Pfad** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt den Marketingkanal und den Unterkanal an, zu dem ein Touchpoint gehört. Im folgenden Beispiel ist Marketingkanal - Pfad Social.LinkedIn, wobei der Marketingkanal Social und der Unterkanal LinkedIn ist.

![&#x200B; 3](assets/1-3.png)

**Medium** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, wird hier das Medium von Adwords/BingAds angezeigt (d.h. CPC).

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt, zeigt dieses Feld den utm_medium-Wert aus der Landingpage-URL an.

`3)` Wenn der Touchpoint aus einer Offline-Kampagne stammt, wird in diesem Feld das Feld &quot;Typ&quot; in der Salesforce-Kampagne angezeigt.

`4)` Dies wird mit dem Wert des Aktivitätstyps aus der verwandten Aktivität gefüllt, die den Touchpoint generiert hat.

Wenn keiner der oben genannten Werte auftritt, legt Marketo Measure automatisch einen Mittelwert fest.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

O

**Opportunity** | Buyer Attribution Touchpoint

In diesem Feld wird die Opportunity angezeigt, der der BAT angehört.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

P

**Plattform** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld werden der Computer- oder Handytyp und der Typ des Betriebssystems angezeigt, das während der Websitzung verwendet wurde.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

R

**Referrer-Seite** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die URL (ohne UTM-Parameter) der letzten Webseite angezeigt, auf der sich der Lead/Kontakt befand und die ihn zu Ihrer Website weitergeleitet hat.

Beispiel:

- Wenn der Touchpoint von einer gebührenpflichtigen/kostenlosen Suche stammt, zeigt das Feld die URL der Suchmaschine an

- Wenn der Touchpoint aus Social Media stammt, zeigt das Feld die URL der sozialen Website (d. h. LinkedIn) an.

**Referrer-Page - Roh** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt dieselben Informationen wie die Seite der verweisenden Stelle an, allerdings zeigt dieses Feld die gesamte verweisende URL (einschließlich UTM-Parameter) an.

**Umsatz - Benutzerdefiniertes Modell** | Buyer Attribution Touchpoint

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld den Geldumsatz an, der einem Touchpoint zugeordnet ist, entsprechend dem in Ihrem benutzerspezifischen Modell festgelegten Attributionsprozentsatz.

Wenn Sie kein benutzerdefiniertes Modell verwenden, beträgt der Geldbetrag 0.

**Umsatz - Erstkontakt** | Buyer Attribution Touchpoint

Dieses Feld zeigt den einem Touchpoint zugeordneten Geldumsatz in Abhängigkeit vom Attributionsprozentsatz im Erstkontakt-Modell.

**Umsatz - Vollständiger Pfad** | Buyer Attribution Touchpoint

Dieses Feld zeigt den Geldumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im vollständigen Pfadmodell.

**Umsatz - Touch bei Lead-Erstellung** | Buyer Attribution Touchpoint

Dieses Feld zeigt den Geldumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im Lead-Erstellungsmodell.

**Umsatz - U-förmig** | Buyer Attribution Touchpoint

Dieses Feld zeigt den Geldumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im U-förmigen Modell.

**Umsatz - W-förmig** | Buyer Attribution Touchpoint

Dieses Feld zeigt den Geldumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im W-förmigen Modell.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

S

**Salesforce Campaign** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die Salesforce-Kampagne angezeigt, zu der der Touchpoint gehört.

**Suchbegriff** | Buyer Touchpoint, Buyer Attribution Touchpoint

Wenn der Touchpoint aus einer gebührenpflichtigen oder kostenlosen Suche stammt, zeigt dieses Feld den in die Suchmaschine eingegebenen Suchbegriff an. Aus Datenschutzgründen sind diese Informationen jedoch in der Regel nicht verfügbar.

**Segment** | Buyer Attribution Touchpoint

In diesem Feld werden die Segmente angezeigt, zu denen der Touchpoint gehört. Dies hängt davon ab, wie Sie Ihre Segmentierungsregeln in der Marketo Measure-App konfiguriert haben.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

D

**Touchpoint-Datum** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Online-Quelle stammt, zeigt dieses Feld das Datum und die Uhrzeit des Touchpoints an.

`2)` Wenn der Touchpoint von einem Offline-Ereignis stammt, zeigt dieses Feld das in der Salesforce-Kampagne festgelegte Datum und die Uhrzeit oder das in den Kampagnen-Synchronisierungsregeln ausgewählte Datumsfeld an.

`3)` Wenn der Touchpoint aus einer Aktivität stammt, zeigt dieses Feld das Datum und die Uhrzeit des Felds an, das in den Aktivitätsregeln als Touchpoint-Datum ausgewählt wurde.

**Touchpoint-Datum (FT)** | Buyer Touchpoint

Dies ist dasselbe Feld wie das Touchpoint-Datum, in diesem Feld werden jedoch insbesondere das Datum und die Uhrzeit des Erstkontakt-Touchpoints angezeigt.

**Touchpoint-Datum (LC)** | Buyer Touchpoint

Dies ist dasselbe Feld wie das Touchpoint-Datum. In diesem Feld werden jedoch insbesondere das Datum und die Uhrzeit des Touchpoints &quot;Lead-Erstellung&quot; angezeigt.

**Touchpoint-Position** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt die Position des Touchpoints an. Die Position des Touchpoints spiegelt die wichtigsten Meilenstein-Touchpoints im Kunden-Journey wider (d. h. FT, Form, LC, OC, Closed). Die Position des Touchpoints hängt davon ab, wann er auf der Journey des Kunden aufgetreten ist, und ein einzelner Touchpoint kann mehr als eine Position aufweisen. Die verschiedenen Touchpoint-Positionen lauten wie folgt:

Erstkontakt (FT) - Die allererste Marketing-Interaktion, die jemand mit Ihrer Marke hat

Lead Creation (LC) - Die allererste bekannte Marketing-Interaktion (normalerweise eine Formularübermittlung oder die Einbeziehung einer Salesforce-Kampagne)

Formular - Wenn ein Besucher ein Online-Formular ausfüllt

Opportunity Creation (OC) - Die Marketing-Interaktion, die dem Zeitpunkt der Erstellung der Opportunity am nächsten ist

Geschlossen - Die Marketing-Interaktion, die dem Zeitpunkt am nächsten ist, wenn die Opportunity geschlossen wird (Gewinner oder Verlust)

**Touchpoint-Quelle** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, zeigt dieses Feld den Namen der Anzeigenplattform an (AdWords/BingAds).

`2)` Wenn der Touchpoint aus einer organischen Suche stammt, zeigt dieses Feld den Namen der Suchmaschine an

`3)` Wenn weder #1 noch #2 zutreffen und der Wert von utm_source in der URL der Landingpage für den Touchpoint vorhanden ist, wird dieser Wert hier angezeigt

`4)` Dies wird als CRM-Kampagne ausgefüllt, wenn der Touchpoint aus einer CRM-Kampagne generiert wird.

`5)` Dies wird als CRM-Aktivität ausgefüllt, wenn der Touchpoint von einer CRM-Aktivität generiert wird.

Wenn keines der oben genannten zutrifft, wird dieses Feld als &quot;Web Direct&quot; oder &quot;Web&quot; ausgefüllt.

**Touchpoint-Quelle (FT)** | Buyer Touchpoint

Dies ist dasselbe Feld wie die Touchpoint-Quelle. Dieses Feld zeigt jedoch speziell die Quelle des Erstkontakt-Touchpoints an.

**Touchpoint-Quelle (LC)** | Buyer Touchpoint

Dies ist dasselbe Feld wie die Touchpoint-Quelle. Dieses Feld zeigt jedoch speziell die Quelle des Touchpoints &quot;Lead-Erstellung&quot;an.

**Touchpoint-Typ** | Auf dem Buyer Touchpoint und dem Buyer Attribution Touchpoint gefunden.

In diesem Feld wird der Interaktionstyp des Touchpoints angezeigt. Er wird wie folgt angezeigt: Webbesuch, Webformular oder Webchat für JavaScript-Touchpoints. Für CRM-Campaign-Touchpoints wird sie als CRM angezeigt. Es wird mit der Aufgabe oder dem Ereignistyp für Aktivitäts-Touchpoints gefüllt.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

U

**UniqueId** | Buyer Touchpoint, Buyer Attribution Touchpoint

Die jedem Touchpoint zugeordnete eindeutige ID

**Benutzer-ID** | Marketo Measure ABTest

Eindeutiger Identifikationscode für jeden Einsatz von Optimiely

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)

## V {#v}

**Variante** | Marketo Measure ABTest

Name der Variante des A/B-Tests

**Varianten-ID** | Marketo Measure ABTest

Der eindeutige Identifikationscode für jede A/B-Test-Variante.

[Klicken Sie hier, um zum Seitenanfang zurückzukehren.](#top)
