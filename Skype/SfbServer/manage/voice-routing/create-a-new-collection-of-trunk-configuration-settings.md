---
title: Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert.
ms.openlocfilehash: 1dff6eaf5c3c9b0d7ea2378dc5499568b0bd65a3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823415"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Skype for Business Server

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:
- Ob die Medienumgebung für Trunks aktiviert werden soll.
- Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.
- Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Bei der Installation von Skype for Business Server wird eine globale Auflistung von Sip-Trunk-Konfigurationseinstellungen erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

Beim Erstellen von SIP-Trunk-Konfigurationseinstellungen mithilfe der Systemsteuerung vonSkype for Business Server stehen Ihnen die folgenden Optionen zur Verfügung:

|UI-Einstellung | PowerShell-Parameter | Beschreibung |
|--|--|--|
|Name|Identität|Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.|
|Beschreibung|Beschreibung|Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).|
|Maximal unterstützte frühe Dialoge|MaxEarlyDialogs|Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.|
|Unterstützte Verschlüsselungsstufe|SRTPMode|Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung "EncryptionLevel" in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der [Cmdlets "New-CsMediaConfiguration"](https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration) und ["Set-CsMediaConfiguration"](https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration) festgelegt.<br/>Gültige Werte sind:<br/><br/>**Erforderlich:** Die SRTP-Verschlüsselung muss verwendet werden.<br/>**Optional:** SRTP wird verwendet, wenn es vom Gateway unterstützt wird.<br/>**Nicht** unterstützt: Die SRTP-Verschlüsselung wird nicht unterstützt und wird daher nicht verwendet.<br/><br/>"SRTPMode" wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird "SRTPMode" intern auf "Not Supported" festgelegt.|
|Support melden|Enable3pccRefer<br/>EnableReferSupport|Mit der Einstellung **Refer-Anforderungen an das Gateway senden** unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.<br/>Mit der Einstellung **Refer-Anforderungen mit 3pcc senden** kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen "Third Party Call Control" bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).|
|Medienumgehung aktivieren|EnableBypass|Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch **Zentrale Medienverarbeitung** aktiviert ist.|
|Zentrale Medienverarbeitung|12222|Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)|
|RTP-Latching aktivieren|EnableRTPLatching|Gibt an, ob SIP-Trunks RTP-Latching unterstützen oder nicht. RTP-Latching ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.|
|Weiterleiten der Anrufliste aktivieren|ForwardCallHistory|Gibt an, ob Informationen zum Anruferverlauf durch den Trunk weitergeleitet werden.|
|Weiterleiten von P-Asserted-Identity-Daten aktivieren|ForwardPAI|Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.|
|Timer für Ausgangsroutingfailover aktivieren|EnableFastFailoverTimer|Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gateway-Reaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.|
|Zugeordnete PSTN-Verwendungen|PSTNUsages|Eine Sammlung von dem Trunk zugewiesenen PSTN-Verwendungen.|
|Übersetzte Nummer zum Testen|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.|
|Zugehörige Übersetzungsregeln|OutboundTranslationRulesList|Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).|
|Übersetzungsregeln für angerufene Nummern|OutboundCallingNumberTranslationRulesList|Sammlung an Regeln für die Nummernübersetzung für ausgehende Anrufe, die dem Trunk zugewiesen sind.|
|Testtelefonnummer|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Anrufende Nummer|Nicht zutreffend|Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.|
|Angerufene Nummer|Nicht zutreffend|Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.|
||||

> [!Note]
> Die Skype for Business Server-CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die in der Skype for Business Server-Systemsteuerung nicht angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "New-CsTrunkConfiguration".](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration) 

**So erstellen Sie neue Trunkkonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung**

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **"Sprachrouting"** und dann auf **"Trunkkonfiguration".**
2. Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen auf Standortebene zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen auf Dienstebene zu erstellen.
3. Wählen  Sie im Dialogfeld  "Standort auswählen" oder "Dienst auswählen" (das angezeigte Dialogfeld hängt davon ab, ob Sie Einstellungen auf Standort- oder Dienstbereichsseite erstellen), wählen Sie den Speicherort für die neuen Konfigurationseinstellungen aus, und klicken Sie dann auf **OK**. Wenn das Dialogfeld leer ist, bedeutet dies, dass es keinen Ort zum Erstellen der neuen Einstellungen gibt. Wenn beispielsweise das  Dialogfeld Standort auswählen leer ist, bedeutet dies, dass allen Standorten bereits eine Auflistung von Trunkkonfigurationsstandorten zugewiesen wurde und jeder Standort (und jeder Dienst) nur eine solche Auflistung hosten kann. In diesem Fall können Sie entweder die vorhandene Auflistung löschen und eine neue Auflistung erstellen oder einfach die vorhandene Auflistung ändern.
4. Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor, und klicken Sie auf **OK**.
5. Die Eigenschaft **Zustand** für die Sammlung wird aktualisiert und lautet jetzt **Ohne Commit**. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit** und dann auf **Commit für alle**.
6. Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.
7. Klicken Sie **im Dialogfeld "Skype for Business-Systemsteuerung"** auf **"OK".**
