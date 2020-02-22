---
title: Konfigurieren des VoIP-Routings für das direkte Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie das VoIP-Routing mit Microsoft Phone System Direct Routing konfigurieren.
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157967"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Konfigurieren des VoIP-Routings für das direkte Routing

In diesem Artikel wird beschrieben, wie Sie das VoIP-Routing für das direkte Routing von Telefonsystemen konfigurieren.  Dies ist Schritt 3 der folgenden Schritte zum Konfigurieren des direkten Routings:

- Schritt 1: [Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md) 
- Schritt 2: [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)    
- **Schritt 3. Konfigurieren des VoIP-Routings** (dieser Artikel)
- Schritt 4: [Übersetzen von Zahlen in ein anderes Format](direct-routing-translate-numbers.md) 

Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Übersicht über das VoIP-Routing

Microsoft Phone System verfügt über einen Routingmechanismus, mit dem ein Anruf an einen bestimmten Session Border Controller (SBC) basierend auf folgenden Informationen gesendet werden kann: 

- Das so genannte Zahlenmuster 
- Das angerufene Zahlenmuster und der spezifische Benutzer, der den Anruf tätigt
 
SBCS kann als aktiv und als Backup festgelegt werden. Wenn der als aktiv konfigurierte SBC für eine bestimmte Anrufroute nicht zur Verfügung steht, wird der Anruf an eine Sicherungs-SBC weitergeleitet.
 
Das VoIP-Routing besteht aus den folgenden Elementen: 

- **VoIP-Routing Richtlinie** – ein Container für PSTN-Nutzungen, der einem Benutzer oder mehreren Benutzern zugewiesen werden kann. 

- **PSTN-Verwendungen** – ein Container für VoIP-Routen und PSTN-Nutzungen, der in verschiedenen VoIP-Routing Richtlinien freigegeben werden kann. 

- **VoIP-Routen** – ein Zahlenmuster und eine Reihe von Online-PSTN-Gateways für Anrufe, bei denen die Rufnummer dem Muster entspricht.

- **Online-PSTN-Gateway** – ein Zeiger auf einen SBC, der auch die Konfiguration speichert, die angewendet wird, wenn ein Anruf über den SBC durchgeführt wird, wie z. b. Weiterleiten von P-Asserted-Identity (Pai) oder bevorzugten Codecs; kann zu VoIP-Routen hinzugefügt werden.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Beispiel 1: VoIP-Routing mit einer PSTN-Nutzung

Das folgende Diagramm zeigt zwei Beispiele für VoIP-Routing Richtlinien in einem Anruffluss.

**Anruffluss 1 (auf der linken Seite):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet. Wenn weder sbc1.contoso.biz noch sbc2.contoso.biz verfügbar sind, wird der Anruf abgebrochen. 

**Anruffluss 2 (rechts):** Wenn ein Benutzer einen Anruf an + 1 425 XXX XX XX oder + 1 206 XXX XX XX tätigt, wird der Anruf zuerst an SBC sbc1.contoso.biz oder sbc2.contoso.biz weitergeleitet. Wenn keine SBC verfügbar ist, wird die Route mit der niedrigeren Priorität ausprobiert (sbc3.contoso.biz und sbc4.contoso.biz). Wenn keine der SBCS verfügbar ist, wird der Anruf abgebrochen. 

![Zeigt Beispiele für VoIP-Routing Richtlinien](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

In beiden Beispielen wird die SBCS in den Routen in zufälliger Reihenfolge erprobt, während der VoIP-Route Prioritäten zugewiesen werden.

  > [!NOTE]
  > Wenn der Benutzer auch keine Microsoft-Anrufplan-Lizenz hat, werden Anrufe an eine beliebige Zahl mit Ausnahme der Zahlen, die mit den Mustern + 1 425 XXX XX XX oder + 1 206 XXX XX XX in der Beispielkonfiguration übereinstimmen, gelöscht. Wenn der Benutzer über eine Callingcard-Lizenz verfügt, wird der Anruf automatisch entsprechend den Richtlinien des Microsoft-Anruf Plans weitergeleitet. Der Microsoft-Anrufplan gilt automatisch als letzte Route für alle Benutzer mit der Lizenz für den Microsoft-Anrufplan und erfordert keine zusätzliche Konfiguration des Anruf Routings.

In dem Beispiel, das in der folgenden Abbildung gezeigt wird, wird eine VoIP-Route hinzugefügt, um Anrufe an alle anderen US-amerikanischen und kanadischen Nummern zu senden (Anrufe, die mit dem sogenannten Number-Muster + 1 XXX XXX XX XX gehen).

![Zeigt die VoIP-Routing Richtlinie mit einer dritten Route an](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Bei allen anderen anrufen:

- Wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan), wird die automatische Route verwendet. 
- Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, wird der Anruf über den Microsoft-Anrufplan weitergeleitet.
- Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf verworfen, weil keine übereinstimmenden Regeln verfügbar sind.

  > [!NOTE]
  > Der Prioritätswert für Route "Other + 1" ist in diesem Fall nicht wichtig, da nur eine Route vorhanden ist, die dem Muster + 1 XXX XXX XX XX entspricht. Wenn ein Benutzer einen Anruf an + 1 324 567 89 89 tätigt und sowohl sbc5.contoso.biz als auch sbc6.contoso.biz nicht zur Verfügung stehen, wird der Anruf abgebrochen.

In der folgenden Tabelle wird die Konfiguration mit drei VoIP-Routen zusammengefasst. In diesem Beispiel sind alle drei Routen Teil derselben PSTN-Nutzung "USA und Kanada".  Alle Routen sind mit der PSTN-Nutzung "USA und Kanada" verknüpft, und die PSTN-Nutzung ist mit der VoIP-Routing Richtlinie "nur US" verbunden. 

|**PSTN-Verwendung**|**VoIP-Route**|**Nummernmuster**|**Priorität**|**Sbchttps**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nur USA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für angerufene Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungs Route für genannte Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Andere + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Route für angerufene Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)|
|||||||


### <a name="example-1-configuration-steps"></a>Beispiel 1: Konfigurationsschritte

Im folgenden Beispiel wird gezeigt, wie Sie:

- Erstellen einer einzelnen PSTN-Nutzung 
- Konfigurieren von drei VoIP-Routen
- Erstellen einer VoIP-Routing Richtlinie
- Zuweisen der Richtlinie zum Benutzer Spencer Low

**Schritt 1:** Erstellen der PSTN-Nutzung "USA und Kanada"

Geben Sie in einer Skype for Business-Remote-PowerShell-Sitzung Folgendes ein:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Überprüfen Sie, ob die Verwendung erstellt wurde, indem Sie Folgendes eingeben: 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
Damit wird eine Liste der Namen zurückgegeben, die möglicherweise abgeschnitten werden:
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
Das folgende Beispiel zeigt das Ergebnis der Ausführung des PowerShell- `(Get-CSOnlinePSTNUsage).usage` Befehls zum Anzeigen von vollständigen Namen (nicht abgeschnitten):

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Schritt 2:** Erstellen Sie in einer PowerShell-Sitzung in Skype for Business Online drei Routen: Redmond 1, Redmond 2 und other + 1, wie in der vorhergehenden Tabelle gezeigt

Um die Route "Redmond 1" zu erstellen, geben Sie Folgendes ein:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Was zurückgegeben wird:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Um die Route Redmond 2 zu erstellen, geben Sie Folgendes ein:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Zum Erstellen der anderen + 1-Route geben Sie Folgendes ein:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Stellen Sie sicher, dass Ihr regulärer Ausdruck im NumberPattern-Attribut ein gültiger Ausdruck ist. Sie können es über diese Website testen:[https://www.regexpal.com](https://www.regexpal.com)

In einigen Fällen müssen alle Anrufe an denselben SBC weitergeleitet werden. use-NumberPattern ". *"

Alle Anrufe an denselben SBC weiterleiten.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Überprüfen Sie, ob Sie die Route ordnungsgemäß `Get-CSOnlineVoiceRoute` konfiguriert haben, indem Sie den PowerShell-Befehl unter Verwendung der folgenden Optionen ausführen:

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Was zurückgegeben werden sollte:
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

Im Beispiel wurde der Route "Other + 1" automatisch Priorität 4 zugewiesen. 

**Schritt 3:** Erstellen Sie eine VoIP-Routing Richtlinie "nur US", und fügen Sie der Richtlinie die PSTN-Nutzung "USA und Kanada" hinzu.

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Das Ergebnis wird im folgenden Beispiel gezeigt:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Schritt 4:** Erteilen Sie die VoIP-Routing Richtlinie mithilfe von PowerShell dem Benutzer Spencer Low:

Geben Sie in einer PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Überprüfen Sie die Richtlinienzuweisung, indem Sie den folgenden Befehl eingeben:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Der Befehl gibt Folgendes zurück:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Beispiel 2: VoIP-Routing mit mehreren PSTN-Nutzungen

Die in Beispiel 1 erstellte VoIP-Routing Richtlinie ermöglicht nur Anrufe an Telefonnummern in den USA und Kanada – es sei denn, die Lizenz für den Microsoft-Anrufplan wird dem Benutzer ebenfalls zugewiesen.

Im folgenden Beispiel können Sie die VoIP-Routing Richtlinie "keine Einschränkungen" erstellen. Die Richtlinie verwendet die in Beispiel 1 erstellte PSTN-Nutzung "USA und Kanada" sowie die neue PSTN-Nutzung "International" erneut.  Diese Richtlinie leitet alle anderen Anrufe an SBCS sbc2.contoso.biz und sbc5.contoso.biz weiter. 

In den Beispielen, die angezeigt werden, weisen Sie die nur US-Richtlinie Benutzern Spencer Low und die Richtlinie "keine Einschränkungen" für den Benutzer John Woods zu, damit das Routing wie folgt erfolgt:

- Spencer Low – nur US-Richtlinie.  Anrufe sind nur für US-und kanadische Rufnummern zulässig. Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCS verwendet werden. Nicht-US-Nummern werden nicht weitergeleitet, es sei denn, die Lizenz für den Anrufplan wird dem Nutzer zugewiesen.

- John Woods – internationale Richtlinie.  Anrufe sind an beliebige Rufnummern zulässig. Beim Aufrufen des Redmond-Nummernbereichs muss der spezifische Satz von SBCS verwendet werden. Nicht-US-Nummern werden mit sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet.

![Zeigt die VoIP-Routing Richtlinie, die dem Benutzer Spencer Low zugewiesen ist.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Bei allen anderen anrufen wird automatisch Route verwendet, wenn ein Benutzer über beide Lizenzen verfügt (Microsoft Phone System und Microsoft Calling Plan). Wenn nichts den Zahlen Mustern in den vom Administrator erstellten Online-VoIP-Routen entspricht, wird der Anruf mit dem Microsoft-Anrufplan weitergeleitet.  Wenn der Benutzer nur über ein Microsoft Phone-System verfügt, wird der Anruf abgebrochen, da keine übereinstimmenden Regeln verfügbar sind.

![Zeigt die dem Benutzer zugewiesenen VoIP-Routing Richtlinien an John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

Die folgende Tabelle enthält eine Zusammenfassung der Routing Richtlinie "keine Einschränkungen"-Nutzungs Bezeichnungen und VoIP-Routen. 

|**PSTN-Verwendung**|**VoIP-Route**|**Nummernmuster**|**Priorität**|**Sbchttps**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Nur USA|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Aktive Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Sicherungs Route für die angerufenen Nummern + 1 425 XXX XX XX oder + 1 206 XXX XX XX|
|Nur USA|"Andere + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Route für die angerufenen Nummern + 1 XXX XXX XX XX (außer + 1 425 XXX XX XX oder + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Route für beliebige Zahlenmuster |


  > [!NOTE]
  > - Die Reihenfolge der PSTN-Nutzungen in VoIP-Routing Richtlinien ist kritisch. Die Verwendungen werden in der angegebenen Reihenfolge angewendet, und wenn bei der ersten Verwendung eine Übereinstimmung gefunden wird, werden andere Verwendungen nie ausgewertet. Die PSTN-Nutzung "International" muss nach der PSTN-Nutzung "nur US" erfolgen. Führen Sie den `Set-CSOnlineVoiceRoutingPolicy` Befehl aus, um die Reihenfolge der PSTN-Verwendungen zu ändern. <br/>Um beispielsweise die Reihenfolge von "USA und Kanada" zuerst und "International" an zweiter Stelle in umgekehrter Reihenfolge zu ändern, führen Sie Folgendes aus:<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Die Priorität für VoIP-Routen "Other + 1" und "International" wird automatisch zugewiesen. Sie haben keine Bedeutung, solange Sie niedrigere Prioritäten als "Redmond 1" und "Redmond 2" haben.


### <a name="example-2-configuration-steps"></a>Beispiel 2: Konfigurationsschritte

Im folgenden Beispiel wird gezeigt, wie Sie:

- Erstellen einer neuen PSTN-Nutzung namens "International"
- Erstellen einer neuen VoIP-Route mit dem Namen "International"
- Erstellen einer VoIP-Routing Richtlinie mit dem Namen "keine Einschränkungen"
- Zuweisen der Richtlinie zum Benutzer John Woods


**Schritt 1**: Erstellen der PSTN-Nutzung "International" 

Geben Sie in einer Remote-PowerShell-Sitzung in Skype for Business Online Folgendes ein:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Schritt 2**: Erstellen der neuen VoIP-Route "International"

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Was zurückgegeben wird:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Schritt 3**: Erstellen einer VoIP-Routing Richtlinie "keine Einschränkungen". 

Die PSTN-Nutzung "Redmond 1" und "Redmond" werden in dieser VoIP-Routing Richtlinie wieder verwendet, um eine besondere Behandlung für Anrufe an die Nummer "+ 1 425 XXX XX XX" und "+ 1 206 XXX XX XX" als Orts-oder Lokalgespräche beizubehalten.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Notieren Sie sich die Reihenfolge der PSTN-Nutzungen:

  a. Wenn ein Anruf an die Nummer "+ 1 425 XXX XX XX" mit den im folgenden Beispiel konfigurierten Verwendungen erfolgt, folgt der Anruf dem in der Verwendung von "USA und Kanada" festgelegten Pfad, und die spezielle Routinglogik wird angewendet. Das bedeutet, dass der Anruf zuerst mithilfe von sbc1.contoso.biz und sbc2.contoso.biz und dann sbc3.contoso.biz und sbc4.contoso.biz als Sicherungs Routen weitergeleitet wird.

  b. Wenn die PSTN-Nutzung "International" vor "USA und Kanada" liegt, werden Anrufe nach + 1 425 XXX XX XX als Teil der Routinglogik an sbc2.contoso.biz und sbc5.contoso.biz weitergeleitet. Geben Sie den folgenden Befehl ein:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Was zurückgegeben wird:

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

**Schritt 4**: weisen Sie die VoIP-Routing Richtlinie mit dem folgenden Befehl dem Benutzer "John Woods" zu.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

Überprüfen Sie dann die Aufgabe mit dem folgenden Befehl: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Was zurückgegeben wird:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Das Ergebnis ist, dass die VoIP-Richtlinie, die auf die Anrufe von John Woods angewendet wurde, nicht eingeschränkt ist und der Logik des Anruf Routings für USA, Kanada und Auslandsgespräche folgen wird.



## <a name="see-also"></a>Siehe auch

[Planen von direktem Routing](direct-routing-plan.md)

[Konfigurieren von direktem Routing](direct-routing-configure.md)