---
unique-page-id: 18874795
description: Hinzufügen [!DNL Marketo Measure] Script - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 57%

---

# Hinzufügen eines[!DNL Marketo Measure]-Skriptes {#adding-marketo-measure-script}

[!DNL Marketo Measure]-JavaScript, das von [!DNL Marketo Measure] nachverfolgt werden soll, muss so schnell wie möglich zu allen Web-Umgebungen hinzugefügt werden. Sobald das JavaScript bereitgestellt ist, [!DNL Marketo Measure] beginnt mit der Erfassung Ihrer digitalen Daten. In diesem Artikel werden die Methoden zur Bereitstellung von [!DNL Marketo Measure] JavaScript und weitere Hinweise.

>[!NOTE]
>
>Vergewissern Sie sich, dass Sie zusätzlich zur [!DNL Marketo Measure]-JavaScript-Bereitstellung [alle entsprechenden Domains in [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} eingefordert haben.

Während der ersten Schritte mit [!DNL Marketo Measure] gibt es zwei Möglichkeiten, [!DNL Marketo Measure]-JavaScript zu Ihrer Website hinzuzufügen:

* Hartcodierung
* Tag-Management-Systeme

## Hartcodierung {#hard-coding}

Als Best Practice empfehlen wir dringend eine [!DNL Marketo Measure]-JavaScript-Hartcodierung in Ihren Web-Umgebungen. Um das Skript zu hartcodieren, müssen Sie das Skript vor dem schließenden einfügen `</head>` auf jeder Seite Ihrer Site.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Hartkodierung des JavaScripts in der `<head>` Ihrer Seiten stellen sicher, dass die [!DNL Marketo Measure] -Skript zuerst geladen wird und Verweisinformationen nicht fehlen. [!DNL Marketo Measure]-JavaScript wird asynchron geladen. Im Falle einer Hartcodierung muss das JavaScript manuell zur Marketing-Automatisierung hinzugefügt werden.

>[!TIP]
>
>Erfahren Sie, wie Sie sicherstellen, dass Ihr Skript [DSGVO-konform](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}.

## Tag-Management-Systeme {#tag-management-systems}

Wenn [!DNL Marketo Measure] JavaScript kann nicht über die Hardware programmiert werden. Eine weitere Möglichkeit besteht darin, die [!DNL Marketo Measure] Skripten mit einem Tag Management-System, z. B. [!DNL Google Tag Manager] (GTM) oder Tealium.

Verwenden von Tag-Management-Systemen zur Bereitstellung [!DNL Marketo Measure] JS kann aufgrund der Latenz der Skriptladezeit zu einem potenziellen Datenverlust von 5-10 % führen. Wenn das Tag-Management-Tool nicht schnell genug geladen wird, kann auch [!DNL Marketo Measure]-JS nicht schnell genug geladen werden und es können Informationen zum ersten Referrer verloren gehen.

Üblicherweise wird [!DNL Marketo Measure]-JS so lange über ein Tag-Management-Tool bereitgestellt, bis es aus Timing-/Ressourcengründen besser ist, auf eine Hartcodierung umzustellen.

Hinzufügen von [!DNL Marketo Measure] -Skript über eine Tag-Management-Lösung erstellen, müssen Sie ein -Tag erstellen und unser JavaScript darin hinzufügen. Wenden Sie dieses Tag auf alle Seiten Ihrer Website an, die nachverfolgt werden sollen.

[!DNL Marketo Measure] empfiehlt, dass das Tag bei jeder Seitenansicht ausgelöst wird. Außerdem ist es am besten, [!DNL Marketo Measure] die höchste Priorität in der Auslöserreihenfolge und stellen Sie sicher, dass keine synchronen Skripte vor der [!DNL Marketo Measure] -Tag, um die höchste Datenqualität sicherzustellen.

Weitere Informationen [finden Sie hier](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## Zusätzliche Überlegungen {#additional-considerations}

[!DNL Marketo Measure]-JavaScript ist Domain-basiert, sodass automatisch alle Sub-Domains verarbeitet werden können, solange sich das JavaScript auf den Seiten befindet und die Stamm-Domain mit der Domain übereinstimmt, die zum Erstellen des Marketo Measure-Kontos verwendet wurde.

Wenn Sie jedoch separate oder internationale Domains verwenden, sollten Sie Ihre [!DNL Marketo Measure]-Beratungsperson darüber informieren. Die Domänen müssen Ihrem Konto auf der Seite [!DNL Marketo Measure] so zu beenden, dass [!DNL Marketo Measure] weiß, dass die Daten der zusätzlichen Domänen mit Ihrem Konto verknüpft werden sollen. Senden Sie also separate/internationale Domänen an Ihre [!DNL Marketo Measure] Berater.

Wenn Sie Seiten von Drittanbietern verwenden, unterhalten Sie sich mit Ihrem [!DNL Marketo Measure] Berater. Im Allgemeinen möchten Sie wissen, ob Sie eine benutzerdefinierte Version von [!DNL Marketo Measure] JavaScript verwenden, um diese Seiten gegebenenfalls zu verfolgen. Ist dies nicht möglich, wird das Tracking über CRM-Campaign-Touchpoints mit Ihren [!DNL Marketo Measure] Berater.

Verfügen Sie über Formulare, die NICHT nachverfolgt werden sollen? [!DNL Marketo Measure] da sie nicht unbedingt für die Attribution sinnvoll sind (z. B. Abmeldeformulare, Kundenanmeldungen usw.)? In diesem Fall sollten Sie den Ausschlusscode hinzufügen [in diesem Artikel](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} zu jedem Formular

Verfügen Sie über Seiten, die nicht sicher sind? Sie sollten sie schützen, da die Navigation zwischen einer sicheren/nicht sicheren Seite die Tracking-Sitzung unterbricht.

Sprechen Sie mit Ihrem Webteam, damit es weiß, dass [!DNL Marketo Measure]-JavaScript immer in den entsprechenden Web-Umgebungen vorhanden sein sollte. Wenn neue Seiten/Formulare/Sites eingeführt werden, stellen Sie sicher, dass die Bereitstellung von [!DNL Marketo Measure]-JavaScript Teil des Protokolls ist.

Wenn eine [!DNL Web Application Firewall (WAF)] -Warnung während des JavaScript-Setups ausgelöst wird, können Benutzer diese WAF-Regel deaktivieren oder die Cookies von Zulassungslisten wie unten dargestellt abbrechen:

![](assets/adding-marketo-measure-script-1.png)

## Formulare, auf die besonders zu achten ist {#forms-to-pay-extra-attention-to}

**Übermittlung mehrerer Formulare**

* Problem: Wenn Sie mehrere verknüpfte Formulare als Teil einer Formularübermittlung haben, kann es sein, dass das erste Formular einen Touchpoint generiert, auch wenn das vollständige Formular nicht gesendet wurde.
* Lösung: Sie müssen eines der Formulare erzwingen, den Benutzer an zu melden. [!DNL Marketo Measure] auf der Grundlage zwischengespeicherter Daten und über Abbruchsverfahren. Im Allgemeinen lässt sich dieses Problem durch [Melden des Benutzer-Codes](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} lösen.

**Kontoanmeldung (keine Erstellung)**

* Problem: [!DNL Marketo Measure] empfiehlt, keine Touchpoints für nachfolgende Kontoanmeldungen zu erstellen, da diese dazu neigen, die Attributionshistorie zu verwässern.
* Lösung: Fügen Sie dem Konto-/Kunden/Partner-Anmeldeformular einen Ausschluss-Code hinzu.

>[!NOTE]
>
>Es wird empfohlen, einen Touchpoint für die Erstellung eines Kontos oder einer Testversion zu erstellen.

**Herunterladen von Assets**

* Problem: Wenn Ihre Assets erfasst sind, [!DNL Marketo Measure] verfolgt Downloads als Formularelemente. Ohne Gating der Assets gibt es Einschränkungen dahingehend, was ohne Anpassung gemeldet werden kann.
* Lösung: Führen Sie ein Gating des Assets durch, wenn es vom [!DNL Marketo Measure]-JavaScript nachverfolgt werden soll. Wenn dies keine Option ist und Sie dennoch einen Touchpoint dafür benötigen, sollten Sie stattdessen eine CRM-Kampagne synchronisieren.

**iFrames**

* Problem: iFrames funktionieren im Grunde als Seiten innerhalb von Seiten.
* Lösung: Die [!DNL Marketo Measure] JS muss direkt im iFrame-Header bereitgestellt werden, damit wir ihn korrekt anhängen können.

**Lightboxes**

* Lightboxes sind normalerweise Popups, die iFrames enthalten
* Lösung: [!DNL Marketo Measure]-JS muss im Header dieses gehosteten iFrames bereitgestellt werden.

**Mehrere Formulare auf einer Seite**

* Problem: Wenn mehrere Formulare auf einer Seite gehostet werden, können Sie unter Umständen nicht erkennen, welches Formular mit dem [!DNL Marketo Measure]-Formular-URL-Feld ausgefüllt wurde.
* Lösung: Wenn Sie wissen müssen, welches Formular ausgefüllt wurde, sollten Sie mit Ihrem Webteam das Einrichten eines dynamischen URL-Hashings erkunden.

**Im `<div>`-Format organisierte Formulare**

* Problem: [!DNL Marketo Measure]-JS hat Schwierigkeiten, im `<div>`-Format organisierte Formulare zu erkennen, sodass unter Umständen benutzerdefinierter Code benötigt wird.
* Lösung: Diese [Vorlagen zum Melden von Benutzenden](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} können von Ihrem Web-Entwicklungs-Team verwendet werden, um den erforderlichen Code hinzuzufügen.

**Chat**

* Problem: Wenn Sie einen Chat-Anbieter verwenden, kann eine besondere Vorgehensweise erforderlich sein.
* Lösung: [!DNL Marketo Measure] kann in Drift, Olark, Livechat, LivePerson und SnapEngage integriert werden. Alle anderen Plattformen müssen über die Zugehörigkeit zu einer CRM-Kampagne nachverfolgt werden.

**Zweite Domain**

* Problem: [!DNL Marketo Measure] JavaScript ist domänenspezifisch, daher müssen für jede separate oder internationale Domäne zusätzliche Schritte unternommen werden. [!DNL Marketo Measure] JS kann Subdomains auf derselben Stammdomäne verarbeiten.
* Lösung: Wenn Sie über mehrere Stamm-Domains verfügen, die von [!DNL Marketo Measure] nachverfolgt werden sollen, fügen Sie JS zu den Domains hinzu UND informieren Sie Ihre [!DNL Marketo Measure]-Beratungsperson darüber, welche Domains manuell mit Ihrem [!DNL Marketo Measure]-Konto verknüpft werden sollen.

## Testen von [!DNL Marketo Measure]-JavaScript {#testing-marketo-measure-javascript}

Ihre [!DNL Marketo Measure] Ein Berater hilft Ihnen, die Website vor Ort zu testen, um sicherzustellen, dass [!DNL Marketo Measure] JavaScript ist auf allen Seiten vorhanden. Teil dieses Tests ist das Senden einiger Formulare mit klar angegebenen Testdetails, um sicherzustellen, dass das Tracking ordnungsgemäß zurückgegeben wird.

Allerdings ist Ihre [!DNL Marketo Measure]-Beratungsperson mit Ihrer Website wahrscheinlich nicht so vertraut wie Ihr Webteam. Aus diesem Grund ist es sehr wichtig, dass Ihr Webteam oder ein anderes entsprechendes Team die Website gründlich prüft. Dies gilt insbesondere dann, wenn komplexe Formulare wie die oben genannten verwendet werden. Ihr Team ist letztendlich dafür verantwortlich sicherzustellen, dass alle erforderlichen Web-Umgebungen ordnungsgemäß nachverfolgt werden. Wenn Sie jedoch von komplexen Formularen oder Situationen Kenntnis haben, können Sie Ihre [!DNL Marketo Measure]-Beratungsperson um Unterstützung bei den Tests bitten.

Gehen Sie wie folgt vor, um ein Formular selbst zu testen:

1. Verwenden Sie immer einen Inkognito-Browser oder leeren Sie Ihren Cache vor jedem Formularübermittlungstest UND verwenden Sie jedes Mal eine andere E-Mail-Adresse.

   a. Es empfiehlt sich, eine fingierte E-Mail-Adresse zu verwenden, bei der ersichtlich ist, dass es sich um einen Test handelt, und in der die Uhrzeit enthalten ist, z. B. testing830am@test.com.

1. Notieren Sie sich die URL der Seite, die Sie das Formular senden, und die verwendete E-Mail.

1. Suchen Sie den Datensatz, der in Ihrem CRM-System (Lead oder Kontakt) für die Formularübermittlung erstellt wurde, und überprüfen Sie, ob ein Touchpoint ordnungsgemäß erstellt wurde.

   a. Sie können einen [!DNL Marketo Measure]-Stock-Bericht wie Leads mit Buyer Touchpoints verwenden oder sich das Lead-/Kontakt-Seiten-Layout ansehen, wenn Sie Ihre Seiten-Layouts mit [!DNL Marketo Measure]-Details aktualisieren.

   b. Dies könnte einige Zeit in Anspruch nehmen, bis die Daten verarbeitet werden.
