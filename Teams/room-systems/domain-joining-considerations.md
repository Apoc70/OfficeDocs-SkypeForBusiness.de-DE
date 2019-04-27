---
title: Überlegungen zur Domänenzusammenführung in Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
ms.openlocfilehash: 675074cc61b60432e68317d139b20b727073961f
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362812"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="113a9-103">Überlegungen zur Domänenzusammenführung in Skype Room System</span><span class="sxs-lookup"><span data-stu-id="113a9-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="113a9-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="113a9-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="113a9-105">Überlegungen zur Domänenteilnahme</span><span class="sxs-lookup"><span data-stu-id="113a9-105">Domain joining considerations</span></span>

<span data-ttu-id="113a9-106">Sie können die Appliance Skype Raum System PC zur Active Directory-Domäne beitreten zu oder verlassen es in einer Arbeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="113a9-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="113a9-107">Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:</span><span class="sxs-lookup"><span data-stu-id="113a9-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="113a9-108">Beitreten der Appliance Skype Raum System PC zu Domäne kann in Ihrer Organisation private stammzertifikatkette automatisch zu importieren.</span><span class="sxs-lookup"><span data-stu-id="113a9-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="113a9-109">Beitreten der Appliance Skype Raum System PC zu Domäne können Sie Domänen-Benutzer und Gruppen über Administratorrechte erteilen.</span><span class="sxs-lookup"><span data-stu-id="113a9-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="113a9-110">Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.</span><span class="sxs-lookup"><span data-stu-id="113a9-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="113a9-111">Wenn Sie eine Einheit Skype Raum System PC mit der Domäne beitreten, ist es erforderlich, dass eine separate Organisationseinheit (OU), erstellen, sodass Sie Ausschlüsse Gruppenrichtlinienobjekt (GPO) für die Organisationseinheit vornehmen können, in denen alle Objekte der Skype Raum System Computer befinden.</span><span class="sxs-lookup"><span data-stu-id="113a9-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="113a9-112">Wenn Sie dies tun, erstellen Sie vor der Teilnahme an der Appliance Skype Raum System PC auf die Domäne Computer-Objekte in der Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="113a9-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="113a9-113">Viele Unternehmen haben die folgenden Gruppenrichtlinienobjekte, die Skype Raum System Appliance PC-Funktionen auswirken.</span><span class="sxs-lookup"><span data-stu-id="113a9-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="113a9-114">Stellen Sie sicher, dass Sie außer Kraft setzen oder die Vererbung von dieser Gruppenrichtlinienobjekte in der Organisationseinheit Skype Raum System blockieren:</span><span class="sxs-lookup"><span data-stu-id="113a9-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="113a9-115">Timeout von Anmeldesitzungen (automatische Sperre)</span><span class="sxs-lookup"><span data-stu-id="113a9-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="113a9-116">Richtlinien in Bezug auf die Energieverwaltung</span><span class="sxs-lookup"><span data-stu-id="113a9-116">Power management related policies</span></span>
    
  - <span data-ttu-id="113a9-117">Notwendigkeit zusätzlicher Authentifizierungsschritte</span><span class="sxs-lookup"><span data-stu-id="113a9-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="113a9-118">Verweigern des Zugriffs auf lokale Laufwerke</span><span class="sxs-lookup"><span data-stu-id="113a9-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="113a9-119">Benutzeraufforderungen bei langsamen Netzwerkverbindungen</span><span class="sxs-lookup"><span data-stu-id="113a9-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="113a9-120">Starten eines bestimmten Programms bei der Anmeldung</span><span class="sxs-lookup"><span data-stu-id="113a9-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="113a9-121">Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.</span><span class="sxs-lookup"><span data-stu-id="113a9-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="113a9-122">Drücken Sie Windows Update, um Raum Skype-System</span><span class="sxs-lookup"><span data-stu-id="113a9-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="113a9-123">Alternativ könnten Sie sich dazu entschließen, den Anwendungs-PC in der Arbeitsgruppe zu belassen.</span><span class="sxs-lookup"><span data-stu-id="113a9-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="113a9-124">Als muss mit dem Desktop Microsoft-Teams oder Skype für Business-Client dies die stammzertifikatkette der Einheit Skype Raum System PC manuell importieren.</span><span class="sxs-lookup"><span data-stu-id="113a9-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="113a9-125">Sie sind nicht erforderlich, um die stammzertifikatkette zu importieren, wenn in Ihrer Bereitstellung ein öffentliches Zertifikat (beispielsweise Entrust, VeriSign usw.) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="113a9-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="113a9-126">Wenn Sie beabsichtigen, Skype Raum System Computern in der Domäne einbinden, um zu vermeiden, beitreten zu Skype Raum System Computer versehentlich zu einer unbeabsichtigten Organisationseinheit, die nicht frei von Gruppenrichtlinienobjekten sein können, stellen Sie sicher, dass Sie die richtige Organisationseinheit teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="113a9-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="113a9-127">Sie können das folgende Cmdlet vom Computer Skype Raum System verwenden, um in der richtigen Organisationseinheit teilnehmen und erhält keine Gruppenrichtlinienobjekte, die möglicherweise LRS Funktionen blockiert.</span><span class="sxs-lookup"><span data-stu-id="113a9-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="113a9-128">Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, wenn Sie Fragen zur Ausführung dieses Cmdlets haben:</span><span class="sxs-lookup"><span data-stu-id="113a9-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="113a9-129">Sogar wenn Sie eine separate OU erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die Probleme auf einer höheren Ebene verursachen könnten.</span><span class="sxs-lookup"><span data-stu-id="113a9-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="113a9-130">Eine Gruppenrichtlinie mit „Nicht aufheben“-Einstellung hat Vorrang gegenüber einer OU mit „Richtlinienvererbung aufheben“-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="113a9-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="113a9-131">Weitere Informationen finden Sie im Artikel [Kein Vorrang im Vergleich zu blockieren der Vererbung von Gruppenrichtlinien](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in der Dokumentation zu Gruppenrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="113a9-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="113a9-132">Unter Umständen stehen Ihnen mehrere Ansätze zur Lösung dieser Probleme zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="113a9-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="113a9-133">Es wird empfohlen, dass Sie sich an Ihre Active Directory-Experten wenden, um sicherzustellen, dass Sie über eine OU mit den angemessenen GPO-Einstellungen oder wenigstens über eine OU verfügen, in der die weiter oben beschriebenen Richtlinien nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="113a9-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="113a9-134">Es wird empfohlen, um Quality of Service (QoS) für Geräte Skype Raum System zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="113a9-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="113a9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="113a9-135">See also</span></span>
  
[<span data-ttu-id="113a9-136">Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="113a9-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="113a9-137">Verwalten der Dienstqualität (Quality of Service, QoS)</span><span class="sxs-lookup"><span data-stu-id="113a9-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)