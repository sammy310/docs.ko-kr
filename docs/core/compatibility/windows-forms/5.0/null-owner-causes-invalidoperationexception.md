---
title: '호환성이 손상되는 변경: DataGridView 관련 API가 InvalidOperationException을 throw함'
description: 개체의 DataGridViewCellAccessibleObject.Owner 값이 null인 경우 일부 DataGridView 관련 API가 예외를 throw하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/18/2020
ms.openlocfilehash: 927b1c9160700159a45aa1472b8d96f1a9ecfe25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759911"
---
# <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="df71e-103">DataGridView 관련 API가 이제 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="df71e-103">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="df71e-104">개체의 <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> 값이 `null`인 경우 <xref:System.Windows.Forms.DataGridView>와 관련된 일부 API는 이제 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-104">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

## <a name="change-description"></a><span data-ttu-id="df71e-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="df71e-105">Change description</span></span>

<span data-ttu-id="df71e-106">이전 .NET 버전에서는 영향을 받는 API가 호출되고 <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> 값이 `null`일 때 <xref:System.NullReferenceException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-106">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="df71e-107">.NET 5.0부터 이러한 API는 호출될 때 <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> 값이 `null`인 경우 <xref:System.NullReferenceException> 대신 <xref:System.InvalidOperationException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-107">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="df71e-108"><xref:System.InvalidOperationException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-108">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="df71e-109">또한 잘못된 속성을 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-109">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="df71e-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="df71e-110">Version introduced</span></span>

<span data-ttu-id="df71e-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="df71e-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="df71e-112">Recommended action</span></span>

<span data-ttu-id="df71e-113">코드를 검토하고 필요한 경우 <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> 속성을 `null`로 사용하여 영향을 받는 형식이 생성되지 않도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-113">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="df71e-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="df71e-114">Affected APIs</span></span>

<span data-ttu-id="df71e-115">다음 표에서는 영향을 받는 속성 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="df71e-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="df71e-116">영향을 받는 메서드 또는 속성</span><span class="sxs-lookup"><span data-stu-id="df71e-116">Affected method or property</span></span> | <span data-ttu-id="df71e-117">유효성이 확인된 속성</span><span class="sxs-lookup"><span data-stu-id="df71e-117">Validated property</span></span> | <span data-ttu-id="df71e-118">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="df71e-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-119">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-120">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-121">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-122">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-123">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-124">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-125">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-126">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-127">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-128">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-129">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="df71e-130">5.0</span><span class="sxs-lookup"><span data-stu-id="df71e-130">5.0</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State`
- `M:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)`
- `M:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction`

### Category

Windows Forms

-->
