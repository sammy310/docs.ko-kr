---
title: NotifyIcon 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 587bf514db853f1122ed16abc05a195985c5ce8d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742130"
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="5dfbd-102">NotifyIcon 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5dfbd-102">NotifyIcon Component Overview (Windows Forms)</span></span>

<span data-ttu-id="5dfbd-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 일반적으로 백그라운드에서 실행되고 대체로 사용자 인터페이스를 표시하지 않는 프로세스에 대한 아이콘을 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="5dfbd-104">예를 들어 작업 표시줄의 상태 알림 영역에서 아이콘을 클릭하여 액세스할 수 있는 바이러스 방지 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>

## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="5dfbd-105">NotifyIcons의 키 속성</span><span class="sxs-lookup"><span data-stu-id="5dfbd-105">Key Properties of NotifyIcons</span></span>

<span data-ttu-id="5dfbd-106">각 <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 상태 영역에 단일 아이콘을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="5dfbd-107">3개의 백그라운드 프로세스가 있고 각 프로세스에 대한 아이콘을 표시하려는 경우 <xref:System.Windows.Forms.NotifyIcon> 구성 요소 3개를 폼에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="5dfbd-108"><xref:System.Windows.Forms.NotifyIcon> 구성 요소의 키 속성은 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="5dfbd-109"><xref:System.Windows.Forms.NotifyIcon.Icon%2A> 속성은 상태 영역에 표시되는 아이콘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="5dfbd-110">아이콘이 표시되려면 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>

## <a name="notifyicons-options"></a><span data-ttu-id="5dfbd-111">NotifyIcons 옵션</span><span class="sxs-lookup"><span data-stu-id="5dfbd-111">NotifyIcons Options</span></span>

<span data-ttu-id="5dfbd-112">풍선 설명, 바로 가기 메뉴 및 도구 설명을 <xref:System.Windows.Forms.NotifyIcon>에 연결하여 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-112">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>

<span data-ttu-id="5dfbd-113">풍선 설명을 표시할 시간 범위를 지정하고 <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> 메서드를 호출하여 <xref:System.Windows.Forms.NotifyIcon>에 대한 풍선 설명을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-113">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="5dfbd-114"><xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>을 각각 사용하여 풍선 설명의 텍스트, 아이콘 및 제목을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-114">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="5dfbd-115"><xref:System.Windows.Forms.NotifyIcon> 구성 요소에 연결된 도구 설명 및 바로 가기 메뉴가 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-115"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="5dfbd-116">자세한 내용은 [도구 설명 구성 요소 개요](tooltip-component-overview-windows-forms.md) 및 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5dfbd-116">For more information, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dfbd-117">참조</span><span class="sxs-lookup"><span data-stu-id="5dfbd-117">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- [<span data-ttu-id="5dfbd-118">NotifyIcon 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5dfbd-118">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
