---
title: '호환성이 손상되는 변경: Blazor: WebEventDescriptor.EventArgsType 속성이 대체됨'
description: WebEventDescriptor EventArgsType 속성이 EventName 속성으로 바뀌는 ASP.NET Core 6.0의 호환성이 손상되는 변경에 대해 알아봅니다.
author: scottaddie
ms.author: scaddie
ms.date: 02/24/2021
no-loc:
- Blazor
ms.openlocfilehash: 6df086ed234c0071ede83e9fe9d1710f011a2039
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260020"
---
# <a name="blazor-no-loc-textwebeventdescriptoreventargstype-property-replaced"></a><span data-ttu-id="5b66a-103">Blazor: :::no-loc text="WebEventDescriptor.EventArgsType"::: 속성이 대체됨</span><span class="sxs-lookup"><span data-stu-id="5b66a-103">Blazor: :::no-loc text="WebEventDescriptor.EventArgsType"::: property replaced</span></span>

<span data-ttu-id="5b66a-104"><xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor>클래스는 JavaScript에서 .NET으로 이벤트를 전달하기 위한 Blazor 내부 프로토콜의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-104">The <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor> class is part of Blazor's internal protocol for communicating events from JavaScript into .NET.</span></span> <span data-ttu-id="5b66a-105">이 클래스는 일반적으로 애플리케이션 코드에서 사용되는 것이 아니라 플랫폼 작성자가 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-105">This class isn't typically used by app code, but rather by platform authors.</span></span>

<span data-ttu-id="5b66a-106">ASP.NET Core 6.0부터 `WebEventDescriptor`의 <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A> 속성이 새로운 `EventName` 속성으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-106">Starting in ASP.NET Core 6.0, the <xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A> property on `WebEventDescriptor` is being replaced by a new `EventName` property.</span></span> <span data-ttu-id="5b66a-107">이 변경은 하위 수준의 플랫폼 구현 세부 정보이므로 앱 코드에 영향을 줄 가능성은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-107">This change is unlikely to affect any app code, as it's a low-level platform implementation detail.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5b66a-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="5b66a-108">Version introduced</span></span>

<span data-ttu-id="5b66a-109">6.0</span><span class="sxs-lookup"><span data-stu-id="5b66a-109">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5b66a-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="5b66a-110">Old behavior</span></span>

<span data-ttu-id="5b66a-111">ASP.NET Core 5.0 및 이전 버전에서 `EventArgsType` 속성은 DOM 이벤트 유형 그룹의 비표준 Blazor 특정 범주 이름을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-111">In ASP.NET Core 5.0 and earlier, the property `EventArgsType` describes a nonstandard, Blazor-specific category name for groups of DOM event types.</span></span> <span data-ttu-id="5b66a-112">예를 들어 `click` 및 `mousedown` 이벤트는 모두 `mouse`의 `EventArgsType` 값에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-112">For example, the `click` and `mousedown` events were both mapped to an `EventArgsType` value of `mouse`.</span></span> <span data-ttu-id="5b66a-113">마찬가지로, `cut`, `copy` 및 `paste` 이벤트는 `clipboard`의 `EventArgsType` 값에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-113">Similarly, `cut`, `copy`, and `paste` events are mapped to an `EventArgsType` value of `clipboard`.</span></span> <span data-ttu-id="5b66a-114">이러한 범주 이름은 들어오는 이벤트 인수 데이터를 역직렬화하는 데 사용할 .NET 형식을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-114">These category names are used to determine the .NET type to use for deserializing the incoming event arguments data.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5b66a-115">새 동작</span><span class="sxs-lookup"><span data-stu-id="5b66a-115">New behavior</span></span>

<span data-ttu-id="5b66a-116">ASP.NET Core 6.0부터 새 속성은 `EventName`은 원래 이벤트의 이름만 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-116">Starting in ASP.NET Core 6.0, the new property `EventName` only specifies the original event's name.</span></span> <span data-ttu-id="5b66a-117">예를 들어 `click`, `mousedown`, `cut`, `copy` 또는 `paste`입니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-117">For example, `click`, `mousedown`, `cut`, `copy`, or `paste`.</span></span> <span data-ttu-id="5b66a-118">더 이상 Blazor 특정 범주 이름을 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-118">There's no longer a need to supply a Blazor-specific category name.</span></span> <span data-ttu-id="5b66a-119">이러한 이유로 이전 속성 `EventArgsType`은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-119">For that reason, the old property `EventArgsType` is removed.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5b66a-120">변경 이유</span><span class="sxs-lookup"><span data-stu-id="5b66a-120">Reason for change</span></span>

<span data-ttu-id="5b66a-121">끌어오기 요청 [dotnet/aspnetcore#29993](https://github.com/dotnet/aspnetcore/pull/29993)에서 사용자 지정 이벤트 인수 클래스에 대한 지원이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-121">In pull request [dotnet/aspnetcore#29993](https://github.com/dotnet/aspnetcore/pull/29993), support for custom event arguments classes was introduced.</span></span> <span data-ttu-id="5b66a-122">이 지원의 일부로 프레임워크는 더 이상 미리 정의된 범주 집합에 맞는 모든 이벤트를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-122">As part of this support, the framework no longer relies on all events fitting into a predefined set of categories.</span></span> <span data-ttu-id="5b66a-123">이제 프레임워크에서 원래 이벤트 이름을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-123">The framework now only needs to know the original event name.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5b66a-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="5b66a-124">Recommended action</span></span>

<span data-ttu-id="5b66a-125">앱 코드는 영향을 받지 않으며 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-125">App code should be unaffected and doesn't need to change.</span></span>

<span data-ttu-id="5b66a-126">사용자 지정 Blazor 렌더링 플랫폼을 빌드하는 경우 이벤트를 `Renderer`로 디스패치하는 메커니즘을 업데이트해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-126">If building a custom Blazor rendering platform, you may need to update the mechanism for dispatching events into the `Renderer`.</span></span> <span data-ttu-id="5b66a-127">이벤트 범주에 대한 하드 코딩된 규칙을 원래 원시 이벤트 이름을 제공하는 간단한 논리로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5b66a-127">Replace any hardcoded rules about event categories with simpler logic that supplies the original, raw event name.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5b66a-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="5b66a-128">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`P:Microsoft.AspNetCore.Components.RenderTree.WebEventDescriptor.EventArgsType`

-->
