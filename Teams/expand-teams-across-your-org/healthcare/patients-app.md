---
title: Übersicht der Patienten-App
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informieren Sie sich über die Integration elektronischer Gesundheitsdatensätze in die Microsoft Teams-Patienten-App mithilfe von FHIR-APIs.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803543"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams

> [!NOTE]
> Die Patienten-App wurde im 30. Oktober, 2020, eingestellt und durch die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt. Patienten-App-Daten werden im Gruppenpostfach der Office 365-Gruppe gespeichert, die das Team zurückgibt. Alle Daten, die mit der Patienten-App verknüpft sind, werden in dieser Gruppe beibehalten, auf die Benutzeroberfläche kann jedoch nicht mehr zugegriffen werden. Benutzer können Ihre Listen mithilfe der [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)erneut erstellen.
>
>Mit Listen können Betreuerteams in Ihrer Gesundheitsorganisation patientenlisten für Szenarien erstellen, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen. Schauen Sie sich die Vorlage Patienten in Listen an, um zu beginnen. Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Dieser Artikel ist für einen allgemeinen IT-Entwickler im Gesundheitswesen vorgesehen, der die Verwendung von FHIR-APIs auf einem medizinischen Informationssystem zum Herstellen einer Verbindung mit Microsoft Teams interessiert. Auf diese Weise können Pflege Koordinations Szenarien, die den Anforderungen einer Gesundheitsorganisation entsprechen, aktiviert werden.

Verknüpfte Artikel dokumentieren die FHIR-Schnittstellenspezifikationen für die Microsoft Teams-Patienten-APP, und in den folgenden Abschnitten wird erläutert, was erforderlich ist, um einen FHIR-Server einzurichten und mit der Patienten-app in Ihrer Entwicklungsumgebung oder Ihrem Mandanten zu verbinden. Außerdem müssen Sie mit der von Ihnen ausgewählten Dokumentation des FHIR-Servers vertraut sein, wobei es sich um eine der unterstützten Optionen handeln muss:

- Datica (durch Ihr [CMI](https://datica.com/compliant-managed-integration/) -Angebot)
- Infor Kleeblatt (über die [Infor FHIR-Brücke](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (über den [R ^ FHIR-Server](https://www.redoxengine.com/fhir/))
- Dapasoft (über [FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Dieser Prozess enthält keine Schritte, die das Microsoft Teams Admin Center oder PowerShell-Cmdlets verwenden, um Features zu aktivieren. Die Konfiguration erfolgt vollständig auf der FHIR-Server/-Service-Seite und im Patienten-App-Client.

Die folgende Abbildung zeigt die Architektur der App "Patienten":

![Diagramm der APP-Architektur der Patienten](../../media/patients-app-architecture.png)

In den folgenden Abschnitten werden die Anforderungen der FHIR-Datenzugriffsschicht für die Patienten-App erläutert, die ein FHIR-Server (oder EPA-fähige FHIR-APIs) erfüllen muss, um die Integration in die Patienten-APP zu ermöglichen, einschließlich der folgenden:

- Erwartungen bezüglich der Benutzerauthentifizierung
- Funktionelle und technische Anforderungen der integrationsschnittstelle
- Erwartungen bezüglich Leistung und Zuverlässigkeit
- Erwartungen rund um FHIR-Ressourcen, die für die Patienten-App unterstützt werden
- Integrationsprozess und das erwartete Projektmodell
- Erste Schritte mit FHIR und einigen häufigen Herausforderungen, die mit der App "Patienten" konfrontiert sind
- Zukünftige Anforderungen für die nächste Iteration der Patienten-App

> [!NOTE]
> In den folgenden Abschnitten wird das Wort "Partner" oder "Interop-Partner" verwendet, um auf eine beliebige Organisation von Drittanbietern zu verweisen, die die Integration von EPA-Systemen für die Patienten-App über FHIR ermöglicht und einen FHIR-Server implementiert, der den aufgeführten Spezifikationen entspricht.

## <a name="functional-and-technical-requirements"></a>Funktionelle und technische Anforderungen  

### <a name="authentication"></a>Authentifizierung  

Autorisierung auf App-Ebene *ohne Unterstützung für die Autorisierung auf Benutzerebene* ist die häufiger unterstützte Möglichkeit, Datentransformationen durchzuführen und Verbindungen zu EPA-Daten über FHIR verfügbar zu machen, auch wenn das EPA-System möglicherweise die Autorisierung auf Benutzerebene implementiert. Der Interop-Dienst (Partner) erhält erhöhten Zugriff auf die EPA-Daten, und wenn Sie dieselben Daten wie die entsprechenden FHIR-Ressourcen verfügbar machen, wird kein Autorisierungskontext an den Interop-Dienst Consumer (die Patienten-APP) übergeben, der in den Interop-Dienst oder die Plattform integriert ist. Die Patienten-App kann die Autorisierung auf Benutzerebene nicht erzwingen, unterstützt jedoch die Anwendungsauthentifizierung zwischen der Patienten-APP und dem Dienst des Interop-Partners.

Das Authentifizierungsmodell für die Anwendungs-zu-Anwendung wird im folgenden beschrieben:

Die Dienst-zu-Service-Authentifizierung sollte über den OAuth 2,0- [Client Anmelde Informationsfluss](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)erfolgen. Der Partnerdienst muss Folgendes bereitstellen:

1. Der Partnerdienst ermöglicht der App "Patienten", ein Konto bei dem Partner zu erstellen, mit dem die Patienten-App client_id und client_secret, die über ein auth-Registrierungs Portal auf dem Authentifizierungsserver des Partners verwaltet werden, generieren und besitzen kann.

2. Der Partner Dienst besitzt das Authentifizierungs-/Autorisierungssystem, das die bereitgestellten Clientanmeldeinformationen akzeptiert und überprüft (authentifiziert) und ein Zugriffstoken mit Mandanten Hinweis im Bereich zurückgibt, wie nachstehend beschrieben.

3. Aus Sicherheitsgründen oder im Fall eines geheimen Verstoßes kann die Patienten-App den geheimen Schlüssel neu generieren und das alte Geheimnis ungültig machen oder löschen (Beispiel für das gleiche ist in Azure Portal-Aad-App-Registrierung verfügbar).

4. Der Metadaten-Endpunkt, der die Konformitäts Anweisung hostet, sollte nicht authentifiziert sein, er sollte ohne Authentifizierungstoken zugänglich sein.

5. Der Partner Dienst stellt den Token-Endpunkt für die patients-App bereit, um mithilfe eines Client Anmelde Informationsflusses ein Zugriffstoken anzufordern. Die Token-URL als pro autorisierungsserver sollte Teil der FHIR-Konformitäts Anweisung (Capability) sein, die aus Metadaten auf dem FHIR-Server abgerufen wurde, wie in diesem Beispiel:

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

Eine Anforderung eines Zugriffstokens besteht aus den folgenden Parametern:

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

Der Partnerdienst bietet die client_id-und client_secret für die Patienten-APP, die über ein auth-Registrierungs Portal auf der Seite des Partners verwaltet wird. Der Partner Dienst stellt den Endpunkt zum Anfordern des Zugriffstokens mithilfe eines Client Anmelde Informationsflusses bereit. Eine erfolgreiche Antwort muss die Parameter token_type, access_token und expires_in umfassen.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routing: Zuordnen des Aad-Mandanten zum Anbieterendpunkt

Die app "Patienten" stellt über einen einzigen Endpunkt eine Verbindung mit einem Partnerdienst her. Der Partnerdienst besitzt und verwaltet einen Mechanismus, mit dem jeder Microsoft-Kunde (AAD-Mandanten-ID) einem jeweiligen Gesundheitsdienstleister (FHIR-Server) zugeordnet wird, mit dem der Partnerdienst arbeitet.

Das Zuordnen des Aad-Mandanten zu einem Anbieterendpunkt verwendet die Aad-Mandanten-ID (GUID). Die Patienten-App übergibt die Mandanten-ID im Bereich, während Sie für jede Anforderung ein Access-Token anfordert. Der Partner Dienst behält die Zuordnung der Mandanten-ID zum Anbieterendpunkt bei und leitet Anforderungen basierend auf der Mandanten-ID an einen Anbieterendpunkt um. Zu diesem Zweck unterstützt der Partner die Konfiguration am Ende (manuell oder über ein Portal als Teil des Onboarding von Anbieter Organisationen zu Ihrer Interop-Plattform).

Der Workflow für Authentifizierung und Routing wird nachfolgend angezeigt:

![Diagramm zum Authentifizierungs-und Routing Workflow](../../media/Patient-app-6.png)

1. Anfordern eines App-Zugriffstokens durch senden:
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Mit einem App-Token Antworten:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Anfordern geschützter Daten mit Zugriffstoken.

4. Autorisierungsmeldung: Wählen Sie den entsprechenden FHIR-Server aus, zu dem Sie von der Mandanten-ID im Bereich weiterleiten möchten.

5. Sendet die APP-geschützten Daten vom autorisierten FHIR-Server nach der Authentifizierung mit dem App-Token.

## <a name="interfaces"></a>Schnittstellen

Spezifische Anrufe und Felder, die von der Patienten-App verwendet werden, sind in den folgenden Artikeln dokumentiert. Wählen Sie die Schnittstelle aus, die für Ihre FHIR Server/FHIR-APIs gelten soll.

- [Benutzeroberflächenspezifikation DSTU2](dstu2-interface.md)
- [Benutzeroberflächenspezifikation STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Leistung und Zuverlässigkeit

Während sich die Patienten-app in der privaten Vorschau befindet, gibt es keine Garantien für die End-to-End-Leistung. Zu den Leistungsfaktoren zählen die relativen Latenzzeiten aller am Workflow beteiligten Hops, beginnend mit der EPA in der Umgebung des Gesundheitssystems, dem Interop-Partner und dessen Infra, einschließlich des FHIR-Servers und Across zur Office 365-Anwendung für Ökosysteme und Patienten.

![Abbildung der Leistung von Interop-Partnern](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Erste Schritte mit FHIR  

Wenn Sie neu bei FHIR sind und einfachen Zugriff auf einen FHIR-Server benötigen, den Sie für die Microsoft Teams EPA-integrationsschnittstelle verfügbar machen können, verfügt Microsoft über einen Open-Source-FHIR-Server, der für alle Entwickler zur Verfügung steht. Lesen Sie den Artikel [Was ist FHIR Server für Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) , um mehr über den von Microsoft verfügbaren Open-Source-FHIR-Server zu erfahren und ihn für ihre Organisationen bereitzustellen.

Sie können auch die HSPC Open Sandbox EPA-Umgebung verwenden, um eine EHR zu erstellen, die auch einen geöffneten FHIR-Server unterstützt und diese Funktion zur Wiedergabe mit der Patienten-App verwendet. Wir empfehlen, dass Sie die [HSPC-Sandbox-Dokumentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)durchlesen. Die Sandbox bietet nicht nur eine einfache, UI-orientierte und benutzerfreundliche Methode zum Erstellen, hinzufügen und Bearbeiten von Patienten, sondern bietet Ihnen auch einige Beispiele für die ersten Schritte. 
