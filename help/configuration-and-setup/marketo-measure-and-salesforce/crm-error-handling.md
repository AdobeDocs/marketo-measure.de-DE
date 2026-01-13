---
description: Erfahren Sie, wie Sie Fehler in CRM-Exporten behandeln
title: Fehlerbehandlung für CRM-Exporte
feature: Salesforce
exl-id: 7452bff0-4bf1-474b-a705-446c29882230
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 8%

---


# Fehlerbehandlung für CRM-Exporte

Mit der Funktion Pause bei Exportfehlern können Sie steuern, ob CRM-Exportvorgänge bei einem Fehler auf Datensatzebene angehalten werden sollen.

Die Einstellung finden Sie unter **Mein Konto** > **Einstellungen** > **CRM** > **Allgemein**.

![Bei Exportfehlern anhalten](assets/stop-progress.png)

>[!NOTE]
>Diese Funktion ist nur sichtbar, wenn die Funktion „Export in CRM“ aktiviert ist.

Wenn diese Funktion aktiviert ist, schreitet der Exportvorgang nicht weiter voran und bleibt im Datensatz, in dem der Fehler aufgetreten ist, bis das Problem behoben ist. Diese Fehler sind in der Regel auf fehlende Berechtigungen, falsch angewendete benutzerdefinierte Validierungsregeln oder Probleme in Workflows/Triggern zurückzuführen. Der Vorgang wird weiterhin wie geplant ausgeführt und versucht automatisch erneut, den fehlgeschlagenen Datensatz zu exportieren, bis er erfolgreich ist.

Wenn Sie diese Funktion deaktivieren, wird ein Warnfenster angezeigt, das Sie darüber informiert, dass dies zu Dateninkonsistenzen führen kann. Es liegt in Ihrer Verantwortung, alle Probleme anzugehen, die sich aus diesen Inkonsistenzen ergeben können.

![Warnung zur Dateninkonsistenz](assets/data-inconsistency.png)

In beiden Fällen werden, unabhängig davon, ob die Funktion aktiviert oder deaktiviert ist, alle aufgetretenen Fehler auf Datensatzebene in der `ExportErrors` protokolliert und der `CRMExport_ExportError` versucht automatisch, diese Datensätze täglich erneut zu exportieren. Dadurch entfällt die Notwendigkeit, eine Support-Anfrage zu stellen, um einen erneuten Export zu initiieren, da dies automatisch ohne das Eingreifen eines Entwicklers geschieht.

Warum ist das Verhalten beim Anhalten des Auftrags angesichts der `ExportErrors` Funktionalität erforderlich? Durch das Anhalten der regulären CRM-Exportvorgänge für einen bestimmten Datensatz wird die Fehlerbehebung erheblich erleichtert. Damit können Sie Aufträge lokal ausführen und die Erstellung einer potenziell großen Anzahl von ExportErrors verhindern, die während des erneuten Exports abgerufen und verarbeitet werden müssten.

Diese Funktion kann je nach bevorzugtem Verhalten ein- oder ausgeschaltet werden. Wenn Sie beispielsweise auf einen besonders herausfordernden Fehler-Code stoßen und es vorziehen, „unvollständige“ Daten vorübergehend zu akzeptieren, können Sie die Funktion deaktivieren. Sobald das Problem behoben ist, können Sie die Funktion wieder aktivieren, um sicherzustellen, dass zukünftige Exporte vollständig und korrekt sind.
