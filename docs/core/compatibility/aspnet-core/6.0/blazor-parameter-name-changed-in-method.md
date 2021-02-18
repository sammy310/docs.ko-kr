---
title: '호환성이 손상되는 변경: Blazor: RequestImageFileAsync 메서드에서 매개 변수 이름이 변경됨'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 관해 알아보기. Blazor: RequestImageFileAsync 메서드에서 매개 변수 이름이 변경됨'
author: scottaddie
ms.author: scaddie
ms.date: 02/09/2021
ms.openlocfilehash: bfaaa6bfe94c32fbc1a5b5b70db863d105d389b5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488243"
---
# <a name="blazor-parameter-name-changed-in-requestimagefileasync-method"></a><span data-ttu-id="bd921-103">Blazor: RequestImageFileAsync 메서드에서 매개 변수 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="bd921-103">Blazor: Parameter name changed in RequestImageFileAsync method</span></span>

<span data-ttu-id="bd921-104">`RequestImageFileAsync` 메서드의 `maxWith` 매개 변수 이름이 `maxWith`에서 `maxWidth`로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd921-104">The `RequestImageFileAsync` method's `maxWith` parameter was renamed from `maxWith` to `maxWidth`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="bd921-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bd921-105">Version introduced</span></span>

<span data-ttu-id="bd921-106">6.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="bd921-106">6.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="bd921-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="bd921-107">Old behavior</span></span>

<span data-ttu-id="bd921-108">매개 변수 이름의 철자는 `maxWith`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd921-108">The parameter name is spelled `maxWith`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="bd921-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="bd921-109">New behavior</span></span>

<span data-ttu-id="bd921-110">매개 변수 이름의 철자는 `maxWidth`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd921-110">The parameter name is spelled `maxWidth`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="bd921-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="bd921-111">Reason for change</span></span>

<span data-ttu-id="bd921-112">원래 매개 변수 이름이 철자 오류였습니다.</span><span class="sxs-lookup"><span data-stu-id="bd921-112">The original parameter name was a typographical error.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bd921-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bd921-113">Recommended action</span></span>

<span data-ttu-id="bd921-114">`RequestImageFile` API에서 명명된 매개 변수를 사용하는 경우 `maxWith` 매개 변수 이름을 `maxWidth`로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bd921-114">If you're using named parameters in the `RequestImageFile` API, update the `maxWith` parameter name to `maxWidth`.</span></span> <span data-ttu-id="bd921-115">그러지 않으면 변경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd921-115">Otherwise, no change is necessary.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="bd921-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bd921-116">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Components.Forms.BrowserFileExtensions.RequestImageFileAsync`

-->
