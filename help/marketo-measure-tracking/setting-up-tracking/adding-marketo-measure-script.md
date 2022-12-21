---
unique-page-id: 18874795
description: Hinzufügen [!DNL Marketo Measure] Script - [!DNL Marketo Measure] - Produktdokumentation
title: Hinzufügen [!DNL Marketo Measure] Skript
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# Hinzufügen [!DNL Marketo Measure] Skript {#adding-marketo-measure-script}

[!DNL Marketo Measure] JavaScript, das Sie verfolgen möchten [!DNL Marketo Measure] sollte so bald wie möglich allen Webeigenschaften hinzugefügt werden. Sobald das JavaScript bereitgestellt ist, [!DNL Marketo Measure] beginnt mit der Erfassung Ihrer digitalen Daten. In diesem Artikel werden die Methoden zur Bereitstellung von [!DNL Marketo Measure] JavaScript und weitere zu berücksichtigende Aspekte.

>[!NOTE]
>
>Vergewissern Sie sich, dass Sie [forderte alle geeigneten Domänen in der [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target=&quot;_blank&quot;} zusätzlich zur Bereitstellung des [!DNL Marketo Measure] JavaScript.

Erste Schritte mit [!DNL Marketo Measure], gibt es zwei Möglichkeiten, den [!DNL Marketo Measure] JavaScript auf Ihrer Website:

* Hartkodierung
* Tag Management Systems

## Hartkodierung {#hard-coding}

Als Best Practice empfehlen wir dringend die Hartkodierung [!DNL Marketo Measure] JavaScript auf Ihre Webeigenschaften anwenden. Um das Skript zu hartcodieren, müssen Sie das Skript vor dem schließenden einfügen `</head>` auf jeder Seite Ihrer Site.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Hartkodierung des JavaScripts in der `<head>` Ihrer Seiten stellen sicher, dass [!DNL Marketo Measure] wird zuerst geladen und Verweisinformationen werden nicht verpasst. Die [!DNL Marketo Measure] JavaScript wird asynchron geladen. Bei Hardcodierung muss das JavaScript manuell zur Marketing-Automatisierung hinzugefügt werden.

>[!TIP]
>
>Erfahren Sie, wie Sie sicherstellen, dass Ihr Skript [DSGVO-konform](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target=&quot;_blank&quot;}.

## Tag Management Systems {#tag-management-systems}

Wenn [!DNL Marketo Measure] JavaScript kann nicht per Hardcodierung erstellt werden. Eine weitere Möglichkeit besteht darin, die [!DNL Marketo Measure] Skripten mit einem Tag Management-System wie [!DNL Google Tag Manager] (GTM) oder Tealium.

Beachten Sie, dass Sie mithilfe von Tag-Management-Systemen [!DNL Marketo Measure] JS kann aufgrund der Latenz der Skriptladezeit zu einem potenziellen Datenverlust von 5-10 % führen. Wenn das Tag-Management-Tool nicht schnell genug geladen wird, [!DNL Marketo Measure] JS kann auch nicht schnell genug geladen werden und kann Informationen zum ersten Referrer verlieren.

Üblicherweise wird die Bereitstellung von [!DNL Marketo Measure] JS über ein Tag-Management-Tool verwenden, bis Timing/Ressourcenzuweisung besser auf die Hartkodierung umgestellt werden kann.

Hinzufügen [!DNL Marketo Measure] über eine Tag-Management-Lösung erstellen, müssen Sie ein neues Tag erstellen und unser JavaScript darin hinzufügen. Wenden Sie dieses Tag auf alle Seiten Ihrer Website an, die verfolgt werden sollen.

[!DNL Marketo Measure] empfiehlt, dass bei jeder Seitenansicht das -Tag ausgelöst wird. Außerdem ist es am besten, [!DNL Marketo Measure] die höchste Priorität in der Auslöserreihenfolge und stellen Sie sicher, dass keine synchronen Skripte vor der [!DNL Marketo Measure] -Tag, um die höchste Datenqualität sicherzustellen.

Weitere Informationen können [hier finden](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target=&quot;_blank&quot;}.

## Zusätzliche Überlegungen {#additional-considerations}

[!DNL Marketo Measure] JavaScript ist domänenbasiert, sodass automatisch alle Subdomains verarbeitet werden können, solange sich das JavaScript auf den Seiten befindet und die Stammdomäne mit der Domäne übereinstimmt, die zum Erstellen des Marketo Measurement-Kontos verwendet wurde.

Wenn Sie jedoch separate oder internationale Domänen verwenden, sollten Sie sicherstellen, dass Ihre [!DNL Marketo Measure] Berater wissen es. Die Domäne(n) muss manuell zu Ihrem Konto im [!DNL Marketo Measure] so zu beenden, dass [!DNL Marketo Measure] erkennt, dass die Daten der zusätzlichen Domänen mit Ihrem Konto verknüpft werden. Senden Sie also bitte jede separate/internationale Domäne an Ihre [!DNL Marketo Measure] Berater.

Wenn Sie Seiten von Drittanbietern verwenden, unterhalten Sie sich mit Ihrem [!DNL Marketo Measure] Berater. Im Allgemeinen möchten Sie wissen, ob Sie eine benutzerdefinierte Version von [!DNL Marketo Measure] JavaScript verwenden, um diese Seiten gegebenenfalls zu verfolgen. Ist dies nicht möglich, wird das Tracking über CRM-Campaign-Touchpoints mit Ihren [!DNL Marketo Measure] Berater.

Verfügen Sie über Formulare, die NICHT nachverfolgt werden sollen? [!DNL Marketo Measure] da sie nicht unbedingt für die Attribution sinnvoll sind (z. B. Abmeldeformulare, Kundenanmeldungen usw.)? Wenn ja, sollten Sie den Ausschlusscode hinzufügen [in diesem Artikel](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target=&quot;_blank&quot;} für jedes Formular

Haben Sie nicht sichere Seiten? In diesem Fall sollten Sie sie schützen, da die Navigation zwischen einer sicheren/nicht sicheren Seite die Tracking-Sitzung unterbricht.

Stellen Sie sicher, dass Sie sich mit Ihrem Web-Team unterhalten, damit es weiß [!DNL Marketo Measure] JavaScript sollte sich immer in den entsprechenden Webeigenschaften befinden. Wenn neue Seiten/Formulare/Sites eingeführt werden, stellen Sie sicher, dass Sie [!DNL Marketo Measure] JavaScript ist Teil des Protokolls.

Wenn eine [!DNL Web Application Firewall (WAF)] -Warnung während des JavaScript-Setups ausgelöst wird, können Benutzer die WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![](assets/adding-marketo-measure-script-1.png)

## Forms widmet {#forms-to-pay-extra-attention-to}

**Übermittlung mehrerer Formulare**

* Problem: Wenn Sie mehrere verknüpfte Formulare als Teil einer Formularübermittlung haben, kann es sein, dass das erste Formular einen Touchpoint generiert, auch wenn das gesamte Formular nicht übermittelt wird.
* Lösung: Sie müssen eines der Formulare erzwingen, den Benutzer zu melden. [!DNL Marketo Measure] auf der Grundlage zwischengespeicherter Daten und über Abbruchsverfahren. Im Allgemeinen [Benutzer-Code des Berichts](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;} kann dies lösen.

**Kontoanmeldung (keine Erstellung)**

* Problem: [!DNL Marketo Measure] empfiehlt, keine Touchpoints für nachfolgende Kontoanmeldungen zu erstellen, da diese dazu neigen, die Attributionsgeschichte zu verwässern.
* Lösung: Fügen Sie dem Anmeldeformular für Konto/Kunde/Partner den Ausschließen-Code hinzu.

>[!NOTE]
>
>Es wird empfohlen, einen Touchpoint für die Erstellung eines Kontos oder einer Testversion zu erstellen.

**Herunterladen von Assets**

* Problem: Wenn Ihre Assets erfasst werden, [!DNL Marketo Measure] verfolgt Downloads beim Ausfüllen des Formulars. Wenn Ihre Assets nicht erfasst werden, gibt es Einschränkungen für das, worüber wir ohne Anpassung berichten können.
* Lösung: Greifen Sie das Asset zu, wenn Sie es verfolgen möchten. [!DNL Marketo Measure] JavaScript. Wenn dies keine Option ist und Sie dennoch einen Touchpoint dafür benötigen, sollten Sie stattdessen eine CRM-Kampagne synchronisieren.

**iFrames**

* Problem: iFrames funktionieren im Wesentlichen als Seiten innerhalb von Seiten.
* Lösung: Die [!DNL Marketo Measure] JS muss direkt im iFrame-Header bereitgestellt werden, damit wir das Formular korrekt anhängen können.

**Lightboxes**

* Lightboxes sind normalerweise Popups, die iFrames enthalten
* Lösung: die [!DNL Marketo Measure] JS muss in der Kopfzeile dieses gehosteten iFrame bereitgestellt werden.

**Mehrere Formulare auf einer Seite**

* Problem: Wenn mehrere Formulare auf einer Seite gehostet werden, können Sie möglicherweise nicht feststellen, welches bestimmte Formular mit der Variablen [!DNL Marketo Measure] Feld Formular-URL .
* Lösung: Wenn Sie wissen müssen, welches Formular ausgefüllt wurde, sollten Sie die Einrichtung eines dynamischen URL-Hashings mit Ihrem Webteam konsultieren.

**Forms organisiert in `<div>` format**

* Problem: [!DNL Marketo Measure] Es fällt JS schwer, Formulare zu erkennen, die in `<div>` formatieren, damit benutzerdefinierter Code benötigt werden kann.
* Lösung: Diese [Berichtsbenutzervorlagen](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;} kann von Ihrem Web-Entwicklungsteam verwendet werden, um den erforderlichen Code hinzuzufügen.

**Chat**

* Problem: Wenn Sie einen Chat-Provider verwenden, kann eine besondere Behandlung erforderlich sein.
* Lösung: [!DNL Marketo Measure] integriert in Drift, Olark, Livechat, LivePerson und SnapEngage. Alle anderen Plattformen müssen über die Mitgliedschaft in einer CRM-Kampagne verfolgt werden.

**Zweite Domäne**

* Problem: [!DNL Marketo Measure] JavaScript ist domänenspezifisch, daher müssen für jede separate oder internationale Domäne zusätzliche Schritte unternommen werden. Beachten Sie Folgendes: [!DNL Marketo Measure] JS kann Subdomains auf derselben Stammdomäne verarbeiten.
* Lösung: Wenn Sie über mehrere Stammdomänen verfügen, die Sie verfolgen möchten [!DNL Marketo Measure] Stellen Sie sicher, dass JS zu den Domänen hinzugefügt wird, UND lassen Sie Ihre [!DNL Marketo Measure] Berater, die wissen, welche Domänen manuell mit Ihrer [!DNL Marketo Measure] -Konto.

## Test [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

Ihre [!DNL Marketo Measure] Ein Berater hilft Ihnen, die Website vor Ort zu testen, um sicherzustellen, dass [!DNL Marketo Measure] JavaScript ist auf allen Seiten vorhanden. Teil dieser Tests sind die Übermittlung einiger Formularausfüllungen mit eindeutig angegebenen Testdetails, um sicherzustellen, dass das Tracking ordnungsgemäß zurückgegeben wird.

Allerdings muss Ihre [!DNL Marketo Measure] Der Berater ist mit Ihrer Website wahrscheinlich nicht so vertraut wie Ihr Webteam. Aus diesem Grund ist es sehr wichtig, dass Ihr Webteam oder ein anderes entsprechendes Team die Website gründlich prüft, insbesondere wenn komplexe Formulare wie die oben genannten verwendet werden. Ihr Team ist letztendlich dafür verantwortlich sicherzustellen, dass alle erforderlichen Webeigenschaften ordnungsgemäß verfolgt werden. Wenn Sie jedoch von komplexen Formularen oder Situationen Kenntnis haben, können Sie Ihre [!DNL Marketo Measure] Berater für Unterstützung bei Tests.

Gehen Sie wie folgt vor, um ein Formular selbst zu testen:

1. Verwenden Sie immer einen Inkognito-Browser oder leeren Sie Ihren Cache zwischen jedem Formularübermittlungstest UND verwenden Sie jedes Mal eine andere E-Mail-Adresse.

   a. Es empfiehlt sich, eine gefälschte E-Mail zu verwenden, die angibt, dass es sich um einen Test und eine Tageszeit handelt. Beispiel: testing830am@test.com

1. Notieren Sie die URL der Seite, die Sie das Formular senden, und die verwendete E-Mail.

1. Suchen Sie den Datensatz, der in Ihrem CRM-System (Lead oder Kontakt) für die Formularübermittlung erstellt wurde, und überprüfen Sie, ob ein Touchpoint ordnungsgemäß erstellt wurde.

   a. Sie können eine [!DNL Marketo Measure] Stock-Bericht wie Leads mit Käufer-Touchpoints oder das Layout der Lead-/Kontaktseite anzeigen, wenn Sie Ihre Seitenlayouts mit [!DNL Marketo Measure] Details.

   b. Beachten Sie, dass die Verarbeitung der Daten einige Zeit in Anspruch nehmen kann.
