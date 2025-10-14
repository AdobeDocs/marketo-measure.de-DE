---
unique-page-id: 18874795
description: Adding [!DNL Marketo Measure] script - [!DNL Marketo Measure]
title: Hinzufügen eines [!DNL Marketo Measure] -Skriptes
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 57%

---

# Hinzufügen eines[!DNL Marketo Measure]-Skriptes {#adding-marketo-measure-script}

[!DNL Marketo Measure]-JavaScript, das von [!DNL Marketo Measure] nachverfolgt werden soll, muss so schnell wie möglich zu allen Web-Umgebungen hinzugefügt werden. Nach der Bereitstellung von JavaScript beginnt [!DNL Marketo Measure] mit der Erfassung Ihrer digitalen Daten. In diesem Artikel werden die Methoden zur Bereitstellung [!DNL Marketo Measure] JavaScript und weitere Überlegungen beschrieben.

>[!NOTE]
>
>Vergewissern Sie sich, dass Sie zusätzlich zur [!DNL Marketo Measure]-JavaScript-Bereitstellung [alle entsprechenden Domains in [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} eingefordert haben.

Während der ersten Schritte mit [!DNL Marketo Measure] gibt es zwei Möglichkeiten, [!DNL Marketo Measure]-JavaScript zu Ihrer Website hinzuzufügen:

* Hartcodierung
* Tag-Management-Systeme

## Hartcodierung {#hard-coding}

Als Best Practice empfehlen wir dringend eine [!DNL Marketo Measure]-JavaScript-Hartcodierung in Ihren Web-Umgebungen. Um das Skript hartcodieren zu können, müssen Sie das Skript vor dem schließenden `</head>` auf jeder Seite Ihrer Site platzieren.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Durch die Hartkodierung des JavaScript in den `<head>` Ihrer Seiten wird sichergestellt, dass das [!DNL Marketo Measure]-Skript zuerst geladen wird und Verweisinformationen nicht verpasst werden. [!DNL Marketo Measure]-JavaScript wird asynchron geladen. Im Falle einer Hartcodierung muss das JavaScript manuell zur Marketing-Automatisierung hinzugefügt werden.

>[!TIP]
>
>Erfahren Sie, wie Sie sicherstellen können, dass Ihr Skript [DSGVO-konform](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"} ist.

## Tag-Management-Systeme {#tag-management-systems}

Wenn das Hinzufügen [!DNL Marketo Measure] JavaScript über eine Hartkodierung nicht möglich ist, besteht eine andere Möglichkeit darin, das [!DNL Marketo Measure]-Skript mithilfe eines Tag Management-Systems wie [!DNL Google Tag Manager] (GTM) oder Tealium hinzuzufügen.

Die Verwendung von Tag-Management-Systemen zur Bereitstellung von [!DNL Marketo Measure] JS kann zu einem potenziellen Datenverlust von 5-10 % aufgrund der Latenz der Skript-Ladezeit führen. Wenn das Tag-Management-Tool nicht schnell genug geladen wird, kann auch [!DNL Marketo Measure]-JS nicht schnell genug geladen werden und es können Informationen zum ersten Referrer verloren gehen.

Üblicherweise wird [!DNL Marketo Measure]-JS so lange über ein Tag-Management-Tool bereitgestellt, bis es aus Timing-/Ressourcengründen besser ist, auf eine Hartcodierung umzustellen.

Um [!DNL Marketo Measure] Skript über eine Tag-Management-Lösung hinzuzufügen, müssen Sie ein Tag erstellen und unsere JavaScript darin hinzufügen. Wenden Sie dieses Tag auf alle Seiten Ihrer Website an, die nachverfolgt werden sollen.

[!DNL Marketo Measure] empfiehlt, dass das Tag bei jeder Seitenansicht ausgelöst wird. Außerdem ist es am besten, [!DNL Marketo Measure] in der Auslösereihenfolge die höchste Priorität zuzuweisen und sicherzustellen, dass es keine synchronen Skripte vor dem [!DNL Marketo Measure]-Tag gibt, um die höchste Datenqualität sicherzustellen.

Weitere Informationen [finden Sie hier](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## Zusätzliche Überlegungen {#additional-considerations}

[!DNL Marketo Measure]-JavaScript ist Domain-basiert, sodass automatisch alle Sub-Domains verarbeitet werden können, solange sich das JavaScript auf den Seiten befindet und die Stamm-Domain mit der Domain übereinstimmt, die zum Erstellen des Marketo Measure-Kontos verwendet wurde.

Wenn Sie jedoch separate oder internationale Domains verwenden, sollten Sie Ihre [!DNL Marketo Measure]-Beratungsperson darüber informieren. Die Domains müssen [!DNL Marketo Measure] manuell zu Ihrem Konto hinzugefügt werden, damit [!DNL Marketo Measure] die zusätzlichen Domain-Daten mit Ihrem Konto verknüpfen kann. Senden Sie daher separate/internationale Domains an Ihren [!DNL Marketo Measure].

Wenn Sie Seiten von Drittanbietern verwenden, sprechen Sie mit Ihrem [!DNL Marketo Measure] Consultant über Ihren Anwendungsfall. Im Allgemeinen möchten Sie wissen, ob Sie eine benutzerdefinierte Version [!DNL Marketo Measure] JavaScript hinzufügen können, um diese Seiten ggf. zu verfolgen. Wenn dies nicht möglich ist, wird das Tracking über CRM-Campaign-Touchpoints mit Ihrem [!DNL Marketo Measure]-Berater untersucht.

Haben Sie Formulare, die NICHT von [!DNL Marketo Measure] nachverfolgt werden sollten, da sie für die Attribution nicht unbedingt sinnvoll sind (z. B. Abmeldeformulare, Kundenanmeldungen usw.)? In diesem Fall sollten Sie den Ausschlusscode ([&#x200B; diesem Artikel) &#x200B;](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} Formular hinzufügen

Verfügen Sie über Seiten, die nicht sicher sind? Sie sollten sie schützen, da die Navigation zwischen einer sicheren/nicht sicheren Seite die Tracking-Sitzung unterbricht.

Sprechen Sie mit Ihrem Webteam, damit es weiß, dass [!DNL Marketo Measure]-JavaScript immer in den entsprechenden Web-Umgebungen vorhanden sein sollte. Wenn neue Seiten/Formulare/Sites eingeführt werden, stellen Sie sicher, dass die Bereitstellung von [!DNL Marketo Measure]-JavaScript Teil des Protokolls ist.

Wenn während des JavaScript-Setups eine [!DNL Web Application Firewall (WAF)] ausgelöst wird, können Benutzerinnen und Benutzer diese WAF-Regel deaktivieren oder die Cookies auf die Zulassungsliste setzen, wie im folgenden Beispiel gezeigt:

![](assets/adding-marketo-measure-script-1.png)

## Formulare, auf die besonders zu achten ist {#forms-to-pay-extra-attention-to}

**Übermittlung mehrerer Formulare**

* Problem: Wenn Sie mehrere verknüpfte Formulare im Rahmen einer einzigen Formularübermittlung haben, erzeugt das erste Formular möglicherweise einen Touchpoint, auch wenn das gesamte Formular nicht übermittelt wurde.
* Lösung: Sie müssen eines der Formulare zwingen, den Benutzer auf der Grundlage zwischengespeicherter Daten an zu [!DNL Marketo Measure] und Abbruchpraktiken zu besprechen. Im Allgemeinen lässt sich dieses Problem durch [Melden des Benutzer-Codes](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} lösen.

**Kontoanmeldung (keine Erstellung)**

* Problem: [!DNL Marketo Measure] empfiehlt, keine Touchpoints für nachfolgende Kontoanmeldungen zu erstellen, da diese dazu neigen, die Attributionshistorie zu verwässern.
* Lösung: Fügen Sie dem Konto-/Kunden/Partner-Anmeldeformular einen Ausschluss-Code hinzu.

>[!NOTE]
>
>Es wird empfohlen, einen Touchpoint für die Erstellung eines Kontos oder einer Testversion zu erstellen.

**Herunterladen von Assets**

* Problem: Wenn Ihre Assets kategorisiert sind, verfolgt [!DNL Marketo Measure] Downloads beim Ausfüllen des Formulars. Ohne Gating der Assets gibt es Einschränkungen dahingehend, was ohne Anpassung gemeldet werden kann.
* Lösung: Führen Sie ein Gating des Assets durch, wenn es vom [!DNL Marketo Measure]-JavaScript nachverfolgt werden soll. Wenn dies keine Option ist und Sie dennoch einen Touchpoint dafür benötigen, sollten Sie stattdessen eine CRM-Kampagne synchronisieren.

**iFrames**

* Problem: iFrames funktionieren im Grunde als Seiten innerhalb von Seiten.
* Lösung: Das [!DNL Marketo Measure] JS muss direkt im iFrame-Header bereitgestellt werden, damit es ordnungsgemäß an das Formular angehängt werden kann.

**Lightboxes**

* Lightboxes sind normalerweise Popups, die iFrames enthalten
* Lösung: [!DNL Marketo Measure]-JS muss im Header dieses gehosteten iFrames bereitgestellt werden.

**Mehrere Formulare auf einer Seite**

* Problem: Wenn mehrere Formulare auf einer Seite gehostet werden, können Sie unter Umständen nicht erkennen, welches Formular mit dem [!DNL Marketo Measure]-Formular-URL-Feld ausgefüllt wurde.
* Lösung: Wenn Sie wissen müssen, welches Formular ausgefüllt wurde, erkunden Sie, wie Sie mit Ihrem Web-Team dynamisches URL-Hashing einrichten.

**Im `<div>`-Format organisierte Formulare**

* Problem: [!DNL Marketo Measure]-JS hat Schwierigkeiten, im `<div>`-Format organisierte Formulare zu erkennen, sodass unter Umständen benutzerdefinierter Code benötigt wird.
* Lösung: Diese [Vorlagen zum Melden von Benutzenden](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} können von Ihrem Web-Entwicklungs-Team verwendet werden, um den erforderlichen Code hinzuzufügen.

**Chat**

* Problem: Wenn Sie einen Chat-Anbieter verwenden, kann eine besondere Vorgehensweise erforderlich sein.
* Lösung: [!DNL Marketo Measure] kann in Drift, Olark, Livechat, LivePerson und SnapEngage integriert werden. Alle anderen Plattformen müssen über die Zugehörigkeit zu einer CRM-Kampagne nachverfolgt werden.

**Zweite Domain**

* Problem: [!DNL Marketo Measure] JavaScript Domain-spezifisch ist, müssen zusätzliche Schritte für alle separaten oder internationalen Domains unternommen werden. [!DNL Marketo Measure] JS kann Subdomains auf derselben Stamm-Domain verarbeiten.
* Lösung: Wenn Sie über mehrere Stamm-Domains verfügen, die von [!DNL Marketo Measure] nachverfolgt werden sollen, fügen Sie JS zu den Domains hinzu UND informieren Sie Ihre [!DNL Marketo Measure]-Beratungsperson darüber, welche Domains manuell mit Ihrem [!DNL Marketo Measure]-Konto verknüpft werden sollen.

## Testen von [!DNL Marketo Measure]-JavaScript {#testing-marketo-measure-javascript}

Ihr [!DNL Marketo Measure] Consultant hilft Ihnen beim Spottest der Website, um sicherzustellen, dass [!DNL Marketo Measure] JavaScript auf allen Seiten vorhanden ist. Zu diesen Tests gehört die Übermittlung einiger Formularausfüllungen mit klar angegebenen Testdetails, um sicherzustellen, dass das Tracking ordnungsgemäß zurückgegeben wird.

Allerdings ist Ihre [!DNL Marketo Measure]-Beratungsperson mit Ihrer Website wahrscheinlich nicht so vertraut wie Ihr Webteam. Aus diesem Grund ist es sehr wichtig, dass Ihr Webteam oder ein anderes entsprechendes Team die Website gründlich prüft. Dies gilt insbesondere dann, wenn komplexe Formulare wie die oben genannten verwendet werden. Ihr Team ist letztendlich dafür verantwortlich sicherzustellen, dass alle erforderlichen Web-Umgebungen ordnungsgemäß nachverfolgt werden. Wenn Sie jedoch von komplexen Formularen oder Situationen Kenntnis haben, können Sie Ihre [!DNL Marketo Measure]-Beratungsperson um Unterstützung bei den Tests bitten.

Gehen Sie wie folgt vor, um ein Formular selbst zu testen:

1. Verwenden Sie immer einen Inkognito-Browser oder leeren Sie Ihren Cache vor jedem Formularübermittlungstest UND verwenden Sie jedes Mal eine andere E-Mail-Adresse.

   a. Es empfiehlt sich, eine fingierte E-Mail-Adresse zu verwenden, bei der ersichtlich ist, dass es sich um einen Test handelt, und in der die Uhrzeit enthalten ist, z. B. testing830am@test.com.

1. Notieren Sie sich die URL der Seite, an die Sie das Formular senden, und die verwendete E-Mail.

1. Suchen Sie den Datensatz, der in Ihrem CRM-System (Lead oder Kontakt) für die Formularübermittlung erstellt wurde, und überprüfen Sie, ob ein Touchpoint ordnungsgemäß erstellt wurde.

   a. Sie können einen [!DNL Marketo Measure]-Stock-Bericht wie Leads mit Buyer Touchpoints verwenden oder sich das Lead-/Kontakt-Seiten-Layout ansehen, wenn Sie Ihre Seiten-Layouts mit [!DNL Marketo Measure]-Details aktualisieren.

   b. Die Verarbeitung der Daten kann einige Zeit dauern.
