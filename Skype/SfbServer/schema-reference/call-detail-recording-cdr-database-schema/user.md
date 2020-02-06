---
title: Benutzeransicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Die Benutzeransicht speichert Informationen zu Benutzern, die an anrufen oder Sitzungen beteiligt waren, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814833"
---
# <a name="user-view"></a><span data-ttu-id="b5f30-104">Benutzeransicht</span><span class="sxs-lookup"><span data-stu-id="b5f30-104">User view</span></span>
 
<span data-ttu-id="b5f30-105">Die Benutzeransicht speichert Informationen zu Benutzern, die an anrufen oder Sitzungen beteiligt waren, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b5f30-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="b5f30-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b5f30-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b5f30-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b5f30-107">**Column**</span></span>|<span data-ttu-id="b5f30-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b5f30-108">**Data Type**</span></span>|<span data-ttu-id="b5f30-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="b5f30-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b5f30-110">UserID</span><span class="sxs-lookup"><span data-stu-id="b5f30-110">UserId</span></span>  <br/> |<span data-ttu-id="b5f30-111">int</span><span class="sxs-lookup"><span data-stu-id="b5f30-111">int</span></span>  <br/> |<span data-ttu-id="b5f30-112">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b5f30-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b5f30-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="b5f30-113">UserUri</span></span>  <br/> |<span data-ttu-id="b5f30-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5f30-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b5f30-115">Der URI des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b5f30-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="b5f30-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="b5f30-116">TenantKey</span></span>  <br/> |<span data-ttu-id="b5f30-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b5f30-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b5f30-118">Mandant des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="b5f30-118">Tenant of user.</span></span> <span data-ttu-id="b5f30-119">Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="b5f30-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b5f30-120">UriType</span><span class="sxs-lookup"><span data-stu-id="b5f30-120">UriType</span></span>  <br/> |<span data-ttu-id="b5f30-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b5f30-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b5f30-122">Der Typ des Benutzer-URIs.</span><span class="sxs-lookup"><span data-stu-id="b5f30-122">Type of user URI.</span></span> <span data-ttu-id="b5f30-123">Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="b5f30-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

