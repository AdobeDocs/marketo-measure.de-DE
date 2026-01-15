---
description: Erfahren Sie, wie Sie Fehler in CRM-Exporten behandeln
title: Fehlerbehandlung für CRM-Exporte
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 8%

---

# Fehlerbehandlung für CRM-Exporte

Die Einstellung Bei Exportfehlern anhalten finden Sie unter **Mein Konto** > **Einstellungen** > **CRM** > **Allgemein**. Damit können Sie steuern, ob CRM-Exportvorgänge bei einem Fehler auf Datensatzebene angehalten werden sollen.

>[!NOTE]
>
>Diese Funktion ist nur sichtbar, wenn die Funktion „Export in CRM“ aktiviert ist.

Wenn diese Funktion aktiviert ist, schreitet der Exportvorgang nicht weiter voran und bleibt im Datensatz, in dem der Fehler aufgetreten ist, bis das Problem behoben ist. Diese Fehler sind in der Regel auf fehlende Berechtigungen, falsch angewendete benutzerdefinierte Validierungsregeln oder Probleme in Workflows/Triggern zurückzuführen. Der Vorgang wird wie geplant ausgeführt und versucht automatisch erneut, den fehlgeschlagenen Datensatz zu exportieren, bis er erfolgreich ist.

Wenn Sie diese Funktion deaktivieren, wird ein Warnfenster angezeigt, in dem Sie darauf hingewiesen werden, dass dies zu Dateninkonsistenzen führen kann. Es liegt in Ihrer Verantwortung, alle Probleme anzugehen, die sich aus diesen Inkonsistenzen ergeben können.

Unabhängig davon, ob die Funktion aktiviert oder deaktiviert ist, werden alle aufgetretenen Fehler auf Datensatzebene in der `ExportErrors` protokolliert und der `CRMExport_ExportError` versucht automatisch, diese Datensätze täglich erneut zu exportieren. Dadurch entfällt die Notwendigkeit, eine Support-Anfrage zu stellen, um einen erneuten Export zu initiieren, da dies automatisch ohne das Eingreifen eines Entwicklers geschieht.

Warum ist das Verhalten beim Anhalten des Auftrags angesichts der `ExportErrors` Funktionalität erforderlich? Durch das Anhalten der regulären CRM-Exportvorgänge für einen bestimmten Datensatz wird die Fehlerbehebung erheblich erleichtert. Damit können Sie Aufträge lokal ausführen und die Erstellung einer potenziell großen Anzahl von ExportErrors verhindern, die während des erneuten Exports abgerufen und verarbeitet werden müssten.

Diese Funktion kann je nach bevorzugtem Verhalten ein- oder ausgeschaltet werden. Wenn Sie beispielsweise auf einen besonders herausfordernden Fehler-Code stoßen und es vorziehen, „unvollständige“ Daten vorübergehend zu akzeptieren, können Sie die Funktion deaktivieren. Sobald das Problem behoben ist, können Sie die Funktion wieder aktivieren, um sicherzustellen, dass zukünftige Exporte vollständig und korrekt sind.
