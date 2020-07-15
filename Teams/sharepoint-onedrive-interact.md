---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & OneDrive for Business-Interaktion mit Teams; Speicherung privater Chat-Dateien & Interaktion zwischen Team, Standardkanal & Dokumentbibliothek.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a66cacf7a60b020b4b56e0824d0a275efdf704f8
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45140939"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="b4d45-103">Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4d45-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="b4d45-104">Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="b4d45-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="b4d45-105">Jedes Team in Microsoft Teams hat eine Teamwebsite in SharePoint Online, und jeder Standardkanal in einem Team erhält einen Ordner in der standardmäßigen Teamwebsite-Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b4d45-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="b4d45-106">In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und die in SharePoint gesetzten Berechtigungen und Datei Sicherheitsoptionen werden in Teams automatisch wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b4d45-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="b4d45-107">Wenn Sie sehen möchten, welche Auswirkungen das Ändern einer Websiteadresse in SharePoint hat, lesen Sie [Ändern einer Websiteadresse](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="b4d45-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="b4d45-108">Dieser Artikel bezieht sich nur auf Standardkanäle.</span><span class="sxs-lookup"><span data-stu-id="b4d45-108">This article applies only to standard channels.</span></span> <span data-ttu-id="b4d45-109">Die Architektur für private Kanäle unterscheidet sich von Standardkanälen.</span><span class="sxs-lookup"><span data-stu-id="b4d45-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="b4d45-110">Jeder private Kanal verfügt über eine eigene SharePoint-Websitesammlung, die von der übergeordneten Teamwebsite getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="b4d45-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="b4d45-111">Weitere Informationen finden Sie unter [private Kanäle in Microsoft Teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="b4d45-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="b4d45-112">Private Chat-Dateien werden im OneDrive for Business-Ordner des Absenders gespeichert, und Berechtigungen werden allen Teilnehmern im Rahmen des Dateifreigabe Prozesses automatisch gewährt.</span><span class="sxs-lookup"><span data-stu-id="b4d45-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="b4d45-113">Wenn Benutzer nicht mit SharePoint Online-Lizenzen zugewiesen und aktiviert sind, verfügen Sie nicht über OneDrive for Business-Speicher in Microsoft 365 oder Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4d45-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="b4d45-114">Die Dateifreigabe funktioniert weiterhin in Standardkanälen, aber die Benutzer können keine Dateien in Chats ohne OneDrive for Business-Speicher in Microsoft 365 oder Office 365 freigeben.</span><span class="sxs-lookup"><span data-stu-id="b4d45-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="b4d45-115">Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten.</span><span class="sxs-lookup"><span data-stu-id="b4d45-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4d45-116">Die Integration in SharePoint lokal wird für Microsoft Teams zurzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4d45-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="b4d45-117">Im folgenden finden Sie ein Beispiel für Beziehungen zwischen Team, Standardkanal und Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="b4d45-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="b4d45-118">Für jedes Team wird eine SharePoint-Website erstellt, und der Ordner " **freigegebene Dokumente** " ist der Standardordner, der für das Team erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b4d45-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="b4d45-119">Jeder Standardkanal, einschließlich des **allgemeinen** Kanals (der Standardkanal für jedes Team), verfügt über einen Ordner in **freigegebenen Dokumenten**.</span><span class="sxs-lookup"><span data-stu-id="b4d45-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramm der Ordner "freigegebene Dokumente" in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="b4d45-121">Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b4d45-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="b4d45-122">Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung.</span><span class="sxs-lookup"><span data-stu-id="b4d45-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="b4d45-123">In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4d45-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="b4d45-124">So fügen Sie Ihrem Team eine Registerkarte hinzu, die mit einer vorhandenen SharePoint-Website Seite oder mit Ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft ist:</span><span class="sxs-lookup"><span data-stu-id="b4d45-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="b4d45-125">Wählen Sie das Pluszeichen neben den Registerkarten aus.</span><span class="sxs-lookup"><span data-stu-id="b4d45-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="b4d45-126">Wählen Sie entweder **SharePoint** für eine vorhandene SharePoint-Website Seite oder eine **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="b4d45-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="b4d45-127">Wählen Sie die entsprechende Seite oder Dokumentbibliothek aus.</span><span class="sxs-lookup"><span data-stu-id="b4d45-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="b4d45-128">Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b4d45-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramm des OneDrive-Ordners mit dem Namen Microsoft Teams-Chat Dateien](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="b4d45-130">Beachten Sie, dass für öffentliche Teams die SharePoint-Teamwebsite mit dem Zugriff "jeder außer externen Benutzern" bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b4d45-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="b4d45-131">Das öffentliche Team wird nicht in Teams für Personen angezeigt, die nicht Mitglieder dieses Teams sind.</span><span class="sxs-lookup"><span data-stu-id="b4d45-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="b4d45-132">Sie können jedoch mithilfe der URL der SharePoint-Teamwebsite auf Inhalte auf der SharePoint-Teamwebsite zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b4d45-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="b4d45-133">Registerkarte "Kanaldateien"</span><span class="sxs-lookup"><span data-stu-id="b4d45-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="b4d45-134">Die Registerkarte **Dateien** in Microsoft Teams ähnelt der Ansicht SharePoint-Dokumente.</span><span class="sxs-lookup"><span data-stu-id="b4d45-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="b4d45-135">Auf der Registerkarte " **Dateien** " können Benutzer:</span><span class="sxs-lookup"><span data-stu-id="b4d45-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="b4d45-136">Weitere Optionen finden Sie im Menü " **neue** Datei".</span><span class="sxs-lookup"><span data-stu-id="b4d45-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="b4d45-137">Synchronisieren Sie Dateien auf dem lokalen Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="b4d45-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="b4d45-138">Wechseln Sie im Menü **alle Dokumente** von der **Listen** Ansicht zur **kompaktliste** in die **Kachel** Ansicht.</span><span class="sxs-lookup"><span data-stu-id="b4d45-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="b4d45-139">Ermitteln Sie Dateien, die auf die Berücksichtung oder Malware abstellen.</span><span class="sxs-lookup"><span data-stu-id="b4d45-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="b4d45-140">Sehen Sie sofort, ob eine Datei schreibgeschützt oder ausgecheckt ist.</span><span class="sxs-lookup"><span data-stu-id="b4d45-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="b4d45-141">Auschecken und Einchecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="b4d45-141">Check out and check in files.</span></span>
- <span data-ttu-id="b4d45-142">Anheften, unpin und Ändern der Sortierreihenfolge von Dateien</span><span class="sxs-lookup"><span data-stu-id="b4d45-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="b4d45-143">Ermitteln, welche Dateien Metadaten benötigen</span><span class="sxs-lookup"><span data-stu-id="b4d45-143">Identify which files need metadata</span></span>
- <span data-ttu-id="b4d45-144">Wählen Sie aus vielen weiteren Filteroptionen aus.</span><span class="sxs-lookup"><span data-stu-id="b4d45-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="b4d45-145">Gruppieren Sie Dateien basierend auf Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="b4d45-145">Group files based on column headings.</span></span>
- <span data-ttu-id="b4d45-146">Ändern Sie die Spalteneinstellungen (nach links oder rechts, ausblenden) und Spaltenbreite.</span><span class="sxs-lookup"><span data-stu-id="b4d45-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="b4d45-147">Standardeinstellung für den Verknüpfungstyp</span><span class="sxs-lookup"><span data-stu-id="b4d45-147">Default link type setting</span></span>

<span data-ttu-id="b4d45-148">SharePoint und OneDrive verfügen über eine Administratoreinstellung zum Angeben des Standardverknüpfungstyp für Links, die für eine Datei erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b4d45-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="b4d45-149">Teams nimmt denselben Ansatz an, indem die Einstellungen wieder verwendet werden, die der Administrator für SharePoint und OneDrive festlegt.</span><span class="sxs-lookup"><span data-stu-id="b4d45-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="b4d45-150">Weitere Informationen zu diesem Ansatz finden Sie unter [Ändern des Standard Link Typs, wenn Benutzer Links für die Freigabe erhalten](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="b4d45-150">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="b4d45-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4d45-151">More information</span></span>

<span data-ttu-id="b4d45-152">Weitere Informationen zur Funktionsweise von SharePoint mit Teams finden Sie unter [SharePoint und Teams: besser zusammen](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="b4d45-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="b4d45-153">Wenn Sie mehr über die Gastfreundlichkeit in Teams erfahren möchten, lesen Sie, [wie die Gast Erfahrung aussieht](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="b4d45-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>
