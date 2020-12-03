---
title: '호환성이 손상되는 변경: Blazor: RenderTreeFrame 읽기 전용 퍼블릭 필드가 속성이 됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Blazor: RenderTreeFrame 읽기 전용 퍼블릭 필드가 속성이 됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e9da9c538cc0a8ed4f138ef64ece0c7d144f28d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759607"
---
# <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a><span data-ttu-id="d7055-103">Blazor: RenderTreeFrame 읽기 전용 퍼블릭 필드가 속성이 됨</span><span class="sxs-lookup"><span data-stu-id="d7055-103">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>

<span data-ttu-id="d7055-104">ASP.NET Core 3.0 및 3.1에서는 <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> 구조체가 <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence> 등을 비롯한 다양한 `readonly public` 필드를 노출했습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-104">In ASP.NET Core 3.0 and 3.1, the <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame> struct exposed various `readonly public` fields, including <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType>, <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>, and others.</span></span> <span data-ttu-id="d7055-105">ASP.NET Core 5.0 RC1 이상 버전에서는 모든 `readonly public` 필드가 `readonly public` 속성으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-105">In ASP.NET Core 5.0 RC1 and later versions, all the `readonly public` fields changed to `readonly public` properties.</span></span>

<span data-ttu-id="d7055-106">이 변경은 다음과 같은 이유로 인해 많은 개발자에게 영향을 주지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-106">This change won't affect many developers because:</span></span>

* <span data-ttu-id="d7055-107">`.razor` 파일(또는 수동 <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> 호출)을 사용하여 구성 요소를 정의하는 앱이나 라이브러리는 이 형식을 직접 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-107">Any app or library that simply uses `.razor` files (or even manual <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder> calls) to define its components wouldn't be referencing this type directly.</span></span>
* <span data-ttu-id="d7055-108">`RenderTreeFrame` 형식 자체는 프레임워크 외부에서 사용하기 위한 것이 아니라 구현 세부 정보로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-108">The `RenderTreeFrame` type itself is regarded as an implementation detail, not intended for use outside of the framework.</span></span> <span data-ttu-id="d7055-109">ASP.NET Core 3.0 이상에는 해당 형식이 직접 사용되는 경우 컴파일러 경고를 발생시키는 분석기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-109">ASP.NET Core 3.0 and later includes an analyzer that issues compiler warnings if the type is being used directly.</span></span>
* <span data-ttu-id="d7055-110">`RenderTreeFrame`을 직접 참조하는 경우에도 이 변경은 소스 변경이 아니라 이진 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-110">Even if you reference `RenderTreeFrame` directly, this change is binary-breaking but not source-breaking.</span></span> <span data-ttu-id="d7055-111">즉, 기존 소스 코드는 올바르게 컴파일하고 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-111">That is, your existing source code will compile and behave properly.</span></span> <span data-ttu-id="d7055-112">.NET Core 3.x 프레임워크에 대해 컴파일한 후 .NET 5.0 RC1 이상 프레임워크에 대해 이진 파일을 실행하는 경우에만 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-112">You'll only encounter an issue if compiling against a .NET Core 3.x framework and then running those binaries against the .NET 5.0 RC1 and later framework.</span></span>

<span data-ttu-id="d7055-113">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7055-113">For discussion, see GitHub issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d7055-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d7055-114">Version introduced</span></span>

<span data-ttu-id="d7055-115">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="d7055-115">5.0 RC1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d7055-116">이전 동작</span><span class="sxs-lookup"><span data-stu-id="d7055-116">Old behavior</span></span>

<span data-ttu-id="d7055-117">`RenderTreeFrame`의 퍼블릭 멤버는 필드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-117">Public members on `RenderTreeFrame` are defined as fields.</span></span> <span data-ttu-id="d7055-118">예를 들어 `renderTreeFrame.Sequence` 및 `renderTreeFrame.ElementName`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-118">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="d7055-119">새 동작</span><span class="sxs-lookup"><span data-stu-id="d7055-119">New behavior</span></span>

<span data-ttu-id="d7055-120">`RenderTreeFrame`의 퍼블릭 멤버는 이전과 동일한 이름의 속성으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-120">Public members on `RenderTreeFrame` are defined as properties with the same names as before.</span></span> <span data-ttu-id="d7055-121">예를 들어 `renderTreeFrame.Sequence` 및 `renderTreeFrame.ElementName`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-121">For example, `renderTreeFrame.Sequence` and `renderTreeFrame.ElementName`.</span></span>

<span data-ttu-id="d7055-122">이 변경 후 이전에 미리 컴파일된 코드를 다시 컴파일하지 않은 경우 다음과 비슷한 예외가 throw될 수 있습니다. *MissingFieldException: 필드를 찾을 수 없습니다. ‘Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType’* .</span><span class="sxs-lookup"><span data-stu-id="d7055-122">If older precompiled code hasn't been recompiled since this change, it may throw an exception similar to *MissingFieldException: Field not found: 'Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType'*.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d7055-123">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d7055-123">Reason for change</span></span>

<span data-ttu-id="d7055-124">ASP.NET Core 5.0에서 Blazor 구성 요소 렌더링에 큰 영향을 주는 성능 개선을 구현하기 위해 이러한 변경이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-124">This change was necessary to implement high-impact performance improvements in Blazor component rendering in ASP.NET Core 5.0.</span></span> <span data-ttu-id="d7055-125">동일한 수준의 안전 및 캡슐화를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-125">The same levels of safety and encapsulation are maintained.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d7055-126">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d7055-126">Recommended action</span></span>

<span data-ttu-id="d7055-127">대부분의 Blazor 개발자는 이러한 변경의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-127">Most Blazor developers are unaffected by this change.</span></span> <span data-ttu-id="d7055-128">이 변경은 아주 드문 경우에 라이브러리 및 패키지 작성자에게 영향을 미칠 가능성이 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-128">The change is more likely to affect library and package authors, but only in rare cases.</span></span> <span data-ttu-id="d7055-129">특히 다음과 같은 경우:</span><span class="sxs-lookup"><span data-stu-id="d7055-129">Specifically, if you're developing:</span></span>

* <span data-ttu-id="d7055-130">앱을 개발하는 중이며 ASP.NET Core 3.x 버전을 사용하거나 5.0 RC1 이상으로 업그레이드하는 경우 고유한 코드를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-130">An app and using ASP.NET Core 3.x or upgrading to 5.0 RC1 or later, you don't need to change your own code.</span></span> <span data-ttu-id="d7055-131">하지만 이 변경을 고려하여 업그레이드된 라이브러리에 의존하는 경우에는 해당 라이브러리의 최신 버전으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-131">However, if you depend on a library that upgraded to account for this change, then you need to update to a newer version of that library.</span></span>
* <span data-ttu-id="d7055-132">라이브러리를 개발하는 중이며 ASP.NET Core 5.0 RC1 이상만 지원하려는 경우 아무 작업도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-132">A library and want to support only ASP.NET Core 5.0 RC1 or later, no action is needed.</span></span> <span data-ttu-id="d7055-133">프로젝트 파일에서 `<TargetFramework>` 값을 `net5.0` 이상 버전으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-133">Just ensure that your project file declares a `<TargetFramework>` value of `net5.0` or a later version.</span></span>
* <span data-ttu-id="d7055-134">라이브러리를 개발하는 중이며 ASP.NET Core 3.x 및 5.0을 ‘모두’ 지원하려는 경우 코드에서 `RenderTreeFrame` 멤버를 읽도록 할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-134">A library and want to support both ASP.NET Core 3.x *and* 5.0, determine whether your code reads any `RenderTreeFrame` members.</span></span> <span data-ttu-id="d7055-135">예를 들어 `someRenderTreeFrame.FrameType`을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-135">For example, evaluating `someRenderTreeFrame.FrameType`.</span></span>
  * <span data-ttu-id="d7055-136">대부분의 라이브러리는 `.razor` 구성 요소를 포함하는 라이브러리를 비롯하여 `RenderTreeFrame` 멤버를 읽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-136">Most libraries won't read `RenderTreeFrame` members, including libraries that contain `.razor` components.</span></span> <span data-ttu-id="d7055-137">이 경우 아무 작업도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-137">In this case, no action is needed.</span></span>
  * <span data-ttu-id="d7055-138">그러나 라이브러리가 해당 멤버를 읽는 경우에는 `netstandard2.1` 및 `net5.0`을 모두 지원하기 위해 멀티 타기팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-138">However, if your library does that, you'll need to multi-target to support both `netstandard2.1` and `net5.0`.</span></span> <span data-ttu-id="d7055-139">프로젝트 파일에서 다음과 같이 변경을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-139">Apply the following changes in your project file:</span></span>
    * <span data-ttu-id="d7055-140">기존 `<TargetFramework>` 요소를 `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-140">Replace the existing `<TargetFramework>` element with `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.</span></span>
    * <span data-ttu-id="d7055-141">지원하려는 두 버전을 모두 고려하여 조건부 `Microsoft.AspNetCore.Components` 패키지 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-141">Use a conditional `Microsoft.AspNetCore.Components` package reference to account for both versions you wish to support.</span></span> <span data-ttu-id="d7055-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7055-142">For example:</span></span>

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

<span data-ttu-id="d7055-143">추가 설명을 보려면 [@jsakamoto가 `Toolbelt.Blazor.HeadElement` 라이브러리를 이미 업그레이드한 방법을 보여 주는 diff](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7055-143">For further clarification, see this [diff showing how @jsakamoto already upgraded the `Toolbelt.Blazor.HeadElement` library](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d7055-144">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d7055-144">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
