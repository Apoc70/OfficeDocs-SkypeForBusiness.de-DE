---
title: Starten einer Audiokonferenz per Telefon ohne PIN in Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Hier erfahren Sie, wie Sie im Teams Admin Center die Teilnahme anonymer Anrufer an einer Besprechung aktivieren oder deaktivieren. '
ms.openlocfilehash: 6d5dd7c08d37993c541a0a4f670fd240057bfb3a
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691501"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams

Für Benutzer, die sich in eine Besprechung einwählen, kann es frustrierend sein, im Wartebereich platziert zu werden und Musik zu hören, da der Microsoft Teams-Besprechungsorganisator die Besprechung noch nicht gestartet hat. 
  
Wenn sich ein Besprechungsorganisator in die Besprechung einwählt, benötigt er zum Starten der Besprechung standardmäßig eine PIN. Sie können dies so einrichten, dass sich jeder in die Besprechung einwählen kann, ohne zur Eingabe einer PIN zum Starten der Besprechung aufgefordert zu werden. Sie können diese Einstellung für einen einzelnen Benutzer im Admin Center aktivieren oder deaktivieren.
  
Der Besprechungsorganisator benötigt keine PIN, wenn jemand die Besprechung über die Microsoft Teams-App gestartet hat. Eine PIN ist nur erforderlich, wenn der Besprechungsorganisator per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen und er für Audiokonferenzen aktiviert wird. Weitere Informationen finden Sie unter [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) und [E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren der Teilnahme anonymer Anrufer an einer Besprechung

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**. 

2. Wählen Sie einen Benutzer in der Liste aus, und klicken Sie dann oben auf der Seite auf **Bearbeiten**. 

3. Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**.

4. Aktivieren oder deaktivieren Sie im Bereich **Audiokonferenz** **-Einwahl Anrufer die erste Person in einer Besprechung**.
    
4. Klicken Sie auf **Anwenden**. 

**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, lesen Sie [Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md).
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN nicht erforderlich ist, ist deaktiviert:
    
  - Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird gefragt, ob er der Organisator ist. Wenn er dies bejaht, wird er aufgefordert, seine PIN einzugeben. Wenn er die PIN eingegeben hat, wird die Besprechung gestartet, und der Benutzer nimmt teil.
    
  - Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung keine PIN erfordert, ist aktiviert:
    
  - Wenn die Besprechung nicht begonnen hat (also noch keine Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Da die Einstellung für den Organisator deaktiviert ist, beginnt die Besprechung, und der anonyme Anrufer nimmt an der Besprechung teil.
    
  - Wenn die Besprechung bereits begonnen hat (also bereits Teilnehmer anwesend sind): Der Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nicht aufgefordert, die PIN einzugeben. Die Besprechung wurde bereits gestartet, und der Anrufer nimmt teil.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

In Windows PowerShell geht es um die Verwaltung von Benutzern und die Benutzer, die zugelassen oder nicht zulässig sind. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe einer zentralen Verwaltungsstelle verwalten, die Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Die ersten Schritte mit Windows PowerShell finden Sie in den folgenden Themen:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
