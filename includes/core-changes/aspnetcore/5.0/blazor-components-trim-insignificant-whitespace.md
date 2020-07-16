---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174267"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="7a866-101">Blazor: 컴파일 시간에 구성 요소에서 중요하지 않은 공백을 자름</span><span class="sxs-lookup"><span data-stu-id="7a866-101">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="7a866-102">ASP.NET Core 5.0 미리 보기 7부터 Razor 컴파일러는 컴파일 시간에 Blazor 구성 요소( *.razor* 파일)에서 중요하지 않은 공백을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-102">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="7a866-103">자세한 내용은 이슈 [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a866-103">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7a866-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7a866-104">Version introduced</span></span>

<span data-ttu-id="7a866-105">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="7a866-105">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7a866-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="7a866-106">Old behavior</span></span>

<span data-ttu-id="7a866-107">Blazor Server 및 Blazor WebAssembly의 3.x 버전에서는 구성 요소의 소스 코드에서 공백이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-107">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="7a866-108">공백만 있는 텍스트 노드는 시각적 효과가 없는 경우에도 브라우저의 DOM(문서 개체 모델)에서 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-108">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="7a866-109">다음 Blazor 구성 요소 코드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-109">Consider the following Blazor component code:</span></span>

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

<span data-ttu-id="7a866-110">앞의 예제에서는 다음 위치에서 두 개의 공백 노드를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-110">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="7a866-111">`@foreach` 코드 블록의 외부</span><span class="sxs-lookup"><span data-stu-id="7a866-111">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="7a866-112">`<li>` 요소의 주위</span><span class="sxs-lookup"><span data-stu-id="7a866-112">Around the `<li>` element.</span></span>
* <span data-ttu-id="7a866-113">`@item.Text` 출력의 주위</span><span class="sxs-lookup"><span data-stu-id="7a866-113">Around the `@item.Text` output.</span></span>

<span data-ttu-id="7a866-114">100개 항목을 포함하는 목록은 402개 공백 노드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-114">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="7a866-115">공백 노드가 렌더링된 출력에 시각적으로 영향을 주지 않더라도 해당 개수는 렌더링된 모든 노드의 절반을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-115">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="7a866-116">구성 요소의 정적 HTML을 렌더링하면 태그 안의 공백이 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-116">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="7a866-117">예를 들어 다음 구성 요소의 소스를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-117">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="7a866-118">공백이 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-118">Whitespace isn't preserved.</span></span> <span data-ttu-id="7a866-119">미리 렌더링된 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-119">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a><span data-ttu-id="7a866-120">새 동작</span><span class="sxs-lookup"><span data-stu-id="7a866-120">New behavior</span></span>

<span data-ttu-id="7a866-121">`@preservewhitespace` 지시문이 `true` 값과 함께 사용되지 않을 때 공백 노드가 제거되는 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-121">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="7a866-122">공백 노드가 요소 내에서 선행 또는 후행인 경우</span><span class="sxs-lookup"><span data-stu-id="7a866-122">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="7a866-123">공백 노드가 `RenderFragment` 매개 변수 내에서 선행 또는 후행인 경우(예:</span><span class="sxs-lookup"><span data-stu-id="7a866-123">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="7a866-124">자식 콘텐츠가 다른 구성 요소로 전달됨)</span><span class="sxs-lookup"><span data-stu-id="7a866-124">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="7a866-125">공백 노드가 `@if` 및 `@foreach`와 같은 C# 코드 블록의 앞 또는 뒤에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="7a866-125">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7a866-126">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7a866-126">Reason for change</span></span>

<span data-ttu-id="7a866-127">ASP.NET Core 5.0에서 Blazor의 목표는 렌더링 및 diff 수행 성능을 향상하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-127">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="7a866-128">중요하지 않은 공백 트리 노드는 벤치마크에서 렌더링 시간의 최대 40%를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-128">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7a866-129">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7a866-129">Recommended action</span></span>

<span data-ttu-id="7a866-130">대부분의 경우 렌더링된 구성 요소의 시각적 레이아웃에는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-130">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="7a866-131">그러나 `white-space: pre` 같은 CSS 규칙을 사용하는 경우 공백 제거는 렌더링된 출력에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-131">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="7a866-132">성능 최적화를 사용하지 않고 공백을 유지하려면 다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-132">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="7a866-133">*.razor* 파일의 맨 위에 `@preservewhitespace true` 지시문을 추가하여 특정 구성 요소에 기본 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-133">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="7a866-134">*_Imports.razor* 파일 안에 `@preservewhitespace true` 지시문을 추가하여 전체 하위 디렉터리 또는 전체 프로젝트에 기본 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-134">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="7a866-135">대부분의 경우 애플리케이션은 대개 계속해서 정상적으로(그러나 더 빠르게) 동작하므로 필요한 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-135">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="7a866-136">공백 제거 시 특정 구성 요소에 문제가 발생하는 경우에는 해당 구성 요소에서 `@preservewhitespace true`를 사용하여 최적화를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a866-136">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

#### <a name="category"></a><span data-ttu-id="7a866-137">범주</span><span class="sxs-lookup"><span data-stu-id="7a866-137">Category</span></span>

<span data-ttu-id="7a866-138">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7a866-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7a866-139">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7a866-139">Affected APIs</span></span>

<span data-ttu-id="7a866-140">없음</span><span class="sxs-lookup"><span data-stu-id="7a866-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
