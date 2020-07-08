---
title: Blazor를 사용 하 여 재사용 가능한 UI 구성 요소 빌드
description: Blazor를 사용 하 여 재사용 가능한 UI 구성 요소를 빌드하고 ASP.NET Web Forms 컨트롤과 비교 하는 방법을 알아봅니다.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: f6528b1e68b49b6ee3949baca166f4806448718b
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051454"
---
# <a name="build-reusable-ui-components-with-blazor"></a><span data-ttu-id="2c787-103">Blazor를 사용 하 여 재사용 가능한 UI 구성 요소 빌드</span><span class="sxs-lookup"><span data-stu-id="2c787-103">Build reusable UI components with Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="2c787-104">ASP.NET Web Forms에 대 한 멋진 사항 중 하나는 다시 사용할 수 있는 ui (사용자 인터페이스) 코드를 다시 사용할 수 있는 UI 컨트롤에 캡슐화 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-104">One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls.</span></span> <span data-ttu-id="2c787-105">*.Ascx* 파일을 사용 하 여 태그에서 사용자 지정 사용자 정의 컨트롤을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-105">Custom user controls can be defined in markup using *.ascx* files.</span></span> <span data-ttu-id="2c787-106">전체 디자이너 지원으로 코드에서 정교한 서버 컨트롤을 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-106">You can also build elaborate server controls in code with full designer support.</span></span>

<span data-ttu-id="2c787-107">Blazor는 *구성 요소*를 통한 UI 캡슐화도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-107">Blazor also supports UI encapsulation through *components*.</span></span> <span data-ttu-id="2c787-108">구성 요소:</span><span class="sxs-lookup"><span data-stu-id="2c787-108">A component:</span></span>

- <span data-ttu-id="2c787-109">는 자체 포함 UI의 청크입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-109">Is a self-contained chunk of UI.</span></span>
- <span data-ttu-id="2c787-110">자체 상태 및 렌더링 논리를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-110">Maintains its own state and rendering logic.</span></span>
- <span data-ttu-id="2c787-111">는 UI 이벤트 처리기를 정의 하 고, 입력 데이터에 바인딩하고, 자체 수명 주기를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-111">Can define UI event handlers, bind to input data, and manage its own lifecycle.</span></span>
- <span data-ttu-id="2c787-112">는 일반적으로 Razor 구문를 사용 하 여 *razor* 파일에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-112">Is typically defined in a *.razor* file using Razor syntax.</span></span>

## <a name="an-introduction-to-razor"></a><span data-ttu-id="2c787-113">Razor 소개</span><span class="sxs-lookup"><span data-stu-id="2c787-113">An introduction to Razor</span></span>

<span data-ttu-id="2c787-114">Razor는 HTML 및 c #을 기반으로 하는 간단한 태그 템플릿 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-114">Razor is a light-weight markup templating language based on HTML and C#.</span></span> <span data-ttu-id="2c787-115">Razor를 사용 하면 태그와 c # 코드 간을 원활 하 게 전환 하 여 구성 요소 렌더링 논리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-115">With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic.</span></span> <span data-ttu-id="2c787-116">*Razor* 파일이 컴파일되면 렌더링 논리가 .net 클래스에서 구조화 된 방식으로 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-116">When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class.</span></span> <span data-ttu-id="2c787-117">컴파일된 클래스의 이름은 *razor* 파일 이름에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-117">The name of the compiled class is taken from the *.razor* file name.</span></span> <span data-ttu-id="2c787-118">네임 스페이스는 프로젝트 및 폴더 경로에 대 한 기본 네임 스페이스에서 가져온 것입니다. 또는 지시문을 사용 하 여 네임 스페이스를 명시적으로 지정할 수 있습니다 `@namespace` (아래 Razor 지시문에 추가).</span><span class="sxs-lookup"><span data-stu-id="2c787-118">The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).</span></span>

<span data-ttu-id="2c787-119">구성 요소의 렌더링 논리는 c #을 사용 하 여 동적 논리가 추가 된 일반 HTML 태그를 사용 하 여 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-119">A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#.</span></span> <span data-ttu-id="2c787-120">`@`문자는 c #으로 전환 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-120">The `@` character is used to transition to C#.</span></span> <span data-ttu-id="2c787-121">Razor는 일반적으로 HTML로 다시 전환 하는 경우를 파악 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-121">Razor is typically smart about figuring out when you've switched back to HTML.</span></span> <span data-ttu-id="2c787-122">예를 들어 다음 구성 요소는 `<p>` 현재 시간을 사용 하 여 태그를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-122">For example, the following component renders a `<p>` tag with the current time:</span></span>

```razor
<p>@DateTime.Now</p>
```

<span data-ttu-id="2c787-123">C # 식의 시작과 끝을 명시적으로 지정 하려면 괄호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-123">To explicitly specify the beginning and ending of a C# expression, use parentheses:</span></span>

```razor
<p>@(DateTime.Now)</p>
```

<span data-ttu-id="2c787-124">Razor를 사용 하면 렌더링 논리에서 c # 제어 흐름을 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-124">Razor also makes it easy to use C# control flow in your rendering logic.</span></span> <span data-ttu-id="2c787-125">예를 들어 다음과 같이 HTML을 조건부로 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-125">For example, you can conditionally render some HTML like this:</span></span>

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

<span data-ttu-id="2c787-126">또는 다음과 같은 일반적인 c # 루프를 사용 하 여 항목 목록을 생성할 수 있습니다 `foreach` .</span><span class="sxs-lookup"><span data-stu-id="2c787-126">Or you can generate a list of items using a normal C# `foreach` loop like this:</span></span>

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

<span data-ttu-id="2c787-127">ASP.NET Web Forms 지시문과 같은 razor 지시문은 Razor 구성 요소가 컴파일되는 방법의 다양 한 측면을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-127">Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled.</span></span> <span data-ttu-id="2c787-128">구성 요소의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-128">Examples include the component's:</span></span>

- <span data-ttu-id="2c787-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2c787-129">Namespace</span></span>
- <span data-ttu-id="2c787-130">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="2c787-130">Base class</span></span>
- <span data-ttu-id="2c787-131">구현 된 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c787-131">Implemented interfaces</span></span>
- <span data-ttu-id="2c787-132">제네릭 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c787-132">Generic parameters</span></span>
- <span data-ttu-id="2c787-133">가져온 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2c787-133">Imported namespaces</span></span>
- <span data-ttu-id="2c787-134">경로</span><span class="sxs-lookup"><span data-stu-id="2c787-134">Routes</span></span>

<span data-ttu-id="2c787-135">Razor 지시문은 문자로 시작 `@` 하 고 일반적으로 파일의 시작 부분에서 새 줄의 시작 부분에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-135">Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file.</span></span> <span data-ttu-id="2c787-136">예를 들어 `@namespace` 지시문은 구성 요소의 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-136">For example, the `@namespace` directive defines the component's namespace:</span></span>

```razor
@namespace MyComponentNamespace
```

<span data-ttu-id="2c787-137">다음 표에서는 Blazor에서 사용 되는 다양 한 Razor 지시문과 해당 ASP.NET Web Forms 해당 하는 경우에 대해 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-137">The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.</span></span>

|<span data-ttu-id="2c787-138">지시문</span><span class="sxs-lookup"><span data-stu-id="2c787-138">Directive</span></span>    |<span data-ttu-id="2c787-139">설명</span><span class="sxs-lookup"><span data-stu-id="2c787-139">Description</span></span>|<span data-ttu-id="2c787-140">예제</span><span class="sxs-lookup"><span data-stu-id="2c787-140">Example</span></span>|<span data-ttu-id="2c787-141">Web Forms 동일</span><span class="sxs-lookup"><span data-stu-id="2c787-141">Web Forms equivalent</span></span>|
|-------------|-----------|-------|--------------------|
|`@attribute` |<span data-ttu-id="2c787-142">구성 요소에 클래스 수준 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-142">Adds a class-level attribute to the component</span></span>|`@attribute [Authorize]`|<span data-ttu-id="2c787-143">없음</span><span class="sxs-lookup"><span data-stu-id="2c787-143">None</span></span>|
|`@code`      |<span data-ttu-id="2c787-144">구성 요소에 클래스 멤버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-144">Adds class members to the component</span></span>|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|<span data-ttu-id="2c787-145">지정 된 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-145">Implements the specified interface</span></span>|`@implements IDisposable`|<span data-ttu-id="2c787-146">코드 숨김 사용</span><span class="sxs-lookup"><span data-stu-id="2c787-146">Use code-behind</span></span>|
|`@inherits`  |<span data-ttu-id="2c787-147">지정 된 기본 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-147">Inherits from the specified base class</span></span>|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |<span data-ttu-id="2c787-148">구성 요소에 서비스를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-148">Injects a service into the component</span></span>|`@inject IJSRuntime JS`|<span data-ttu-id="2c787-149">없음</span><span class="sxs-lookup"><span data-stu-id="2c787-149">None</span></span>|
|`@layout`    |<span data-ttu-id="2c787-150">구성 요소에 대 한 레이아웃 구성 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-150">Specifies a layout component for the component</span></span>|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |<span data-ttu-id="2c787-151">구성 요소에 대 한 네임 스페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-151">Sets the namespace for the component</span></span>|`@namespace MyNamespace`|<span data-ttu-id="2c787-152">없음</span><span class="sxs-lookup"><span data-stu-id="2c787-152">None</span></span>|
|`@page`      |<span data-ttu-id="2c787-153">구성 요소의 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-153">Specifies the route for the component</span></span>|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |<span data-ttu-id="2c787-154">구성 요소에 대 한 제네릭 형식 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-154">Specifies a generic type parameter for the component</span></span>|`@typeparam TItem`|<span data-ttu-id="2c787-155">코드 숨김 사용</span><span class="sxs-lookup"><span data-stu-id="2c787-155">Use code-behind</span></span>|
|`@using`     |<span data-ttu-id="2c787-156">범위에 가져올 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-156">Specifies a namespace to bring into scope</span></span>|`@using MyComponentNamespace`|<span data-ttu-id="2c787-157">*web.config* 에서 네임 스페이스 추가</span><span class="sxs-lookup"><span data-stu-id="2c787-157">Add namespace in *web.config*</span></span>|

<span data-ttu-id="2c787-158">또한 Razor 구성 요소는 요소에 대 한 *지시문 특성* 을 광범위 하 게 사용 하 여 구성 요소가 컴파일되는 방법 (이벤트 처리, 데이터 바인딩, 구성 요소 & 요소 참조 등)의 다양 한 측면을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-158">Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on).</span></span> <span data-ttu-id="2c787-159">지시문 특성은 모두 괄호 안의 값이 선택 사항인 일반적인 제네릭 구문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-159">Directive attributes all follow a common generic syntax where the values in parenthesis are optional:</span></span>

```razor
@directive(-suffix(:name))(="value")
```

<span data-ttu-id="2c787-160">다음 표에서는 Blazor에 사용 되는 Razor 지시문에 대 한 다양 한 특성을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-160">The following table summarizes the various attributes for Razor directives used in Blazor.</span></span>

|<span data-ttu-id="2c787-161">특성</span><span class="sxs-lookup"><span data-stu-id="2c787-161">Attribute</span></span>    |<span data-ttu-id="2c787-162">Description</span><span class="sxs-lookup"><span data-stu-id="2c787-162">Description</span></span>|<span data-ttu-id="2c787-163">예제</span><span class="sxs-lookup"><span data-stu-id="2c787-163">Example</span></span>|
|-------------|-----------|-------|
|`@attributes`|<span data-ttu-id="2c787-164">특성 사전을 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-164">Renders a dictionary of attributes</span></span>|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |<span data-ttu-id="2c787-165">양방향 데이터 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-165">Creates a two-way data binding</span></span>    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |<span data-ttu-id="2c787-166">지정 된 이벤트에 대 한 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-166">Adds an event handler for the specified event</span></span>|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |<span data-ttu-id="2c787-167">컬렉션의 요소를 유지 하기 위해 diff 알고리즘에서 사용할 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-167">Specifies a key to be used by the diffing algorithm for preserving elements in a collection</span></span>|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |<span data-ttu-id="2c787-168">구성 요소 또는 HTML 요소에 대 한 참조를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-168">Captures a reference to the component or HTML element</span></span>|`<MyDialog @ref="myDialog" />`|

<span data-ttu-id="2c787-169">Blazor (,, 등)에서 사용 하는 다양 한 지시문 특성은 `@onclick` `@bind` `@ref` 아래 단원 및 이후 단원에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-169">The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.</span></span>

<span data-ttu-id="2c787-170">*.Aspx* 및 *.ascx* 파일에 사용 되는 대부분의 구문에는 Razor의 병렬 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-170">Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor.</span></span> <span data-ttu-id="2c787-171">다음은 ASP.NET Web Forms 및 Razor의 구문에 대 한 간단한 비교입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-171">Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.</span></span>

|<span data-ttu-id="2c787-172">기능</span><span class="sxs-lookup"><span data-stu-id="2c787-172">Feature</span></span>                      |<span data-ttu-id="2c787-173">Web Forms</span><span class="sxs-lookup"><span data-stu-id="2c787-173">Web Forms</span></span>           |<span data-ttu-id="2c787-174">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c787-174">Syntax</span></span>               |<span data-ttu-id="2c787-175">Razor</span><span class="sxs-lookup"><span data-stu-id="2c787-175">Razor</span></span>         |<span data-ttu-id="2c787-176">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c787-176">Syntax</span></span> |
|-----------------------------|--------------------|---------------------|--------------|-------|
|<span data-ttu-id="2c787-177">지시문</span><span class="sxs-lookup"><span data-stu-id="2c787-177">Directives</span></span>                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|<span data-ttu-id="2c787-178">코드 블록</span><span class="sxs-lookup"><span data-stu-id="2c787-178">Code blocks</span></span>                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|<span data-ttu-id="2c787-179">식</span><span class="sxs-lookup"><span data-stu-id="2c787-179">Expressions</span></span><br><span data-ttu-id="2c787-180">(HTML 인코딩)</span><span class="sxs-lookup"><span data-stu-id="2c787-180">(HTML-encoded)</span></span>|`<%: %>`            |`<%:DateTime.Now %>` |<span data-ttu-id="2c787-181">명시적`@`</span><span class="sxs-lookup"><span data-stu-id="2c787-181">Implicit: `@`</span></span><br><span data-ttu-id="2c787-182">뚜렷한`@()`</span><span class="sxs-lookup"><span data-stu-id="2c787-182">Explicit: `@()`</span></span>|`@DateTime.Now`<br>`@(DateTime.Now)`|
|<span data-ttu-id="2c787-183">의견</span><span class="sxs-lookup"><span data-stu-id="2c787-183">Comments</span></span>                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|<span data-ttu-id="2c787-184">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="2c787-184">Data binding</span></span>                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

<span data-ttu-id="2c787-185">Razor 구성 요소 클래스에 멤버를 추가 하려면 지시문을 사용 `@code` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-185">To add members to the Razor component class, use the `@code` directive.</span></span> <span data-ttu-id="2c787-186">이 기법은 `<script runat="server">...</script>` ASP.NET Web Forms 사용자 정의 컨트롤 또는 페이지에서 블록을 사용 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-186">This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.</span></span>

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

<span data-ttu-id="2c787-187">Razor는 c #을 기반으로 하기 때문에 c # 프로젝트 (*.csproj*) 내에서 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-187">Because Razor is based on C#, it must be compiled from within a C# project (*.csproj*).</span></span> <span data-ttu-id="2c787-188">Visual Basic 프로젝트 (*.vbproj*)에서 *razor* 파일을 컴파일할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-188">You can't compile *.razor* files from a Visual Basic project (*.vbproj*).</span></span> <span data-ttu-id="2c787-189">Blazor 프로젝트에서 Visual Basic 프로젝트를 계속 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-189">You can still reference Visual Basic projects from your Blazor project.</span></span> <span data-ttu-id="2c787-190">반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-190">The opposite is true too.</span></span>

<span data-ttu-id="2c787-191">전체 Razor 구문 참조는 [ASP.NET Core에 대 한 Razor 구문 참조](/aspnet/core/mvc/views/razor)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c787-191">For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).</span></span>

## <a name="use-components"></a><span data-ttu-id="2c787-192">구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="2c787-192">Use components</span></span>

<span data-ttu-id="2c787-193">일반 HTML 외에도 구성 요소는 렌더링 논리의 일부로 다른 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-193">Aside from normal HTML, components can also use other components as part of their rendering logic.</span></span> <span data-ttu-id="2c787-194">Razor에서 구성 요소를 사용 하는 구문은 ASP.NET Web Forms 앱에서 사용자 정의 컨트롤을 사용 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-194">The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app.</span></span> <span data-ttu-id="2c787-195">구성 요소는 구성 요소의 형식 이름과 일치 하는 요소 태그를 사용 하 여 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-195">Components are specified using an element tag that matches the type name of the component.</span></span> <span data-ttu-id="2c787-196">예를 들어 `Counter` 다음과 같은 구성 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-196">For example, you can add a `Counter` component like this:</span></span>

```razor
<Counter />
```

<span data-ttu-id="2c787-197">ASP.NET Web Forms와 달리 Blazor의 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-197">Unlike ASP.NET Web Forms, components in Blazor:</span></span>

- <span data-ttu-id="2c787-198">요소 접두사를 사용 하지 않습니다 (예: `asp:` ).</span><span class="sxs-lookup"><span data-stu-id="2c787-198">Don't use an element prefix (for example, `asp:`).</span></span>
- <span data-ttu-id="2c787-199">페이지 또는 *web.config*에서 등록 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-199">Don't require registration on the page or in the *web.config*.</span></span>

<span data-ttu-id="2c787-200">.NET 형식 처럼 Razor 구성 요소는 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-200">Think of Razor components like you would .NET types, because that's exactly what they are.</span></span> <span data-ttu-id="2c787-201">구성 요소가 포함 된 어셈블리를 참조 하는 경우에는 구성 요소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-201">If the assembly containing the component is referenced, then the component is available for use.</span></span> <span data-ttu-id="2c787-202">구성 요소의 네임 스페이스를 범위로 가져오려면 지시문을 적용 합니다 `@using` .</span><span class="sxs-lookup"><span data-stu-id="2c787-202">To bring the component's namespace into scope, apply the `@using` directive:</span></span>

```razor
@using MyComponentLib

<Counter />
```

<span data-ttu-id="2c787-203">기본 Blazor 프로젝트에서 볼 수 있듯이 `@using` 지시문을 *_Imports razor* 파일에 배치 하 여 동일한 디렉터리와 하위 디렉터리에 있는 모든 *razor* 파일로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-203">As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.</span></span>

<span data-ttu-id="2c787-204">구성 요소에 대 한 네임 스페이스가 범위에 없는 경우 c #에서 가능 하므로 전체 형식 이름을 사용 하 여 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-204">If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:</span></span>

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a><span data-ttu-id="2c787-205">구성 요소 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c787-205">Component parameters</span></span>

<span data-ttu-id="2c787-206">ASP.NET Web Forms에서 공용 속성을 사용 하 여 매개 변수 및 데이터를 컨트롤에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-206">In ASP.NET Web Forms, you can flow parameters and data to controls using public properties.</span></span> <span data-ttu-id="2c787-207">이러한 속성은 특성을 사용 하 여 태그에서 설정 하거나 코드에서 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-207">These properties can be set in markup using attributes or set directly in code.</span></span> <span data-ttu-id="2c787-208">구성 요소 속성은 `[Parameter]` 구성 요소 매개 변수로 간주할 특성으로도 표시 되어야 하지만 Blazor 구성 요소는 비슷한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-208">Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.</span></span>

<span data-ttu-id="2c787-209">다음 `Counter` 구성 요소는 단추를 클릭할 때마다 `IncrementAmount` 가 증가 해야 하는 양을 지정 하는 데 사용할 수 있는 이라는 구성 요소 매개 변수를 정의 합니다 `Counter` .</span><span class="sxs-lookup"><span data-stu-id="2c787-209">The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.</span></span>

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

<span data-ttu-id="2c787-210">Blazor에서 구성 요소 매개 변수를 지정 하려면 ASP.NET Web Forms에서와 같이 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-210">To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:</span></span>

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a><span data-ttu-id="2c787-211">이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="2c787-211">Event handlers</span></span>

<span data-ttu-id="2c787-212">ASP.NET Web Forms 및 Blazor 모두 UI 이벤트를 처리 하기 위한 이벤트 기반 프로그래밍 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-212">Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events.</span></span> <span data-ttu-id="2c787-213">이러한 이벤트의 예로는 단추 클릭 및 텍스트 입력이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-213">Examples of such events include button clicks and text input.</span></span> <span data-ttu-id="2c787-214">ASP.NET Web Forms에서는 HTML 서버 컨트롤을 사용 하 여 DOM에서 노출 하는 UI 이벤트를 처리 하거나 웹 서버 컨트롤에서 노출 하는 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-214">In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls.</span></span> <span data-ttu-id="2c787-215">이벤트는 폼 다시 게시 요청을 통해 서버에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-215">The events are surfaced on the server through form post-back requests.</span></span> <span data-ttu-id="2c787-216">다음 Web Forms 단추 클릭 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-216">Consider the following Web Forms button click example:</span></span>

<span data-ttu-id="2c787-217">*Counter. .ascx*</span><span class="sxs-lookup"><span data-stu-id="2c787-217">*Counter.ascx*</span></span>

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

<span data-ttu-id="2c787-218">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="2c787-218">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

<span data-ttu-id="2c787-219">Blazor에서는 폼의 지시문 특성을 사용 하 여 DOM UI 이벤트에 대 한 처리기를 직접 등록할 수 있습니다 `@on{event}` .</span><span class="sxs-lookup"><span data-stu-id="2c787-219">In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`.</span></span> <span data-ttu-id="2c787-220">`{event}`자리 표시자는 이벤트의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-220">The `{event}` placeholder represents the name of the event.</span></span> <span data-ttu-id="2c787-221">예를 들어 다음과 같이 단추 클릭을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-221">For example, you can listen for button clicks like this:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

<span data-ttu-id="2c787-222">이벤트 처리기는 선택적 이벤트 관련 인수를 수락 하 여 이벤트에 대 한 자세한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-222">Event handlers can accept an optional, event-specific argument to provide more information about the event.</span></span> <span data-ttu-id="2c787-223">예를 들어 마우스 이벤트는 인수를 사용할 수 `MouseEventArgs` 있지만 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-223">For example, mouse events can take a `MouseEventArgs` argument, but it isn't required.</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

<span data-ttu-id="2c787-224">이벤트 처리기에 대 한 메서드 그룹을 참조 하는 대신 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-224">Instead of referring to a method group for an event handler, you can use a lambda expression.</span></span> <span data-ttu-id="2c787-225">람다 식을 사용 하면 다른 범위 내 값을 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-225">A lambda expression allows you to close over other in-scope values.</span></span>

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

<span data-ttu-id="2c787-226">이벤트 처리기는 동기적 또는 비동기적으로 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-226">Event handlers can execute synchronously or asynchronously.</span></span> <span data-ttu-id="2c787-227">예를 들어 다음 `OnClick` 이벤트 처리기는 비동기적으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-227">For example, the following `OnClick` event handler executes asynchronously:</span></span>

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

<span data-ttu-id="2c787-228">이벤트가 처리 된 후 구성 요소 상태 변경을 고려 하 여 구성 요소가 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-228">After an event is handled, the component is rendered to account for any component state changes.</span></span> <span data-ttu-id="2c787-229">비동기 이벤트 처리기를 사용 하면 처리기 실행이 완료 된 직후에 구성 요소가 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-229">With asynchronous event handlers, the component is rendered immediately after the handler execution completes.</span></span> <span data-ttu-id="2c787-230">비동기 작업이 완료 되 면 구성 요소가 *다시* 렌더링 됩니다 `Task` .</span><span class="sxs-lookup"><span data-stu-id="2c787-230">The component is rendered *again* after the asynchronous `Task` completes.</span></span> <span data-ttu-id="2c787-231">비동기 실행 모드는 비동기 작업이 진행 되는 동안 적절 한 UI를 렌더링할 수 있는 기회를 제공 `Task` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-231">This asynchronous execution mode provides an opportunity to render some appropriate UI while the asynchronous `Task` is still in progress.</span></span>

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

<span data-ttu-id="2c787-232">구성 요소는 형식의 구성 요소 매개 변수를 정의 하 여 자체 이벤트를 정의할 수도 있습니다 `EventCallback<TValue>` .</span><span class="sxs-lookup"><span data-stu-id="2c787-232">Components can also define their own events by defining a component parameter of type `EventCallback<TValue>`.</span></span> <span data-ttu-id="2c787-233">이벤트 콜백은 선택적 인수, 동기 또는 비동기, 메서드 그룹 또는 람다 식 등 DOM UI 이벤트 처리기의 모든 변형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-233">Event callbacks support all the variations of DOM UI event handlers: optional arguments, synchronous or asynchronous, method groups, or lambda expressions.</span></span>

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a><span data-ttu-id="2c787-234">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="2c787-234">Data binding</span></span>

<span data-ttu-id="2c787-235">Blazor는 UI 구성 요소에서 구성 요소의 상태에 데이터를 바인딩하는 간단한 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-235">Blazor provides a simple mechanism to bind data from a UI component to the component's state.</span></span> <span data-ttu-id="2c787-236">이 방식은 데이터 소스에서 UI 컨트롤로 데이터를 바인딩하는 ASP.NET Web Forms의 기능과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-236">This approach differs from the features in ASP.NET Web Forms for binding data from data sources to UI controls.</span></span> <span data-ttu-id="2c787-237">데이터 처리 섹션에서 다양 한 데이터 원본의 데이터를 처리 [하](data.md) 는 방법을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-237">We'll cover handling data from different data sources in the [Dealing with data](data.md) section.</span></span>

<span data-ttu-id="2c787-238">UI 구성 요소에서 구성 요소의 상태로 양방향 데이터 바인딩을 만들려면 `@bind` 지시문 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-238">To create a two-way data binding from a UI component to the component's state, use the `@bind` directive attribute.</span></span> <span data-ttu-id="2c787-239">다음 예제에서 확인란의 값은 필드에 바인딩됩니다 `isChecked` .</span><span class="sxs-lookup"><span data-stu-id="2c787-239">In the following example, the value of the check box is bound to the `isChecked` field.</span></span>

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

<span data-ttu-id="2c787-240">구성 요소가 렌더링 되 면 확인란의 값은 필드의 값으로 설정 됩니다 `isChecked` .</span><span class="sxs-lookup"><span data-stu-id="2c787-240">When the component is rendered, the value of the checkbox is set to the value of the `isChecked` field.</span></span> <span data-ttu-id="2c787-241">사용자가 확인란을 설정/해제 하면 `onchange` 이벤트가 발생 하 고 `isChecked` 필드가 새 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-241">When the user toggles the checkbox, the `onchange` event is fired and the `isChecked` field is set to the new value.</span></span> <span data-ttu-id="2c787-242">`@bind`이 경우 구문은 다음 태그와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-242">The `@bind` syntax in this case is equivalent to the following markup:</span></span>

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

<span data-ttu-id="2c787-243">바인딩에 사용 되는 이벤트를 변경 하려면 특성을 사용 `@bind:event` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-243">To change the event used for the bind, use the `@bind:event` attribute.</span></span>

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

<span data-ttu-id="2c787-244">구성 요소는 해당 매개 변수에 대 한 데이터 바인딩을 지원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-244">Components can also support data binding to their parameters.</span></span> <span data-ttu-id="2c787-245">데이터 바인딩하려면 바인딩 가능 매개 변수와 동일한 이름을 사용 하 여 이벤트 콜백 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-245">To data bind, define an event callback parameter with the same name as the bindable parameter.</span></span> <span data-ttu-id="2c787-246">이름에 "Changed" 접미사가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-246">The "Changed" suffix is added to the name.</span></span>

<span data-ttu-id="2c787-247">*PasswordBox razor*</span><span class="sxs-lookup"><span data-stu-id="2c787-247">*PasswordBox.razor*</span></span>

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

<span data-ttu-id="2c787-248">데이터 바인딩을 기본 UI 요소에 연결 하려면 특성을 사용 하는 대신 값을 설정 하 고 UI 요소에서 직접 이벤트를 처리 합니다 `@bind` .</span><span class="sxs-lookup"><span data-stu-id="2c787-248">To chain a data binding to an underlying UI element, set the value and handle the event directly on the UI element instead of using the `@bind` attribute.</span></span>

<span data-ttu-id="2c787-249">구성 요소 매개 변수에 바인딩하려면 특성을 사용 하 여 `@bind-{Parameter}` 바인딩할 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-249">To bind to a component parameter, use a `@bind-{Parameter}` attribute to specify the parameter to which you want to bind.</span></span>

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a><span data-ttu-id="2c787-250">상태 변경</span><span class="sxs-lookup"><span data-stu-id="2c787-250">State changes</span></span>

<span data-ttu-id="2c787-251">구성 요소의 상태가 일반적인 UI 이벤트 또는 이벤트 콜백 외부에서 변경 된 경우 구성 요소는 다시 렌더링 해야 한다는 것을 수동으로 신호로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-251">If the component's state has changed outside of a normal UI event or event callback, then the component must manually signal that it needs to be rendered again.</span></span> <span data-ttu-id="2c787-252">구성 요소의 상태가 변경 되었음을 알리려면 `StateHasChanged` 구성 요소에서 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-252">To signal that a component's state has changed, call the `StateHasChanged` method on the component.</span></span>

<span data-ttu-id="2c787-253">아래 예제에서 구성 요소는 `AppState` 응용 프로그램의 다른 부분에서 업데이트할 수 있는 서비스의 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-253">In the example below, a component displays a message from an `AppState` service that can be updated by other parts of the app.</span></span> <span data-ttu-id="2c787-254">구성 요소는 `StateHasChanged` `AppState.OnChange` 메시지를 업데이트할 때마다 구성 요소가 렌더링 되도록 해당 메서드를 이벤트에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-254">The component registers its `StateHasChanged` method with the `AppState.OnChange` event so that the component is rendered whenever the message gets updated.</span></span>

```csharp
public class AppState
{
    public string Message { get; }

    // Lets components receive change notifications
    public event Action OnChange;

    public void UpdateMessage(string message)
    {
        Message = message;
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

## <a name="component-lifecycle"></a><span data-ttu-id="2c787-255">구성 요소 수명 주기</span><span class="sxs-lookup"><span data-stu-id="2c787-255">Component lifecycle</span></span>

<span data-ttu-id="2c787-256">ASP.NET Web Forms 프레임 워크에는 모듈, 페이지 및 컨트롤에 대 한 잘 정의 된 수명 주기 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-256">The ASP.NET Web Forms framework has well-defined lifecycle methods for modules, pages, and controls.</span></span> <span data-ttu-id="2c787-257">예를 들어 다음 컨트롤은 `Init` , `Load` 및 `UnLoad` 수명 주기 이벤트에 대 한 이벤트 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-257">For example, the following control implements event handlers for the `Init`, `Load`, and `UnLoad` lifecycle events:</span></span>

<span data-ttu-id="2c787-258">*Counter.ascx.cs*</span><span class="sxs-lookup"><span data-stu-id="2c787-258">*Counter.ascx.cs*</span></span>

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

<span data-ttu-id="2c787-259">Blazor 구성 요소에는 잘 정의 된 수명 주기도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-259">Blazor components also have a well-defined lifecycle.</span></span> <span data-ttu-id="2c787-260">구성 요소의 수명 주기를 사용 하 여 구성 요소 상태를 초기화 하 고 고급 구성 요소 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-260">A component's lifecycle can be used to initialize component state and implement advanced component behaviors.</span></span>

<span data-ttu-id="2c787-261">모든 Blazor의 구성 요소 수명 주기 메서드에는 동기 버전과 비동기 버전이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-261">All of Blazor's component lifecycle methods have both synchronous and asynchronous versions.</span></span> <span data-ttu-id="2c787-262">구성 요소 렌더링이 동기식입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-262">Component rendering is synchronous.</span></span> <span data-ttu-id="2c787-263">비동기 논리는 구성 요소 렌더링의 일부로 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-263">You can't run asynchronous logic as part of the component rendering.</span></span> <span data-ttu-id="2c787-264">모든 비동기 논리는 수명 주기 메서드의 일부로 실행 되어야 합니다 `async` .</span><span class="sxs-lookup"><span data-stu-id="2c787-264">All asynchronous logic must execute as part of an `async` lifecycle method.</span></span>

### <a name="oninitialized"></a><span data-ttu-id="2c787-265">OnInitialized 됨</span><span class="sxs-lookup"><span data-stu-id="2c787-265">OnInitialized</span></span>

<span data-ttu-id="2c787-266">`OnInitialized`및 `OnInitializedAsync` 메서드는 구성 요소를 초기화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-266">The `OnInitialized` and `OnInitializedAsync` methods are used to initialize the component.</span></span> <span data-ttu-id="2c787-267">구성 요소는 일반적으로 처음 렌더링 된 후에 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-267">A component is typically initialized after it's first rendered.</span></span> <span data-ttu-id="2c787-268">구성 요소가 초기화 된 후에는 최종적으로 삭제 되기 전에 여러 번 렌더링 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-268">After a component is initialized, it may be rendered multiple times before it's eventually disposed.</span></span> <span data-ttu-id="2c787-269">`OnInitialized`메서드는 `Page_Load` ASP.NET Web Forms 페이지 및 컨트롤의 이벤트와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-269">The `OnInitialized` method is similar to the `Page_Load` event in ASP.NET Web Forms pages and controls.</span></span>

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a><span data-ttu-id="2c787-270">OnParametersSet</span><span class="sxs-lookup"><span data-stu-id="2c787-270">OnParametersSet</span></span>

<span data-ttu-id="2c787-271">`OnParametersSet`및 `OnParametersSetAsync` 메서드는 구성 요소가 부모 로부터 매개 변수를 수신 하 고 값이 속성에 할당 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-271">The `OnParametersSet` and `OnParametersSetAsync` methods are called when a component has received parameters from its parent and the value are assigned to properties.</span></span> <span data-ttu-id="2c787-272">이러한 메서드는 구성 요소 초기화 후와 *구성 요소가 렌더링 될*때마다 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-272">These methods are executed after component initialization and *each time the component is rendered*.</span></span>

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a><span data-ttu-id="2c787-273">OnAfterRender</span><span class="sxs-lookup"><span data-stu-id="2c787-273">OnAfterRender</span></span>

<span data-ttu-id="2c787-274">`OnAfterRender`및 `OnAfterRenderAsync` 메서드는 구성 요소가 렌더링을 완료 한 후에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-274">The `OnAfterRender` and `OnAfterRenderAsync` methods are called after a component has finished rendering.</span></span> <span data-ttu-id="2c787-275">요소 및 구성 요소 참조가이 시점에 채워집니다 (아래 개념에 대 한 자세한 정보).</span><span class="sxs-lookup"><span data-stu-id="2c787-275">Element and component references are populated at this point (more on these concepts below).</span></span> <span data-ttu-id="2c787-276">이 시점에서 브라우저와의 상호 작용을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-276">Interactivity with the browser is enabled at this point.</span></span> <span data-ttu-id="2c787-277">DOM 및 JavaScript 실행과의 상호 작용은 안전 하 게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-277">Interactions with the DOM and JavaScript execution can safely take place.</span></span>

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

<span data-ttu-id="2c787-278">`OnAfterRender``OnAfterRenderAsync` *서버에서 사전 렌더링 하는 경우 및는 호출 되지 않습니다*.</span><span class="sxs-lookup"><span data-stu-id="2c787-278">`OnAfterRender` and `OnAfterRenderAsync` *aren't called when prerendering on the server*.</span></span>

<span data-ttu-id="2c787-279">`firstRender`구성 요소가 처음으로 렌더링 될 때 매개 변수가이 `true` 고, 그렇지 않으면 해당 값은 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-279">The `firstRender` parameter is `true` the first time the component is rendered; otherwise, its value is `false`.</span></span>

### <a name="idisposable"></a><span data-ttu-id="2c787-280">IDisposable</span><span class="sxs-lookup"><span data-stu-id="2c787-280">IDisposable</span></span>

<span data-ttu-id="2c787-281">Blazor 구성 요소 `IDisposable` 는 UI에서 구성 요소가 제거 될 때 리소스를 삭제 하도록 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-281">Blazor components can implement `IDisposable` to dispose of resources when the component is removed from the UI.</span></span> <span data-ttu-id="2c787-282">Razor 구성 요소는 `IDispose` 지시문을 사용 하 여를 구현할 수 있습니다 `@implements` .</span><span class="sxs-lookup"><span data-stu-id="2c787-282">A Razor component can implement `IDispose` by using the `@implements` directive:</span></span>

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

## <a name="capture-component-references"></a><span data-ttu-id="2c787-283">캡처 구성 요소 참조</span><span class="sxs-lookup"><span data-stu-id="2c787-283">Capture component references</span></span>

<span data-ttu-id="2c787-284">ASP.NET Web Forms에서 해당 ID를 참조 하 여 코드에서 직접 컨트롤 인스턴스를 조작 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-284">In ASP.NET Web Forms, it's common to manipulate a control instance directly in code by referring to its ID.</span></span> <span data-ttu-id="2c787-285">Blazor에서 구성 요소에 대 한 참조를 캡처 및 조작할 수도 있지만 일반적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-285">In Blazor, it's also possible to capture and manipulate a reference to a component, although it's much less common.</span></span>

<span data-ttu-id="2c787-286">Blazor에서 구성 요소 참조를 캡처하려면 `@ref` 지시어 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-286">To capture a component reference in Blazor, use the `@ref` directive attribute.</span></span> <span data-ttu-id="2c787-287">특성의 값은 참조 된 구성 요소와 형식이 같은 설정 가능한 필드의 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-287">The value of the attribute should match the name of a settable field with the same type as the referenced component.</span></span>

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

<span data-ttu-id="2c787-288">부모 구성 요소가 렌더링 되 면 필드는 자식 구성 요소 인스턴스로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-288">When the parent component is rendered, the field is populated with the child component instance.</span></span> <span data-ttu-id="2c787-289">그런 다음 구성 요소 인스턴스의 메서드를 호출 하거나 다른 방식으로 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-289">You can then call methods on, or otherwise manipulate, the component instance.</span></span>

<span data-ttu-id="2c787-290">구성 요소 참조를 사용 하 여 구성 요소 상태를 직접 조작 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-290">Manipulating component state directly using component references isn't recommended.</span></span> <span data-ttu-id="2c787-291">이렇게 하면 구성 요소가 올바른 시간에 자동으로 렌더링 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-291">Doing so prevents the component from being rendered automatically at the correct times.</span></span>

## <a name="capture-element-references"></a><span data-ttu-id="2c787-292">캡처 요소 참조</span><span class="sxs-lookup"><span data-stu-id="2c787-292">Capture element references</span></span>

<span data-ttu-id="2c787-293">Blazor 구성 요소는 요소에 대 한 참조를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-293">Blazor components can capture references to an element.</span></span> <span data-ttu-id="2c787-294">ASP.NET Web Forms의 HTML 서버 컨트롤과 달리 Blazor의 요소 참조를 사용 하 여 DOM을 직접 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-294">Unlike HTML server controls in ASP.NET Web Forms, you can't manipulate the DOM directly using an element reference in Blazor.</span></span> <span data-ttu-id="2c787-295">Blazor는 DOM diff 알고리즘을 사용 하 여 대부분의 DOM 상호 작용을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-295">Blazor handles most DOM interactions for you using its DOM diffing algorithm.</span></span> <span data-ttu-id="2c787-296">Blazor의 캡처된 요소 참조는 불투명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-296">Captured element references in Blazor are opaque.</span></span> <span data-ttu-id="2c787-297">그러나 JavaScript interop 호출에서 특정 요소 참조를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-297">However, they're used to pass a specific element reference in a JavaScript interop call.</span></span> <span data-ttu-id="2c787-298">JavaScript interop에 대 한 자세한 내용은 [ASP.NET Core Blazor javascript interop](/aspnet/core/blazor/javascript-interop)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c787-298">For more information about JavaScript interop, see [ASP.NET Core Blazor JavaScript interop](/aspnet/core/blazor/javascript-interop).</span></span>

## <a name="templated-components"></a><span data-ttu-id="2c787-299">템플릿 기반 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2c787-299">Templated components</span></span>

<span data-ttu-id="2c787-300">ASP.NET Web Forms에서 *템플릿 기반 컨트롤*을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-300">In ASP.NET Web Forms, you can create *templated controls*.</span></span> <span data-ttu-id="2c787-301">개발자는 템플릿 기반 컨트롤을 사용 하 여 컨테이너 컨트롤을 렌더링 하는 데 사용 되는 HTML 부분을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-301">Templated controls enable the developer to specify a portion of the HTML used to render a container control.</span></span> <span data-ttu-id="2c787-302">템플릿 기반 서버 컨트롤을 작성 하는 메커니즘은 복잡 하지만 사용자 지정 가능한 방식으로 데이터를 렌더링 하는 강력한 시나리오를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-302">The mechanics of building templated server controls are complex, but they enable powerful scenarios for rendering data in a user customizable way.</span></span> <span data-ttu-id="2c787-303">템플릿 기반 컨트롤의 예로는 `Repeater` 및가 `DataList` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-303">Examples of templated controls include `Repeater` and `DataList`.</span></span>

<span data-ttu-id="2c787-304">Blazor 구성 요소는 또는 형식의 구성 요소 매개 변수를 정의 하 여 템플릿을 만들 수도 있습니다 `RenderFragment` `RenderFragment<T>` .</span><span class="sxs-lookup"><span data-stu-id="2c787-304">Blazor components can also be templated by defining component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="2c787-305">는 `RenderFragment` 구성 요소에서 렌더링할 수 있는 Razor 태그의 청크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-305">A `RenderFragment` represents a chunk of Razor markup that can then be rendered by the component.</span></span> <span data-ttu-id="2c787-306">는 `RenderFragment<T>` 렌더링 조각이 렌더링 될 때 지정할 수 있는 매개 변수를 사용 하는 Razor 태그의 청크입니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-306">A `RenderFragment<T>` is a chunk of Razor markup that takes a parameter that can be specified when the render fragment is rendered.</span></span>

### <a name="child-content"></a><span data-ttu-id="2c787-307">자식 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="2c787-307">Child content</span></span>

<span data-ttu-id="2c787-308">Blazor 구성 요소는 자식 콘텐츠를로 캡처하고 `RenderFragment` 구성 요소 렌더링의 일부로 해당 콘텐츠를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-308">Blazor components can capture their child content as a `RenderFragment` and render that content as part of the component rendering.</span></span> <span data-ttu-id="2c787-309">자식 콘텐츠를 캡처하려면 형식의 구성 요소 매개 변수를 정의 하 `RenderFragment` 고 이름을로 지정 `ChildContent` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-309">To capture child content, define a component parameter of type `RenderFragment` and name it `ChildContent`.</span></span>

<span data-ttu-id="2c787-310">*ChildContentComponent. razor*</span><span class="sxs-lookup"><span data-stu-id="2c787-310">*ChildContentComponent.razor*</span></span>

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

<span data-ttu-id="2c787-311">그러면 부모 구성 요소가 일반적인 Razor 구문를 사용 하 여 자식 콘텐츠를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-311">A parent component can then supply child content using normal Razor syntax.</span></span>

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a><span data-ttu-id="2c787-312">템플릿 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c787-312">Template parameters</span></span>

<span data-ttu-id="2c787-313">또한 템플릿 기반 Blazor 구성 요소는 또는 형식의 여러 구성 요소 매개 변수를 정의할 수 있습니다 `RenderFragment` `RenderFragment<T>` .</span><span class="sxs-lookup"><span data-stu-id="2c787-313">A templated Blazor component can also define multiple component parameters of type `RenderFragment` or `RenderFragment<T>`.</span></span> <span data-ttu-id="2c787-314">의 매개 변수는 `RenderFragment<T>` 호출 될 때 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-314">The parameter for a `RenderFragment<T>` can be specified when it's invoked.</span></span> <span data-ttu-id="2c787-315">구성 요소에 대 한 제네릭 형식 매개 변수를 지정 하려면 `@typeparam` Razor 지시문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-315">To specify a generic type parameter for a component, use the `@typeparam` Razor directive.</span></span>

<span data-ttu-id="2c787-316">*SimpleListView*</span><span class="sxs-lookup"><span data-stu-id="2c787-316">*SimpleListView.razor*</span></span>

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

<span data-ttu-id="2c787-317">템플릿 기반 구성 요소를 사용 하는 경우 매개 변수의 이름과 일치 하는 자식 요소를 사용 하 여 템플릿 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-317">When using a templated component, the template parameters can be specified using child elements that match the names of the parameters.</span></span> <span data-ttu-id="2c787-318">요소로 전달 되는 형식의 구성 요소 인수에는 `RenderFragment<T>` 라는 암시적 매개 변수가 `context` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-318">Component arguments of type `RenderFragment<T>` passed as elements have an implicit parameter named `context`.</span></span> <span data-ttu-id="2c787-319">자식 요소의 특성을 사용 하 여이 구현 매개 변수의 이름을 변경할 수 있습니다 `Context` .</span><span class="sxs-lookup"><span data-stu-id="2c787-319">You can change the name of this implement parameter using the `Context` attribute on the child element.</span></span> <span data-ttu-id="2c787-320">형식 매개 변수의 이름과 일치 하는 특성을 사용 하 여 제네릭 형식 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-320">Any generic type parameters can be specified using an attribute that matches the name of the type parameter.</span></span> <span data-ttu-id="2c787-321">가능 하면 형식 매개 변수가 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-321">The type parameter will be inferred if possible:</span></span>

```razor
<SimpleListView Items="messages" TItem="string">
    <Heading>
        <h1>My list</h1>
    </Heading>
    <ItemTemplate Context="message">
        <p>The message is: @message</p>
    </ItemTemplate>
</SimpleListView>
```

<span data-ttu-id="2c787-322">이 구성 요소의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-322">The output of this component looks like this:</span></span>

```html
<h1>My list</h1>
<ul>
    <li><p>The message is: message1</p></li>
    <li><p>The message is: message2</p></li>
<ul>
```

## <a name="code-behind"></a><span data-ttu-id="2c787-323">코드 숨김</span><span class="sxs-lookup"><span data-stu-id="2c787-323">Code-behind</span></span>

<span data-ttu-id="2c787-324">Blazor 구성 요소는 일반적으로 단일 *razor* 파일로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-324">A Blazor component is typically authored in a single *.razor* file.</span></span> <span data-ttu-id="2c787-325">그러나 코드를 사용 하 여 코드와 태그를 분리 하는 것도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-325">However, it's also possible to separate the code and markup using a code-behind file.</span></span> <span data-ttu-id="2c787-326">구성 요소 파일을 사용 하려면 구성 요소 파일의 파일 이름과 일치 하지만 *.cs* 확장명이 추가 된 c # 파일 (*Counter.razor.cs*)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-326">To use a component file, add a C# file that matches the file name of the component file but with a *.cs* extension added (*Counter.razor.cs*).</span></span> <span data-ttu-id="2c787-327">C # 파일을 사용 하 여 구성 요소에 대 한 기본 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-327">Use the C# file to define a base class for the component.</span></span> <span data-ttu-id="2c787-328">기본 클래스의 이름을 원하는 대로 지정할 수 있지만 클래스 이름을 component 클래스와 동일 하 게 하는 것이 일반적 이지만 `Base` 확장 ()이 추가 `CounterBase` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-328">You can name the base class anything you'd like, but it's common to name the class the same as the component class, but with a `Base` extension added (`CounterBase`).</span></span> <span data-ttu-id="2c787-329">구성 요소 기반 클래스도에서 파생 되어야 합니다 `ComponentBase` .</span><span class="sxs-lookup"><span data-stu-id="2c787-329">The component-based class must also derive from `ComponentBase`.</span></span> <span data-ttu-id="2c787-330">그런 다음 Razor 구성 요소 파일에서 지시문을 추가 `@inherits` 하 여 구성 요소 ()에 대 한 기본 클래스를 지정 `@inherits CounterBase` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-330">Then, in the Razor component file, add the `@inherits` directive to specify the base class for the component (`@inherits CounterBase`).</span></span>

<span data-ttu-id="2c787-331">*카운터. razor*</span><span class="sxs-lookup"><span data-stu-id="2c787-331">*Counter.razor*</span></span>

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

<span data-ttu-id="2c787-332">*Counter.razor.cs*</span><span class="sxs-lookup"><span data-stu-id="2c787-332">*Counter.razor.cs*</span></span>

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

<span data-ttu-id="2c787-333">기본 클래스에서 구성 요소의 멤버에 대 한 표시 여부는 `protected` `public` 구성 요소 클래스에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-333">The visibility of the component's members in the base class must be `protected` or `public` to be visible to the component class.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c787-334">추가 자료</span><span class="sxs-lookup"><span data-stu-id="2c787-334">Additional resources</span></span>

<span data-ttu-id="2c787-335">위의 Blazor 구성 요소에 대 한 모든 측면을 철저 하 게 처리 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c787-335">The preceding isn't an exhaustive treatment of all aspects of Blazor components.</span></span> <span data-ttu-id="2c787-336">[Razor 구성 요소 ASP.NET Core 만들고 사용](/aspnet/core/blazor/components)하는 방법에 대 한 자세한 내용은 Blazor 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c787-336">For more information on how to [Create and use ASP.NET Core Razor components](/aspnet/core/blazor/components), see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2c787-337">[이전](app-startup.md)
>[다음](pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="2c787-337">[Previous](app-startup.md)
[Next](pages-routing-layouts.md)</span></span>
