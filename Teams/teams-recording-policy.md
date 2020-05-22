---
title: Einführung in die richtlinienbasierte Aufzeichnung von Teams für den Anruf & Besprechungen
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Informationen zu Teamrichtlinien basierter Aufzeichnung für den Anruf & Besprechungen
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ef9ca9a5f03ecffe1460a24db186a266fd4a84c
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326672"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="2853e-103">Einführung in die richtlinienbasierte Aufzeichnung von Teams für Anrufe & Besprechungen</span><span class="sxs-lookup"><span data-stu-id="2853e-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="2853e-104">Mithilfe einer richtlinienbasierten Aufzeichnung können Organisationen, die Microsoft Teams für Anrufe und Besprechungen übernehmen, unter Verwendung einer Verwaltungsrichtlinie festlegen, wann Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die spätere Verarbeitung und Aufbewahrung erfasst werden sollen, wie dies in den entsprechenden Unternehmens-oder Aufsichtsrichtlinien erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2853e-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="2853e-105">Teams wurden verbessert, um die Integration von Drittanbieter-Aufzeichnungslösungen zu unterstützen, einschließlich der Plattformfunktionen, Benutzer Erfahrungen und administrativen Schnittstellen, die für die Bereitstellung einer End-to-End-Lösung für die Konfiguration, Verwaltung, Aufzeichnung, Speicherung und Analyse von Teams-Kommunikationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2853e-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="2853e-106">Dazu gehören Kommunikationsplattform-APIs und Ereignisse für die Aufzeichnung, die Folgendes bietet:</span><span class="sxs-lookup"><span data-stu-id="2853e-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="2853e-107">Nahtlose, qualitativ hochwertige Medien Erfassung auf allen Geräten und alle unterstützten Endpunkte für Audio, Video, Bildschirmfreigabe und Chat.</span><span class="sxs-lookup"><span data-stu-id="2853e-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="2853e-108">Unterstützung für die Interaktions Erfassung zwischen Teams-Benutzern und unterstützten Anruf Endpunkten (Teams, Mobile Teams, Skype for Business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="2853e-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="2853e-109">Neue administrative Richtlinien für die Konformitäts Aufzeichnung, einschließlich der Integration in vorhandene Teams administrative Anruf-und Besprechungstools und-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="2853e-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

- <span data-ttu-id="2853e-110">Für Benutzer von Teams mit einer separaten Lizenz aktiviert</span><span class="sxs-lookup"><span data-stu-id="2853e-110">Enabled for Teams users with a separate license</span></span>

<span data-ttu-id="2853e-111">Die Integrationsfunktionen der Kompatibilitäts Aufzeichnung wurden auch bei Ignite 2019 in der [<span class="underline">Sitzung Compliance Recording und Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)überprüft.</span><span class="sxs-lookup"><span data-stu-id="2853e-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="2853e-112">Übersicht über die Interaktions Aufzeichnung für Teams</span><span class="sxs-lookup"><span data-stu-id="2853e-112">Teams interaction recording overview</span></span>

<span data-ttu-id="2853e-113">Anwendungsfälle für die Interaktions Aufzeichnung können effektiv in vier primäre Kategorien von Aufzeichnungsfunktionen aufgeteilt werden – Bequemlichkeit, funktionelle, organisatorische und rechtmäßige abfangfunktion, wie in der Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2853e-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="2853e-114">![Screenshot der Interaktions Aufzeichnung was und warum.](media/recording-taxonomy.png "Das Bild zeigt die Aufzeichnungs Kategorien.")</span><span class="sxs-lookup"><span data-stu-id="2853e-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="2853e-115">Jede der Kategorien umfasst unterschiedliche Anforderungen für die Art und Weise, wie Aufzeichnungen initiiert werden, was aufgezeichnet wird, wo Aufzeichnungen gespeichert werden, wer benachrichtigt wird, wer den Zugriff steuert und wie die Aufbewahrung gehandhabt wird.</span><span class="sxs-lookup"><span data-stu-id="2853e-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="2853e-116">Komfort</span><span class="sxs-lookup"><span data-stu-id="2853e-116">Convenience</span></span>        | <span data-ttu-id="2853e-117">Funktions</span><span class="sxs-lookup"><span data-stu-id="2853e-117">Functional</span></span>         | <span data-ttu-id="2853e-118">Org-allgemein</span><span class="sxs-lookup"><span data-stu-id="2853e-118">Org - General</span></span>      | <span data-ttu-id="2853e-119">Org-reguliert</span><span class="sxs-lookup"><span data-stu-id="2853e-119">Org - Regulated</span></span> | <span data-ttu-id="2853e-120">Rechtmäßiger Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2853e-120">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="2853e-121">Initiator</span><span class="sxs-lookup"><span data-stu-id="2853e-121">Initiator</span></span>              | <span data-ttu-id="2853e-122">Benutzer</span><span class="sxs-lookup"><span data-stu-id="2853e-122">User</span></span>               | <span data-ttu-id="2853e-123">App/Lösung</span><span class="sxs-lookup"><span data-stu-id="2853e-123">App/Solution</span></span>       | <span data-ttu-id="2853e-124">Administrator (System)</span><span class="sxs-lookup"><span data-stu-id="2853e-124">Admin (system)</span></span>     | <span data-ttu-id="2853e-125">Administrator (System)</span><span class="sxs-lookup"><span data-stu-id="2853e-125">Admin (system)</span></span>  | <span data-ttu-id="2853e-126">Lea</span><span class="sxs-lookup"><span data-stu-id="2853e-126">LEA</span></span>                |
| <span data-ttu-id="2853e-127"> Target</span><span class="sxs-lookup"><span data-stu-id="2853e-127">Target</span></span>                 | <span data-ttu-id="2853e-128">Pro Anruf/Besprechung</span><span class="sxs-lookup"><span data-stu-id="2853e-128">Per-call / meeting</span></span> | <span data-ttu-id="2853e-129">Pro Anruf/Besprechung</span><span class="sxs-lookup"><span data-stu-id="2853e-129">Per-call / meeting</span></span> | <span data-ttu-id="2853e-130">Pro Anruf/Besprechung</span><span class="sxs-lookup"><span data-stu-id="2853e-130">Per-call / meeting</span></span> | <span data-ttu-id="2853e-131">Pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="2853e-131">Per-user</span></span>        | <span data-ttu-id="2853e-132">Pro Endpunkt/did</span><span class="sxs-lookup"><span data-stu-id="2853e-132">Per-endpoint / DID</span></span> |
| <span data-ttu-id="2853e-133">Speicher Besitzer</span><span class="sxs-lookup"><span data-stu-id="2853e-133">Storage owner</span></span>          | <span data-ttu-id="2853e-134">Benutzer</span><span class="sxs-lookup"><span data-stu-id="2853e-134">User</span></span>               | <span data-ttu-id="2853e-135">App</span><span class="sxs-lookup"><span data-stu-id="2853e-135">App</span></span>                | <span data-ttu-id="2853e-136">Admin</span><span class="sxs-lookup"><span data-stu-id="2853e-136">Admin</span></span>              | <span data-ttu-id="2853e-137">Compliance</span><span class="sxs-lookup"><span data-stu-id="2853e-137">Compliance</span></span>      | <span data-ttu-id="2853e-138">Lea</span><span class="sxs-lookup"><span data-stu-id="2853e-138">LEA</span></span>                |
| <span data-ttu-id="2853e-139">Benachrichtigung erforderlich?</span><span class="sxs-lookup"><span data-stu-id="2853e-139">Notification required?</span></span> | <span data-ttu-id="2853e-140">Ja </span><span class="sxs-lookup"><span data-stu-id="2853e-140">Yes</span></span>                | <span data-ttu-id="2853e-141">Ja </span><span class="sxs-lookup"><span data-stu-id="2853e-141">Yes</span></span>                | <span data-ttu-id="2853e-142">Ja </span><span class="sxs-lookup"><span data-stu-id="2853e-142">Yes</span></span>                | <span data-ttu-id="2853e-143">Ja</span><span class="sxs-lookup"><span data-stu-id="2853e-143">Yes</span></span>             | <span data-ttu-id="2853e-144">Nein</span><span class="sxs-lookup"><span data-stu-id="2853e-144">No</span></span>                 |
| <span data-ttu-id="2853e-145">Zugriffs Besitzer</span><span class="sxs-lookup"><span data-stu-id="2853e-145">Access Owner</span></span>           | <span data-ttu-id="2853e-146">Benutzer</span><span class="sxs-lookup"><span data-stu-id="2853e-146">User</span></span>               | <span data-ttu-id="2853e-147">App</span><span class="sxs-lookup"><span data-stu-id="2853e-147">App</span></span>                | <span data-ttu-id="2853e-148">Admin</span><span class="sxs-lookup"><span data-stu-id="2853e-148">Admin</span></span>              | <span data-ttu-id="2853e-149">Compliance</span><span class="sxs-lookup"><span data-stu-id="2853e-149">Compliance</span></span>      | <span data-ttu-id="2853e-150">Lea</span><span class="sxs-lookup"><span data-stu-id="2853e-150">LEA</span></span>                |
| <span data-ttu-id="2853e-151">Aufbewahrungsrichtlinie?</span><span class="sxs-lookup"><span data-stu-id="2853e-151">Retention Policy?</span></span>      | <span data-ttu-id="2853e-152">Optional</span><span class="sxs-lookup"><span data-stu-id="2853e-152">Optional</span></span>           | <span data-ttu-id="2853e-153">Ja </span><span class="sxs-lookup"><span data-stu-id="2853e-153">Yes</span></span>                | <span data-ttu-id="2853e-154">Ja </span><span class="sxs-lookup"><span data-stu-id="2853e-154">Yes</span></span>                | <span data-ttu-id="2853e-155">Ja </span><span class="sxs-lookup"><span data-stu-id="2853e-155">Yes</span></span>             | <span data-ttu-id="2853e-156">Ja</span><span class="sxs-lookup"><span data-stu-id="2853e-156">Yes</span></span>                |

<span data-ttu-id="2853e-157">Teams bietet verschiedene Funktionen für die [<span class="underline">bequeme</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) und funktionelle Aufzeichnung für Besprechungen und Live-Events.</span><span class="sxs-lookup"><span data-stu-id="2853e-157">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="2853e-158">Die organisatorische Aufzeichnung bedeutet, dass Organisationen, die Teams für Anrufe und Besprechungen einführen, in einer administrativen Richtlinie festlegen können, ob Anrufe und Onlinebesprechungen automatisch aufgezeichnet und für die spätere Verarbeitung und Aufbewahrung nach Maßgabe der einschlägigen Unternehmens-oder Aufsichtsrichtlinien festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2853e-158">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="2853e-159">Benutzern, die dieser Richtlinie unterliegen, ist bewusst, dass Ihre digitalen Interaktionen mit Teams aufgezeichnet werden, Sie aber nicht in der Lage sind, die Aufzeichnung zu deaktivieren, und nach Abschluss der Interaktion keinen Zugriff auf die Aufzeichnung hat.</span><span class="sxs-lookup"><span data-stu-id="2853e-159">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="2853e-160">Die Aufzeichnung wird Teil des Organisations Archivs, das Compliance-und juristischen Personen für eDiscovery, rechtliche Aufbewahrung und andere Unternehmens Aufbewahrungszwecke zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="2853e-160">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="2853e-161">Beispiel für Benutzeranforderungen</span><span class="sxs-lookup"><span data-stu-id="2853e-161">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2853e-162"><strong>Persona</strong></span><span class="sxs-lookup"><span data-stu-id="2853e-162"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="2853e-163"><strong>Muss</strong></span><span class="sxs-lookup"><span data-stu-id="2853e-163"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2853e-164">Aufgezeichnete Benutzer</span><span class="sxs-lookup"><span data-stu-id="2853e-164">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2853e-165">Benachrichtigt werden, wenn die Aufzeichnung gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2853e-165">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="2853e-166">Informieren Sie sich, wenn der Richtlinien-und/oder Rekorder-Fehler Änderungen beim Anrufverhalten verursacht.</span><span class="sxs-lookup"><span data-stu-id="2853e-166">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2853e-167">Kommunikations Administrator</span><span class="sxs-lookup"><span data-stu-id="2853e-167">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2853e-168">Erläutern Sie, warum und wie Sie Aufzeichnungs Richtlinien für Benutzer/Endpunkte von Teams anwenden/erzwingen.</span><span class="sxs-lookup"><span data-stu-id="2853e-168">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="2853e-169">Konfigurieren und Verwalten von Teams zum Aufzeichnen von Richtlinien für die Organisation</span><span class="sxs-lookup"><span data-stu-id="2853e-169">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="2853e-170">Überwachen und behandeln von Problemen mit der Aufzeichnung bei Anrufen und Besprechungen in Teams.</span><span class="sxs-lookup"><span data-stu-id="2853e-170">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="2853e-171">Unterstützen Sie den internen Compliance Officer mit betrieblichen Analysen zu Nutzung, Qualität und Zuverlässigkeit.</span><span class="sxs-lookup"><span data-stu-id="2853e-171">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2853e-172">Compliance Officer</span><span class="sxs-lookup"><span data-stu-id="2853e-172">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2853e-173">Sammeln Sie alle Teams-Kommunikationen in der Weise, die erforderlich ist, um Compliance-Verpflichtungen in angemessenen regionalen Grenzen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2853e-173">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="2853e-174">Suchen Sie nach Interaktionen basierend auf kommunikationsbezogenen Metadaten oder Interaktions Inhalten.</span><span class="sxs-lookup"><span data-stu-id="2853e-174">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="2853e-175">Gängige Beispiele sind:</span><span class="sxs-lookup"><span data-stu-id="2853e-175">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2853e-176"><strong>Metadaten</strong> - Teilnehmer, Zeit, Richtung, gewählte Nummer, Herkunftsnummer, benutzerdefinierte Geschäftsdaten</span><span class="sxs-lookup"><span data-stu-id="2853e-176"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="2853e-177"><strong>Inhalt</strong> – Transkription, Sentiment, Phonetik, Verwandte Interaktionen</span><span class="sxs-lookup"><span data-stu-id="2853e-177"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="2853e-178">Analysieren und interagieren Sie mit gesammelten Kommunikationen, einschließlich der Möglichkeit, Interaktionen während der Erfassung zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="2853e-178">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="2853e-179">Sicherstellen der Sicherheit der gesammelten Kommunikation und verhindern von Manipulationen in allen Phasen.</span><span class="sxs-lookup"><span data-stu-id="2853e-179">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="2853e-180">Übersicht über die Lösungsarchitektur</span><span class="sxs-lookup"><span data-stu-id="2853e-180">Solution architecture overview</span></span>

<span data-ttu-id="2853e-181">Lösungen für die Compliance-Aufzeichnung sind in Teams integriert, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2853e-181">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="2853e-182">![Screenshot mit der Einstellung "benutzerdefinierte App für Team"](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "Die Bilder zeigen den Fluss an, wenn eine Teams-Besprechung oder ein Anruf gesendet und empfangen wird.")</span><span class="sxs-lookup"><span data-stu-id="2853e-182">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="2853e-183">Recorder</span><span class="sxs-lookup"><span data-stu-id="2853e-183">Recorder</span></span>

<span data-ttu-id="2853e-184">Die wichtigste Komponente der Compliance-Aufzeichnungslösung ist die Aufzeichnung.</span><span class="sxs-lookup"><span data-stu-id="2853e-184">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="2853e-185">Datenschreiber sind als skalierbare Azure-based Services (Bots) konzipiert, die die [<span class="underline">Kommunikationsplattform von Microsoft nutzen</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) und sich als Anwendungen mit Microsoft Graph registrieren.</span><span class="sxs-lookup"><span data-stu-id="2853e-185">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="2853e-186">Der Recorder bietet die direkte Interaktion mit den Teams für Anrufe und Besprechungen der [<span class="underline">Kommunikationsplattform-APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) und stellt den Endpunkt für die Medien aufnahmebereit.</span><span class="sxs-lookup"><span data-stu-id="2853e-186">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="2853e-187">Eine [<span class="underline">Beispielanwendung für Compliance-Recorder steht zur Verfügung</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) , die zeigt, wie der bot konfiguriert, die app-Instanz erstellt und die Konformitätsrichtlinien zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2853e-187">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="2853e-188">Das Beispiel enthält auch Beispiele für die API-Verwendung für die Aufzeichnung bestimmter Interaktionen, beispielsweise die Behandlung des [<span class="underline">eingehenden Anruf</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   Routings, [<span class="underline">Ändern der Aufnahme Zustände</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)und [<span class="underline">Entfernen des Benutzers, der aufgezeichnet wird</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="2853e-188">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="2853e-189">Graph-Dokumentation zu den spezifischen APIs finden Sie hier für [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) und [<span class="underline">incomingcontext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="2853e-189">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="2853e-190">Die genaue Implementierung des Recorder-Diensts variiert je nach Partner, muss aber so konzipiert sein, dass mehrere Datenschreiber unterstützt werden, um eine hohe Verfügbarkeit und geografische Verteilung der Bereitstellung zu erreichen, um die Latenz von Teams auf die Aufzeichnung zu verringern.</span><span class="sxs-lookup"><span data-stu-id="2853e-190">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="2853e-191">Außerdem wird davon ausgegangen, dass die Datenschreiber selbst mit Flexibilität und Redundanz konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="2853e-191">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="2853e-192">Partner müssen die mindestens erforderliche Veröffentlichungsversion der Microsoft Graph Communications-APIs und-SDKs mit Microsoft bestätigen, bevor Sie Ihre Lösung für die Zertifizierung übermitteln, um sicherzustellen, dass alle Anforderungen der Integration der Konformitäts Aufzeichnung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2853e-192">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="2853e-193">Zwei spezifische Anforderungen, die für das Szenario der Konformitäts Aufzeichnung grundlegend sind, sind:</span><span class="sxs-lookup"><span data-stu-id="2853e-193">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="2853e-194">Recorder-bot muss in Azure bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="2853e-194">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="2853e-195">Der Recorder-bot muss auf einer Windows-VM in Azure ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="2853e-195">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="2853e-196">Die Azure-und Windows-VM-Anforderungen gelten nur für die Teams-bot-Komponente, was bedeutet, dass ein Partner die restliche Plattform Ihrer Wahl implementieren kann, vorausgesetzt, Sie kann die relevanten Leistungs-und Funktionsanforderungen für die Compliance-Aufzeichnung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2853e-196">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="2853e-197">Richtlinienzuweisung und Bereitstellung von Compliance-Aufzeichnungen</span><span class="sxs-lookup"><span data-stu-id="2853e-197">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="2853e-198">IT-Administratoren können ermitteln, welche Benutzer aufgezeichnet werden und welche Aufzeichnung für jeden Benutzer verwendet werden soll, indem Sie Richtlinien für die Konformitäts Aufzeichnung erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2853e-198">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="2853e-199">Datenschreiber werden automatisch zur Teilnahme an Unterhaltungen eingeladen, die auf der Konfiguration dieser Richtlinien basieren, wenn eine Kommunikations Interaktion stattfindet.</span><span class="sxs-lookup"><span data-stu-id="2853e-199">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="2853e-200">Richtlinien für die Richtlinien Konformitäts Aufzeichnung werden mit [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) verwaltet und können für jede Organisation auf Mandanten-und Benutzerebene angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2853e-200">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant and per-user level for each organization.</span></span> <span data-ttu-id="2853e-201">Weitere Informationen zu Microsoft docs für [<span class="underline">Besprechungsrichtlinien</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) und [<span class="underline">Anruf Richtlinien</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="2853e-201">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) and [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).</span></span>

1. <span data-ttu-id="2853e-202">Erstellen Sie eine Anwendungsinstanz in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="2853e-202">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="2853e-203">Erstellen einer Richtlinie für die Konformitäts Aufzeichnung</span><span class="sxs-lookup"><span data-stu-id="2853e-203">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="2853e-204"><span class="underline">Satz-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="2853e-204"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="2853e-205">Weisen Sie die Richtlinien für die Konformitäts Aufzeichnung einem Benutzer zu.</span><span class="sxs-lookup"><span data-stu-id="2853e-205">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="2853e-206"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="2853e-206"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="2853e-207">Benutzererlebnisse</span><span class="sxs-lookup"><span data-stu-id="2853e-207">User experiences</span></span>

<span data-ttu-id="2853e-208">Die Unterstützung für Benachrichtigungen wird mithilfe der Erfahrungen des Teams-Clients aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2853e-208">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="2853e-209">Die Erfahrungen können entweder visuell oder Audio sein.</span><span class="sxs-lookup"><span data-stu-id="2853e-209">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="2853e-210">**Teams-Clients – visuelle Benachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="2853e-210">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="2853e-211">Desktop/Web</span><span class="sxs-lookup"><span data-stu-id="2853e-211">Desktop/web</span></span>
- <span data-ttu-id="2853e-212">Mobil (IOS/Android)</span><span class="sxs-lookup"><span data-stu-id="2853e-212">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="2853e-213">Teams-Telefone</span><span class="sxs-lookup"><span data-stu-id="2853e-213">Teams phones</span></span>
- <span data-ttu-id="2853e-214">Teams-Räume</span><span class="sxs-lookup"><span data-stu-id="2853e-214">Teams rooms</span></span>

<span data-ttu-id="2853e-215">**Andere Endpunkte-Audio-Hinweis**</span><span class="sxs-lookup"><span data-stu-id="2853e-215">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="2853e-216">SIP-Telefone</span><span class="sxs-lookup"><span data-stu-id="2853e-216">SIP phones</span></span>
- <span data-ttu-id="2853e-217">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2853e-217">Skype for Business</span></span>
- <span data-ttu-id="2853e-218">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="2853e-218">Audio conferencing</span></span>
- <span data-ttu-id="2853e-219">PSTN-Anrufer</span><span class="sxs-lookup"><span data-stu-id="2853e-219">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="2853e-220">Konformitäts Aufzeichnung für Teams-Zertifizierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="2853e-220">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="2853e-221">Neben der Veröffentlichung öffentlich verfügbarer APIs, die Partnern die Entwicklung und Integration von CCaaS-Lösungen in Teams ermöglichen, haben wir das Zertifizierungsprogramm für die Compliance-Aufzeichnung für Microsoft Teams entwickelt, um Kunden die Gewissheit zu bieten, dass die Lösung jedes teilnehmenden Partners getestet und überprüft wurde, um die Qualität, Kompatibilität und Zuverlässigkeit zu gewährleisten, die Sie von Microsoft-Lösungen erwarten.</span><span class="sxs-lookup"><span data-stu-id="2853e-221">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="2853e-222">Die folgenden Partner sind dabei, Ihre Lösung für Microsoft Teams zu zertifizieren.</span><span class="sxs-lookup"><span data-stu-id="2853e-222">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="2853e-223">Partner</span><span class="sxs-lookup"><span data-stu-id="2853e-223">Partner</span></span>|<span data-ttu-id="2853e-224">Lösungs Website</span><span class="sxs-lookup"><span data-stu-id="2853e-224">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="2853e-225">ASC-Technologien</span><span class="sxs-lookup"><span data-stu-id="2853e-225">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="2853e-226">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2853e-226">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="2853e-227">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="2853e-227">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="2853e-228">Schön</span><span class="sxs-lookup"><span data-stu-id="2853e-228">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="2853e-229">Numonix</span><span class="sxs-lookup"><span data-stu-id="2853e-229">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="2853e-230">Rotes Feld</span><span class="sxs-lookup"><span data-stu-id="2853e-230">Red Box</span></span> |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|<span data-ttu-id="2853e-231">Verint</span><span class="sxs-lookup"><span data-stu-id="2853e-231">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="2853e-232">Diese Liste wird aktualisiert, wenn weitere Partner teilnehmen und die Zertifizierungskriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2853e-232">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2853e-233">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2853e-233">Next steps</span></span>

<span data-ttu-id="2853e-234">Wenn Sie ein Anbieter sind und versuchen, dem Zertifizierungsprogramm beizutreten, senden Sie <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@Microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="2853e-234">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>