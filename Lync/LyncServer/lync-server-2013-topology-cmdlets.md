---
title: 'Lync Server 2013: Topologie-Cmdlets'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2fc5224257c4bb228fdcb0b6f6f27f5416a3b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="b9e6e-102">Topologie-Cmdlets Jn lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9e6e-102">Topology cmdlets jn Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e6e-103">_**Letztes Änderungsdatum des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b9e6e-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b9e6e-104">Viele der in Microsoft lync Server 2013 enthaltenen Topologie-Cmdlets sind für die Verwendung mit dem Setup-und Topologie-Generator konzipiert. aus diesem Grund gibt es eine Reihe von Topologie-Cmdlets, die von Administratoren nur selten direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="b9e6e-105">Es gibt jedoch Situationen, in denen Administratoren verpflichtet werden, diese Cmdlets zu verwenden. Nachdem Sie beispielsweise neue Kerberos-Konten erstellt haben, müssen Sie das Cmdlet [enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) ausführen, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="b9e6e-106">Darüber hinaus werden Administratoren wahrscheinlich Cmdlets wie [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) und [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) ausführen, um sicherzustellen, dass lync Server 2013 ordnungsgemäß installiert wurde und wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b9e6e-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="b9e6e-107">Topologie-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b9e6e-107">Topology Cmdlets</span></span>

<span data-ttu-id="b9e6e-108">Die folgende Liste enthält Cmdlets, die sich direkt auf die Verwaltung Ihrer lync Server-Topologie beziehen:</span><span class="sxs-lookup"><span data-stu-id="b9e6e-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="b9e6e-109">**Topologie**</span><span class="sxs-lookup"><span data-stu-id="b9e6e-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-110">[Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9e6e-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-111">[Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-112">[Satz-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-112">[Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9e6e-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-113">[Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-114">[Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-115">[Publish-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-116">[Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9e6e-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-117">[Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-118">[Importieren-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-118">[Import-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9e6e-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-119">[Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9e6e-120">[Deaktivieren-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-120">[Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-121">[Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-122">[Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b9e6e-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-123">[Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b9e6e-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b9e6e-124">[Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9e6e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9e6e-125">See Also</span></span>


[<span data-ttu-id="b9e6e-126">Lync Server PowerShell-Blog</span><span class="sxs-lookup"><span data-stu-id="b9e6e-126">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
