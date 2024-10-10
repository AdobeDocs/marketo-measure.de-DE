---
unique-page-id: 37355835
description: Touchpoint-Felder - [!DNL Marketo Measure]
title: Touchpoint Felder
exl-id: d6c2bd60-5341-4a52-939a-942afc093306
feature: Touchpoints
source-git-commit: 3424f8a63da40f8762defae1e6ae22ebe60530d0
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 0%

---

# Touchpoint Felder {#touchpoint-fields}

Wenn Kunden mit [!DNL Marketo Measure] integriert sind und keine direkte Tagging-Integration vorliegt, lehrt unser Customer Success-Team in der Vergangenheit unsere Kunden, ihre Landingpages entsprechend zu taggen, damit sie das richtige UTM-Format verwenden und ihre Anzeigen auflösen können. Einige dieser Kunden verwenden keine UTMs, sondern ihre eigenen Tagging-Parameter. Dies bedeutet, dass es sehr zeitaufwendig sein kann, alle ihre Landingpages in allen ihren Anzeigennetzwerken mit einer neuen Tagging-Struktur zu bearbeiten, die von [!DNL Marketo Measure] durchgesetzt wird. Um uns an ihre Tagging-Struktur anzupassen, akzeptieren wir jetzt benutzerdefinierte Parameter, die unseren Regeldefinitionen zugeordnet werden können. Das Ziel besteht darin, sich an die Verwendung benutzerdefinierter Tracking-Parameter durch Kunden anzupassen, sodass wir nicht verlangen müssen, dass sie ihre URL-Struktur ändern.

>[!AVAILABILITY]
>
>Verfügbar mit vollständiger Segmentierung in Tier-2-Abonnements.

>[!NOTE]
>
>Dies ist eine erweiterte Funktion, die nur von Professional Services eingerichtet werden sollte.

## Aktivieren der Funktion {#enabling-the-feature}

Navigieren Sie im Menü [!DNL Marketo Measure] Einstellungen zur Seite Touchpoint-Felder . Danach können Sie die Funktion aktivieren, indem Sie unter **Berechnete Felder aktivieren** die Option **Ja** auswählen. Nachdem die Funktion aktiviert wurde, können Sie Touchpoint-Felder erstellen.

![](assets/one.png)

## Verfahren {#how-to}

Um ein berechnetes Feld zu erstellen, sollten Sie beachten, dass ein Benutzer drei verschiedene Aktionen ausführen kann: Extrahieren, Zuordnen und Verketten von Feldern. Diese werden auch als Operatoren zur Definition eines berechneten Felds bezeichnet.

### Auszüge {#extracts}

Der Operator [!UICONTROL extrahiert ] ruft den Wert aus einem Feld von einem anderen Speicherort ab, z. B. einem Kampagnenfeld, einem Lead-Feld oder extrahieren Sie in einem erweiterten Anwendungsfall benutzerdefinierte Parameter aus der Landingpage. Anschließend wird es in ein Touchpoint-Feld eingefügt.

**Beispiel 1**

Es gibt ein benutzerdefiniertes Feld im Kontakt, campaign_source__c, das der Kunde zum Zweck der Berichterstellung auf dem Touchpoint ablegen möchte. Sie können eine Regel definieren, um ein berechnetes Feld namens &quot;Campaign Source&quot;zu erstellen und den Wert in dieses Feld zu ziehen.

Ziel: Verwenden Sie den Wert eines benutzerdefinierten Felds und platzieren Sie es auf das Touchpoint-Objekt, um die Berichterstellung zu vereinfachen.

* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Campaign Source&quot;.
* Definieren Sie die Regel, indem Sie mit der Suche nach dem Feld Contact.Campaign_Source__c beginnen.
* Verwenden Sie den Operator &quot;extracts&quot;, da wir den Wert aus dem Parameter abrufen müssen
* Um die vollständige Zeichenfolge aus dem Feld zu extrahieren, verwenden wir den Ausdruck &quot;(.&#42;)&quot;

   * **(** markiert den Beginn der Extraktion
   * **)** markiert das Ende der Extraktion
   * **.&#42;** gibt an, dass wir die vollständige Zeichenfolge extrahieren

![](assets/two.png)

**Beispiel 2**

Ein häufiges Nutzungsszenario, das diese Funktion ermöglicht, besteht darin, Werte aus benutzerdefinierten Parametern einer URL-Zeichenfolge zu extrahieren. Dies ist nützlich, wenn Sie andere Parameter als UTMs verwenden, die Werte jedoch in Touchpoint-Feldern analysieren möchten.

**Link:** `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=5OFF` oder `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=25OFF`.\
**Ziel:** Erstellen Sie ein benutzerdefiniertes Feld mit dem Namen &quot;Rabattcode&quot;und legen Sie den Wert &quot;5OFF&quot;oder &quot;25OFF&quot;ab, egal welcher Wert übergeben wird.

* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Rabattcode&quot;.
* Definieren Sie die Regel, indem Sie mit der Suche nach dem Feld Touchpoint.Session.LandingPage beginnen.
* Verwenden Sie den Operator &quot;extracts&quot;, da wir den Wert aus dem Parameter abrufen müssen
* Um den Wert des Angebots zu extrahieren, definieren wir den Wert als &quot;promo=(\w+)&quot;

   * **(** markiert den Beginn der Extraktion
   * **)** markiert das Ende der Extraktion
   * **\w** gibt an, dass wir ein &quot;Wort&quot;mit 0-9 extrahieren
   * **+** extrahiert den vollständigen Wert des Parameters ohne Zeichenbeschränkung
   * Beachten Sie, dass Sie einen Schrägstrich und keinen umgekehrten Schrägstrich verwenden.

![](assets/three.png)

**Beispiel 3**

Versuchen wir ein ähnliches Beispiel, in dem wir einen Trackingcode extrahieren, z. B.: `https://www.adobe.com/blog/marketing-revenue-reporting-overview?cid=123456`.

**Ziel:** Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Adobe Campaign ID&quot;mit dem Wert aus dem Parameter &quot;cid&quot;.

* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Adobe Campaign ID&quot;
* Definieren Sie die Regel, indem Sie mit der Suche nach dem Feld Touchpoint.Session.LandingPage beginnen.
* Verwenden Sie den Operator &quot;extracts&quot;, da wir den Wert aus dem Parameter abrufen müssen
* Um den Wert &quot;123456&quot;zu extrahieren, definieren wir den Wert als &quot;cid=(\d{6})&quot;

   * **(** markiert den Beginn der Extraktion
   * **)** markiert das Ende der Extraktion
   * **\d** gibt an, dass wir eine &quot;Ziffer&quot;extrahieren
   * **{6}** ist die Anzahl der Zeichen, die wir extrahieren

![](assets/four.png)

**Beispiel 4**

Da Ihre Landingpages komplizierter werden und Sie mehrere Tracking-Parameter haben, müssen Sie möglicherweise mehrere Touchpoint-Felder erstellen und Werte mehrmals extrahieren, z. B.:
`https://www.adobe.com/blog/marketing-revenue-reporting-overview?trackID=123456&country=US&campaign_ID=7890`.

**Ziel:** Erstellen Sie mehrere berechnete Felder für &quot;Zielland&quot;und &quot;Benutzerdefinierte Kampagnen-ID&quot;mit den entsprechenden Werten aus den Parametern.

* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Target Country&quot;
* Definieren Sie die Regel, indem Sie mit der Suche nach dem Feld Touchpoint.Session.LandingPage beginnen.
* Verwenden Sie den Operator &quot;extracts&quot;, da wir den Wert aus dem Parameter abrufen müssen
* Um den Wert &quot;US&quot;zu extrahieren, definieren wir den Wert als &quot;country=(\w{2})&quot;

   * **(** markiert den Beginn der Extraktion
   * **)** markiert das Ende der Extraktion
   * **\w** gibt an, dass wir ein &quot;Wort&quot;extrahieren
   * **{2}** ist die Anzahl der Zeichen, die wir extrahieren

* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Benutzerdefinierte Kampagnen-ID&quot;
* Definieren Sie die Regel, indem Sie mit der Suche nach dem Feld Touchpoint.Session.LandingPage beginnen.
* Verwenden Sie den Operator &quot;extracts&quot;, da wir den Wert aus dem Parameter abrufen müssen
* Um den Wert &quot;123456&quot;zu extrahieren, definieren wir den Wert als &quot;campaign_ID=(\d{6})&quot;

   * **(** markiert den Beginn der Extraktion
   * **)** markiert das Ende der Extraktion
   * **\d** gibt an, dass wir eine &quot;Ziffer&quot;extrahieren
   * **{6}** ist die Anzahl der Zeichen, die wir extrahieren

![](assets/five.png)

### Ordnet {#maps-to}

Der Operator [!UICONTROL ist ] zugeordnet, erstellt eine Tabelle mit Werten, die übersetzt oder in einen anderen Wert zusammengefasst werden müssen. Normalerweise hat dies die Form eines Schlüsselwerts, bei dem ein Code einen benutzerfreundlichen Namen darstellt und diesem Anzeigenamen zugeordnet werden muss.

**Beispiel 1**

Es gibt Kampagnen, die Sie für eine Werbeaktion zum Ende des Sommers und für eine Werbeaktion zum Black Friday erstellt haben und die über mehrere Kanäle laufen. Sie möchten ein berechnetes Feld mit dem Namen &quot;Initiative&quot;erstellen und alle Touchpoints mit einer Promotion zum Ende des Sommers oder einer Black Friday-Promotion einem Initiativwert wie &quot;Promotions&quot;zuordnen, zusätzlich zu anderen möglichen Werten.

![](assets/six.png)

**Beispiel 2**

Nachdem wir gelernt haben, wie wir Felder extrahieren und zuordnen können, lassen Sie uns diese Aktionen kombinieren, um zunächst einen Wert aus einem Parameter zu extrahieren und ihn dann einem benutzerfreundlichen Namen zuzuordnen, der etwas sinnvoller ist. Beginnen wir mit dieser Landingpage: `https://www.adobe.com/blog/marketing-revenue-reporting-overview?BZ=04-01-09-03-10`.

**Ziel:** Erstellen Sie mehrere berechnete Felder, bei denen die erste Zahl einer Region zugeordnet ist, die zweite einem Produkt, die dritte einer Initiative, die vierte einer Persona und die fünfte einer Medienplattform. Ordnen Sie dann den numerischen Wert einem &quot;Anzeigenamen&quot;zu.

* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Region&quot;
* Definieren Sie die Regel, indem Sie mit der Suche nach dem Feld Touchpoint.Session.LandingPage beginnen.
* Verwenden Sie den Operator &quot;[!UICONTROL extracts]&quot;, da wir den Wert aus dem Parameter abrufen müssen
* Um den Wert &quot;04&quot;zu extrahieren, definieren wir den Wert als &quot;BZ=(\d{2})-\d{2}-\d{2}-\d{2}-\d{2}&quot;.

   * **(** markiert den Beginn der Extraktion

      * Beachten Sie, dass nur die ersten Ziffern die offene Klammer aufweisen, da wir nur die 4 extrahieren
   * **)** markiert das Ende der Extraktion

      * Beachten Sie, dass nur die ersten Ziffern die geschlossene Klammer aufweisen, da wir nur die 4 extrahieren.
   * **\d** gibt an, dass wir eine &quot;Ziffer&quot;extrahieren
   * **{2}** ist die Anzahl der Zeichen, die wir extrahieren



* Klicken Sie auf [!UICONTROL Speichern]. Sie müssen Ihr neues Feld speichern, bevor es für die nächste Regel verwendet werden kann!
* Als Nächstes möchten wir alle möglichen Werte für die ersten Ziffern den Anzeigenamen zuordnen.
* Erstellen Sie ein berechnetes Feld und beschriften Sie es mit &quot;Region_Name&quot;.
* Definieren Sie die Regel, indem Sie mit der Suche nach Ihrem extrahierten Feld beginnen. In diesem Fall [!DNL Touchpoint.Region]
* Verwenden Sie den Operator &quot;[!UICONTROL ist ] zugeordnet&quot;, da wir für jede Zahl eine Zuordnung zu ihrem Wert erstellen möchten
* Sie erhalten eine Tabelle, in der Sie die einzelnen Zuordnungen auflisten können. Am Ende sieht es ungefähr so aus:
* Basierend auf der Zuordnung und der obigen URL lautet der &quot;Region_Value&quot; für einen Touchpoint mit dieser Landingpage &quot;EMEA&quot;.
* Wiederholen Sie die Extraktion und die Zuordnung für die restlichen vier Ziffernsätze.

   * Um den 01 zu extrahieren, definieren Sie den Wert als &quot;BZ=\d{2}-**(\d{2})**-\d{2}-\d{2}-\d{2}&quot;.
   * Um den 09 zu extrahieren, definieren Sie den Wert als &quot;BZ=\d{2}-\d{2}-**(\d{2})**-\d{2}-\d{2}&quot;.
   * Um den 03 zu extrahieren, definieren Sie den Wert als &quot;BZ=\d{2}-\d{2}-\d{2}-**(\d{2})**-\d{2}&quot;.
   * Um den 10 zu extrahieren, definieren Sie den Wert als &quot;BZ=\d{2}-\d{2}-\d{2}-\d{2}-**(\d{2})**&quot;

![](assets/seven.png)

### Konkatenate {#concatenates}

Der Operator [!UICONTROL  verkettet ] Werte aus mehreren Feldern zu einem Feld. Dies ist nützlich, um einen benutzerdefinierten Wert zu erstellen, der Daten über verschiedene Felder hinweg abruft, um

**Beispiel 1**

Es gibt separate Felder im Opportunity-Objekt für Segment__c und Grade__c, die der Benutzer zu Berichterstellungszwecken zu einem einzelnen Feld im Touchpoint-Objekt kombinieren möchte. Durch Verketten der Felder werden Werte wie Enterprise_A oder Mid-Market_B angezeigt.

![](assets/eight.png)

## Touchpoint-Felder und -Segmente {#touchpoint-fields-and-segments}

Nachdem die Werte aus Ihrer URL analysiert wurden und auf dem Touchpoint vorhanden sind, werden die neuen Felder überall dort angezeigt, wo Touchpoint-Felder verwendet werden, z. B. beim Erstellen von Segmenten oder beim Definieren von Touchpoint-Löschregeln.

In dieser Produktversion ist die Möglichkeit verfügbar, Segmente mithilfe von Touchpoint-Feldern zu erstellen. Segmente konnten zuvor nicht mit Touchpoint-Feldern erstellt werden.

![](assets/nine.png)

Um das Erstellen von Segmenten zu vereinfachen, ist es jetzt möglich, dynamische Segmente aus den erstellten Touchpoint-Feldern zu erstellen. Wenn Sie beispielsweise ein Touchpoint-Feld erstellt haben, das eine geografische Region analysiert hat, anstatt ein Segment für jede mögliche Region zu erstellen, können Sie ein Segment einrichten und wir erstellen für jede Instanz Segmente, für die ein neuer Wert angezeigt wird. Dies ist äußerst hilfreich, wenn ein Attribut wie die Postleitzahl analysiert und als Segment verwendet werden muss!

Ihr Setup würde ungefähr so aussehen wie der Screenshot unten. Der Segmentname ruft den Wert des Touchpoint-Felds dynamisch mit den geschweiften Klammern ab, um nach Ihrem Feld zu suchen.

![](assets/ten.png)

Die Regel verweist auf dasselbe Touchpoint-Feld und sucht nach Werten, die &quot;nicht gleich null&quot;sind.

![](assets/eleven.png)

## FAQs {#faq}

**Gibt es eine maximale Anzahl von Touchpoint-Feldern, die wir erstellen können?**

Es sind maximal 100 Felder erlaubt.

**Ich sehe mein neues Touchpoint-Feld nicht, das ich gerade in der Auswahlliste erstellt habe. Wo ist es?**

Vergessen Sie nicht, Ihre Regeln zu speichern, nachdem Sie sie erstellt haben. Wenn Ihr neues Feld nicht angezeigt wird, überprüfen Sie, ob Sie gespeichert haben. Sie müssen Ihr neues Feld speichern, bevor es für die nächste Regel verwendet werden kann.

>[!NOTE]
>
>Aufgrund der Komplexität ist ein Touchpoint-Feld, das den Operator &quot;Maps zu&quot;verwendet, nicht für die Verwendung in einem anderen Touchpoint-Feld verfügbar.

**Welchen Ausdruck verwende ich, um mehrere Parameter aus einer einzelnen Landingpage zu extrahieren?**

Wie im Extract-Beispiel Nr. 4 müssen Sie mehrere Felder erstellen, um jeden Parameter zu extrahieren. Wenn Sie also fünf verschiedene Werte haben, erstellen Sie fünf Touchpoint-Felder, um sie zu extrahieren.

**Warum sehe ich meine neuen Felder nicht im [!DNL Marketo Measure]-Schema?**

Es sind zusätzliche Arbeiten erforderlich, um die neuen Felder im Data Warehouse-Schema [!DNL Marketo Measure] verfügbar zu machen. Derzeit werden Felder über Einstellungen und Konfigurationen offen gelegt, sodass Sie die Touchpoint-Felder beim Erstellen von Segmenten oder Erstellen von Touchpoint-Löschregeln verwenden können.

**Wie kann ich überprüfen, ob mein Extraktionsausdruck gültig ist, und den richtigen Wert abrufen?**

Es gibt ein Online-Tool ([[!DNL https]://regex101.com/](https://regex101.com/){target="_blank"}), mit dem Sie den Ausdruck ausführen und testen können. Der Ausdruck wird grün angezeigt, wenn er gültig ist, oder rot, wenn er ungültig ist. Außerdem ist das Feld [!UICONTROL Erläuterung] oben rechts hilfreich und teilt Ihnen mit, was Sie extrahieren.

![](assets/twelve.png)

![](assets/thirteen.png)
