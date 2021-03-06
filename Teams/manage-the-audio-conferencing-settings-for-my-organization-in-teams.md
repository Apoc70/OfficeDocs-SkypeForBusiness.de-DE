---
title: Verwalten von Audio-Konferenzeinstellungen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Hier finden Sie Informationen zu den Schritten, mit denen Sie in Microsoft Teams einem Benutzer eine Lizenz für Dial-in-Konferenzen und eine Konferenzkennung zuweisen, sowie zu vielen anderen Einstellungen für Dial-in-Konferenzen. '
ms.openlocfilehash: f2d056ffd2c3b40b8e39f6d4727859b45e675ebf
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031801"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams.

Möglicherweise ist es einfacher für Sie, alle Audiokonferenzeinstellungen für Microsoft Teams an derselben Stelle zu sehen. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audiokonferenzen

> [!NOTE]
> Sie können mit Microsoft Teams keine Lizenzen zuweisen. Sie müssen das Microsoft 365 Admin Center verwenden. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing). 
  
 **So weisen Sie eine Lizenz für einen Benutzer zu**
  
1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.
    
2. Navigieren Sie in der linken Navigationsleiste des **Microsoft 365 Admin Center** zu **den**  >  **aktiven** Benutzern des Benutzers, und wählen Sie dann den Benutzer oder die Benutzer aus der Liste der verfügbaren Benutzer aus.
    
    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter** , wählen Sie die Lizenz aus, und klicken Sie auf **Submit** (Übermitteln).  
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**. 
    
4. Aktivieren Sie auf der Seite **Produktlizenzen** die **Option Audiokonferenzen** , und klicken Sie dann auf **Speichern**. Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).
    
   > [!NOTE]
   > Nachdem Sie die Lizenz zugewiesen haben, wird Microsoft möglicherweise zunächst nicht als Audiokonferenz-Anbieter in der Liste angezeigt. Wenn dies der Fall ist, melden Sie sich entweder beim Admin Center ab, oder drücken Sie STRG + F5, um das Browserfenster zu aktualisieren. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren der an Audiokonferenzbenutzer gesendeten E-Mails

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.

4. Klicken Sie auf **Speichern**.

    
**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

![Ein Symbol, das das Team-Logo ](media/teams-logo-30x30.png) **mit dem Microsoft Teams Admin Center** zeigt

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurücksetzen**.  

3. Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**. Eine Konferenz-ID wird automatisch erstellt, und eine e-Mail, die an den Benutzer mit der neuen Konferenz-ID gesendet wird, wenn das Senden von e-Mails an Ihre Benutzer aktiviert ist. It's enabled by default.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es vorkommen, dass ein Benutzer diesen nicht verwenden möchte, und Sie ihn auf eine bestimmte Nummer setzen möchten, oder wenn sich Ihre Benutzer nicht mehr daran erinnern oder Ihre Konferenz-ID verloren haben. 

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenzen** auf **PIN zurücksetzen** und dann auf **Zurücksetzen**. 
  
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt. 
  
Siehe [Zurücksetzen der Audiokonferenz-Pin](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer e-Mail mit Audio-Konferenz Informationen an einen Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie unter **Audiokonferenz** auf **Konferenz Informationen in einer e-Mail senden**. 

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet. 

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer** , und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie neben **Audiokonferenzen** auf **Bearbeiten**.
 
3. Im Bereich **Audiokonferenz** können Sie die **gebührenpflichtige Nummer** und, falls zulässig, die **gebührenfreie Nummer** einstellen.

4. Klicken Sie auf **Speichern**.
    
Weitere Informationen finden Sie unter [Einrichten der Telefonnummern, die in Einladungen enthalten sind](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Auswählen von Audiokonferenz-Brücken Einstellungen

**Einrichten der Besprechungs Erfahrung, wenn Anrufer an einer Besprechung teilnehmen**

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Konferenz Brücken** auf **Brücken Einstellungen**. 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).

    Dies ist standardmäßig aktiviert. Wenn Sie diese Option deaktivieren, werden Benutzer, die der Besprechung standardmäßig bereits beigetreten sind, nicht benachrichtigt, wenn jemand die Besprechung eingibt oder verlässt.

4. Wählen Sie unter **Eintrag/Exit Announcement** entweder **Töne** oder **Namen oder Telefonnummern** aus. 

    Wenn Sie **Namen oder Telefonnummern** wählen, können Sie auch festlegen, dass **Anrufer bitten, Ihren Namen aufzuzeichnen, bevor Sie an der Besprechung teilnehmen**. 
    > [!NOTE]
    > Standardmäßig können externe Teilnehmer die Telefonnummern von Einwahl Teilnehmern nicht sehen. Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden).


5. Klicken Sie auf **Speichern**.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Geben Sie auf der Seite **Bridge settings** (Brückeneinstellungen) in der Liste **PIN-Länge** die gewünschte Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern**.

    Die PIN muss aus vier bis zwölf Ziffern bestehen. Standardmäßig werden fünf Ziffern verwendet.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren der an Audiobenutzer gesendeten E-Mails**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Automatically send emails to users if their audio conferencing settings change** (Bei einer Änderung der Audiokonferenzeinstellungen automatisch E-Mails an Benutzer senden).

4. Klicken Sie auf **Speichern**. 
 
    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden. Navigieren Sie dazu zu den Audiokonferenzeigenschaften des Benutzers, und klicken Sie auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).
    
    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Anzeigen und Festlegen der primären Sprache (Standardsprache) und der sekundären Sprachen (alternativen Sprachen) für eine Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**.

3. Wählen Sie die gewünschten Sprachen unter **Standardsprache** und **Alternative Sprachen (optional)** aus.

4. Klicken Sie auf **Speichern**.


Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten**. Hier können Sie:
    
   - Zeigen Sie die Telefonnummern an, die für Audiokonferenzen verwendet werden sollen. 
    
   - Zeigen Sie den Standort und die primäre Sprache an, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.

  
Weitere Informationen finden Sie unter [Anzeigen einer Liste von Audiokonferenz-Nummern](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


