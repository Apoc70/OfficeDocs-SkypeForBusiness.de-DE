---
title: Einrichten der Telefon Lizenz für den öffentlichen Bereich
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Informationen zum Einrichten von Telefonen im öffentlichen Bereich für Lobbies, Empfangsbereiche und Konferenzräume '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476710"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Einrichten der Lizenz für Telefone für gemeinsame Bereiche für Microsoft Teams
> [!NOTE]
> Telefone im öffentlichen Bereich unterstützen keine Voicemail.

Ein Telefon im öffentlichen Bereich befindet sich normalerweise in einem Bereich wie einer Lobby oder einem anderen Bereich, der für viele Personen zur Verfügung steht, um einen Anruf zu tätigen. beispielsweise einen Empfangsbereich, eine Lobby oder ein Konferenztelefon. Telefone im öffentlichen Bereich sind mit Konten verbunden, die mit einer Telefon Lizenz für den öffentlichen Bereich verknüpft sind. Die TeamsIPPhone-Richtlinie muss auch entsprechend festgesetzt werden, damit das Telefon über eine Benutzeroberfläche mit gemeinsamem Bereich verfügt.

In den nachstehenden Schritten unterstützen wir Sie beim Einrichten eines Kontos für das Telefon System für die Bereitstellung von Telefonen im allgemeinen Bereich für Ihre Organisation. Für eine vollständige Besprechungsraum-Erfahrung, einschließlich Audiokonferenzen, sollten Sie erwägen, die dedizierte Besprechungsraum-Lizenz mit einem Besprechungsraum Gerät zu erwerben. 

Zunächst müssen Sie eine Lizenz für das Common Area Phone (GAP) erwerben und sicherstellen, dass Sie über ein zertifiziertes Telefon verfügen. Informationen zu zertifizierten Telefonen finden Sie unter [Microsoft Teams-Geräte](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Schritt 1 - Lizenzen kaufen

1. Wechseln Sie im Microsoft 365 Admin Center zu **Abrechnungs**  >  **Kauf Dienste** , und erweitern Sie dann **andere Pläne**.

    ![Screenshot der Telefon Kachel für den öffentlichen Bereich](media/set-up-common-area-phone-image1.png)

2. Wählen Sie den **Bereich Telefon**  >  **Jetzt kaufen**.

3. Klicken Sie auf der Seite Checkout auf **Jetzt kaufen**.

4. Erweitern Sie **Add-on-Abonnements** , und klicken Sie dann, um einen Anrufplan zu kaufen. Wählen Sie entweder den Plan für **Inlandsanrufe** oder den Tarif für **Inlands-und Auslandsgespräche**.

> [!NOTE]
> Wenn Sie das direkte Routing von Microsoft Phone System verwenden, benötigen Sie keine Anruf Plan Lizenz.

> [!NOTE]
> Sie müssen keine Telefon System Lizenz hinzufügen. Sie ist in der Lizenz Telefon für gemeinsame Bereiche enthalten.

Weitere Informationen zu Lizenzen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

Die Telefon Lizenz für den öffentlichen Bereich unterstützt: 


|   |  Telefon für gemeinsame Bereiche  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Telefonsystem |    &#x2714; |
|Audiokonferenzen |       &#x2718; &sup1;  |
|Microsoft InTune |    &#x2718; |
|Weltweite Verfügbarkeit |       &#x2718; &sup2;  |
|Kanalverfügbarkeit |    EA, EAS, CSP, gcc, EBS, Web Direct  |
|      |         |

&sup1; Telefone im öffentlichen Bereich können mit einer vom Besprechungsorganisator bereitgestellten Einwahlnummer an Audiokonferenzen teilnehmen.

&sup2; In souveränen Clouds nicht verfügbar  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Schritt 2 - Ein neues Benutzerkonto für das Telefon erstellen und die Lizenzen zuweisen

1. Wechseln Sie im Microsoft 365 Admin Center zu **Benutzer**, denen  >  **aktive**Benutzer  >  **einen Benutzer hinzufügen**.

2. Geben Sie einen Benutzernamen wie "Main" für den Vornamen und "Empfang" für den zweiten Namen ein.

3. Geben Sie einen Anzeigenamen ein, wenn er nicht wie "Hauptempfang" automatisch generiert wird.

4. Geben Sie einen Benutzernamen wie "MainReception" oder "Mainlobby" ein.

5. Für Telefone im öffentlichen Bereich empfiehlt es sich, ein Kennwort manuell festzulegen oder das gleiche Kennwort für alle Telefone im öffentlichen Bereich zu haben. Darüber hinaus ist es möglich, dass Sie das Kontrollkästchen **diesen Benutzer zum Ändern des Kennworts bei der ersten Anmeldung** verwenden deaktivieren.

6. Weisen Sie dem Benutzer die Lizenzen zu. Klicken Sie auf der gleichen Seite auf **Produktlizenzen** erweitern. Aktivieren Sie das Telefon für den öffentlichen Bereich, und wählen Sie entweder einen **Inlandsanruf Plan** oder einen **Plan für Inlands-und Auslandsanrufe**aus. 

    ![Screenshot mit Lizenzzuweisung](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Wenn Sie das direkte Routing von Microsoft Phone System verwenden, müssen Sie keine Anruf Plan Lizenz zuweisen.

Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Schritt 3 - Eine Telefonnummer dem Benutzerkonto Telefon für gemeinsame Bereich zuweisen

Verwenden Sie das Team Admin Center, um dem Benutzer eine Nummer zuzuweisen.

1. Wählen Sie im Team Admin Center die Option **Voicemail**-  >  **Nummern**aus.

3.    Wählen Sie eine Nummer aus der Liste der Telefonnummern aus und klicken Sie auf **Zuweisen**.

4. Geben Sie auf der Seite **zuweisen** im Feld VoIP-Benutzer den Namen des Benutzers ein, der das Telefon verwenden soll, und wählen Sie dann den Benutzer in der Dropdownliste **Sprachbenutzer auswählen** aus.

5. Als nächstes müssen Sie eine Notfalladresse hinzufügen. Wählen Sie in der Dropdownliste **Suchen**nach Ort, nach **Beschreibung suchen**oder nach **Ort suchen** aus, und geben Sie dann den Ort, die Beschreibung oder den Ort in das Textfeld ein. Wenn Sie nach der Suche suchen, suchen Sie unter **Notfalladresse auswählen** , um das richtige für Sie auszuwählen.

6. Klicken Sie auf **Speichern** und Ihr Benutzer sollte so aussehen:

   ![Screenshot mit Lizenzzuweisung](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Benutzer werden nur angezeigt, wenn Sie über eine Telefon System Lizenz verfügen. Wenn Sie dies gerade erst getan haben, dann kann es etwas dauern, bis der Benutzer in der Liste erscheint.

Weitere Informationen finden Sie unter [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md).

Sie können auch Ihre Telefonnummer, die Sie mit einem anderen Netzbetreiber haben, übernehmen und "portieren" oder auf Microsoft 365 oder Office 365 übertragen. Weitere Informationen finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
