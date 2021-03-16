---
title: '호환성이 손상되는 변경: 상태 표시줄 컨트롤 제거'
description: 일부 Windows Forms 컨트롤을 더 이상 사용할 수 없는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 07/18/2020
ms.openlocfilehash: c93b16047896b263248858e807b74c547cfa6d9d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256193"
---
# <a name="removed-status-bar-controls"></a><span data-ttu-id="b3d73-103">상태 표시줄 컨트롤 제거</span><span class="sxs-lookup"><span data-stu-id="b3d73-103">Removed status bar controls</span></span>

<span data-ttu-id="b3d73-104">.NET 5부터 일부 Windows Forms 컨트롤을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-104">Starting in .NET 5, some Windows Forms controls are no longer available.</span></span>

## <a name="change-description"></a><span data-ttu-id="b3d73-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="b3d73-105">Change description</span></span>

<span data-ttu-id="b3d73-106">.NET 5부터 상태 표시줄 관련 Windows Forms 컨트롤 중 일부를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-106">Starting with .NET 5, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="b3d73-107">향상된 디자인 및 지원을 제공하는 대체 컨트롤이 .NET Framework 2.0에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-107">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="b3d73-108">사용되지 않는 컨트롤은 이전에 디자이너 도구 상자에서 제거되었지만, 여전히 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-108">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="b3d73-109">이제 완전히 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-109">Now, they have been completely removed.</span></span>

<span data-ttu-id="b3d73-110">다음 형식은 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-110">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

## <a name="version-introduced"></a><span data-ttu-id="b3d73-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b3d73-111">Version introduced</span></span>

<span data-ttu-id="b3d73-112">5.0</span><span class="sxs-lookup"><span data-stu-id="b3d73-112">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b3d73-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b3d73-113">Recommended action</span></span>

<span data-ttu-id="b3d73-114">이러한 컨트롤 및 해당 시나리오에 대한 대체 API로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b3d73-114">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="b3d73-115">이전 컨트롤(API)</span><span class="sxs-lookup"><span data-stu-id="b3d73-115">Old Control (API)</span></span> | <span data-ttu-id="b3d73-116">권장 대체</span><span class="sxs-lookup"><span data-stu-id="b3d73-116">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="b3d73-117">StatusBar</span><span class="sxs-lookup"><span data-stu-id="b3d73-117">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="b3d73-118">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="b3d73-118">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

## <a name="affected-apis"></a><span data-ttu-id="b3d73-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b3d73-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle`

### Category

Windows Forms

-->
