---
title: '호환성이 손상되는 변경: Activity.Tags의 태그 순서가 반대로 표시됨'
description: Activity.Tags가 추가된 순서에 따라 항목을 목록에 저장하는 핵심 .NET 라이브러리의 .NET 5.0 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 1ff14dc1a4f7a0bf8cf9e79f3750b819f4d4a5ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759748"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="c9911-103">Activity.Tags의 태그 순서가 반대로 표시됨</span><span class="sxs-lookup"><span data-stu-id="c9911-103">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="c9911-104">이제 <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>이 항목을 추가된 순서대로 목록에 저장합니다. 즉, 첫 번째로 추가된 항목이 목록의 첫 번째 항목이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9911-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="c9911-105">이 변경 내용은 [OpenTelemetry 특성 사양](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes)을 따른 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9911-105">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

## <a name="change-description"></a><span data-ttu-id="c9911-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="c9911-106">Change description</span></span>

<span data-ttu-id="c9911-107">이전 .NET 버전에서는 <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>이 항목을 추가된 순서와 반대로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c9911-107">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="c9911-108">즉, 첫 번째로 추가된 항목이 목록의 마지막 항목이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9911-108">That is, the first item added is last in the list.</span></span> <span data-ttu-id="c9911-109">.NET 5.0부터 항목 순서가 반대로 전환되어 첫 번째로 추가된 항목이 항상 목록의 첫 번째 항목이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9911-109">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c9911-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c9911-110">Version introduced</span></span>

<span data-ttu-id="c9911-111">5.0</span><span class="sxs-lookup"><span data-stu-id="c9911-111">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c9911-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="c9911-112">Recommended action</span></span>

<span data-ttu-id="c9911-113">앱에 <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> 목록 순서에 대한 종속성이 있고 .NET 5.0 이상으로 업그레이드하는 경우 이 코드 부분을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9911-113">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c9911-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c9911-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
