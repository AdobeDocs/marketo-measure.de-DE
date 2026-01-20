---
unique-page-id: 27656745
description: Häufig gestellte Fragen (mehrere Währungen) - [!DNL Marketo Measure]
title: Häufig gestellte Fragen (mehrere Währungen)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 0%

---

# Häufig gestellte Fragen (mehrere Währungen) {#faq-multi-currency}

**Wie weiß ich, welche Funktion aktiviert werden soll?**

Beachten Sie, dass es für diese Funktion zwei verschiedene Funktionsbits gibt. Beide befinden sich auf der Registerkarte [!UICONTROL Allgemein] des CRM-Abschnitts in den Einstellungen: Mehrere Währungen und Erweiterte Währungen. Wenn der Kunde mehr als eine Währung verwendet, sollten mehrere Währungen aktiviert werden. Die zusätzliche Funktion „Erweiterte Währungen“ hingegen kann aktiviert werden, wenn der Kunde die Funktion „Erweiterte Währungsverwaltung“ von [!DNL Salesforce] verwendet, bei der der Benutzer einen zeitbasierten Bereich für Konversionsraten festlegen kann.

Marketo Measure ruft die Währungseinstellung automatisch aus dem CRM des Kunden ab. Eine manuelle Konfiguration in Marketo Measure, die dem CRM-System entspricht, ist nicht mehr erforderlich. Die Währungseinstellung befindet sich auf der Seite „Allgemein“ unter „CRM“.

**Warum gibt mir mein Werbekonto eine Warnmeldung?**

Neben Ihrem Werbekonto wird eine Warnmeldung angezeigt, in der möglicherweise Währungen aus einer nicht unterstützten Währung eingehen. In diesem Fall enthalten Ihre Dashboards Kacheln mit der Meldung „Gemischte Währungen“. Wir empfehlen Ihnen, mit Ihrem CRM-Administrator zusammenzuarbeiten, um sicherzustellen, dass diese unbekannte Währung eine Konversion in Ihrem CRM enthält.

**Was bedeutet „Gemischte Währungen“ auf meiner Dashboard-Kachel?**

Wenn Sie eine Kachel haben, die unten die Meldung „Gemischte Währungen“ enthält, bedeutet das, dass wir einige Kosten importiert haben, die einer Währung zugeordnet sind, die wir nicht erkennen. Da alle unsere Konversionen von dem CRM mit einem tatsächlichen Konversionsrate stammen müssen, bedeutet dies, dass Ihrem CRM diese Währung fehlt. Wir empfehlen Ihnen, mit Ihrem CRM-Administrator zusammenzuarbeiten, um sicherzustellen, dass diese unbekannte Währung eine Konversion in Ihrem CRM enthält.

**Wie kann ich den Fehler „Gemischte Währungen“ beheben, der durch ungültige Währungen verursacht wird?**

Unser System aktualisiert nicht erkannte Währungen auf „XXX“. Um Opportunitys mit ungültigen Währungen auszuschließen, erstellen Sie eine Unterdrückungsregel auf der Seite Touchpoint-Einstellungen , um Touchpoints für Opportunitys mit der Währung „XXX“ zu verhindern. Nach der Verarbeitung berichten wir nur über bekannte Währungen.

**Wie kann ich eine neue Währung oder einen neuen Umrechnungskurs hinzufügen?**

Eine neue Währung oder ein neuer Umrechnungskurs kann nur in [!DNL Salesforce] oder [!DNL Dynamics] deklariert werden, sodass es nur eine einzige Quelle der Wahrheit für diese Werte gibt. Sobald eine neue Währung oder ein neuer Umrechnungskurs erkannt wurde, lädt [!DNL Marketo Measure] diese herunter und stellt sie Ihnen zur Verfügung. Wir bieten keinen Bereich an, um diese Preise einzugeben.

**Die Währung wird nicht im richtigen Format angezeigt. Wie kann ich das ändern?**

Wir verstehen, dass einige Länder eine andere Art der Formatierung von Beträgen haben (z. B. 1.234,00, 1.234, 1.234). Aber wir führen eine weitere Komplexität ein, wenn wir nicht nur die Währung eines Benutzers bestimmen müssen, sondern auch sein Herkunftsland, da verschiedene Länder und Währungen unterschiedlich behandelt werden können. Das von uns gewählte konsistente Format ist 1.234,00. Dies kann nicht geändert werden.

**Warum können Sie das Währungssymbol für meine ausgewählte Währung nicht anzeigen?**

[!DNL Salesforce] und [!DNL Dynamics] zeigen ihre Beträge mit dem aus drei Buchstaben bestehenden Konversionscode an. Aus Konsistenzgründen werden unsere konvertierten Beträge auch mit dem 3-Buchstaben-Konversionscode und nicht mit dem Symbol angezeigt.

**Was wird mein Kunde sehen, wenn mehrere Währungen nicht aktiviert sind?**

Wenn der Kunde nicht über die Funktion mit mehreren Währungen verfügt, verwenden wir standardmäßig das Währungsgebietsschema des CRM und ändern alle ISO-Codes, die seine Ausgaben und Einnahmen in der Unternehmenswährung anzeigen. Wenn dies falsch ist und der Kunde eine gemischte Verwendung von Währungen hat, wäre die Lösung, ein Upgrade durchzuführen, um die Funktion mit mehreren Währungen zu erhalten.

**Wie wirkt sich diese Funktion auf Touchpoint-basierte Berichte im CRM aus?**

Für [!DNL Dynamics] und [!DNL Salesforce] Kunden, die nur das grundlegende (nicht erweiterte) Währungsmanagement verwenden, sollten Touchpoint-Umsatzbeträge korrekt konvertiert werden, sodass CRM-Berichte wie erwartet funktionieren sollten.

Leider gibt es einige Nuancen in der Funktionsweise für Benutzer von [!DNL Salesforce] Advanced Currency Management, aufgrund einer langjährigen Einschränkung der [!DNL Salesforce]. Die kurze Antwort auf „Was tun wir in diesem Fall“ ist, dass wir die Umsatzbeträge mithilfe der Pauschalsätze umrechnen, die auf der Registerkarte „Verwalten von Währungen“ der allgemeinen (d. h. nicht erweiterten) Ebene definiert sind. Mit anderen Worten, wir ignorieren die datierten Wechselkurse ganz, obwohl der Kunde datierte Wechselkurse definiert hat.

Für den interessierten Leser ist dies der Grund, warum es so funktioniert. Unsere Touchpoints verwenden Formelfelder zur Berechnung des Umsatzes (abgeleitet aus dem zugehörigen Opportunity-Betrag). [!DNL Salesforce] unterstützt nativ die Währungsumrechnung für diese Formelberechnungen, jedoch nur für die grundlegende Variante der Währungsunterstützung. Es ist uns unmöglich, ein Formelfeld zu definieren, das sich auf die datierten Wechselkurse bezieht. [!DNL Salesforce] unterstützt diese Funktion einfach nicht, daher haben wir keine Möglichkeit, die datierten Sätze in unseren Einnahmenberechnungen zu referenzieren, obwohl diese datierten Sätze in [!DNL Salesforce] existieren (es klingt verrückt, aber so funktioniert es.)

**Wenn mein Kunde einen Workflow zum Ausfüllen eines konvertierten Felds verwendet hat, wie sollte er dieses Feld künftig verwenden?**

Da unser Angebot nun die Konversionen für den Kunden verarbeitet, empfehlen wir, die Workflows und das benutzerdefinierte Feld zu entfernen und es uns zu ermöglichen, seinen Rohwert zu importieren.

>[!MORELIKETHIS]
>
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
