---
unique-page-id: 27656745
description: Häufig gestellte Fragen (mehrere Währungen) - [!DNL Marketo Measure]
title: Häufig gestellte Fragen (mehrere Währungen)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: 3b14e758e81f237406da4e0fe1682a02b7a841fd
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 0%

---

# Häufig gestellte Fragen (mehrere Währungen) {#faq-multi-currency}

**Woher weiß ich, welches Feature-Bit aktiviert werden soll?**

Beachten Sie, dass es für diese Funktion zwei verschiedene Feature Bit gibt. Beide befinden sich im Tab [!UICONTROL Allgemein] des CRM-Abschnitts unter Einstellungen: Mehrere Währungen und Erweiterte Währungen. Mehrere Währungen sollten aktiviert werden, wenn der Kunde mehr als eine Währung verwendet. Die zusätzliche Funktion &quot;Erweiterte Währungen&quot;kann hingegen aktiviert werden, wenn der Kunde die Funktion &quot;Erweiterte Währungsverwaltung&quot;von [!DNL Salesforce] verwendet, mit der der Benutzer einen zeitbasierten Bereich für Konversionsraten festlegen kann.

Marketo Measure ruft die Währungseinstellung automatisch aus dem CRM-System des Kunden ab. In Marketo Measure ist keine manuelle Konfiguration erforderlich, die dem CRM-System entspricht. Die Währungseinstellung finden Sie auf der Seite &quot;Allgemein&quot;unter &quot;CRM&quot;.

**Warum gibt mir mein Werbekonto eine Warnmeldung?**

Neben Ihrem Anzeigenkonto wird eine Warnmeldung angezeigt, bei der Währungen von einer nicht unterstützten Währung eingehen können. In diesem Fall enthalten Ihre Dashboards Kacheln mit der Meldung &quot;Gemischte Währungen&quot;. Wir empfehlen Ihnen, mit Ihrem CRM-Administrator zusammenzuarbeiten, um sicherzustellen, dass diese unbekannte Währung eine Konversion in Ihrem CRM-System enthält.

**Was bedeutet &quot;Gemischte Währungen&quot;auf meiner Dashboard-Kachel?**

Wenn Sie eine Kachel mit der Meldung &quot;Gemischte Währungen&quot;am unteren Rand haben, bedeutet das, dass wir einige Kosten importiert haben, die einer Währung zugeordnet sind, die wir nicht erkennen. Da alle Konversionen aus dem CRM-System mit einer tatsächlichen Konversionsrate stammen müssen, bedeutet dies, dass Ihrem CRM diese Währung fehlt. Wir empfehlen Ihnen, mit Ihrem CRM-Administrator zusammenzuarbeiten, um sicherzustellen, dass diese unbekannte Währung eine Konversion in Ihrem CRM-System enthält.

**Wie kann ich den Fehler &quot;Gemischte Währungen&quot;beheben, der durch ungültige Währungen verursacht wurde?**

Unser System aktualisiert nicht erkannte Währungen auf &quot;XXX&quot;. Um Möglichkeiten mit ungültigen Währungen auszuschließen, erstellen Sie auf der Seite &quot;Touchpoint-Einstellungen&quot;eine Unterdrückungsregel, um Touchpoints für Chancen mit der Währung &quot;XXX&quot;zu verhindern. Nach der Verarbeitung werden wir nur über bekannte Währungen berichten.

**Wie kann ich eine neue Währung oder einen neuen Umrechnungskurs hinzufügen?**

Die Deklarierung einer neuen Währung oder eines neuen Konversionskurses kann nur in [!DNL Salesforce] oder [!DNL Dynamics] erfolgen, sodass für diese Werte nur eine einzige &quot;Source of Truth&quot;vorliegt. Sobald eine neue Währung oder Umrechnungsrate erkannt wurde, lädt [!DNL Marketo Measure] diese herunter und stellt sie für Sie bereit. Wir bieten keinen Bereich, in dem diese Preise angegeben werden können.

**Die Währung wird nicht im richtigen Format angezeigt. Wie kann ich dies ändern?**

Wir wissen, dass einige Länder eine andere Art haben, Beträge zu formatieren (z. B. 1.234.00, 1.234, 1.234). Aber wir führen ein weiteres Maß an Komplexität ein, wenn wir nicht nur die Währung eines Benutzers bestimmen müssen, sondern auch dessen Herkunftsland, da unterschiedliche Länder und Währungen unterschiedlich gehandhabt werden können. Das von uns gewählte konsistente Format ist 1.234.00. Dies kann nicht geändert werden.

**Warum können Sie das Währungssymbol für meine ausgewählte Währung nicht anzeigen?**

[!DNL Salesforce] und [!DNL Dynamics] zeigen ihre Beträge mit dem 3-Buchstaben-Konversionscode an. Aus Gründen der Konsistenz werden unsere konvertierten Beträge auch mit dem 3-Buchstaben-Konversionscode und nicht mit dem Symbol angezeigt.

**Was wird mein Kunde sehen, wenn mehrere Währungen nicht aktiviert sind?**

Wenn der Kunde nicht über die Funktion für mehrere Währungen verfügt, wird standardmäßig sein Währungsgebietsschema aus dem CRM ausgewählt und alle ISO-Codes geändert, die seine Ausgaben und Umsätze in der Unternehmenskurve anzeigen. Wenn dies nicht korrekt ist und der Kunde eine gemischte Verwendung der Währung hat, besteht die Lösung darin, ein Upgrade durchzuführen, um die Funktion mit mehreren Währungen zu erhalten.

**Wie wirkt sich diese Funktion auf Touchpoint-basierte Berichte im CRM aus?**

Bei Kunden mit [!DNL Dynamics] und [!DNL Salesforce], die nur die einfache (nicht erweiterte) Währungsverwaltung verwenden, sollten die Umsatzbeträge von Touchpoints korrekt konvertiert werden, sodass CRM-Berichte erwartungsgemäß funktionieren sollten.

Leider gibt es einige Nuancen dazu, wie dies für Benutzer von [!DNL Salesforce] Advanced Currency Management funktioniert, da die Verwendung von [!DNL Salesforce] seit langem eingeschränkt ist. Die kurze Antwort auf &quot;Was tun wir in diesem Fall&quot; ist, dass wir Umsätze mithilfe der Pauschalsätze umrechnen, die im Tab &quot;Währungen verwalten&quot; (d. h. nicht erweiterter Standard) definiert sind. Mit anderen Worten, wir ignorieren die veralteten Wechselkurse ganz und gar, obwohl der Kunde die alten Wechselkurse definiert hat.

Für den interessierten Leser hier ist der Grund, warum es so funktioniert. Unsere Touchpoints verwenden Formelfelder zur Berechnung des Umsatzes (abgeleitet aus dem zugehörigen Opportunity-Betrag). [!DNL Salesforce] unterstützt nativ die Währungsumrechnung für diese Formelberechnungen, jedoch nur für ihren grundlegenden Geschmack der Währungsunterstützung. Es ist unmöglich für uns, ein Formelfeld zu definieren, das auf die alten Wechselkurse verweist. [!DNL Salesforce] unterstützt diese Funktion einfach nicht, daher haben wir keine Möglichkeit, die veralteten Raten in unseren Umsatzberechnungen zu referenzieren, obwohl diese veralteten Raten in [!DNL Salesforce] vorhanden sind (es klingt verrückt, aber so funktioniert es.)

**Wenn mein Kunde einen Workflow zum Ausfüllen eines konvertierten Felds verwendet hat, wie sollte er dieses Feld künftig verwenden?**

Da unser Angebot nun die Konversionen für den Kunden verarbeitet, empfehlen wir, die Workflows und das benutzerdefinierte Feld zu entfernen und den Rohdatenwert zu importieren.

>[!MORELIKETHIS]
>
>[Fehlerbenachrichtigungen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
