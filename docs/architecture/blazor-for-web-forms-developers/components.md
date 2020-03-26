---
title: 블레이저로 재사용 가능한 UI 구성 요소 빌드
description: Blazor를 사용하여 재사용 가능한 UI 구성 요소를 빌드하는 방법과 ASP.NET 웹 폼 컨트롤과 비교하는 방법에 대해 알아봅니다.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 228f7aec4c7b87cb6d4127b55745f7a5ed90aaf9
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80228621"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="46281-103">블레이저로 재사용 가능한 UI 구성 요소 빌드</span><span class="sxs-lookup"><span data-stu-id="46281-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="46281-104">ASP.NET Web Forms의 가장 아름다운 점 중 하나는 재사용 가능한 UI(사용자 인터페이스) 코드를 재사용 가능한 UI 컨트롤로 캡슐화하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="46281-105">*.ascx* 파일을 사용하여 태그에서 사용자 지정 사용자 컨트롤을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="46281-106">또한 전체 디자이너 지원을 통해 코드에서 정교한 서버 컨트롤을 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="46281-107">Blazor는 *구성 요소를*통해 UI 캡슐화도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="46281-108">구성 요소:</span><span class="sxs-lookup"><span data-stu-id="46281-108">A component:</span></span>

- <span data-ttu-id="46281-109">UI의 독립형 청크입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="46281-110">자체 상태 및 렌더링 논리를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="46281-111">UI 이벤트 처리기를 정의하고, 입력 데이터에 바인딩하고, 자체 수명 주기를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="46281-112">일반적으로 Razor 구문을 사용하여 *.razor* 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="46281-113">면도기 소개</span><span class="sxs-lookup"><span data-stu-id="46281-113">An introduction to Razor</span></span>

<span data-ttu-id="46281-114">Razor는 HTML 및 C#을 기반으로 하는 경량 마크업 템플릿 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="46281-115">Razor를 사용하면 태그와 C# 코드 간에 원활하게 전환하여 구성 요소 렌더링 논리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="46281-116">*.razor* 파일을 컴파일하면 렌더링 논리가 .NET 클래스의 구조화 된 방식으로 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="46281-117">컴파일된 클래스의 이름은 *.razor* 파일 이름에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46281-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="46281-118">네임스페이스는 프로젝트 및 폴더 경로의 기본 네임스페이스에서 가져온 것이거나 `@namespace` 지시문을 사용하여 네임스페이스를 명시적으로 지정할 수 있습니다(아래 Razor 지시문에 대해 자세히 참조).</span><span class="sxs-lookup"><span data-stu-id="46281-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="46281-119">구성 요소의 렌더링 논리는 C#을 사용하여 추가된 동적 논리가 있는 일반 HTML 태그를 사용하여 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="46281-120">문자는 `@` C#으로 전환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="46281-121">면도기는 일반적으로 HTML로 다시 전환 한 경우 알아내는 것에 대해 똑똑합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="46281-122">예를 들어 다음 구성 요소는 `<p>` 현재 시간으로 태그를 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="46281-123">C# 식의 시작과 끝을 명시적으로 지정하려면 괄호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="46281-124">또한 Razor를 사용하면 렌더링 논리에서 C# 제어 흐름을 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="46281-125">예를 들어 다음과 같은 일부 HTML을 조건부로 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="46281-126">또는 다음과 같이 일반 C# `foreach` 루프를 사용하여 항목 목록을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="46281-127">Razor 지시문은 ASP.NET 웹 양식의 지시문과 마찬가지로 Razor 구성 요소가 컴파일되는 방식의 여러 측면을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="46281-128">예를 들어 구성 요소의 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-128">Examples include the component's:</span></span>

- <span data-ttu-id="46281-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="46281-129">Namespace</span></span>
- <span data-ttu-id="46281-130">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="46281-130">Base class</span></span>
- <span data-ttu-id="46281-131">구현된 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46281-131">Implemented interfaces</span></span>
- <span data-ttu-id="46281-132">제네릭 매개 변수</span><span class="sxs-lookup"><span data-stu-id="46281-132">Generic parameters</span></span>
- <span data-ttu-id="46281-133">가져온 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="46281-133">Imported namespaces</span></span>
- <span data-ttu-id="46281-134">경로</span><span class="sxs-lookup"><span data-stu-id="46281-134">Routes</span></span>

<span data-ttu-id="46281-135">Razor 지시문은 `@` 문자로 시작하며 일반적으로 파일 시작 시 새 줄의 시작 부분에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="46281-136">예를 들어 `@namespace` 지시문은 구성 요소의 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="46281-137">다음 표에는 Blazor에 사용되는 다양한 Razor 지시문과 ASP.NET Web Forms 등가물(있는 경우)이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="46281-138">지시문</span><span class="sxs-lookup"><span data-stu-id="46281-138">Directive</span></span>    |<span data-ttu-id="46281-139">Description</span><span class="sxs-lookup"><span data-stu-id="46281-139">Description</span></span>|<span data-ttu-id="46281-140">예제</span><span class="sxs-lookup"><span data-stu-id="46281-140">Example</span></span>|<span data-ttu-id="46281-141">동등한 웹 양식</span><span class="sxs-lookup"><span data-stu-id="46281-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="46281-142">구성 요소에 클래스 수준 특성 추가</span><span class="sxs-lookup"><span data-stu-id="46281-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="46281-143">None</span><span class="sxs-lookup"><span data-stu-id="46281-143">None</span></span>|
|`@code`      |<span data-ttu-id="46281-144">구성 요소에 클래스 멤버 추가</span><span class="sxs-lookup"><span data-stu-id="46281-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="46281-145">지정된 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="46281-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="46281-146">코드 숨김 사용</span><span class="sxs-lookup"><span data-stu-id="46281-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="46281-147">지정된 기본 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="46281-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="46281-148">구성 요소에 서비스 삽입</span><span class="sxs-lookup"><span data-stu-id="46281-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="46281-149">None</span><span class="sxs-lookup"><span data-stu-id="46281-149">None</span></span>|
|`@layout`    |<span data-ttu-id="46281-150">구성 요소에 대한 레이아웃 구성 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="46281-151">구성 요소의 네임스페이스 설정</span><span class="sxs-lookup"><span data-stu-id="46281-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="46281-152">None</span><span class="sxs-lookup"><span data-stu-id="46281-152">None</span></span>|
|`@page`      |<span data-ttu-id="46281-153">구성 요소의 배선을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="46281-154">구성 요소에 대한 제네릭 형식 매개 변수 지정</span><span class="sxs-lookup"><span data-stu-id="46281-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="46281-155">코드 숨김 사용</span><span class="sxs-lookup"><span data-stu-id="46281-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="46281-156">범위로 가져올 네임스페이스 지정</span><span class="sxs-lookup"><span data-stu-id="46281-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="46281-157">*web.config에* 네임스페이스 추가</span><span class="sxs-lookup"><span data-stu-id="46281-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="46281-158">또한 Razor 구성 요소는 요소에 대한 *지시문 특성을* 광범위하게 사용하여 구성 요소가 컴파일되는 방식(이벤트 처리, 데이터 바인딩, 구성 요소 & 요소 참조 등)의 다양한 측면을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="46281-159">지시문 특성은 모두 괄호 안의 값이 선택 사항인 일반적인 일반 구문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="46281-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="46281-160">다음 표에는 Blazor에서 사용되는 Razor 지시문에 대한 다양한 특성이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="46281-161">특성</span><span class="sxs-lookup"><span data-stu-id="46281-161">Attribute</span></span>    |<span data-ttu-id="46281-162">Description</span><span class="sxs-lookup"><span data-stu-id="46281-162">Description</span></span>|<span data-ttu-id="46281-163">예제</span><span class="sxs-lookup"><span data-stu-id="46281-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="46281-164">특성 사전 렌더링</span><span class="sxs-lookup"><span data-stu-id="46281-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="46281-165">양방향 데이터 바인딩 생성</span><span class="sxs-lookup"><span data-stu-id="46281-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="46281-166">지정된 이벤트에 대한 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="46281-167">컬렉션의 요소를 보존하기 위해 디핑 알고리즘에서 사용할 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="46281-168">구성 요소 또는 HTML 요소에 대한 참조 캡처</span><span class="sxs-lookup"><span data-stu-id="46281-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="46281-169">Blazor (,`@onclick`및 `@bind` `@ref`기타)에서 사용하는 다양한 지시문 속성은 아래 및 이후 장에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="46281-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="46281-170">*.aspx* 및 *.ascx* 파일에 사용되는 많은 구문에는 Razor에 병렬 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="46281-171">다음은 ASP.NET 웹 양식 및 Razor에 대한 구문에 대한 간단한 비교입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="46281-172">기능</span><span class="sxs-lookup"><span data-stu-id="46281-172">Feature</span></span>                      |<span data-ttu-id="46281-173">웹 양식</span><span class="sxs-lookup"><span data-stu-id="46281-173">Web Forms</span></span>           |<span data-ttu-id="46281-174">구문</span><span class="sxs-lookup"><span data-stu-id="46281-174">Syntax</span></span>               |<span data-ttu-id="46281-175">Razor</span><span class="sxs-lookup"><span data-stu-id="46281-175">Razor</span></span>         |<span data-ttu-id="46281-176">구문</span><span class="sxs-lookup"><span data-stu-id="46281-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="46281-177">지시문</span><span class="sxs-lookup"><span data-stu-id="46281-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="46281-178">코드 블록</span><span class="sxs-lookup"><span data-stu-id="46281-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="46281-179">표현식</span><span class="sxs-lookup"><span data-stu-id="46281-179">Expressions</span></span><br><span data-ttu-id="46281-180">(HTML 인코딩)</span><span class="sxs-lookup"><span data-stu-id="46281-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="46281-181">암시적:`@`</span><span class="sxs-lookup"><span data-stu-id="46281-181">Implicit: `@`</span></span><br><span data-ttu-id="46281-182">명시적:`@()`</span><span class="sxs-lookup"><span data-stu-id="46281-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="46281-183">주석</span><span class="sxs-lookup"><span data-stu-id="46281-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="46281-184">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="46281-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="46281-185">Razor 구성 요소 클래스에 멤버를 `@code` 추가하려면 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="46281-186">이 기술은 ASP.NET Web `<script runat="server">...</script>` Forms 사용자 컨트롤 또는 페이지에서 블록을 사용하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="46281-187">Razor는 C#을 기반으로 하므로 C#*프로젝트(.csproj)* 내에서 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="46281-188">Visual Basic*프로젝트(.vbproj)에서는* *.razor* 파일을 컴파일할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="46281-189">블레이저 프로젝트에서 Visual Basic 프로젝트를 계속 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="46281-190">그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-190">The opposite is true too.</span></span>

<span data-ttu-id="46281-191">전체 Razor 구문 참조는 [ASP.NET 코어에 대한 Razor 구문 참조를](/aspnet/core/mvc/views/razor)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46281-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="46281-192">구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="46281-192">Use components</span></span>

<span data-ttu-id="46281-193">일반 HTML 외에도 구성 요소는 렌더링 논리의 일부로 다른 구성 요소를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="46281-194">Razor에서 구성 요소를 사용하는 구문은 ASP.NET Web Forms 앱에서 사용자 컨트롤을 사용하는 것과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="46281-195">구성 요소는 구성 요소의 형식 이름과 일치하는 요소 태그를 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="46281-196">예를 들어 다음과 같은 `Counter` 구성 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="46281-197">ASP.NET 웹 양식과 달리 Blazor의 구성 요소는 다음과 같은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="46281-198">요소 접두사(예: )를 `asp:`사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="46281-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="46281-199">페이지 또는 *web.config에서*등록할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="46281-200">.NET 형식과 같은 Razor 구성 요소를 생각해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="46281-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="46281-201">구성요소를 포함하는 어셈블리가 참조되면 구성요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="46281-202">구성 요소의 네임스페이스를 범위로 `@using` 가져오려면 지시문을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="46281-203">기본 Blazor 프로젝트에서 볼 수 있듯이 지시문을 `@using` *_Imports.razor* 파일에 넣어 동일한 디렉터리 및 자식 디렉터리의 모든 *.razor* 파일로 가져오는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="46281-204">구성 요소의 네임스페이스가 범위에 없는 경우 C#에서와 같이 전체 형식 이름을 사용하여 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="46281-205">구성 요소 매개 변수</span><span class="sxs-lookup"><span data-stu-id="46281-205">Component parameters</span></span>

<span data-ttu-id="46281-206">웹 양식 ASP.NET 매개 변수와 데이터를 공용 속성을 사용하여 컨트롤로 플로우는 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="46281-207">이러한 속성은 특성을 사용하여 태그로 설정하거나 코드에서 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="46281-208">Blazor 구성 요소는 유사한 방식으로 작동하지만 구성 요소 속성도 구성 요소 매개 변수로 간주할 `[Parameter]` 특성으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="46281-209">다음 `Counter` 구성 요소는 단추를 `IncrementAmount` 클릭할 때마다 `Counter` 증분해야 하는 양을 지정하는 데 사용할 수 있는 구성 요소 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

```razor
<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    int currentCount = 0;

    [Parameter]
    public int IncrementAmount { get; set; } = 1;

    void IncrementCount()
    {
        currentCount+=IncrementAmount;
    }
}
```

<span data-ttu-id="46281-210">Blazor에서 구성 요소 매개 변수를 지정하려면 ASP.NET 웹 양식에서와 마찬가지로 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="46281-211">이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="46281-211">Event handlers</span></span>

<span data-ttu-id="46281-212">ASP.NET 웹 양식과 Blazor 모두 UI 이벤트를 처리하기 위한 이벤트 기반 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="46281-213">이러한 이벤트의 예로는 단추 클릭 및 텍스트 입력이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="46281-214">웹 양식 ASP.NET HTML 서버 컨트롤을 사용하여 DOM에서 노출되는 UI 이벤트를 처리하거나 웹 서버 컨트롤에서 노출되는 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="46281-215">이벤트는 포스트백 양식 요청을 통해 서버에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="46281-216">다음 웹 양식 단추 클릭 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="46281-217">*카운터.ascx*</span><span class="sxs-lookup"><span data-stu-id="46281-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="46281-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="46281-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="46281-219">Blazor에서 폼의 `@on{event}`지시문 특성을 사용하여 DOM UI 이벤트에 대한 처리기를 직접 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="46281-220">`{event}` 자리 표시자는 이벤트의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46281-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="46281-221">예를 들어 다음과 같은 단추 클릭을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="46281-222">이벤트 처리기는 선택적 이벤트별 인수를 수락하여 이벤트에 대한 자세한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="46281-223">예를 들어 마우스 이벤트는 `MouseEventArgs` 인수를 사용할 수 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="46281-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="46281-224">이벤트 처리기에 대한 메서드 그룹을 참조하는 대신 lambda 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="46281-225">람다 식을 사용하면 다른 범위 내 값을 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="46281-226">이벤트 처리기는 동기 또는 비동기적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="46281-227">예를 들어 다음 `OnClick` 이벤트 처리기는 비동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="46281-228">이벤트가 처리되면 구성 요소 상태 변경을 고려하여 구성 요소가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="46281-229">비동기 이벤트 처리기를 사용하면 처리기 실행이 완료된 직후 에 구성 요소가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="46281-230">비동기가 `Task` 완료되면 구성 요소가 *다시* 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="46281-231">이 비동기 실행 모드는 비동기가 `Task` 진행 중인 동안 적절한 UI를 렌더링할 수 있는 기회를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

```razor
<button @onclick="ShowMessage">Get message</button>

@if (showMessage)
{
    @if (message == null)
    {
        <p><em>Loading...</em></p>
    }
    else
    {
        <p>The message is: @message</p>
    }
}

@code
{
    bool showMessage = false;
    string message;

    public async Task ShowMessage()
    {
        showMessage = true;
        message = await MessageService.GetMessageAsync();
    }
}
```

<span data-ttu-id="46281-232">구성 요소는 형식의 `EventCallback<TValue>`구성 요소 매개 변수를 정의하여 자체 이벤트를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="46281-233">이벤트 콜백은 선택적 인수, 동기 또는 비동기, 메서드 그룹 또는 람다 식과 같은 DOM UI 이벤트 처리기의 모든 변형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="46281-234">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="46281-234">Data binding</span></span>

<span data-ttu-id="46281-235">Blazor는 UI 구성 요소에서 구성 요소의 상태에 데이터를 바인딩하는 간단한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="46281-236">이 방법은 데이터 원본에서 UI 컨트롤로 데이터를 바인딩하기 위해 ASP.NET Web Forms의 기능과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="46281-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="46281-237">데이터 처리 섹션에서 다른 데이터 원본의 데이터 처리에 대해 [다룹니다.](data.md)</span><span class="sxs-lookup"><span data-stu-id="46281-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="46281-238">UI 구성 요소에서 구성 요소의 상태로 양방향 데이터 바인딩을 `@bind` 만들려면 지시문 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="46281-239">다음 예제에서는 확인란의 값이 `isChecked` 필드에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="46281-240">구성 요소가 렌더링되면 확인란의 값이 `isChecked` 필드 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="46281-241">사용자가 확인란을 전환하면 `onchange` 이벤트가 발생되고 필드가 `isChecked` 새 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="46281-242">이 `@bind` 경우 구문은 다음 태그와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="46281-243">바인딩에 사용되는 이벤트를 변경하려면 특성을 `@bind:event` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="46281-244">구성 요소는 매개 변수에 대한 데이터 바인딩을 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="46281-245">데이터 바인딩하려면 바인딩 가능한 매개 변수와 이름이 같은 이벤트 콜백 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="46281-246">"변경된" 접미사가 이름에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="46281-247">*암호 상자.면도기*</span><span class="sxs-lookup"><span data-stu-id="46281-247">*PasswordBox.razor*</span></span>

```razor
Password: <input
    value="@Password"
    @oninput="OnPasswordChanged"
    type="@(showPassword ? "text" : "password")" />

<label><input type="checkbox" @bind="showPassword" />Show password</label>

@code {
    private bool showPassword;

    [Parameter]
    public string Password { get; set; }

    [Parameter]
    public EventCallback<string> PasswordChanged { get; set; }

    private Task OnPasswordChanged(ChangeEventArgs e)
    {
        Password = e.Value.ToString();
        return PasswordChanged.InvokeAsync(Password);
    }
}
```

<span data-ttu-id="46281-248">데이터 바인딩을 기본 UI 요소에 연결하려면 값을 설정하고 특성을 사용하는 대신 UI `@bind` 요소에서 직접 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="46281-249">구성 요소 매개 변수에 `@bind-{Parameter}` 바인딩하려면 특성을 사용하여 바인딩할 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="46281-250">상태 변경</span><span class="sxs-lookup"><span data-stu-id="46281-250">State changes</span></span>

<span data-ttu-id="46281-251">컴포넌트의 상태가 일반 UI 이벤트 또는 이벤트 콜백 외부에서 변경된 경우 구성 요소는 수동으로 다시 렌더링해야 한다는 신호를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="46281-252">구성 요소의 상태가 변경되었음을 알리려면 `StateHasChanged` 구성 요소의 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="46281-253">아래 예제에서 구성 요소는 앱의 `AppState` 다른 부분에서 업데이트할 수 있는 서비스의 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="46281-254">구성 요소는 메시지가 `StateHasChanged` 업데이트될 `AppState.OnChange` 때마다 구성 요소가 렌더링되도록 해당 메서드를 이벤트에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        shortlist.Add(itinerary);
        NotifyStateChanged();
    }

    private void NotifyStateChanged() => OnChange?.Invoke();
}
```

```razor
@inject AppState AppState

<p>App message: @AppState.Message</p>

@code {
    protected override void OnInitialized()
    {
        AppState.OnChange += StateHasChanged
    }
}
```

## <a name="component-lifecycle"></a><span data-ttu-id="46281-255">구성 요소 수명 주기</span><span class="sxs-lookup"><span data-stu-id="46281-255">Component lifecycle</span></span>

<span data-ttu-id="46281-256">ASP.NET Web Forms 프레임워크에는 모듈, 페이지 및 컨트롤에 대해 잘 정의된 수명 주기 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="46281-257">예를 들어 다음 컨트롤은 `Init`에 `Load`대한 이벤트 처리기를 구현합니다. `UnLoad`</span><span class="sxs-lookup"><span data-stu-id="46281-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="46281-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="46281-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="46281-259">Blazor 구성 요소에는 잘 정의된 수명 주기도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="46281-260">구성 요소의 수명 주기를 사용하여 구성 요소 상태를 초기화하고 고급 구성 요소 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="46281-261">Blazor의 모든 구성 요소 수명 주기 메서드에는 동기 버전과 비동기 버전이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="46281-262">구성 요소 렌더링은 동기입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-262">Component rendering is synchronous.</span></span> <span data-ttu-id="46281-263">구성 요소 렌더링의 일부로 비동기 논리를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="46281-264">모든 비동기 논리는 `async` 수명 주기 메서드의 일부로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="46281-265">초기화</span><span class="sxs-lookup"><span data-stu-id="46281-265">OnInitialized</span></span>

<span data-ttu-id="46281-266">`OnInitialized` 및 `OnInitializedAsync` 메서드는 구성 요소를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="46281-267">구성 요소는 일반적으로 처음 렌더링된 후 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="46281-268">구성 요소가 초기화되면 결국 삭제되기 전에 여러 번 렌더링될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="46281-269">이 `OnInitialized` 메서드는 ASP.NET `Page_Load` 웹 양식 페이지 및 컨트롤의 이벤트와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="46281-270">온매개 변수 집합</span><span class="sxs-lookup"><span data-stu-id="46281-270">OnParametersSet</span></span>

<span data-ttu-id="46281-271">및 `OnParametersSet` `OnParametersSetAsync` 메서드는 구성 요소가 부모로부터 매개 변수를 수신하고 값이 속성에 할당될 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="46281-272">이러한 메서드는 구성 요소 초기화 후 및 구성 요소가 *렌더링될 때마다 실행됩니다.*</span><span class="sxs-lookup"><span data-stu-id="46281-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="46281-273">온애프터렌더</span><span class="sxs-lookup"><span data-stu-id="46281-273">OnAfterRender</span></span>

<span data-ttu-id="46281-274">`OnAfterRender` 및 `OnAfterRenderAsync` 메서드는 구성 요소 렌더링이 완료된 후 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="46281-275">요소 및 구성 요소 참조는 이 시점에서 채워집니다(아래 이러한 개념에 대한 자세한 내용은 참조).</span><span class="sxs-lookup"><span data-stu-id="46281-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="46281-276">이 시점에서 브라우저와의 상호 작용이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="46281-277">DOM 및 JavaScript 실행과의 상호 작용은 안전하게 이루어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

```csharp
protected override void OnAfterRender(bool firstRender)
{
    if (firstRender)
    {
        ...
    }
}
protected override async Task OnAfterRenderAsync(bool firstRender)
{
    if (firstRender)
    {
        await ...
    }
}
```

<span data-ttu-id="46281-278">`OnAfterRender``OnAfterRenderAsync` *서버에서 사전 렌더링할 때 호출되지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="46281-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="46281-279">`firstRender` 매개 변수는 `true` 구성 요소가 처음 렌더링될 때입니다. 그렇지 않으면 해당 `false`값은 .</span><span class="sxs-lookup"><span data-stu-id="46281-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="46281-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="46281-280">IDisposable</span></span>

<span data-ttu-id="46281-281">Blazor 구성 `IDisposable` 요소는 UI에서 구성 요소를 제거할 때 리소스를 삭제하도록 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="46281-282">Razor 구성 요소는 `IDispose` 지시문을 `@implements` 사용하여 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

```razor
@using System
@implements IDisposable

...

@code {
    public void Dispose()
    {
        ...
    }
}
```

## <a name="capture-component-references"></a><span data-ttu-id="46281-283">구성 요소 참조 캡처</span><span class="sxs-lookup"><span data-stu-id="46281-283">Capture component references</span></span>

<span data-ttu-id="46281-284">ASP.NET Web Forms에서는 코드에서 해당 ID를 참조하여 컨트롤 인스턴스를 직접 조작하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="46281-285">Blazor에서는 훨씬 덜 일반적이지만 구성 요소에 대한 참조를 캡처하고 조작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="46281-286">Blazor에서 구성 요소 참조를 `@ref` 캡처하려면 지시문 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="46281-287">특성값은 설정된 필드의 이름과 참조된 구성 요소와 동일한 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

```razor
<MyLoginDialog @ref="loginDialog" ... />

@code {
    MyLoginDialog loginDialog;

    void OnSomething()
    {
        loginDialog.Show();
    }
}
```

<span data-ttu-id="46281-288">상위 구성 요소가 렌더링되면 필드는 자식 구성 요소 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="46281-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="46281-289">그런 다음 구성 요소 인스턴스를 호출하거나 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="46281-290">구성 요소 참조를 사용하여 구성 요소 상태를 직접 조작하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="46281-291">이렇게 하면 올바른 시간에 구성 요소가 자동으로 렌더링되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="46281-292">요소 참조 캡처</span><span class="sxs-lookup"><span data-stu-id="46281-292">Capture element references</span></span>

<span data-ttu-id="46281-293">Blazor 구성 요소는 요소에 대한 참조를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="46281-294">ASP.NET 웹 양식의 HTML 서버 컨트롤과 달리 Blazor의 요소 참조를 사용하여 DOM을 직접 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="46281-295">Blazor는 DOM 디핑 알고리즘을 사용하여 대부분의 DOM 상호 작용을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="46281-296">블레이저에서 캡처된 요소 참조는 불투명합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="46281-297">그러나 JavaScript 인터오프 호출에서 특정 요소 참조를 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="46281-298">자바 스크립트 interop에 대한 자세한 내용은 [ASP.NET 코어 블레이저 자바 스크립트 인터옵을](/aspnet/core/blazor/javascript-interop)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46281-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="46281-299">템플릿 기반 구성 요소</span><span class="sxs-lookup"><span data-stu-id="46281-299">Templated components</span></span>

<span data-ttu-id="46281-300">ASP.NET 웹 양식에서 *템플릿 컨트롤을*만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="46281-301">템플릿 컨트롤을 사용하면 개발자가 컨테이너 컨트롤을 렌더링하는 데 사용되는 HTML 의 일부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="46281-302">템플릿 서버 컨트롤을 빌드하는 방법은 복잡하지만 사용자 사용자 지정 가능한 방식으로 데이터를 렌더링하기 위한 강력한 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="46281-303">템플릿 컨트롤의 예는 `Repeater` `DataList`다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="46281-304">Blazor 구성 요소는 형식 `RenderFragment` 또는 `RenderFragment<T>`의 구성 요소 매개 변수를 정의하여 템플릿을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="46281-305">A는 `RenderFragment` 구성 요소에서 렌더링할 수 있는 Razor 태그 의 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46281-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="46281-306">A는 `RenderFragment<T>` 렌더링 조각이 렌더링될 때 지정할 수 있는 매개 변수를 취하는 Razor 태그의 청크입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="46281-307">하위 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="46281-307">Child content</span></span>

<span data-ttu-id="46281-308">Blazor 구성 요소는 자식 `RenderFragment` 콘텐츠를 a로 캡처하고 해당 콘텐츠를 구성 요소 렌더링의 일부로 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="46281-309">자식 콘텐츠를 캡처하려면 형식의 `RenderFragment` 구성 요소 `ChildContent`매개 변수를 정의하고 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="46281-310">*차일드콘텐츠컴포넌트.면도기*</span><span class="sxs-lookup"><span data-stu-id="46281-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="46281-311">그런 다음 부모 구성 요소는 일반 Razor 구문을 사용하여 자식 콘텐츠를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="46281-312">템플릿 매개 변수</span><span class="sxs-lookup"><span data-stu-id="46281-312">Template parameters</span></span>

<span data-ttu-id="46281-313">템플릿 블레이저 구성 요소는 형식 `RenderFragment` 또는 `RenderFragment<T>`의 여러 구성 요소 매개 변수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="46281-314">a의 `RenderFragment<T>` 매개 변수는 호출될 때 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="46281-315">구성 요소에 대한 제네릭 형식 `@typeparam` 매개 변수를 지정하려면 Razor 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="46281-316">*심플리스트뷰.면도기*</span><span class="sxs-lookup"><span data-stu-id="46281-316">*SimpleListView.razor*</span></span>

```razor
@typeparam TItem

@Heading

<ul>
@foreach (var item in Items)
{
    <li>@ItemTemplate(item)</li>
}
</ul>

@code {
    [Parameter]
    public RenderFragment Heading { get; set; }

    [Parameter]
    public RenderFragment<TItem> ItemTemplate { get; set; }

    [Parameter]
    public IEnumerable<TItem> Items { get; set; }
}
```

<span data-ttu-id="46281-317">템플릿 구성 요소를 사용하는 경우 매개 변수의 이름과 일치하는 자식 요소를 사용하여 템플릿 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="46281-318">요소로 전달 `RenderFragment<T>` 된 형식의 구성 요소 `context`인수에는 암시적 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="46281-319">자식 요소의 특성을 사용하여 `Context` 이 구현 매개 변수의 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="46281-320">모든 제네릭 형식 매개 변수는 형식 매개 변수의 이름과 일치하는 특성을 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="46281-321">가능한 경우 형식 매개 변수가 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Content="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="46281-322">이 구성 요소의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="46281-323">코드 숨김</span><span class="sxs-lookup"><span data-stu-id="46281-323">Code-behind</span></span>

<span data-ttu-id="46281-324">Blazor 구성 요소는 일반적으로 단일 *.razor* 파일에서 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="46281-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="46281-325">그러나 코드 숨김 파일을 사용하여 코드와 태그를 분리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="46281-326">구성 요소 파일을 사용하려면 구성 요소 파일의 파일 이름과 일치하지만 *.cs* 확장자(Counter.razor.cs)가 추가된 C# 파일을 추가합니다.*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="46281-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="46281-327">C# 파일을 사용하여 구성요소에 대한 기본 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="46281-328">기본 클래스의 이름을 원하는 대로 지정할 수 있지만 클래스의 이름을 구성 요소 클래스와 동일하지만 확장이 추가된 경우()를 `Base` `CounterBase`지정하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="46281-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="46281-329">구성 요소 기반 클래스도 `ComponentBase`에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="46281-330">그런 다음 Razor 구성 요소 `@inherits` 파일에서 지시문을 추가하여 구성`@inherits CounterBase`요소()에 대한 기본 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="46281-331">*카운터.면도기*</span><span class="sxs-lookup"><span data-stu-id="46281-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="46281-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="46281-332">*Counter.razor.cs*</span></span>

```csharp
public class CounterBase : ComponentBase
{
    protected int currentCount = 0;

    protected void IncrementCount()
    {
        currentCount++;
    }
}
```

<span data-ttu-id="46281-333">기본 클래스에서 구성 요소 멤버의 가시성은 `protected` 구성 `public` 요소 클래스에 표시되거나 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46281-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46281-334">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="46281-334">Additional resources</span></span>

<span data-ttu-id="46281-335">앞의 Blazor 구성 요소의 모든 측면의 철저 한 치료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46281-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="46281-336">[핵심 면도기 구성 요소를 만들고 사용하는](/aspnet/core/blazor/components)방법에 ASP.NET 자세한 내용은 Blazor 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46281-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="46281-337">[이전](app-startup.md)
>[다음](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="46281-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
