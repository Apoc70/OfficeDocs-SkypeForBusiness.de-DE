---
title: Verwalten Ihrer Branchen-apps in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre benutzerdefinierten Teams-apps von der Entwicklung zur Bereitstellung bringen.
ms.openlocfilehash: cd64ff0a3307ada0f1fbfaf29b94cfcd1da3c0df
ms.sourcegitcommit: d6a0ff7f00defda2b58726f5f0f0fac871f46ab7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "37682715"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>Verwalten Ihrer Branchen-apps in Microsoft Teams

Dieser Artikel enthält eine umfassende Anleitung, wie Sie Ihre Teams-APP von der Entwicklung zur Bereitstellung führen können. Dieser Leitfaden konzentriert sich auf die Team Aspekte der APP und ist für IT-Experten vorgesehen. Weitere Informationen zum Entwickeln von Teams-apps finden Sie [hier](https://docs.microsoft.com/microsoftteams/platform).

![Übersicht über Ihre APP von der Entwicklung bis zur Bereitstellung](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Erste Schritte

Zum Erstellen und Verwalten von Lob-apps in Teams benötigen Sie zwei Mandanten: einen Testmandanten für die Entwicklung und einen Produktions Mandanten.

> [!NOTE]
> Wenn Sie noch nicht über einen Testmandanten verfügen, können Sie mit dem Office 365-Entwicklerprogramm schnell eins erstellen und es mit Testdaten füllen. [Weitere Informationen finden Sie hier](https://developer.microsoft.com/office/dev-program).

## <a name="step-1-develop-and-test"></a>Schritt 1: entwickeln und testen

### <a name="create-test-users"></a>Erstellen von Testbenutzern

Stellen Sie sicher, dass Ihre Entwickler, ob intern oder extern, über Konten in Ihrem Testmandanten verfügen. [Weitere Informationen zum Hinzufügen von Benutzern](https://docs.microsoft.com/office365/admin/add-users/add-users).

### <a name="allow-custom-apps-in-the-test-tenant"></a>Zulassen von benutzerdefinierten apps im Testmandanten

Damit Entwickler den Zugriff haben, den Sie für Tests benötigen, können Sie allen Benutzern im Testmandanten ermöglichen, benutzerdefinierte Apps (auch bekannt als Sideloading) hochzuladen. Auf diese Weise können Entwickler eine benutzerdefinierte App hochladen, um Sie persönlich oder über den Testmandanten zu verwenden, ohne die APP an den Team-Apps-Store übermitteln zu müssen. Beim Hochladen einer benutzerdefinierten App können Entwickler eine APP testen, bevor Sie Sie weiter verbreiten.

Führen Sie die folgenden Schritte aus, um Benutzern das Hochladen benutzerdefinierter apps zu ermöglichen:

1. Aktivieren Sie die organisationsweite Einstellung **Interaktion mit benutzerdefinierten apps zulassen** . Gehen Sie dazu so vor:
    1. Wechseln Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)zu **Teams-apps** > -**Berechtigungsrichtlinien**, und klicken Sie dann auf **organisationsweite Einstellungen**.
    2. Aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**, und klicken Sie dann auf **Speichern**.

    ![Screenshot der organisationsweiten Einstellung "Interaktion mit benutzerdefinierten apps zulassen"](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Aktivieren Sie die Einstellung **benutzerdefinierte apps hochladen** in der globalen App-Setup Richtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)zu den**Setup Richtlinien**für **Teams-apps** > , und klicken Sie dann auf die **globale (org-Wide Standard)-** Richtlinie.
    2. Aktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.

    ![Screenshot der Richtlinieneinstellung "benutzerdefinierte apps hochladen" für die APP](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> Es gibt auch die Einstellung "benutzerdefinierte App hochladen" auf Team Ebene. Diese Einstellung ist standardmäßig aktiviert. Wenn Entwickler jedoch keine benutzerdefinierte app in ein Team hochladen können, überprüfen Sie die Einstellungen, indem Sie die [folgenden Schritte ausführen](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting).

### <a name="create-your-app"></a>Erstellen Ihrer APP

Entwickler sollten nun über die erforderlichen Elemente verfügen, um Ihre APP zu erstellen. [Hier](https://docs.microsoft.commicrosoftteams/platform) finden Sie Anleitungen dazu.

## <a name="step-2-validate-in-production"></a>Schritt 2: Überprüfen in der Produktion

### <a name="get-the-app-package"></a>Abrufen des App-Pakets

Wenn die APP für die Verwendung in der Produktion bereit ist, sollte der Entwickler ein App-Paket erstellen. Sie können dafür [App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio) verwenden. Sie senden Ihnen die Datei im ZIP-Format.

Microsoft verwendet [Diese Richtlinien](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval) , um sicherzustellen, dass apps den Qualitäts-und Sicherheitsstandards des globalen Teams Apps Store entsprechen.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Zulassen, dass vertrauenswürdige Benutzer benutzerdefinierte apps im Produktions Mandanten hochladen

Um zu überprüfen, ob die app in Ihrem Produktions Mandanten ordnungsgemäß funktioniert, müssen Sie sich selbst und/oder vertrauenswürdigen Benutzern in Ihrer Organisation erlauben, benutzerdefinierte apps hochzuladen.  Ähnlich wie in den vorherigen Schritten für [benutzerdefinierte apps im Testmandanten zulassen](#allow-custom-apps-in-the-test-tenant) verwenden Sie dazu die APP-Setup Richtlinien.

> [!NOTE]
> Wenn es Ihnen unangenehm ist, die APP für die Validierung selbst oder für vertrauenswürdige Benutzer in ihren Produktions Mandanten hochzuladen, können Sie diesen Schritt überspringen und die Schritte 3 und 4 ausführen, um die nicht validierte app in ihren Mandanten-Apps-Store hochzuladen. Dann beschränken Sie den Zugriff auf diese APP nur auf sich selbst und auf Benutzer, denen Sie vertrauen. Diese Benutzer können dann die APP aus dem Mandanten-Apps-Store abrufen, um eine Validierung durchzuführen. Verwenden Sie nach der Überprüfung der APP dieselben Berechtigungsrichtlinien, um Access zu öffnen und die APP für die Produktion zu verwenden.

Führen Sie die folgenden Schritte aus, um vertrauenswürdigen Benutzern das Hochladen benutzerdefinierter apps zu ermöglichen:

1. Aktivieren Sie die organisationsweite Einstellung **Interaktion mit benutzerdefinierten apps zulassen** . Gehen Sie dazu so vor:
    1. Wechseln Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)zu **Teams-apps** > -**Berechtigungsrichtlinien**, und klicken Sie dann auf **organisationsweite Einstellungen**.
    2. Aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**, und klicken Sie dann auf **Speichern**.
2. Deaktivieren Sie die Einstellung **benutzerdefinierte apps hochladen** in der globalen App-Setup Richtlinie. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)zu den**Setup Richtlinien**für **Teams-apps** > , und klicken Sie dann auf die **globale (org-Wide Standard)-** Richtlinie.
    2. Deaktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.
3. Erstellen Sie eine neue Richtlinie für die APP-Einrichtung, die das Hochladen benutzerdefinierter apps und die Zuweisung an Ihre vertrauenswürdigen Benutzer ermöglicht. Gehen Sie dazu so vor:
    1. Navigieren Sie in der linken Navigationsleiste des [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/)zu den**Setup Richtlinien**für **Teams-apps** > , und klicken Sie dann auf **Hinzufügen**. Geben Sie der neuen Richtlinie einen Namen und eine Beschreibung, aktivieren Sie **benutzerdefinierte apps hochladen**, und klicken Sie dann auf **Speichern**.
    2. Wählen Sie die neu erstellte Richtlinie aus, und klicken Sie dann auf **Benutzer verwalten**. Suchen Sie nach einem Benutzer, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf über **nehmen**. Wiederholen Sie diesen Schritt, um die Richtlinie allen vertrauenswürdigen Benutzern zuzuweisen.

        ![Screenshot der Seite "App-Setup Richtlinie hinzufügen"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Diese Benutzer können jetzt das App-Manifest hochladen, um zu überprüfen, ob die APP im Produktions Mandanten ordnungsgemäß funktioniert.

## <a name="step-3-upload-to-the-tenant-apps-catalog"></a>Schritt 3: Hochladen in den Mandanten-apps-Katalog

Wenn Sie die APP für Benutzer im Mandanten-App-Store verfügbar machen möchten, laden Sie die APP hoch. Sie können dies über den Desktop-Client von Teams tun. Führen Sie die [folgenden Schritte aus](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog).

![Screenshot der Seite "Apps"](media/manage-your-lob-apps-store.png)

## <a name="step-4-configure-and-assign-permissions"></a>Schritt 4: Konfigurieren und Zuweisen von Berechtigungen

### <a name="control-access-to-the-app"></a>Steuern des Zugriffs auf die APP

Standardmäßig haben alle Benutzer Zugriff auf diese APP im Store für Teams-apps. Um zu beschränken und zu steuern, wer die Berechtigung zum Verwenden der APP hat, können Sie eine neue APP-Berechtigungsrichtlinie erstellen und zuweisen. Führen Sie die [folgenden Schritte aus](teams-app-permission-policies.md#create-a-custom-app-permission-policy).

![Screenshot der Seite "App-Berechtigungsrichtlinie hinzufügen"](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Anheften der APP für Benutzer zum Ermitteln

Standardmäßig müssten die Benutzer diese APP finden, wenn Sie zu den Apps für Teams wechseln müssten, um Sie zu speichern und zu durchsuchen. Um Benutzern das Abrufen der APP zu erleichtern, können Sie die app in Teams an die APP-Leiste anheften. Erstellen Sie dazu eine neue APP-Setup Richtlinie, und weisen Sie Sie Benutzern zu. Führen Sie die [folgenden Schritte aus](teams-app-setup-policies.md#create-a-custom-app-setup-policy).

![Screenshot des Bereichs "angeheftete apps hinzufügen"](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Schritt 5: Aktualisieren der APP

![Übersicht über Ihre APP von der Entwicklung bis zur Bereitstellung](media/manage-your-lob-apps-update.png)

Um eine APP zu aktualisieren, sollten Entwickler weiterhin [Schritt 1](#step-1-develop-and-test) und [Schritt 2](#step-2-validate-in-production)folgen.

Sie können die APP über den Mandanten-apps-Katalog aktualisieren. Gehen Sie dazu im Desktop Client von Teams zu **apps** > , die**für &lt;Ihren&gt;Mandantennamen erstellt**wurden, und klicken Sie auf **...** Klicken Sie in der oberen rechten Ecke der APP auf **Aktualisieren**. Dadurch wird die vorhandene App im Katalog der Mandanten-apps ersetzt, und alle Berechtigungsrichtlinien und Setup Richtlinien bleiben für die aktualisierte APP erzwungen. 

![Screenshot zum Aktualisieren einer APP auf der Seite "Apps"](media/manage-your-lob-apps-update-app.png)