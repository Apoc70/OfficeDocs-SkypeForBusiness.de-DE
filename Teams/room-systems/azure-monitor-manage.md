---
title: Verwalten von Microsoft-Teams Chatrooms Geräte mit Azure Monitor
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection: M365-voice
description: In diesem Artikel wird erläutert, wie Microsoft Teams Chatrooms Geräte in Azure Monitor mit integrierten, End-to-End-Weise verwalten.
ms.openlocfilehash: 4606bdde4e47eb2662e73434d1026d47093fb1e1
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362807"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a><span data-ttu-id="bf171-103">Verwalten von Microsoft-Teams Chatrooms Geräte mit Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="bf171-103">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>

<span data-ttu-id="bf171-104">In diesem Artikel wird erläutert, wie Microsoft Teams Chatrooms Geräte in Azure Monitor mit integrierten, End-to-End-Weise verwalten.</span><span class="sxs-lookup"><span data-stu-id="bf171-104">This article discusses how to manage Microsoft Teams Rooms devices in an integrated, end-to-end manner using Azure Monitor.</span></span>

<span data-ttu-id="bf171-105">Sie können konfigurieren, Azure überwachen, um grundlegende Telemetrie bereitzustellen, mit deren Hilfe Sie bei der Verwaltung von Skype meeting Room-Geräte (finden Sie unter [Planen von Microsoft Teams Chatrooms Verwaltung mit Azure Monitor](azure-monitor-plan.md) und [Bereitstellen von Microsoft Teams Chatrooms mit Azure Monitor]((azure-monitor-deploy.md) for details).</span><span class="sxs-lookup"><span data-stu-id="bf171-105">You can configure Azure Monitor to provide basic telemetry that will help you manage Skype meeting room devices (see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md) and [Deploy Microsoft Teams Rooms management with Azure Monitor]((azure-monitor-deploy.md) for details).</span></span> <span data-ttu-id="bf171-106">Der Management-Lösung Laufe der Zeit zusätzliche Daten und Management-Funktionen können Sie um eine ausführlichere Ansicht der Leistung des Geräts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf171-106">As your management solution matures, you can use additional data and management capabilities to create a more detailed view of device performance.</span></span>

## <a name="understand-the-log-entries"></a><span data-ttu-id="bf171-107">Verstehen der Protokolleinträge</span><span class="sxs-lookup"><span data-stu-id="bf171-107">Understand the log entries</span></span>

<span data-ttu-id="bf171-108">Die folgenden Sicherheitsereignisse werden alle fünf Minuten, wenn die Microsoft-Teams Raum app die entsprechende Informationen in der Windows-Ereignisprotokoll aufgezeichnet, in das Ereignisprotokoll Beschreibungsfeld eingefügt.</span><span class="sxs-lookup"><span data-stu-id="bf171-108">The following event descriptions are inserted into the event log description field every five minutes, when the Microsoft Teams Room app records the corresponding information in the Windows event log.</span></span> <span data-ttu-id="bf171-109">Microsoft Agent Monitoring übergibt diese Einträge an Protokoll Analytics in Azure Monitor, wodurch sie in das Dashboard analysiert, die Sie bei der [Verwaltung von Microsoft-Teams-Chatrooms Bereitstellen mit Azure Monitor](azure-monitor-deploy.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bf171-109">The Microsoft Monitoring Agent passes these records to Log Analytics in Azure Monitor, which parses them into the dashboard you created in [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="bf171-110">Mit dem Dashboard können Sie nach einzelnen Protokolleinträgen suchen, um die Ausführung von Aktionen festzulegen (falls erforderlich).</span><span class="sxs-lookup"><span data-stu-id="bf171-110">Using the dashboard you can look at individual log entries to determine courses of action if needed.</span></span> 

<span data-ttu-id="bf171-p103">Die Ereignis-IDs 2000 und 3000 geben an, dass das fragliche Gerät nicht wie erwartet funktioniert. Ereignis-IDs 2001 und 3001 geben an, dass ein Problem gefunden wurde. Für Ereignis-ID 4000 ist möglicherweise eine Aktion erforderlich, wenn diese im Vergleich zu einem von Ihnen festgelegten Punkt oder anderen in Ihrer Organisation bereitgestellten Geräte häufiger angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf171-p103">Event IDs 2000 and 3000 indicate the device in question is working as expected. Event IDs 2001 and 3001 indicate an issue was found. Event ID 4000 may require action if it is seen more often than you expect, compared to a baseline you set or other deployed devices in your organization.</span></span>

<span data-ttu-id="bf171-114">Wenn Sie diese Ereignisbeschreibungen verstehen, werden Sie schnell über Probleme informiert und wissen, wo Ihr Ansatz für die weitere Problembehebung sein kann.</span><span class="sxs-lookup"><span data-stu-id="bf171-114">Understanding these event descriptions alerts you to problems quickly, and provides a starting point for further troubleshooting.</span></span>

| <span data-ttu-id="bf171-115">Ereignis&nbsp;ID&nbsp;Ebene</span><span class="sxs-lookup"><span data-stu-id="bf171-115">Event&nbsp;ID&nbsp;level</span></span>|<span data-ttu-id="bf171-116">Ereignis&nbsp;Verhalten&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="bf171-116">Event&nbsp;behavior&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span></span>|<span data-ttu-id="bf171-117">Ereignis&nbsp;Beschreibung&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="bf171-117">Event&nbsp;Description&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span></span>|
|:---    |:---   |:---  |
| <span data-ttu-id="bf171-118">2000</span><span class="sxs-lookup"><span data-stu-id="bf171-118">2000</span></span>  <br> <span data-ttu-id="bf171-119">Informationen</span><span class="sxs-lookup"><span data-stu-id="bf171-119">Information</span></span> | <span data-ttu-id="bf171-120">Dies ist ein Ereignis über einen fehlerfreien Takt.</span><span class="sxs-lookup"><span data-stu-id="bf171-120">This is a healthy heartbeat event.</span></span> <span data-ttu-id="bf171-121">Alle 5 Minuten, Microsoft Teams Chatrooms überprüft, ob es Microsoft-Teams oder Skype für Unternehmen angemeldet ist und Netzwerk- und Verbindungsproblemen Exchange hat.</span><span class="sxs-lookup"><span data-stu-id="bf171-121">Every 5 minutes, Microsoft Teams Rooms checks that it is signed in to Microsoft Teams or Skype for Business and has network and Exchange connectivity.</span></span> <br> <span data-ttu-id="bf171-122">Wenn alle 3 Bedingungen erfüllt werden, wird alle 5 Minuten Ereignis-ID 2000 in das Ereignisprotokoll geschrieben, bis das Gerät offline ist oder mindestens eine der Bedingungen nicht mehr erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="bf171-122">If all 3 factors are true, it will write Event ID 2000 into the event log every 5 minutes until the device is offline or one or more of the conditions is no longer met.</span></span> | <span data-ttu-id="bf171-123">{"Beschreibung": "Heartbeat ist fehlerfrei.", "ResourceState": "Fehlerfrei", "-Operation": "Heartbeat", "OperationResult": "Übergeben", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "Alias<span></span>@contoso.com", "DisplayName": "Anzeigename ","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"IP-Adresse v6"}</span><span class="sxs-lookup"><span data-stu-id="bf171-123">{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}</span></span> <br><br> <span data-ttu-id="bf171-124">In diesem Beispiel alle Heartbeat-Bedingung erfüllt wurden, und das Gerät Microsoft Teams Chatrooms als fehlerfrei gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="bf171-124">In this example, all heartbeat conditions were met and the Microsoft Teams Rooms device was marked as being healthy.</span></span> <span data-ttu-id="bf171-125">Bei dem Auftreten von Fehlern hätte die App stattdessen Ereignis-ID 2001 aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bf171-125">If there were errors, the app would record Event ID 2001 instead.</span></span> |
| <span data-ttu-id="bf171-126">2001</span><span class="sxs-lookup"><span data-stu-id="bf171-126">2001</span></span>  <br> <span data-ttu-id="bf171-127">Fehler</span><span class="sxs-lookup"><span data-stu-id="bf171-127">Error</span></span> | <span data-ttu-id="bf171-128">Dies ist eine app Error-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bf171-128">This is an app error event.</span></span> <span data-ttu-id="bf171-129">Alle 5 Minuten, überprüft Microsoft Teams Chatrooms, dass es bei Microsoft-Teams oder Skype für Unternehmen mit Netzwerk- und Verbindungsproblemen Exchange angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="bf171-129">Every 5 minutes, Microsoft Teams Rooms checks that it is signed in to Microsoft Teams or Skype for Business with network and Exchange connectivity.</span></span> <span data-ttu-id="bf171-130">Wenn eine oder mehrere Faktoren nicht zutreffen, wird sie schreiben EventID 2001 in das Ereignisprotokoll alle 5 Minuten, bis das Gerät ist offline oder alle Aktionen erneut erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="bf171-130">If one or more factors are not true, it will write EventID 2001 into the event log every 5 minutes until the device is offline or all of the conditions are able to be met once again.</span></span>  | <span data-ttu-id="bf171-131">{"Description":"Network status : Healthy.</span><span class="sxs-lookup"><span data-stu-id="bf171-131">{"Description":"Network status : Healthy.</span></span> <span data-ttu-id="bf171-132">Exchange status : Connected.</span><span class="sxs-lookup"><span data-stu-id="bf171-132">Exchange status : Connected.</span></span> <span data-ttu-id="bf171-133">**Signin status: Unhealthy.**</span><span class="sxs-lookup"><span data-stu-id="bf171-133">**Signin status: Unhealthy.**</span></span> <span data-ttu-id="bf171-134">","ResourceState":"Fehlerhaft","-Operation":"Heartbeat","OperationResult":"Fehler","OS":" Windows 10","OSVersion":"10.0.14393.693","Alias":" ","DisplayName":"Anzeigename","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10"," IPv6Address":"Ip-Adresse v6"}</span><span class="sxs-lookup"><span data-stu-id="bf171-134">", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}</span></span> <br><br>  <span data-ttu-id="bf171-135">In diesem Beispiel ermittelt Microsoft Teams Chatrooms, dass die Netzwerkverbindung fehlerfrei und die app wurde mit Exchange verbunden, aber der fett formatierten Teil gibt an, dass die app nicht mit Skype für Unternehmen verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="bf171-135">In this example, Microsoft Teams Rooms determined that the network connection was healthy and the app was connected to Exchange, but the bolded portion indicates the app is not connected to Skype for Business.</span></span> <span data-ttu-id="bf171-136">Dies könnte ein Problem mit der Serverkonfiguration auf dem Gerät oder Host sein.</span><span class="sxs-lookup"><span data-stu-id="bf171-136">This could be a configuration issue on the device or host.</span></span>  <br> <br> <span data-ttu-id="bf171-137">Der Netzwerkstatus zeigt entweder „Healthy“ (Fehlerfrei) oder „Unhealthy“ (Fehlerhaft) an.</span><span class="sxs-lookup"><span data-stu-id="bf171-137">The Network status will show as either Healthy or Unhealthy.</span></span> <span data-ttu-id="bf171-138">Wenn der Status fehlerhaft ist, Sie müssen möglicherweise ein Problem mit der oder das Gerät entfernt wurde (aber dann würden Sie wahrscheinlich auch Exchange und Microsoft-Teams oder Skype Business Fehler haben).</span><span class="sxs-lookup"><span data-stu-id="bf171-138">If the status is unhealthy, you may have a network issue or the device may have been unplugged (but then you would probably also have Exchange and Microsoft Teams or Skype for Business errors).</span></span>  <br><br> <span data-ttu-id="bf171-139">Der Exchange-Status wird als verbunden oder eine der folgenden angezeigt: nicht verbundene, verbinden, AutodiscoveryError (die am häufigsten Fehler), GeneralError oder ServerVersionNotSupported.</span><span class="sxs-lookup"><span data-stu-id="bf171-139">The Exchange Status will show as either Connected or one of the following: Disconnected, Connecting, AutodiscoveryError (the most commonly seen error), GeneralError, or ServerVersionNotSupported.</span></span> <span data-ttu-id="bf171-140">Wenn der Status verbinden, warten Sie ist, bis die nächste Health-Nachricht gesendet wird, anderen Fehlern finden Sie das Problem in ein Administrator mit Erfahrung in der Exchange-Probleme beheben.</span><span class="sxs-lookup"><span data-stu-id="bf171-140">If the status is Connecting, wait until the next health message is sent, for other errors refer the issue to an admin with experience in solving Exchange issues.</span></span>  <br><br>  <span data-ttu-id="bf171-p111">Der Anmeldestatus (zeigt an, dass die App bei Skype for Business angemeldet ist) wird als „Healthy“ bzw. „Unhealthy“ angezeigt. Wenn der Status „Unhealthy“ ist, bemühen Sie einen Techniker, um das Problem zu weiter zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="bf171-p111">The Signin status (indicating the app is signed in to Skype for Business) will show as either Healthy or Unhealthy. If the status is unhealthy, send a technician to investigate further.</span></span> |
| <span data-ttu-id="bf171-143">3000</span><span class="sxs-lookup"><span data-stu-id="bf171-143">3000</span></span>  <br> <span data-ttu-id="bf171-144">Informationen</span><span class="sxs-lookup"><span data-stu-id="bf171-144">Information</span></span> | <span data-ttu-id="bf171-145">Dieses Ereignis wird überprüft, dass eine Überprüfung der Hardware ausgeführt und fehlerfrei gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="bf171-145">This event verifies that a hardware check was run and found to be healthy.</span></span> <span data-ttu-id="bf171-146">Alle 5 Minuten Microsoft Teams Chatrooms Prüfungen, die den Hardwarekomponenten wie am Anfang Raum anzeigen, Mikrofon, Lautsprecher und Kamera konfiguriert sind komplett vernetztes und funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="bf171-146">Every 5 minutes Microsoft Teams Rooms checks that configured hardware components such as front of room display, microphone, speaker, and camera are connected and functioning.</span></span> <span data-ttu-id="bf171-147">Wenn alle Komponenten fehlerfrei sind, wird Ereignis-ID 3000 in das Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf171-147">If all components are healthy, it will write EventID 3000 into the event log.</span></span> <span data-ttu-id="bf171-148">Dieses Ereignis wird so lange alle 5 Minuten in das Protokoll geschrieben, bis ein Fehler mit dem verbundenen Gerät auftritt.</span><span class="sxs-lookup"><span data-stu-id="bf171-148">This event will continue to be written every 5 minutes unless there is an issue with a connected device.</span></span>  <br> | <span data-ttu-id="bf171-149">{"Beschreibung": "HardwareCheckEngine ist fehlerfrei.", "ResourceState": "Fehlerfrei", "-Operation": "HardwareCheckEngine", "OperationResult": "Übergeben", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "Alias<span></span>@contoso.com", " DisplayName":"Anzeigename","AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"Ip-Adresse v6"}</span><span class="sxs-lookup"><span data-stu-id="bf171-149">{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}</span></span>  <br><br> <span data-ttu-id="bf171-150">In diesem Beispiel sind bei keiner Hardwareüberprüfung Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bf171-150">In this example, all hardware checks were passed.</span></span> <span data-ttu-id="bf171-151">Wenn Fehler aufgetreten sind, würde die app-Ereignis-ID 3001 stattdessen aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bf171-151">If there were errors,   the app would record Event ID 3001 instead.</span></span> |
| <span data-ttu-id="bf171-152">3001</span><span class="sxs-lookup"><span data-stu-id="bf171-152">3001</span></span>  <br> <span data-ttu-id="bf171-153">Error-Ereignis</span><span class="sxs-lookup"><span data-stu-id="bf171-153">Error Event</span></span>  | <span data-ttu-id="bf171-154">Dies ist eine Hardware Error-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bf171-154">This is a hardware error event.</span></span> <span data-ttu-id="bf171-155">Die Microsoft-Teams Chatrooms app verfügt über ein Prozess, der die Integrität der verbundenen Hardwarekomponenten (Vordergrund Raum, Mikrofon, Lautsprecher und Kamera) alle 5 Minuten überprüft.</span><span class="sxs-lookup"><span data-stu-id="bf171-155">The Microsoft Teams Rooms app has a process that will check the health of connected hardware components (front of room, microphone, speaker, camera) every 5 minutes.</span></span> <span data-ttu-id="bf171-156">Wenn eine oder mehrere Komponenten fehlerhaft sind, wird es EventID 3001 in das Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="bf171-156">If one or more of the components are unhealthy, it will write EventID 3001 into the event log.</span></span> <span data-ttu-id="bf171-157">Dieses Ereignis wird weiterhin geschrieben werden alle 5 Minuten, bis das Problem mit dem Gerät behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="bf171-157">This event will continue to be written every 5 minutes until the issue with the device is fixed.</span></span>   | <span data-ttu-id="bf171-158">{"Beschreibung": " **Status Front des Raums anzeigen: instabil.**</span><span class="sxs-lookup"><span data-stu-id="bf171-158">{"Description":" **Front of Room Display status : Unhealthy.**</span></span> <span data-ttu-id="bf171-159">Configured display count is 2.</span><span class="sxs-lookup"><span data-stu-id="bf171-159">Configured display count is 2.</span></span> <span data-ttu-id="bf171-160">Real display count is 0.</span><span class="sxs-lookup"><span data-stu-id="bf171-160">Real display count is 0.</span></span> <span data-ttu-id="bf171-161">**Conference Microphone status : Unhealthy.**</span><span class="sxs-lookup"><span data-stu-id="bf171-161">**Conference Microphone status : Unhealthy.**</span></span> <span data-ttu-id="bf171-162">Conference Speaker status : Healthy.</span><span class="sxs-lookup"><span data-stu-id="bf171-162">Conference Speaker status : Healthy.</span></span> <span data-ttu-id="bf171-163">Default Speaker status : Healthy.</span><span class="sxs-lookup"><span data-stu-id="bf171-163">Default Speaker status : Healthy.</span></span> <span data-ttu-id="bf171-164">Kamera-Status: fehlerfrei. ","ResourceState":"Fehlerhaft","-Operation":"HardwareCheckEngine","OperationResult":"Fehler","OS":"Windows 10","OSVersion":"10.0.14393.1198","Alias":" Alias<span></span>@contoso.com ","DisplayName":"Yosemite Konferenzraum","AppVersion":"2.0.58.0","IPv4Address":"10.10.10.10","IPv6Address":"IPv6Address","IPv4Address2":"10.10.10.10"}</span><span class="sxs-lookup"><span data-stu-id="bf171-164">Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}</span></span> <br><br>  <span data-ttu-id="bf171-165">Die Hardware-Peripheriegeräte werden entweder als „Healthy“ (Fehlerfrei) oder „Unhealthy“ (Fehlerhaft) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf171-165">Hardware peripherals are shown as either Healthy or Unhealthy.</span></span> <br> <span data-ttu-id="bf171-166">In diesem Beispiel werden zwei Vorderseite Raum zeigt konfiguriert, und derzeit keine davon steht.</span><span class="sxs-lookup"><span data-stu-id="bf171-166">In this example, there are two front of room displays configured, and currently neither of them is available.</span></span> <span data-ttu-id="bf171-167">Der Konferenz Mikrofon Status ist fehlerhaft, die möglicherweise einer Reihe von möglichen Ursachen.</span><span class="sxs-lookup"><span data-stu-id="bf171-167">The Conference Microphone status is unhealthy, which could have a number of possible causes.</span></span> <span data-ttu-id="bf171-168">Da mindestens eine Ressource die Überprüfung nicht bestanden haben, wird die ResourceState als fehlerhaft aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="bf171-168">Since at least one resource did not pass the check, the ResourceState is listed as Unhealthy.</span></span> <span data-ttu-id="bf171-169">Senden Sie einen Techniker weiter untersuchen.</span><span class="sxs-lookup"><span data-stu-id="bf171-169">Send a technician to investigate further.</span></span> |
| <span data-ttu-id="bf171-170">4000</span><span class="sxs-lookup"><span data-stu-id="bf171-170">4000</span></span>  <br> <span data-ttu-id="bf171-171">Informationen</span><span class="sxs-lookup"><span data-stu-id="bf171-171">Information</span></span>  <br> | <span data-ttu-id="bf171-172">Dies ist ein App-Neustartereignis.</span><span class="sxs-lookup"><span data-stu-id="bf171-172">This is an App Restart event.</span></span> <span data-ttu-id="bf171-173">Immer, wenn die App neu gestartet wird, wird dieses Ereignis im Windows-Fehlerprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="bf171-173">Every time the app is restarted, it will log this event into the Windows event log.</span></span>  <br> | <span data-ttu-id="bf171-174">{"Beschreibung": "App neu gestartet wird.", "ResourceState": "Fehlerfrei", "-Operation": "Neu starten", "OperationResult": "Übergeben", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "Alias<span></span>@domain.com", "DisplayName": "Anzeigename", " AppVersion":"1.0.38.0","IPv4Address":"10.10.10.10","IPv6Address":"Ip-Adresse v6"}</span><span class="sxs-lookup"><span data-stu-id="bf171-174">{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}</span></span> <br><br> <span data-ttu-id="bf171-175">Die app kann aus verschiedenen Gründen neu starten.</span><span class="sxs-lookup"><span data-stu-id="bf171-175">The app may restart for a variety of reasons.</span></span> <span data-ttu-id="bf171-176">Vergleichen Sie die Neustartfrequenz der Geräte im selben Gebäude und in anderen Gebäuden und berücksichtigen Sie dabei Probleme wie Stromzufuhrschwankungen und Stromausfälle, da diese Hinweise auf mögliche Infrastrukturprobleme geben können.</span><span class="sxs-lookup"><span data-stu-id="bf171-176">compare the restart frequency of devices in the same building and in different buildings, keeping in mind known issues like power fluctuations and failures, as this may provide clues to infrastructure problems.</span></span>|

## <a name="see-also"></a><span data-ttu-id="bf171-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf171-177">See also</span></span>
 

[<span data-ttu-id="bf171-178">Planen der Verwaltung von Microsoft-Teams Chatrooms mit Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="bf171-178">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="bf171-179">Bereitstellen von Microsoft-Teams Chatrooms Management mit Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="bf171-179">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)