---
title: Microsoft-Teams Chatrooms Wartung und Betrieb
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Lesen Sie in diesem Thema, um Informationen zur Verwaltung von der Microsoft-Teams Chatrooms, die nächste Generation von Skype Raum Systemen zu erfahren.
ms.openlocfilehash: efaf2a1bae7980855501b826d6a2ee902f0f56b2
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362854"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="06b6d-103">Microsoft-Teams Chatrooms Wartung und Betrieb</span><span class="sxs-lookup"><span data-stu-id="06b6d-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="06b6d-104">Lesen Sie in diesem Thema, um Informationen zur Verwaltung von der Microsoft-Teams Chatrooms, die nächste Generation von Skype Raum Systemen zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="06b6d-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="06b6d-105">Microsoft-Teams Chatrooms ist Microsofts neueste konferenzlösung entwickelt, um Ihre Besprechungsraum in ein rich-collaborative Erlebnis umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="06b6d-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="06b6d-106">Benutzer werden die vertraute Microsoft-Teams, genießen oder Skype für Business-Schnittstelle und IT-Administratoren wird eine auf einfache Weise bereitgestellte und verwaltete Windows 10 Skype Besprechung app zu schätzen wissen.</span><span class="sxs-lookup"><span data-stu-id="06b6d-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="06b6d-107">Microsoft-Teams Chatrooms ist darauf ausgelegt, vorhandene Ausrüstung, wie LCD-Bereiche zur Erleichterung der Installation auf die Microsoft-Teams oder Skype für Unternehmen in Ihrem Besprechungsraum bringen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="06b6d-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="06b6d-108">Zusätzliche Konfiguration ist Remoteverwaltung möglich mit Microsoft Azure Monitor gemäß [Planen Microsoft Teams Chatrooms Management mit Azure Monitor](azure-monitor-plan.md), [Microsoft-Teams-Chatrooms bereitstellen Management mit Azure Monitor](azure-monitor-deploy.md), [Verwalten Microsoft-Teams Chatrooms Geräte mit Azure Monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="06b6d-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="06b6d-109">Sie können auch [verwalten Microsoft Teams Chatrooms Konsole Einstellungen Remote mit einer XML-Konfigurationsdatei](xml-config-file.md), einschließlich eines Designs benutzerdefinierte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="06b6d-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="06b6d-110">Erfassen von Protokollen auf Microsoft Teams Räume</span><span class="sxs-lookup"><span data-stu-id="06b6d-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="06b6d-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-111"></span></span>

<span data-ttu-id="06b6d-112">Um die Protokolle gespeichert werden, müssen Sie das Protokoll Auflistung Skript aufrufen, das mit der Microsoft-Teams Chatrooms app verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06b6d-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="06b6d-113">Starten Sie im Administratormodus eine Eingabeaufforderung mit erhöhten Rechten, und geben Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="06b6d-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="06b6d-114">Die Protokolle werden als ZIP-Datei in c:\rigel ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06b6d-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="06b6d-115">Anzeigeeinstellungen vorne im Raum</span><span class="sxs-lookup"><span data-stu-id="06b6d-115">Front of Room Display Settings</span></span>
<span data-ttu-id="06b6d-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-116"></span></span>

<span data-ttu-id="06b6d-117">Konfigurieren Sie den Bildschirm vorne im Raum für den Modus „Erweitert“.</span><span class="sxs-lookup"><span data-stu-id="06b6d-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="06b6d-118">Dadurch wird die Konsole sicherstellen, dass, die Benutzeroberfläche auf, die anzeigen nicht dupliziert werden, wenn Sie die Anzeige schalten.</span><span class="sxs-lookup"><span data-stu-id="06b6d-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06b6d-119">Ein Consumer-TV, der als eine Anzeige vorne im Raum verwendet wird, muss das Feature „Consumer Electronics Control (CEC)“ von HDMI unterstützen/aktivieren, sodass ein automatischer Wechsel zu einer aktiven Videoquelle aus dem Standbymodus möglich ist.</span><span class="sxs-lookup"><span data-stu-id="06b6d-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="06b6d-120">Dieses Feature wird nicht auf allen TVs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06b6d-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="06b6d-121">Microsoft-Teams, Räume zurücksetzen (Factory wiederherstellen)</span><span class="sxs-lookup"><span data-stu-id="06b6d-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="06b6d-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-122"></span></span>

<span data-ttu-id="06b6d-123">Wenn Microsoft Teams Chatrooms auch nicht ausgeführt wird, möglicherweise ausführen Herstellerstandard zurücksetzen helfen.</span><span class="sxs-lookup"><span data-stu-id="06b6d-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="06b6d-124">Dies ist möglich, in der app Einstellungen auf der Registerkarte **Wiederherstellen** unter **diesem PC zurücksetzen**, wählen Sie **Erste Schritte**, und klicken Sie dann **Alles entfernen**.</span><span class="sxs-lookup"><span data-stu-id="06b6d-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="06b6d-125">Führen Sie die verbleibenden aufforderungen, um das Gerät zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="06b6d-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06b6d-126">Es ist ein bekanntes Problem, in dem die Microsoft-Teams Räume werden kann nicht mehr verwendet werden, wenn die Option **Meine Dateien - Apps entfernt und Einstellungen, beibehalten werden sollen, jedoch bleibt Ihre persönlichen Dateien** während des Aktivierungsvorgangs zurücksetzen ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="06b6d-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="06b6d-127">Führen Sie _nicht_ verwenden Sie diese Option.</span><span class="sxs-lookup"><span data-stu-id="06b6d-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="06b6d-128">Unterstützte Remoteoptionen</span><span class="sxs-lookup"><span data-stu-id="06b6d-128">Supported Remote Options</span></span>
<span data-ttu-id="06b6d-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-129"></span></span>

<span data-ttu-id="06b6d-130">In der folgenden Tabelle sind die möglichen Remotevorgänge und die Methoden zusammengefasst, die Sie für diese Vorgänge verwenden können.</span><span class="sxs-lookup"><span data-stu-id="06b6d-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="06b6d-131">\*\*Arbeitsgruppe \*\*</span><span class="sxs-lookup"><span data-stu-id="06b6d-131">**Workgroup**</span></span>|<span data-ttu-id="06b6d-132">**Nicht Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="06b6d-132">**Not domain joined**</span></span>|<span data-ttu-id="06b6d-133">**Mitglied einer Domäne**</span><span class="sxs-lookup"><span data-stu-id="06b6d-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06b6d-134">Neustart</span><span class="sxs-lookup"><span data-stu-id="06b6d-134">Restart</span></span>  <br/> |<span data-ttu-id="06b6d-135">Remotedesktop</span><span class="sxs-lookup"><span data-stu-id="06b6d-135">Remote desktop</span></span>  <br/> <span data-ttu-id="06b6d-136">Remote-Powershell</span><span class="sxs-lookup"><span data-stu-id="06b6d-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="06b6d-137">Remotedesktop (Weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="06b6d-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="06b6d-138">Remote-Powershell (Weitere Konfiguration erforderlich)</span><span class="sxs-lookup"><span data-stu-id="06b6d-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="06b6d-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="06b6d-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="06b6d-140">Betriebssystemupdate</span><span class="sxs-lookup"><span data-stu-id="06b6d-140">Update OS</span></span>  <br/> |<span data-ttu-id="06b6d-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="06b6d-141">Windows Update</span></span>  <br/> |<span data-ttu-id="06b6d-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="06b6d-142">Windows Update</span></span>  <br/> <span data-ttu-id="06b6d-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="06b6d-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="06b6d-144">App-Update</span><span class="sxs-lookup"><span data-stu-id="06b6d-144">App update</span></span>  <br/> |<span data-ttu-id="06b6d-145">Windows Store</span><span class="sxs-lookup"><span data-stu-id="06b6d-145">Windows Store</span></span>  <br/> |<span data-ttu-id="06b6d-146">Windows Store</span><span class="sxs-lookup"><span data-stu-id="06b6d-146">Windows Store</span></span>  <br/> <span data-ttu-id="06b6d-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="06b6d-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="06b6d-148">Skype-Kontokonfiguration</span><span class="sxs-lookup"><span data-stu-id="06b6d-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="06b6d-149">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="06b6d-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="06b6d-150">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="06b6d-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="06b6d-151">Zugriff auf Protokolle</span><span class="sxs-lookup"><span data-stu-id="06b6d-151">Access logs</span></span>  <br/> |<span data-ttu-id="06b6d-152">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="06b6d-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="06b6d-153">Zurzeit nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="06b6d-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="06b6d-154">Konfigurieren von Gruppenrichtlinien für Microsoft-Teams, Räume</span><span class="sxs-lookup"><span data-stu-id="06b6d-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="06b6d-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-155"></span></span>

<span data-ttu-id="06b6d-156">In diesem Abschnitt werden die Systemeinstellungen, von denen Microsoft Teams Chatrooms abhängt, ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="06b6d-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="06b6d-157">Wenn Microsoft Teams Chatrooms mit einer Domäne verknüpft wird, stellen Sie sicher, dass Ihre Gruppenrichtlinien die Einstellungen in der folgenden Tabelle außer Kraft setzen nicht.</span><span class="sxs-lookup"><span data-stu-id="06b6d-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="06b6d-158">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="06b6d-158">**Setting**</span></span>|<span data-ttu-id="06b6d-159">**Ermöglicht**</span><span class="sxs-lookup"><span data-stu-id="06b6d-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06b6d-160">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon automatische Anmeldung = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="06b6d-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="06b6d-161">Microsoft-Teams Chatrooms starten aktiviert</span><span class="sxs-lookup"><span data-stu-id="06b6d-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="06b6d-162">Strom-Management -\> AC, deaktivieren Sie auf Bildschirm nach 10 Minuten</span><span class="sxs-lookup"><span data-stu-id="06b6d-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="06b6d-163">Strom-Management -\> auf AC, setzen Sie nie System in den Energiesparmodus</span><span class="sxs-lookup"><span data-stu-id="06b6d-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="06b6d-164">Microsoft-Teams Chatrooms angefügte zeigt deaktivieren und Reaktivieren von automatisch aktiviert</span><span class="sxs-lookup"><span data-stu-id="06b6d-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="06b6d-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="06b6d-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="06b6d-166">Oder entsprechende Möglichkeit zum Deaktivieren des Kennwortablaufs für das lokale Konto.</span><span class="sxs-lookup"><span data-stu-id="06b6d-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="06b6d-167">Wird dies nicht ausgeführt, kann bei der Anmeldung des Skype-Kontos aufgrund eines abgelaufenen Kennworts ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="06b6d-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="06b6d-168">Beachten Sie, dass sich dies auf alle lokalen Konten auf dem Computer auswirkt, sodass bei Nichtfestlegung dieser Einstellung auch das Administratorkonto ablaufen kann.</span><span class="sxs-lookup"><span data-stu-id="06b6d-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="06b6d-169">Ermöglicht die ständige Anmeldung des Skype-Kontos</span><span class="sxs-lookup"><span data-stu-id="06b6d-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="06b6d-170">Übertragen von Dateien mithilfe von Gruppenrichtlinien wird unter [Konfigurieren einer Dateielement](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)erläutert.</span><span class="sxs-lookup"><span data-stu-id="06b6d-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="06b6d-171">Remoteverwaltung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="06b6d-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="06b6d-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-172"></span></span>

<span data-ttu-id="06b6d-173">Sie können die folgenden Verwaltungsvorgänge Remote mithilfe von PowerShell ausführen (siehe Tabelle unten für Skriptbeispiele):</span><span class="sxs-lookup"><span data-stu-id="06b6d-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="06b6d-174">Abrufen von angeschlossenen Geräten</span><span class="sxs-lookup"><span data-stu-id="06b6d-174">Get attached devices</span></span>
    
- <span data-ttu-id="06b6d-175">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="06b6d-175">Get app status</span></span>
    
- <span data-ttu-id="06b6d-176">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="06b6d-176">Get system info</span></span>
    
- <span data-ttu-id="06b6d-177">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="06b6d-177">Reboot system</span></span>
    
- <span data-ttu-id="06b6d-178">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="06b6d-178">Retrieve logs</span></span>
    
- <span data-ttu-id="06b6d-179">Übertragen von Dateien (einer Domäne gehörenden Microsoft Teams Chatrooms erforderlich)</span><span class="sxs-lookup"><span data-stu-id="06b6d-179">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="06b6d-180">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="06b6d-180">This functionality is off by default.</span></span> <span data-ttu-id="06b6d-181">Sie müssen zum Ausführen der folgenden Vorgänge remote-PowerShell für Ihre Umgebung auf dem System Microsoft Teams Räume zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06b6d-181">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="06b6d-182">Finden Sie in der Dokumentation auf **[Enable-psremoting sieht](https://technet.microsoft.com/library/hh849694.aspx)** für Informationen zur Verwendung von remote-PowerShell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06b6d-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="06b6d-183">Sie können Remote-PowerShell beispielsweise wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="06b6d-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="06b6d-184">Melden Sie sich als Administrator auf einem Gerät mit Microsoft-Teams Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="06b6d-184">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="06b6d-185">Öffnen Sie eine PowerShell-Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="06b6d-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="06b6d-186">Geben Sie den folgenden Befehl ein: Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="06b6d-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="06b6d-187">So führen Sie einen Verwaltungsvorgang durch:</span><span class="sxs-lookup"><span data-stu-id="06b6d-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="06b6d-188">Melden Sie sich an einem Computer mit den Anmeldeinformationen des Kontos, die Berechtigung zum Ausführen von PowerShell-Befehlen auf einem Gerät mit Microsoft-Teams Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="06b6d-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="06b6d-189">Öffnen Sie eine reguläre PowerShell-Eingabeaufforderung auf dem PC.</span><span class="sxs-lookup"><span data-stu-id="06b6d-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="06b6d-190">Kopieren Sie den Befehlstext aus der folgenden Tabelle, und fügen Sie ihn an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="06b6d-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="06b6d-191">Ersetzen Sie `<Device fqdn>` Felder mit den Werten des FQDN für Ihre Umgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="06b6d-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="06b6d-192">Ersetzen Sie \* \<Pfad\> \* mit den Dateinamen und den lokalen Pfad der master SkypeSettings.xml-Konfigurationsdatei (oder Bild Design).</span><span class="sxs-lookup"><span data-stu-id="06b6d-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="06b6d-193">Abzurufenden angeschlossene Geräte</span><span class="sxs-lookup"><span data-stu-id="06b6d-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="06b6d-194">Abrufen des App-Status</span><span class="sxs-lookup"><span data-stu-id="06b6d-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="06b6d-195">Abrufen von Systeminformationen</span><span class="sxs-lookup"><span data-stu-id="06b6d-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="06b6d-196">Neustart des Systems</span><span class="sxs-lookup"><span data-stu-id="06b6d-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="06b6d-197">Abrufen von Protokollen</span><span class="sxs-lookup"><span data-stu-id="06b6d-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="06b6d-198">Drücken Sie eine XML-Konfigurationsdatei (oder Grafik Design)</span><span class="sxs-lookup"><span data-stu-id="06b6d-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="06b6d-199">Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="06b6d-199">Software updates</span></span>
<span data-ttu-id="06b6d-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-200"></span></span>

<span data-ttu-id="06b6d-201">Standardmäßig versucht Microsoft Teams Räume zum Verbinden mit den Windows Store zum Abrufen der neuesten Version von Microsoft-Teams Chatrooms Software, damit das Gerät regulären Internetzugriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="06b6d-201">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="06b6d-202">Kontaktaufnahme mit Microsoft Support-Probleme, werden Sie sicher, dass das Gerät Microsoft Teams Chatrooms mit der neuesten Version der app geladen wird.</span><span class="sxs-lookup"><span data-stu-id="06b6d-202">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="06b6d-203">Standardmäßig Microsoft Teams Chatrooms stellt eine Verbindung mit Windows Update Betriebssystem abgerufen und USB-Peripheriegeräte Firmwareupdates und installiert diese außerhalb der Geschäftszeiten konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="06b6d-203">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="06b6d-204">Sie können Geschäftszeiten konfigurieren, indem Sie sich beim Administratorkonto anmelden und die Einstellungen-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="06b6d-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="06b6d-205">Wenn Sie Updates manuell verwalten möchten, und nicht im normale Verfahren für eine [Microsoft Store for Business](https://businessstore.microsoft.com/store) zu [verteilen offline-apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)haben, können Sie die entsprechende APPX Datei und Abhängigkeiten in [Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168) (aus abrufen. die Anweisungen zum [Konfigurieren einer Microsoft-Teams Chatrooms Konsole](console.md)) mit SCCM verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="06b6d-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="06b6d-206">Die Deployment Kit-Version Positionen davor befindet hinter der Store-Version, damit es immer den neuesten Build möglicherweise nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="06b6d-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="06b6d-207">Aktualisieren von Powershell</span><span class="sxs-lookup"><span data-stu-id="06b6d-207">To update using Powershell</span></span>

1. <span data-ttu-id="06b6d-208">Extrahieren Sie das Paket aus der Installation die [MSI-Datei](https://go.microsoft.com/fwlink/?linkid=851168) zu einer Freigabe das Gerät, die zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="06b6d-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="06b6d-209">Führen Sie das folgende Skript für die Microsoft-Teams Chatrooms Geräte, ändern \<freigeben\> freigeben als Antwort auf das Gerät:</span><span class="sxs-lookup"><span data-stu-id="06b6d-209">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="06b6d-210">Administratormodus und Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="06b6d-210">Admin mode and device management</span></span>
<span data-ttu-id="06b6d-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-211"></span></span>

<span data-ttu-id="06b6d-212">Einige Managementfunktionen, wie die manuelle Installation eines privaten Zertifizierungsstellenzertifikats erfordern das Vorhandensein des Surface Pro Geräts im Admin-Modus.</span><span class="sxs-lookup"><span data-stu-id="06b6d-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="06b6d-213">Wechsel in Administratormodus und zurück, wenn die Microsoft-Teams Chatrooms app ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="06b6d-213">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="06b6d-214">Alle laufenden Anrufe Auflegen, und klicken Sie auf der Startseite zurück.</span><span class="sxs-lookup"><span data-stu-id="06b6d-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="06b6d-215">Wählen Sie das Zahnradsymbol und rufen Sie das Menü (Optionen sind **Einstellungen**, **Eingabehilfen**und **Gerät neu starten** ).</span><span class="sxs-lookup"><span data-stu-id="06b6d-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="06b6d-216">Wählen Sie **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="06b6d-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="06b6d-217">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="06b6d-217">Enter the Administrator Password.</span></span> <span data-ttu-id="06b6d-218">Der Setupbildschirm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="06b6d-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="06b6d-219">Wenn das Gerät in die Domäne eingebundener nicht ist, wird das lokale Administratorkonto (Benutzername "Admin") in der Standardeinstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06b6d-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="06b6d-220">Das Standard-Kennwort für dieses Konto ist 'Sfb', aber es wird empfohlen, dass Ihre Organisation dies für aus Sicherheitsgründen so bald wie möglich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="06b6d-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="06b6d-221">Wenn der Computer Mitglied einer Domäne ist, können Sie sich mit einem Domänenkonto entsprechend berechtigten anmelden.</span><span class="sxs-lookup"><span data-stu-id="06b6d-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="06b6d-222">Wählen Sie **Windows-Einstellungen** in der linken Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="06b6d-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="06b6d-223">Wählen Sie **Zu Administratoranmeldung wechseln** aus.</span><span class="sxs-lookup"><span data-stu-id="06b6d-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="06b6d-224">Geben Sie das Administratorkennwort ein.</span><span class="sxs-lookup"><span data-stu-id="06b6d-224">Enter the Administrator Password.</span></span> <span data-ttu-id="06b6d-225">Daraufhin wird die App ordnungsgemäß abgemeldet, und Sie gelangen zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="06b6d-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="06b6d-226">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="06b6d-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="06b6d-227">Sie müssen die erforderlichen Berechtigungen zum Verwalten des Geräts.</span><span class="sxs-lookup"><span data-stu-id="06b6d-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="06b6d-228">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="06b6d-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="06b6d-229">Melden Sie sich bei Ihrem Administratorkonto ab.</span><span class="sxs-lookup"><span data-stu-id="06b6d-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="06b6d-230">Zurück zu Microsoft-Teams Räumen durch Auswählen des Benutzer Konto-Symbols auf der linken Seite des Bildschirms und anschließend **Skype**.</span><span class="sxs-lookup"><span data-stu-id="06b6d-230">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="06b6d-231">Wenn der Benutzer **Skype** nicht aufgeführt ist, möglicherweise müssen Sie wählen Sie **Benutzer** aus, und geben **. \skype** als den Benutzernamen und das anmelden.</span><span class="sxs-lookup"><span data-stu-id="06b6d-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="06b6d-232">Die Konsole ist nun wieder in den normalen Betrieb-Modus. Das folgende Verfahren benötigen Sie eine Tastatur auf das Gerät anfügen, falls noch nicht angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="06b6d-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="06b6d-233">Wechsel in Administratormodus und zurück, wenn die Anwendung Microsoft-Teams Räume zum Absturz</span><span class="sxs-lookup"><span data-stu-id="06b6d-233">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="06b6d-234">Drücken Sie fünf Mal schnell hintereinander die WINDOWS-TASTE.</span><span class="sxs-lookup"><span data-stu-id="06b6d-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="06b6d-235">Daraufhin gelangen Sie zum Windows-Anmeldebildschirm.</span><span class="sxs-lookup"><span data-stu-id="06b6d-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="06b6d-236">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim Desktop an.</span><span class="sxs-lookup"><span data-stu-id="06b6d-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="06b6d-237">Diese Methode nicht melden Sie sich den Skype-Benutzer oder die app ordnungsgemäß beendet, aber verwenden Sie es, wenn die app wurde nicht mehr reagiert und die andere Methode war nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06b6d-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="06b6d-238">Führen Sie die notwendigen Administratoraufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="06b6d-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="06b6d-239">Starten Sie den Computer, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="06b6d-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="06b6d-240">Die Konsole wird neu gestartet, in den normalen Betrieb-Modus, die Microsoft-Teams Chatrooms app ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="06b6d-240">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="06b6d-241">Sie können die Tastatur entfernen, wenn es angefügt wurde, damit Sie dieses Verfahren ausführen können.</span><span class="sxs-lookup"><span data-stu-id="06b6d-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="06b6d-242">Tipps zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="06b6d-242">Troubleshooting tips</span></span>
   <span data-ttu-id="06b6d-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="06b6d-243"></span></span>

- <span data-ttu-id="06b6d-244">Besprechungsanfragen möglicherweise nicht angezeigt, wenn über Domänengrenzen hinweg (beispielsweise zwischen zwei Unternehmen) gesendet.</span><span class="sxs-lookup"><span data-stu-id="06b6d-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="06b6d-245">In solchen Fällen sollten die IT-Administratoren, ob externe Benutzer zum Planen einer Besprechung zugelassen entscheiden.</span><span class="sxs-lookup"><span data-stu-id="06b6d-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="06b6d-246">Microsoft-Teams Chatrooms unterstützt keine Exchange AutoDiscover leitet über Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="06b6d-246">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="06b6d-247">Im Allgemeinen ist es ratsam für IT-Administratoren, die alle audioendpunkte deaktivieren, die er nicht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="06b6d-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="06b6d-248">Falls ein Spiegelbild in der Raumvorschau angezeigt wird, kann der IT-Administrator dies korrigieren, indem die Stromversorgung der Kamera angestellt wird oder die Bildausrichtung mit der Fernsteuerung der Kamera gekippt wird.</span><span class="sxs-lookup"><span data-stu-id="06b6d-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="06b6d-249">Es ist bekannt, dass der Zugang zum Konsolentouchscreen verloren gehen kann.</span><span class="sxs-lookup"><span data-stu-id="06b6d-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="06b6d-250">In solchen Fällen wird durch einen Neustart des Systems Microsoft Teams Chatrooms manchmal das Problem behoben.</span><span class="sxs-lookup"><span data-stu-id="06b6d-250">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="06b6d-251">Beim Verbinden eines PCs mit der Konsole über verkabelte Erfassung kann ein Verlust der lokalen Audiodaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="06b6d-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="06b6d-252">Das Problem mit der Wiedergabe der lokalen Audiodaten kann in diesem Fall durch einen Neustart des PCs gelöst werden.</span><span class="sxs-lookup"><span data-stu-id="06b6d-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    