---
title: Notfallanrufe planen und verwalten
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Informieren Sie sich über Notrufe, einschließlich Informationen zu Notfalladressen, Routing von Notrufen und dynamischen Notrufen.
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031601"
---
# <a name="manage-emergency-calling"></a>Verwalten von Notrufen

In diesem Artikel werden Konzepte beschrieben, die Sie für die Verwaltung von Notrufen wissen müssen &mdash; . es enthält Informationen zu Notfalladressen, dynamischen Notfalladressen und Routing für Notrufe. In diesem Artikel wird die folgende Terminologie verwendet:

- **Notfalladresse** – eine bürgerliche Adresse &mdash; die physische oder die Adresse eines Geschäfts Orts für Ihre Organisation.

  So wird beispielsweise die Adresse  *12345 North Main Street, Redmond, WA 98052* verwendet, um Notrufe an die entsprechenden Versand Behörden weiterzuleiten und den Notruf Anruf zu unterstützen.

- **Ort** – normalerweise ein Stockwerk, Gebäude, Flügel oder eine Büronummer. Ort ist mit einer Notfalladresse verknüpft, um eine genauere Position innerhalb eines Gebäudes zu erhalten. Sie können eine unbegrenzte Anzahl von Orten haben, die einer Notfalladresse zugeordnet sind. Wenn Ihre Organisation beispielsweise über mehrere Gebäude verfügt, möchten Sie möglicherweise Ortsinformationen für jedes Gebäude und für jede Etage in jedem Gebäude einbeziehen.  

- **Notfall Standort** – ein Ort ist eine bürgerliche Adresse &mdash; mit einem optionalen Ort. Wenn Ihr Unternehmen über mehr als einen physischen Standort verfügt, benötigen Sie wahrscheinlich mehr als einen Notfall Standort. 

  Wenn Sie eine Notfalladresse erstellen, wird automatisch eine eindeutige Standort-ID für diese Adresse erstellt.  Wenn Sie beispielsweise einen Ort zu einer Notfalladresse hinzufügen &mdash; , wenn Sie eine Etage zu einer Gebäudeadresse hinzufügen, &mdash; wird eine Standort-ID für die Kombination aus Notfalladresse und Ort erstellt.  In diesem Beispiel wird es zwei Standort-IDs geben: einen für die bürgerliche Adresse; eine für die verknüpfte bürgerliche Adresse und den zugehörigen Ort.

  Wenn Sie einem Benutzer oder einer Website einen Notfall Standort zuweisen, handelt es sich um diese eindeutige Standort-ID, die dem Benutzer oder der Website zugeordnet ist.

- **Registrierte Adresse** – eine Notfalladresse, die jedem Anruf Plan Benutzer zugewiesen ist; Sie wird manchmal als statische Notfalladresse oder Adresse des Eintrags bezeichnet.  (Registrierte Adressen gelten nicht für die direkte Weiterleitung von Benutzern.)

Sie erstellen Notfalladressen für den Anruf Plan Benutzer mithilfe des Teams admin Centers.  

>[!Note]
>Es gibt einige Unterschiede bei der Verwaltung von Notrufen, je nachdem, ob Sie Telefonsystem-Anrufpläne oder Telefonsystem-direkt Routing für Ihre PSTN-Konnektivität verwenden. Diese Überlegungen werden in diesem Artikel beschrieben.

## <a name="emergency-address-validation"></a>Notfalladressen Überprüfung

Wenn Sie einem Benutzer oder einer Netzwerkkennung eine Notfalladresse zuweisen möchten, müssen Sie sicherstellen, dass die Notfalladresse als "überprüft" gekennzeichnet ist.  Die Adressüberprüfung stellt sicher, dass die Adresse legitim ist und nicht geändert werden kann, nachdem Sie zugewiesen wurde. 

Wenn Sie eine Notfalladresse mithilfe der Funktion "Adresskarten Suche" im Team Admin Center definieren, wird die Adresse automatisch als überprüft markiert. Eine validierte Notfalladresse kann nicht geändert werden. Wenn sich das Format oder die Darstellung der Adresse ändert, müssen Sie daher eine neue Adresse mit dem aktualisierten Format erstellen.


## <a name="emergency-address-geo-codes"></a>Notfalladressen-Geo-Codes

Jede Notfalladresse kann einen Geocode (breiten-und Längengrad) aufweisen, der mit ihr verbunden ist. Diese Geo-Codes werden in einigen Ländern zur Unterstützung bei der Weiterleitung von Notrufen mit dynamischen Speicherorten verwendet. 

Wenn Sie eine Notfalladresse mithilfe der Funktion "Adresskarten Suche" im Team Admin Center definieren, wird dem Geo-Code automatisch eine Notfalladresse zugeordnet. Sie können auch Geo-Codes mit einer Adresse verknüpfen, wenn Sie die Adresse mithilfe von PowerShell definieren. Microsoft empfiehlt jedoch, dass Sie Notfalladressen für den Anrufplan erstellen, indem Sie das Feature "Kartensuche" im Team Admin Center verwenden, um sicherzustellen, dass die Adressen formatiert, überprüft werden und über die entsprechenden Geo-Codes verfügen.  

>[!Important]
>Wenn Sie einen Notfall Standort einem Netzwerkbezeichner für dynamische Notrufe zuweisen möchten, muss die Notfalladresse einen geeigneten Geo-Code enthalten.


## <a name="considerations-for-calling-plans"></a>Überlegungen für Anrufpläne

Informationen dazu, ob Anrufpläne in Ihrem Gebiet verfügbar sind, finden Sie unter [Verfügbarkeit von Ländern und Regionen für Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).


### <a name="emergency-call-enablement"></a>Notfall-Anruf Aktivierung

Jeder Nutzer des Anruf Plans wird automatisch für Notrufe aktiviert und benötigt eine registrierte Notfalladresse, die mit der zugewiesenen Telefonnummer verbunden ist. 

Wenn der Standort mit der Telefonnummer verbunden sein muss, hängt von dem Land/der Region ab:

- In den USA und Kanada ist beispielsweise ein Notfall Standort erforderlich, wenn einem Benutzer eine Nummer zugewiesen wird.

- Für andere Länder wie in Europa, dem Nahen Osten und Afrika (EMEA) ist ein Notfall Standort erforderlich, wenn Sie die Telefonnummer von Microsoft 365 oder Office 365 erhalten oder wenn Sie von einem anderen Dienstanbieter oder Netzbetreiber übertragen wird.

### <a name="dynamic-emergency-calling"></a>Dynamische Notrufe

Dynamische Notrufe für Microsoft-Anrufpläne bieten die Möglichkeit, Notrufe auf der Grundlage des aktuellen Standorts des Teams-Clients zu konfigurieren und zu leiten. Die Möglichkeit zur automatischen Weiterleitung an den entsprechenden öffentlichen Sicherheits-Anrufbeantworter (PSAP) oder zur Benachrichtigung über das Personal von Sicherheitsmitarbeitern variiert je nach dem Land, in dem der Benutzer des Teams verwendet wird.  

Für Benutzer des Anruf Plans wird der dynamische Standort für das Routing von Notrufen nur in den Vereinigten Staaten wie folgt unterstützt. (Informationen zu dynamischen Notrufen und direktem Routing finden Sie unter [Überlegungen für die direkte Weiterleitung](#considerations-for-direct-routing).

- Wenn ein Team-Client für einen USA-Anrufplan-Benutzer dynamisch eine Notfalladresse in den Vereinigten Staaten erwirbt, wird diese Adresse für das Notfall Routing anstelle der registrierten Adresse verwendet, und der Anruf wird automatisch an den PSAP im Servier Bereich der Adresse weitergeleitet.

- Wenn der Benutzer eines Teams für einen United States-Tarif Nutzer keine Notfalladresse in den Vereinigten Staaten erhält, wird die registrierte Notfalladresse verwendet, um den Anruf zu unterstützen und weiterzuleiten. Der Anruf wird jedoch angezeigt, um festzustellen, ob eine aktualisierte Adresse erforderlich ist, bevor der Anrufer mit dem entsprechenden PSAP verbunden wird.

In den USA müssen Sie die bürgerliche Adresse konfigurieren, die Teil der Notfall Speicherorte ist, die Netzwerkkennungen zugeordnet sind, &mdash; und die zugehörigen Geo-Codes einbeziehen. Weitere Informationen finden Sie unter [Planen und Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md).


### <a name="emergency-call-routing"></a>Notfall-Anrufweiterleitung

Wenn ein Team-Anruf Plan-Nutzer eine Notrufnummer anwählt, hängt die Art und Weise, wie der Anruf an die PSAP weitergeleitet wird, von folgenden ab:

- Gibt an, ob die Notfalladresse vom Team-Client dynamisch festgelegt wird.

- Gibt an, ob es sich bei der Notfalladresse um die registrierte Adresse handelt, die mit der Telefonnummer des Benutzers verbunden ist.

- Das Notruf Netz dieses Landes.

  **In den Vereinigten Staaten:**

  - Wenn sich ein Team-Client an einem vom Mandanten definierten dynamischen Notfall Standort befindet, werden Notrufe von diesem Client automatisch an die PSAP weitergeleitet, die diesem geografischen Standort dienen. 

  - Wenn sich ein Teams-Client nicht an einem vom Mandanten definierten dynamischen Notfall Standort befindet, werden Notrufe von diesem Client von einem nationalen Callcenter durchlaufen, um den Standort des Anrufers zu ermitteln, bevor der Anruf an die PSAP, die diesen geografischen Standort bedient, übertragen wird.

  - Wenn ein Notruf Anrufer seinen Notfall Standort nicht auf das Screening Center aktualisieren kann, wird der Anruf an den PSAP übertragen, der die registrierte Adresse des Anrufers bedient.

  **In Kanada, Irland und Großbritannien** werden Notrufe zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf an das entsprechende Dispatch Center angeschlossen wird. 

  **In Frankreich, Deutschland und Spanien** werden Notrufe direkt an das PSAP weitergeleitet, das die mit der Nummer verknüpfte Notfalladresse unabhängig vom Standort des Anrufers bedient.

  **In den Niederlanden** werden Notrufe direkt an den PSAP für die Ortsvorwahl der Nummer weitergeleitet, unabhängig von der Position des Anrufers.

  **In Australien** werden Notfalladressen vom Carrier-Partner konfiguriert und weitergeleitet.

  **In Japan** werden Notrufe nicht unterstützt.


Weitere Informationen finden Sie unter:

- [Anrufpläne](calling-plan-landing-page.md)

- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Nutzungsbedingungen für Notrufe](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Überlegungen zum direkten Routing

Wenn Anrufpläne nicht in Ihrem Gebiet verfügbar sind oder wenn Sie Ihren vorhandenen Netzbetreiber behalten möchten, sollten Sie die [direkte Weiterleitung](direct-routing-landing-page.md)in Frage stellen. Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md) und [Verwalten von Notfall Anruf Routing Richtlinien](manage-emergency-call-routing-policies.md).

### <a name="emergency-call-enablement-and-configuration"></a>Aktivierung und Konfiguration von Notrufen

Sie müssen Notfall-Anruf Richtlinien für die direkte Weiterleitung von Benutzern definieren, indem Sie eine Notfall-Anruf Weiterleitungs Richtlinie (TeamsEmergencyCallRoutingPolicy) verwenden, um Notrufnummern und deren zugehöriges Routingziel zu definieren. (Beachten Sie, dass registrierte Notfall Speicherorte für die direkte Weiterleitung von Benutzern nicht unterstützt werden.)

Sie können eine Notfall Anruf-Routing Richtlinie einem Direct Routing-Benutzerkonto für Teams, einer Netzwerk Website oder beides zuweisen. Wenn ein Teams-Client eine Netzwerkverbindung startet oder ändert, führt Teams eine Suche nach der Netzwerk Website durch, auf der sich der Client wie folgt befindet:

- Wenn der Website eine Notruf Routing Richtlinie zugeordnet ist, wird die Website Richtlinie zur Konfiguration von Notrufen verwendet.

- Wenn der Website keine Notfall-Anruf Weiterleitungs Richtlinie zugeordnet ist oder wenn der Client an einer nicht definierten Website verbunden ist, wird die für das Benutzerkonto zugeordnete Notfall Anrufrouting-Richtlinie verwendet, um Notrufe zu konfigurieren. 

- Wenn der Team-Client keine Notfall-Anruf Weiterleitungs Richtlinie erhalten kann, ist der Benutzer für Notrufe nicht aktiviert.

### <a name="dynamic-emergency-calling"></a>Dynamische Notrufe

Teams-Clients für Direct Routing-Benutzer können eine dynamische Notfalladresse abrufen, mit der Anrufe dynamisch auf Grundlage des Standorts des Anrufers weitergeleitet werden können. Weitere Informationen finden Sie unter [Konfigurieren von dynamischen Notrufen](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing"></a>Notfall-Anrufweiterleitung

Die Routing Richtlinie für Notrufe verweist auf eine Online-PSTN-Nutzung, die über die entsprechende Direct Routing-Konfiguration verfügen muss, um die Notrufe an das entsprechende PSTN-Gateway (s) weiterleiten zu können. Insbesondere müssen Sie sicherstellen, dass ein OnlineVoiceRoute für die Notruf Zeichenfolge vorhanden ist. Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md). 

(Hinweis: Teams-Clients stellen das "+"-Zeichen vor Notrufnummern auf eine ähnliche Weise voran, wie es der Skype for Business-Client tut; also + 911. Dieses Verhalten wird in den nächsten Monaten so geändert, dass Teams-Notrufe keine "+" mehr senden, die der Nummer vorangehen; Das ist 911.)

Die Möglichkeit zur dynamischen Weiterleitung von Notrufen für Direct Routing-Benutzer hängt vom Netzwerk für Notrufe innerhalb eines bestimmten Landes ab. Es stehen zwei Lösungen zur Verfügung:

- Notfall-Routing Dienstanbieter (nur USA) 
- Notfall Standort-Identifikationsnummer (Elin)-Gateway-Anwendungen

#### <a name="emergency-routing-service-providers"></a>Notfall-Routing Dienstanbieter

In den USA gibt es zahlreiche zertifizierte Notverwaltungsdienste (Emergency Routing Service Providers, ERSPs), die Notrufe basierend auf dem Standort des Anrufers automatisch weiterleiten können.

- Wenn ein Notfall-Routing-Service-Anbieter in eine direkte Routing-Bereitstellung integriert ist, werden Notrufe mit einem dynamisch erworbenen Standort automatisch an den öffentlichen Sicherheits Beantwortungs Punkt (PSAP) weitergeleitet, der diesem Standort dient.

-  Notrufe ohne dynamisch erworbenen Standort werden zuerst angezeigt, um den aktuellen Standort des Benutzers zu ermitteln, bevor der Anruf mit dem entsprechenden Dispatch Center basierend auf dem aktualisierten Standort verbunden wird.

Weitere Informationen finden Sie unter [für die direkte Weiterleitung zertifizierte Sitzungs Grenz Controller](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-elin-applications"></a>Notfall Standort-Identifikationsnummer (Elin)-Anwendungen

Session Border Controllers (SBCS) können Notfall Standort-Identifikationsnummern (Elin)-Anwendungen umfassen. Wenn eine SBC Elin-Anwendung in eine Direct Routing-Bereitstellung integriert ist, müssen Sie die Notfalladressen und zugehörigen Telefonnummern in der Elin-Anwendung konfigurieren und dann die Elin-Einträge in die Notfall-Anruf Datenbank im jeweiligen PSTN hochladen.  Notfall Standorte für Teams mit einem Elin-Bezeichner müssen mit denen in der Elin-Anwendung übereinstimmen.

Wenn ein Notruf mit einem dynamisch abgerufenen Standort an den entsprechenden SBC weitergeleitet wird, wird die Elin-Anwendung:

- Analysiert den Notfall Standort des Anrufers.
- Vergleicht die Position mit einem Elin-Eintrag.
- Ersetzt die Nummer des Notruf Anrufers durch die Elin-Telefonnummer.
- Leitet den Anruf an die PSAP weiter, die diesen Ort dient, und die Dispatcher erhalten den Standort aus dem hochgeladenen Elin-Eintrag.

Bei einem Rückruf an die Notrufnummer führt die Elin-Anwendung die umgekehrte Nummer als Ersatz für den ursprünglichen Notruf aus. 

Weitere Informationen finden Sie unter [für die direkte Weiterleitung zertifizierte Sitzungs Grenz Controller](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Benachrichtigung über Sicherheits Desk

Die Benachrichtigung über den Security Desk ist sowohl für Microsoft-Anrufpläne als auch für das direkte Routing von Telefonsystemen verfügbar.

Sie verwenden eine Teams-Notfall-Anrufrichtlinie (TeamsEmergencyCallingPolicy), um zu konfigurieren, wer während eines Notrufs benachrichtigt werden soll und wie Sie benachrichtigt werden: nur Chat, Konferenz-und Stummschaltung, Konferenz-und Stummschaltung, aber mit der Möglichkeit, die Stummschaltung aufzuheben.  Sie können auch eine externe PSTN-Nummer eines Benutzers oder einer Gruppe angeben, um anzurufen und an dem Notruf teilzunehmen. 

Eine Notruf Richtlinie kann einem Teams-Benutzerkonto gewährt werden, das einer Netzwerk Website zugewiesen ist, oder beides.  Wenn ein Teams-Client eine Netzwerkverbindung startet oder ändert, führt Teams eine Suche nach der Netzwerk Website durch, auf der sich der Client befindet:

- Wenn eine Notruf Richtlinie einer Netzwerk Website zugeordnet ist, wird die Website Richtlinie zum Konfigurieren der Benachrichtigung über das Sicherheits Desk verwendet.

- Wenn der Website keine Notruf Richtlinien zugeordnet sind oder wenn der Client an einer nicht definierten Website verbunden ist, wird die für das Benutzerkonto zugeordnete Notruf Richtlinie verwendet, um die Benachrichtigung über das Sicherheits Desk zu konfigurieren.  

- Wenn der Team-Client keine Notruf Richtlinie erhalten kann, ist der Benutzer nicht für die Benachrichtigung über das Security Desk aktiviert.

Während eines Notrufs wird ein Security Desk an den Anruf angeschlossen, und die Erfahrung des Security Desk-Benutzers wird auf der Grundlage der Notruf Richtlinien für Teams gesteuert. Ein Gruppen-Chat wird mit jedem Security Desk-Mitglied gestartet, und der Standort des Notruf Anrufers wird über eine wichtige Nachrichten Benachrichtigung freigegeben.  Wenn eine Konferenz Option als Teil der Richtlinie konfiguriert ist, wird jeder Security Desk-Benutzer zusätzlich als Teil der Konferenz aufgerufen.

    
## <a name="related-topics"></a>Verwandte Themen

- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Notfall Anrufrouting Richtlinien ](manage-emergency-call-routing-policies.md)
- [Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-remove-emergency-location-organization.md)
- [Zuweisen oder Ändern eines Notfall Standorts für Ihren Benutzer](assign-change-emergency-location-user.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
