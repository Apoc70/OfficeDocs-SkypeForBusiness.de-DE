---
title: Ausführliche Informationen zur Tabelle für den Server für beständigen Chat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: In den folgenden Themen werden die Spalten den beständigen Chat Database Schema Tabellen.
ms.openlocfilehash: 5ee15bfab456f2e2e5c1ea535a1b521f9544a352
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212670"
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="ac19c-103">Ausführliche Informationen zur Tabelle für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="ac19c-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="ac19c-104">In den folgenden Themen werden die Spalten den beständigen Chat Database Schema Tabellen.</span><span class="sxs-lookup"><span data-stu-id="ac19c-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ac19c-105">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="ac19c-105">In this section</span></span>

- [<span data-ttu-id="ac19c-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="ac19c-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="ac19c-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="ac19c-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="ac19c-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="ac19c-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="ac19c-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="ac19c-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="ac19c-110">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="ac19c-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="ac19c-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="ac19c-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="ac19c-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="ac19c-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="ac19c-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="ac19c-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="ac19c-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="ac19c-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="ac19c-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="ac19c-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="ac19c-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="ac19c-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="ac19c-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="ac19c-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="ac19c-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="ac19c-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="ac19c-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="ac19c-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="ac19c-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="ac19c-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="ac19c-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="ac19c-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="ac19c-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="ac19c-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="ac19c-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="ac19c-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="ac19c-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="ac19c-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="ac19c-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="ac19c-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="ac19c-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="ac19c-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="ac19c-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="ac19c-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="ac19c-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="ac19c-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="ac19c-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="ac19c-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="ac19c-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="ac19c-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="ac19c-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="ac19c-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="ac19c-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="ac19c-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="ac19c-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="ac19c-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="ac19c-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="ac19c-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="ac19c-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="ac19c-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="ac19c-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="ac19c-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

