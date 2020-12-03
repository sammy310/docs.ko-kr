---
title: '호환성이 손상되는 변경: Blazor: JSObjectReference 및 JSInProcessObjectReference 형식을 internal로 변경함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: JSObjectReference 및 JSInProcessObjectReference 형식을 internal로 변경함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759735"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="ab290-103">Blazor: JSObjectReference 및 JSInProcessObjectReference 형식을 internal로 변경함</span><span class="sxs-lookup"><span data-stu-id="ab290-103">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="ab290-104">ASP.NET Core 5.0 RC1에서 도입된 새로운 `Microsoft.JSInterop.JSObjectReference` 및 `Microsoft.JSInterop.JSInProcessObjectReference` 형식이 `internal`로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-104">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ab290-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ab290-105">Version introduced</span></span>

<span data-ttu-id="ab290-106">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="ab290-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ab290-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="ab290-107">Old behavior</span></span>

<span data-ttu-id="ab290-108">`JSObjectReference`는 `IJSRuntime`를 통해 JavaScript interop 호출에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-108">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="ab290-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-109">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a><span data-ttu-id="ab290-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="ab290-110">New behavior</span></span>

<span data-ttu-id="ab290-111">`JSObjectReference`는 [internal](../../../../csharp/language-reference/keywords/internal.md) 액세스 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-111">`JSObjectReference` uses the [internal](../../../../csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="ab290-112">대신 `public` `IJSObjectReference` 인터페이스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-112">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="ab290-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-113">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="ab290-114">`JSInProcessObjectReference` 또한 `internal`로 표시되었으며 `IJSInProcessObjectReference`로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-114">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ab290-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ab290-115">Reason for change</span></span>

<span data-ttu-id="ab290-116">이 변경으로 인해 JavaScript interop 기능이 Blazor 내의 다른 패턴과 더 일관되게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-116">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="ab290-117">`IJSObjectReference`는 유사한 용도로 사용되고 유사한 메서드 및 확장을 포함한다는 점에서 `IJSRuntime`과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-117">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ab290-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ab290-118">Recommended action</span></span>

<span data-ttu-id="ab290-119">`JSObjectReference` 및 `JSInProcessObjectReference` 항목을 각각 `IJSObjectReference` 및 `IJSInProcessObjectReference`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ab290-119">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ab290-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ab290-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
