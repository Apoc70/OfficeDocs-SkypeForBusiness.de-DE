---
title: Microsoft Teams-App-Verwendungsbericht
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie den Bericht zur APP-Nutzung von Teams im Microsoft Teams Admin Center verwenden.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 565a3cb28b73a37162947859effc6ec154b59258
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938204"
---
# <a name="microsoft-teams-app-usage-report"></a><span data-ttu-id="30ea3-103">Microsoft Teams-App-Verwendungsbericht</span><span class="sxs-lookup"><span data-stu-id="30ea3-103">Microsoft Teams app usage report</span></span>

<span data-ttu-id="30ea3-104">Der Bericht "Teams-App-Nutzung" im Microsoft Teams Admin Center bietet Informationen darüber, welche apps Benutzer in Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="30ea3-104">The Teams app usage report in the Microsoft Teams admin center provides you with information about which apps users are using in Teams.</span></span>  

## <a name="view-the-app-usage-report"></a><span data-ttu-id="30ea3-105">Anzeigen des Berichts zur APP-Nutzung</span><span class="sxs-lookup"><span data-stu-id="30ea3-105">View the App Usage report</span></span>

1.  <span data-ttu-id="30ea3-106">Klicken Sie in der linken Navigationsleiste des Admin Centers auf <https://admin.teams.microsoft.com> **Analytics & Berichte** \> **Nutzungsberichte**.</span><span class="sxs-lookup"><span data-stu-id="30ea3-106">In the left navigation of the admin center at <https://admin.teams.microsoft.com>, click **Analytics & reports** \> **Usage reports**.</span></span> <span data-ttu-id="30ea3-107">Wählen Sie auf der Registerkarte **Berichte anzeigen** unter **Bericht**die Option **apps-Verwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="30ea3-107">On the **View reports** tab, under **Report**, select **Apps Usage**.</span></span>

     :::image type="content" source="media/app-usage-report1.png" alt-text="Screenshot des Menüelements "Verwendungsberichte"":::

2.  <span data-ttu-id="30ea3-109">Wähl Sie unter **Datumsbereich** einen Bereich aus, und klicken Sie dann auf **Bericht ausführen**.</span><span class="sxs-lookup"><span data-stu-id="30ea3-109">Under **Date range**, select a range, and then click **Run report**.</span></span>

      :::image type="content" source="media/app-usage-report2.png" alt-text="Screenshot des App-Verwendungsberichts":::

## <a name="interpret-the-report"></a><span data-ttu-id="30ea3-111">Interpretieren des Berichts</span><span class="sxs-lookup"><span data-stu-id="30ea3-111">Interpret the report</span></span>

|<span data-ttu-id="30ea3-112">Beschriftung</span><span class="sxs-lookup"><span data-stu-id="30ea3-112">Callout</span></span> |<span data-ttu-id="30ea3-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30ea3-113">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="30ea3-114">**1**</span><span class="sxs-lookup"><span data-stu-id="30ea3-114">**1**</span></span>   |<span data-ttu-id="30ea3-115">Der Bericht "Teams-apps-Nutzung" kann für Trends in den letzten 7, 30 oder 90 Tagen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="30ea3-115">The Teams Apps usage report can be viewed for trends over the last 7, 30 or 90 days.</span></span> |
|<span data-ttu-id="30ea3-116">**2**</span><span class="sxs-lookup"><span data-stu-id="30ea3-116">**2**</span></span>   |<span data-ttu-id="30ea3-117">Jeder Bericht hat ein Datum, an dem der Bericht generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="30ea3-117">Each report has a date for when the report was generated.</span></span> <span data-ttu-id="30ea3-118">Die Berichte geben in der Regel eine Wartezeit von 24 Stunden ab dem Zeitpunkt wieder, zu dem eine APP geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="30ea3-118">The reports usually reflect a 24-hour latency from the time an app was opened.</span></span> <br><br>![Screenshot des App-Verwendungsberichts mit Datumsbereichen](media/app-usage-report3.png)|
|<span data-ttu-id="30ea3-120">**3**</span><span class="sxs-lookup"><span data-stu-id="30ea3-120">**3**</span></span>    | <ul><li><span data-ttu-id="30ea3-121">Die X-Achse in den Diagrammen ist der ausgewählte Datumsbereich für den jeweiligen Bericht.</span><span class="sxs-lookup"><span data-stu-id="30ea3-121">The X axis on the charts is the selected date range for the specific report.</span></span></li><li><span data-ttu-id="30ea3-122">Bei der Y-Achse handelt es sich um die Anzahl der Benutzer, die für den angegebenen Tag in einem Diagramm angezeigt werden, da diese Benutzer eine APP mindestens einmal geöffnet haben und dabei als aktiver Benutzer gelten und dem Gesamtergebnis des Mauszeigers zugerechnet werden.</span><span class="sxs-lookup"><span data-stu-id="30ea3-122">The Y axis is the number of users who for the given day hovered over in chart, those users have opened an app at least once and by doing so are considered an Active User and accrue towards the total seen on mouse hover over.</span></span></li></ul>|
|<span data-ttu-id="30ea3-123">**4**</span><span class="sxs-lookup"><span data-stu-id="30ea3-123">**4**</span></span>   |<span data-ttu-id="30ea3-124">Zeigen Sie mit der Maus auf den Punkt, der eine apps-Verwendung an einem bestimmten Datum darstellt, um die Anzahl der Instanzen der aktiven Gesamtbenutzer dieser APP an diesem angegebenen Datum anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="30ea3-124">Hover over the dot representing an Apps Usage on a given date to see the number of instances of that App’s Total Active Users on that given date.</span></span>  |
|<span data-ttu-id="30ea3-125">**5**</span><span class="sxs-lookup"><span data-stu-id="30ea3-125">**5**</span></span>   |<span data-ttu-id="30ea3-126">Alle apps werden eingeschlossen, aber durch Auswählen des Filters-Symbols sind weitere Filter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="30ea3-126">All Apps will be included but by choosing the Filter icon, additional filters are available.</span></span>  |
|<span data-ttu-id="30ea3-127">**6**</span><span class="sxs-lookup"><span data-stu-id="30ea3-127">**6**</span></span>   |<span data-ttu-id="30ea3-128">Die Tabelle enthält eine Aufschlüsselung der aktiven Benutzer und Teams nach APP-Namen.</span><span class="sxs-lookup"><span data-stu-id="30ea3-128">The table gives you a breakdown of active users and teams by App name.</span></span><br><ul><li><span data-ttu-id="30ea3-129">**App-Name** ist der Anzeigename der in Teams verwendeten app.</span><span class="sxs-lookup"><span data-stu-id="30ea3-129">**App name** is the display name of the app used in Teams.</span></span></li><li><span data-ttu-id="30ea3-130">**Aktive Benutzer** ist die Anzahl der Benutzer, die die APP während des angegebenen Zeitraums mindestens einmal geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="30ea3-130">**Active users** is the number of users who opened the app at least once during the specified time period.</span></span></li><li><span data-ttu-id="30ea3-131">Der **App-Typ** ist ein statischer Wert von "Microsoft" oder "Drittanbieter".</span><span class="sxs-lookup"><span data-stu-id="30ea3-131">**App type** is a static value of either “Microsoft” or “Third Party”.</span></span></li><li><span data-ttu-id="30ea3-132">" **Aktive Teams** " ist die Anzahl der Teams, die die APP von mindestens einem Mitglied des Teams und in den angegebenen Zeiträumen geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="30ea3-132">**Active teams** is the number of teams who have opened the App by at least one member of the team and during the specified time periods.</span></span></li><li><span data-ttu-id="30ea3-133">**Publisher** ist der Softwareherausgeber der app.</span><span class="sxs-lookup"><span data-stu-id="30ea3-133">**Publisher** is the software publisher of the app.</span></span></li><li><span data-ttu-id="30ea3-134">**Version** ist die Software Version der APP aus dem App-Publisher.</span><span class="sxs-lookup"><span data-stu-id="30ea3-134">**Version** is the software version of the app, from the app publisher.</span></span></li></ul><br><span data-ttu-id="30ea3-135">![Screenshot eines App-Verwendungsberichts](media/app-usage-report4.png)</span><span class="sxs-lookup"><span data-stu-id="30ea3-135">![Screenshot of an Apps Usage report](media/app-usage-report4.png)</span></span>  |
|<span data-ttu-id="30ea3-136">**7**</span><span class="sxs-lookup"><span data-stu-id="30ea3-136">**7**</span></span>  |<span data-ttu-id="30ea3-137">Wählen Sie **Spalten bearbeiten** aus, um Spalten zur Tabelle hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="30ea3-137">Select **Edit columns** to add or remove columns in the table.</span></span><br><br><span data-ttu-id="30ea3-138">![Screenshot der Seite "Spalten bearbeiten"](media/app-usage-report5.png)</span><span class="sxs-lookup"><span data-stu-id="30ea3-138">![Screenshot of the Edit columns page](media/app-usage-report5.png)</span></span>  |
|<span data-ttu-id="30ea3-139">**8**</span><span class="sxs-lookup"><span data-stu-id="30ea3-139">**8**</span></span>  |<span data-ttu-id="30ea3-140">Sie können den Bericht zur Offlineanalyse in eine CSV-Datei exportieren.</span><span class="sxs-lookup"><span data-stu-id="30ea3-140">You can export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="30ea3-141">Klicken Sie auf **nach Excel exportieren**, und klicken Sie dann auf der Registerkarte **Downloads** auf **herunterladen** , um den Bericht herunterzuladen, wenn er fertig ist.</span><span class="sxs-lookup"><span data-stu-id="30ea3-141">Click **Export to Excel**, and then on the **Downloads** tab, click **Download** to download the report when it's ready.</span></span><br><span data-ttu-id="30ea3-142">![Screenshot der Seite "Downloads"](media/app-usage-report7.png)</span><span class="sxs-lookup"><span data-stu-id="30ea3-142">![Screenshot of Downloads page](media/app-usage-report7.png)</span></span>  |
|<span data-ttu-id="30ea3-143">**9**</span><span class="sxs-lookup"><span data-stu-id="30ea3-143">**9**</span></span>   |<span data-ttu-id="30ea3-144">Wenn Sie den Bericht in Excel anzeigen, wird auch eine **ID-** Spalte angezeigt, die die APP-ID darstellt.</span><span class="sxs-lookup"><span data-stu-id="30ea3-144">When you view the report in Excel, you'll also see an **Id** column, which represents the app ID.</span></span> <span data-ttu-id="30ea3-145">Eine Team-ID ist in der Regel eine alphanumerische Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="30ea3-145">A team ID is typically an alphanumeric string.</span></span> <span data-ttu-id="30ea3-146">Wenn die Spalte " **ID** " als \* \* \n \* \* \* \* angezeigt wird, bedeutet dies, dass ein Benutzer die Löschung der Informationen beantragt hat.</span><span class="sxs-lookup"><span data-stu-id="30ea3-146">If the **Id** column shows as \*\*\n\*\*\*\*, this means that a user requested their information to be deleted.</span></span><br><span data-ttu-id="30ea3-147">![Screenshot des heruntergeladenen Excel-Berichts](media/app-usage-report8.png)</span><span class="sxs-lookup"><span data-stu-id="30ea3-147">![Screenshot of the downloaded Excel report](media/app-usage-report8.png)</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="30ea3-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="30ea3-148">Related topics</span></span>

- [<span data-ttu-id="30ea3-149">Teams – Analyse und Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="30ea3-149">Teams analytics and reporting</span></span>](teams-reporting-reference.md)