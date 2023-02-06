---
unique-page-id: 18874586
description: Glossar der Marketo Measure-Felder - Marketo Measure - Produktdokumentation
title: Glossar der Marketo Measure-Felder
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
source-git-commit: 334dcd3dcbddacc4920d182d94908babd3cb8c89
workflow-type: tm+mt
source-wordcount: '3211'
ht-degree: 0%

---

# Glossar der Marketo Measure-Felder {#glossary-of-marketo-measure-fields}

Dieser Artikel enthält ein Glossar aller Marketo Measure-Felder, die Ihrer Salesforce aus dem Marketo Measure-Basispaket hinzugefügt werden. Sie finden außerdem Informationen darüber, auf welchem Objekt das Feld zu finden ist und wie jedes Feld mit Informationen gefüllt wird.

Für eine Zuordnung, auf die sich jedes Marketo Measure-Feld bezieht, wenden Sie sich an [Hier klicken](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[A](#a) ・ [B](#b) ・ [C](#c) ・ [D](#d) ・ [E](#e) ・ [F](#f) ・ [G](#g) ・ H ・ I ・ J ・ [K](#k) ・ [L](#l) ・ [M](#m) ・ N ・ [O](#o) ・ [P](#p) ・ Q ・ [R](#r) ・ [S](#s) ・ [T](#t) ・ [U](#u) ・ [V](#v) ・ W ・ X ・ Y ・ Z

## A {#a}

**Konto** | Auf dem Touchpoint der Käuferzuordnung gefunden

Dieses Feld enthält den Kontonamen, der mit dem BAT verknüpft ist.

**Anzeigen-Kampagnen-ID** | Auf dem Touchpoint des Käufers, Touchpoint der Käuferzuordnung gefunden

Es gibt drei Möglichkeiten, dieses Feld auszufüllen:

`1)` Wenn der Touchpoint aus einer gebührenpflichtigen Suche stammt (entweder AdWords oder BingAds), wird hier die Anzeigen-Kampagnen-ID aus der Anzeigenplattform angezeigt.

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt, wird das Feld mit dem Wert utm_campaign aus der Landingpage-URL ausgefüllt.

Z. B. `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

In diesem Beispiel würde die Anzeigen-Kampagnen-ID Folgendes anzeigen: __GAId__ Virtuelles Marketing-Ereignis - September 2014

`3)` Wenn der Touchpoint von einer Offline-Salesforce-Kampagne stammt (eine Konferenz, ein Abendessen usw.), wird die Salesforce-Kampagnen-ID durch die Anzeigen-Kampagnen-ID ersetzt.

Wenn keines der oben genannten Felder leer ist.

**Anzeigenkampagnenname** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer gebührenpflichtigen Suche (AdWords/Bing Ads) stammt, wird hier der Name der Anzeigenkampagne aus der Anzeigenplattform angezeigt.

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt und die Landingpage-URL einen Wert für utm_campaign enthält, wird dieser Wert hier ausgefüllt.

`3)` Wenn der Touchpoint aus einer Salesforce-Kampagne stammt, wird hier der Name der Salesforce-Kampagne angezeigt.

`4)` Hiermit wird der Kampagnenname gefüllt, der für Touchpoints definiert ist, die aus Aktivitäten generiert wurden, wie er in Ihrem Marketo Measure-Konto erstellt wurde.

Wenn keines der oben genannten Felder leer ist.

**Anzeigenkampagnenname (FT)** | Käufer Touchpoint

Dieses Feld wird auf die gleiche Weise wie der Name der Anzeigenkampagne ausgefüllt. In diesem Feld wird jedoch speziell der Name der Anzeigenkampagne angezeigt, die den Erstkontakt-Touchpoint generiert hat.

**Anzeigenkampagnenname (LC)** | Käufer Touchpoint

Dieses Feld wird auf die gleiche Weise wie der Name der Anzeigenkampagne ausgefüllt. In diesem Feld wird jedoch speziell der Name der Anzeigenkampagne angezeigt, die den Touchpoint &quot;Lead-Erstellung&quot;generiert hat.

**Anzeigeninhalt** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search (AdWords/Bing Ads) stammt, wird im Feld die vollständige Anzeigenkopie von der Anzeigenplattform angezeigt.

`2)` Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, zeigt dieses Feld den Wert utm_content in der Landingpage-URL an.

`3)` Dies wird mit dem Wert &quot;Betreff&quot;aus der verwandten Aktivität gefüllt, die den Touchpoint generiert hat.

Wenn keines der oben genannten Felder leer ist.

**Anzeigenziel-URL** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer gebührenpflichtigen Suche stammt, zeigt dieses Feld das URL-Ziel an, zu dem Sie weitergeleitet werden, nachdem Sie in der Suchmaschine auf die Anzeige geklickt haben.

Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, ist das Feld leer.

**Anzeigengruppen-ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer gebührenpflichtigen Suche stammt, wird hier die ID der Anzeigengruppe aus AdWords/Bing Ads angezeigt.

Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, ist das Feld leer.

**Anzeigengruppenname** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, wird hier der Anzeigengruppenname von AdWords/Bing Ads angezeigt.

Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, ist das Feld leer.

**Anzeigen-ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, wird hier die Anzeigen-ID von AdWords/Bing Ads angezeigt.

`2)` Dies wird mit der externen Aktivitäts-ID ausgefüllt, wenn der Touchpoint von einer CRM-Aktivität generiert wird.

Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, ist das Feld leer.

**Attribution % Benutzerdefiniertes Modell** | Touchpoint der Käuferzuordnung

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld den Prozentsatz des Umsatzes an, der einem Touchpoint zugeordnet ist, entsprechend den Werten, die in Ihrem benutzerspezifischen Modell festgelegt sind.

Wenn Sie kein benutzerdefiniertes Modell verwenden, ist dieses Feld leer.

**Zuordnung % Erstkontakt** | Touchpoint der Käuferzuordnung

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem First Touch-Modell zugeordnet ist.

**Attribution % Vollständig** | Touchpoint der Käuferzuordnung

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem vollständigen Pfadmodell zugeordnet wurde.

**Attribution % Lead-Erstellung** | Touchpoint der Käuferzuordnung

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint zugeordnet ist, gemäß einem Lead-Erstellungsmodell.

**Attribution % U-förmig** | Touchpoint der Käuferzuordnung

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem U-förmigen Modell zugeordnet wurde.

**Attribution % W-förmig** | Touchpoint der Käuferzuordnung

In diesem Feld wird der Prozentsatz des Umsatzes angezeigt, der einem Touchpoint gemäß einem W-förmigen Modell zugeordnet ist.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## B {#b}

**Marketo Measure Opportunity Amount** | Salesforce-Chancen

Wenn Sie ein benutzerdefiniertes Feld &quot;Betrag&quot;verwenden, um den Umsatz von Opportunity zu melden, kann Marketo Measure diese benutzerdefinierten Felder nicht lesen. Der Marketo Measure Opportunity Amount ist ein ausgeblendetes Feld, das zum Erstellen eines Workflows verwendet wird, mit dem Marketo Measure benutzerdefinierte Amount-Felder für die Opportunity lesen kann.

**Browser** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird der Typ des Webbrowsers angezeigt, der während der Websitzung verwendet wird (Chrome, Safari, Firefox usw.).

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## C {#c}

**Kontakt** | Buyer Touchpoint, Buyer Attribution Touchpoint

Im Feld wird der Kontakt angezeigt, zu dem der Touchpoint gehört.

**Count - Benutzerdefiniertes Modell** | Touchpoint der Käuferzuordnung

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld im Dezimalformat den Prozentsatz der Umsatzgutschriften an einen Touchpoint entsprechend den Werten, die in Ihrem benutzerspezifischen Modell festgelegt sind.

Wenn Sie kein benutzerdefiniertes Modell verwenden, ist dieses Feld leer.

**Count - Benutzerdefiniertes Modell** | Käufer Touchpoint

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld im Dezimalformat den Prozentsatz der einem Touchpoint zugewiesenen Attribution an, der den in Ihrem benutzerspezifischen Modell festgelegten Werten entspricht. Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, handelt es sich nicht um eine Revenue Credit, sondern nur um Attribution Credit.

Wenn Sie kein benutzerdefiniertes Modell verwenden, ist dieses Feld leer.

**Count - Erstkontakt** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt in Dezimalform den Prozentsatz der Umsatzgutschriften an einen Touchpoint gemäß einem First Touch-Modell an.

**Count - Erstkontakt** | Käufer Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der Zuschreibungen, die einem Touchpoint gemäß einem First Touch-Modell gewährt werden. Wenn es sich bei dem Touchpoint um den Erstkontakt handelt, ist dieses Feld immer 1,0 (d. h. 100 % Attribution Guthaben). Wenn der Touchpoint nicht der Erstkontakt ist, ist dieses Feld immer 0 (d. h. 0 % Zuordnungsguthaben).

Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, handelt es sich nicht um eine Revenue Credit, sondern nur um Attribution Credit.

**Count - Vollständiger Pfad** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt in Dezimalform den Prozentsatz des Umsatzes an, der einem Touchpoint gemäß einem vollständigen Pfadmodell zugewiesen wurde.

**Zählung - Touch bei Lead-Erstellung** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt in Dezimalform den Prozentsatz der Umsatzgutschriften an einen Touchpoint gemäß einem Lead-Erstellungsmodell.

**Zählung - Touch bei Lead-Erstellung** | Käufer Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz der einem Touchpoint gemäß einem Lead-Erstellungsmodell zugewiesenen Attribution. Wenn es sich bei dem Touchpoint um den Touchpoint der Lead-Erstellung handelt, ist dieses Feld immer 1,0 (was einen 100-%-Attribution-Anteil angibt). Wenn es sich bei dem Touchpoint nicht um den Touchpoint der Lead-Erstellung handelt, ist dieses Feld immer 0 (d. h. 0 % Attribution).

Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, handelt es sich nicht um eine Revenue Credit, sondern nur um Attribution Credit.

**Anzahl - U-förmig** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt in Dezimalform den Prozentsatz der Umsatzgutschriften an einen Touchpoint gemäß einem U-förmigen Modell.

**Anzahl - U-förmig** | Käufer Touchpoint

Dieses Feld zeigt in Dezimalform den Prozentsatz des Attributionsguts an, der einem Touchpoint gemäß einem U-förmigen Modell gewährt wird. Im U-förmigen Modell wird die Gewichtung zwischen Erstkontakt, Lead-Erstellungs-Touch und allen zwischengeschalteten Formularübermittlungen zwischen Erstkontakt und Lead-Erstellungskontakt aufgeteilt.

Da sich dieses Feld auf das Touchpoint-Objekt des Käufers bezieht, handelt es sich nicht um eine Revenue Credit, sondern nur um Attribution Credit.

**Count - W-förmig** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt in Dezimalform den Prozentsatz der Gutschrift an einen Touchpoint gemäß einem W-förmigen Modell.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## D {#d}

Datum gemeldet | Marketo Measure ABTest, Marketo Measure-Ereignis

Marketo Measure-Ereignis - das Datum, an dem ein Benutzer auf Ihrer Website eine bestimmte Aktion ausgeführt und ein Ereignis aktiviert hat

Marketo Measure ABTest - das Datum, an dem ein Benutzer an einem A/B-Test auf Ihrer Website teilgenommen hat

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## E {#e}

**Ereignisname** | Marketo Measure-Ereignis

In diesem Feld wird der Name der Aktion angezeigt, die das Ereignis ausgelöst hat (d. h. Seitenansicht).

**Ereigniswert** | Marketo Measure-Ereignis

Beschreibung des Ereignisses (d. h. Homepage)

**Experimentname** | Marketo Measure ABTest

In diesem Feld wird der Name des Experiments (d. h. die Testschaltfläche) angezeigt.

**Experiment-ID** |Marketo Measure AB-Test

Der eindeutige Identifikationscode für jedes Experiment

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## F {#f}

Formular-URL | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird eine gekürzte Version der URL einer Seite angezeigt, in der das Ausfüllen des Formulars erfolgte (keine UTM-Parameter)

Formular-URL - Roh | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die gesamte Seiten-URL angezeigt, in der das Formular ausgefüllt wurde, einschließlich UTM-Parameter

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## G {#g}

Geo City | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird der Name der Stadt angezeigt, in der der Lead/Kontakt Ihre Website besucht hat. Dies erfolgt über die Reverse-IP-Suche.

Geo-Land | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt an, wo das Land, in dem der Lead/Kontakt Ihre Website besucht hat, liegt. Dies erfolgt über die Reverse-IP-Suche.

Geo-Region | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die Region oder der Bundesstaat angezeigt, in der der Lead/Kontakt Ihre Website besucht hat. Dies erfolgt über die Reverse-IP-Suche.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## K {#k}

**Schlüsselwort-ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

Wenn der Touchpoint aus einer Paid Search stammt, zeigt dieses Feld die Keyword-ID aus der Anzeigenplattform (Adwords/BingAds) an.

Wenn dieser Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, ist dieses Feld leer.

**Keyword MatchType** | Buyer Touchpoint, Buyer Attribution Touchpoint

Wenn der Touchpoint aus einer gebührenpflichtigen Suche stammt, zeigt dieses Feld den Matchtype aus der Anzeigenplattform (Adwords/Bing) an.

**Suchbegrifftext** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Paid Search stammt, zeigt dieses Feld den Suchbegrifftext aus der Anzeigenplattform (Adwords/BingAds) ODER den Wert aus dem Parameter _bk in der Landingpage-URL an.

Z. B. `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` Wenn der Touchpoint nicht aus einer Paid Search stammt, zeigt dieses Feld den Wert utm_term aus der Landingpage-URL an.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt oder kein utm_term -Wert vorhanden ist, ist dieses Feld leer.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## L {#l}

**Landingpage** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die gekürzte Version der URL (keine UTM-Parameter) der ersten Webseite angezeigt, die während einer Websitzung besucht wurde.

**Landingpage - Roh** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die gesamte URL (einschließlich UTM-Parameter) der ersten Webseite angezeigt, die während einer Websitzung besucht wurde.

**Lead** | Käufer Touchpoint, Marketo Measure Person

Dieses Feld zeigt den Namen des Leads an, zu dem ein Touchpoint gehört.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## Mio {#m}

**Marketingkanal** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt die allgemeine Gruppe von Marketing-Aktivitäten oder Marketingkanälen an, zu denen der Touchpoint gehört (d. h. Paid Search, Direct, Social usw.). Touchpoints werden nach der Einrichtung Ihrer Kanäle in der Marketo Measure App gruppiert. Weitere Informationen zu Marketingkanälen und zur Einrichtung Ihrer Kanäle finden Sie unter [Hier klicken](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**Marketingkanal - Pfad** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt den Marketing-Kanal und den Unterkanal an, zu dem ein Touchpoint gehört. Im folgenden Beispiel ist Marketing-Kanal - Pfad Social.LinkedIn, wobei der Marketing-Kanal Social und der Unterkanal LinkedIn ist.

![](assets/1-3.png)

**Mittel** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, wird hier das Medium von Adwords/BingAds angezeigt (d.h. CPC).

`2)` Wenn der Touchpoint nicht aus einer gebührenpflichtigen Suche stammt, zeigt dieses Feld den Wert utm_medium aus der Landingpage-URL an.

`3)` Wenn der Touchpoint aus einer Offline-Kampagne stammt, wird in diesem Feld das Feld &quot;Typ&quot;in der Salesforce-Kampagne angezeigt.

`4)` Dies wird mit dem Aktivitätstyp -Wert aus der verwandten Aktivität gefüllt, die den Touchpoint generiert hat.

Wenn keiner der oben genannten Werte auftritt, legt Marketo Measure automatisch einen Mittelwert fest.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

O

**Chancen** | Touchpoint der Käuferzuordnung

In diesem Feld wird die Chance angezeigt, der die BVT angehört.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

P

**Plattform** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld werden der Computer- oder Telefontyp und der Typ des Betriebssystems angezeigt, das während der Websitzung verwendet wurde.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

R

**Referrer Page** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die URL (ohne UTM-Parameter) der letzten Webseite angezeigt, auf der sich der Lead/Kontakt befand, der sie zu Ihrer Website weitergeleitet hat.

Beispiel:

- Wenn der Touchpoint von einer gebührenpflichtigen/kostenlosen Suche stammt, zeigt das Feld die URL der Suchmaschine an

- Wenn der Touchpoint aus Social stammt, zeigt das Feld die URL der sozialen Website (d. h. LinkedIn) an.

**Referrer Page - Roh** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt dieselben Informationen wie die Seite der verweisenden Stelle an, allerdings zeigt dieses Feld die gesamte verweisende URL (einschließlich UTM-Parameter) an.

**Umsatz - Benutzerdefiniertes Modell** | Touchpoint der Käuferzuordnung

Wenn Sie ein benutzerdefiniertes Attributionsmodell verwenden, zeigt dieses Feld den Geldumsatz an, der einem Touchpoint zugeordnet ist, entsprechend dem in Ihrem benutzerspezifischen Modell festgelegten Attributionsprozentsatz.

Wenn Sie kein benutzerdefiniertes Modell verwenden, beträgt der Dollarbetrag 0.

**Umsatz - Erstkontakt** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt den einem Touchpoint zugeordneten Dollarumsatz in Abhängigkeit vom Attributionsprozentsatz im First Touch-Modell.

**Umsatz - Vollständiger Pfad** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt den Dollarumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im vollständigen Pfadmodell.

**Umsatz - Touch bei Lead-Erstellung** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt den einem Touchpoint zugeordneten Dollarumsatz in Abhängigkeit vom Attributionsprozentsatz im Lead-Erstellungsmodell.

**Umsatz - U-förmig** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt den Dollarumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im U-förmigen Modell.

**Umsatz - W-förmig** | Touchpoint der Käuferzuordnung

Dieses Feld zeigt den Dollarumsatz, der einem Touchpoint zugeordnet wird, in Abhängigkeit vom Attributionsprozentsatz im W-förmigen Modell.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

S

**Salesforce Campaign** | Buyer Touchpoint, Buyer Attribution Touchpoint

In diesem Feld wird die Salesforce-Kampagne angezeigt, zu der der Touchpoint gehört.

**Suchbegriff** | Buyer Touchpoint, Buyer Attribution Touchpoint

Wenn der Touchpoint aus einer gebührenpflichtigen oder kostenlosen Suche stammt, zeigt dieses Feld den in die Suchmaschine eingegebenen Suchbegriff an. Aus Datenschutzgründen sind diese Informationen jedoch in der Regel nicht verfügbar.

**Segment** | Touchpoint der Käuferzuordnung

In diesem Feld werden die Segmente angezeigt, zu denen der Touchpoint gehört. Dies hängt davon ab, wie Sie Ihre Segmentierungsregeln in der Marketo Measure-App konfiguriert haben.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

D

**Touchpoint-Datum** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint aus einer Online-Quelle stammt, zeigt dieses Feld das Datum und die Uhrzeit des Touchpoints an.

`2)` Wenn der Touchpoint von einem Offline-Ereignis stammt, zeigt dieses Feld das in der Salesforce-Kampagne festgelegte Datum und die Uhrzeit oder das in den Kampagnen-Synchronisierungsregeln ausgewählte Datumsfeld an.

`3)` Wenn der Touchpoint aus einer Aktivität stammt, zeigt dieses Feld das Datum und die Uhrzeit des Felds an, das in den Aktivitätsregeln als Touchpoint-Datum ausgewählt wurde.

**Touchpoint-Datum (FT)** | Käufer Touchpoint

Dies ist dasselbe Feld wie das Touchpoint-Datum, in diesem Feld werden jedoch insbesondere das Datum und die Uhrzeit des Erstkontakt-Touchpoints angezeigt.

**Touchpoint-Datum (LC)** | Käufer Touchpoint

Dies ist dasselbe Feld wie das Touchpoint-Datum. In diesem Feld werden jedoch insbesondere das Datum und die Uhrzeit des Kontaktpunkts &quot;Lead-Erstellung&quot;angezeigt.

**Touchpoint-Position** | Buyer Touchpoint, Buyer Attribution Touchpoint

Dieses Feld zeigt die Position des Touchpoints an. Die Position des Touchpoints spiegelt die wichtigsten Meilensteinkontaktpunkte im Kunden-Journey wider (d. h. FT, Form, LC, OC, Closed). Die Position des Touchpoints hängt davon ab, wann er auf der Journey des Kunden aufgetreten ist, und ein einzelner Touchpoint kann mehr als eine Position aufweisen. Die verschiedenen Touchpoint-Positionen lauten wie folgt:

Erstkontakt (FT) - Die allererste Marketing-Interaktion, die jemand mit Ihrer Marke hat

Lead Creation (LC) - Die allererste bekannte Marketing-Interaktion (normalerweise eine Formularübermittlung oder die Einbeziehung einer Salesforce-Kampagne)

Formular - Wenn ein Besucher ein Online-Formular ausfüllt

Opportunity Creation (OC) - Die Marketing-Interaktion, die dem Zeitpunkt der Erstellung der Opp am nächsten ist

Geschlossen - Die Marketing-Interaktion, die am nächsten ist, wenn die Opp geschlossen wird (Gewinner oder Verlust)

**Touchpoint-Quelle** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Wenn der Touchpoint von einer Paid Search stammt, zeigt dieses Feld den Namen der Anzeigenplattform an (AdWords/BingAds).

`2)` Wenn der Touchpoint aus einer organischen Suche stammt, zeigt dieses Feld den Namen der Suchmaschine an

`3)` Wenn nicht #1 oder #2 und der Wert utm_source in der URL der Landingpage für den Touchpoint vorhanden ist, wird dieser Wert hier angezeigt

`4)` Dies wird als CRM-Kampagne ausgefüllt, wenn der Touchpoint aus einer CRM-Kampagne generiert wird.

`5)` Dies wird als CRM-Aktivität ausgefüllt, wenn der Touchpoint von einer CRM-Aktivität generiert wird.

Wenn keines der oben genannten Felder, wird dieses Feld als &quot;Web Direct&quot; oder &quot;Web&quot; ausgefüllt.

**Touchpoint-Quelle (FT)** | Käufer Touchpoint

Dies ist dasselbe Feld wie die Touchpoint-Quelle . Dieses Feld zeigt jedoch speziell die Quelle des Erstkontakt-Touchpoints an.

**Touchpoint-Quelle (LC)** | Käufer Touchpoint

Dies ist dasselbe Feld wie die Touchpoint-Quelle . Dieses Feld zeigt jedoch speziell die Quelle des Touchpoints &quot;Lead-Erstellung&quot;an.

**Touchpoint-Typ** | Auf dem Touchpoint der Käuferzuordnung und dem Touchpoint der Käuferzuordnung gefunden.

In diesem Feld wird der Interaktionstyp des Touchpoints angezeigt. Sie wird wie folgt angezeigt: Webbesuch, Webformular oder Webchat für JavaScript-Touchpoints. Für CRM-Campaign-Touchpoints wird sie als CRM angezeigt. Es wird mit der Aufgabe oder dem Ereignistyp für Aktivitäts-Touchpoints gefüllt.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

U

**UniqueId** | Buyer Touchpoint, Buyer Attribution Touchpoint

Die jedem Touchpoint zugeordnete eindeutige ID

**Benutzer-ID** | Marketo Measure ABTest

Eindeutiger Identifikationscode für jeden Einsatz von Optimiely

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)

## V {#v}

**Variante** | Marketo Measure ABTest

Name der Variante des A/B-Tests

**Varianten-ID** | Marketo Measure ABTest

Der eindeutige Identifikationscode für jede A/B-Test-Variante.

[Klicken Sie hier , um zum Seitenanfang zurückzukehren.](#top)
