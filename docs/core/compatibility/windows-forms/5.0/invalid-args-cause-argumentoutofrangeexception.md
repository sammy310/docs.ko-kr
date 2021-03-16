---
title: '호환성이 손상되는 변경: WinForms 속성은 이제 ArgumentOutOfRangeException을 throw함'
description: 일부 Windows Forms 속성이 잘못된 인수에 대해 ArgumentOutOfRangeException을 throw하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 06/18/2020
ms.openlocfilehash: 493669af1ed5646d93e7c7d2688afd40f3fa731c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256155"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="6c3c8-103">WinForms 속성은 이제 ArgumentOutOfRangeException을 throw함</span><span class="sxs-lookup"><span data-stu-id="6c3c8-103">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="6c3c8-104">이제 일부 Windows Forms 속성에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-104">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="6c3c8-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="6c3c8-105">Change description</span></span>

<span data-ttu-id="6c3c8-106">이전에 범위를 벗어난 인수를 전달하면 이 속성은 <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>,<xref:System.ArgumentException>과 같은 다양한 예외를 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-106">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="6c3c8-107">.NET 5부터 범위를 벗어난 인수를 전달하면 해당 속성은 이제 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-107">Starting in .NET 5, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="6c3c8-108"><xref:System.ArgumentOutOfRangeException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-108">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="6c3c8-109">또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6c3c8-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6c3c8-110">Version introduced</span></span>

<span data-ttu-id="6c3c8-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6c3c8-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6c3c8-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6c3c8-112">Recommended action</span></span>

- <span data-ttu-id="6c3c8-113">잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="6c3c8-114">필요한 경우 속성을 설정할 때 <xref:System.ArgumentOutOfRangeException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-114">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6c3c8-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6c3c8-115">Affected APIs</span></span>

<span data-ttu-id="6c3c8-116">다음 표에서는 영향을 받는 속성 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c3c8-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="6c3c8-117">속성</span><span class="sxs-lookup"><span data-stu-id="6c3c8-117">Property</span></span> | <span data-ttu-id="6c3c8-118">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="6c3c8-118">Parameter name</span></span> | <span data-ttu-id="6c3c8-119">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="6c3c8-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="6c3c8-120">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="6c3c8-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="6c3c8-121">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="6c3c8-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="6c3c8-122">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="6c3c8-122">5.0 Preview 6</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
