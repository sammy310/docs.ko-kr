---
title: Build reusable UI components with Blazor
description: Learn how to build reusable UI components with Blazor and how they compare to ASP.NET Web Forms controls.
author: danroth27
ms.author: daroth
ms.date: 09/18/2019
ms.openlocfilehash: 5e5ca128bea2e77d795cede17df73963d9b49a48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337392"
---
# <a name="build-reusable-ui-components-with-blazor"></a>Build reusable UI components with Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

One of the beautiful things about ASP.NET Web Forms is how it enables encapsulation of reusable pieces of user interface (UI) code into reusable UI controls. Custom user controls can be defined in markup using *.ascx* files. You can also build elaborate server controls in code with full designer support.

Blazor also supports UI encapsulation through *components*. A component:

- Is a self-contained chunk of UI.
- Maintains its own state and rendering logic.
- Can define UI event handlers, bind to input data, and manage its own lifecycle.
- Is typically defined in a *.razor* file using Razor syntax.

## <a name="an-introduction-to-razor"></a>An introduction to Razor

Razor is a light-weight markup templating language based on HTML and C#. With Razor, you can seamlessly transition between markup and C# code to define your component rendering logic. When the *.razor* file is compiled, the rendering logic is captured in a structured way in a .NET class. The name of the compiled class is taken from the *.razor* file name. The namespace is taken from the default namespace for the project and the folder path, or you can explicitly specify the namespace using the `@namespace` directive (more on Razor directives below).

A component's rendering logic is authored using normal HTML markup with dynamic logic added using C#. The `@` character is used to transition to C#. Razor is typically smart about figuring out when you've switched back to HTML. For example, the following component renders a `<p>` tag with the current time:

```razor
<p>@DateTime.Now</p>
```

To explicitly specify the beginning and ending of a C# expression, use parentheses:

```razor
<p>@(DateTime.Now)</p>
```

Razor also makes it easy to use C# control flow in your rendering logic. For example, you can conditionally render some HTML like this:

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

Or you can generate a list of items using a normal C# `foreach` loop like this:

```razor
<ul>
@foreach (var item in items)
{
    <li>item.Text</li>
}
</ul>
```

Razor directives, like directives in ASP.NET Web Forms, control many aspects of how a Razor component is compiled. Examples include the component's:

- 네임스페이스
- 기본 클래스
- Implemented interfaces
- Generic parameters
- Imported namespaces
- 경로

Razor directives start with the `@` character and are typically used at the start of a new line at the start of the file. For example, the `@namespace` directive defines the component's namespace:

```razor
@namespace MyComponentNamespace
```

The following table summarizes the various Razor directives used in Blazor and their ASP.NET Web Forms equivalents, if they exist.

|Directive    |설명|예|Web Forms equivalent|
|-------------|-----------|-------|--------------------|
|`@attribute` |Adds a class-level attribute to the component|`@attribute [Authorize]`|None|
|`@code`      |Adds class members to the component|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|Implements the specified interface|`@implements IDisposable`|코드 숨김 사용|
|`@inherits`  |Inherits from the specified base class|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |Injects a service into the component|`@inject IJSRuntime JS`|None|
|`@layout`    |Specifies a layout component for the component|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |Sets the namespace for the component|`@namespace MyNamespace`|None|
|`@page`      |Specifies the route for the component|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |Specifies a generic type parameter for the component|`@typeparam TItem`|코드 숨김 사용|
|`@using`     |Specifies a namespace to bring into scope|`@using MyComponentNamespace`|Add namespace in *web.config*|

Razor components also make extensive use of *directive attributes* on elements to control various aspects of how components get compiled (event handling, data binding, component & element references, and so on). Directive attributes all follow a common generic syntax where the values in parenthesis are optional:

```razor
@directive(-suffix(:name))(="value")
```

The following table summarizes the various attributes for Razor directives used in Blazor.

|특성    |설명|예|
|-------------|-----------|-------|
|`@attributes`|Renders a dictionary of attributes|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |Creates a two-way data binding    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |Adds an event handler for the specified event|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |Specifies a key to be used by the diffing algorithm for preserving elements in a collection|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |Captures a reference to the component or HTML element|`<MyDialog @ref="myDialog" />`|

The various directive attributes used by Blazor (`@onclick`, `@bind`, `@ref`, and so on) are covered in the sections below and later chapters.

Many of the syntaxes used in *.aspx* and *.ascx* files have parallel syntaxes in Razor. Below is a simple comparison of the syntaxes for ASP.NET Web Forms and Razor.

|기능                      |Web Forms           |구문               |Razor         |구문 |
|-----------------------------|--------------------|---------------------|--------------|-------|
|지시문                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|코드 블록                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|표현식<br>(HTML-encoded)|`<%: %>`            |`<%:DateTime.Now %>` |Implicit: `@`<br>Explicit: `@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|설명                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|데이터 바인딩                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

To add members to the Razor component class, use the `@code` directive. This technique is similar to using a `<script runat="server">...</script>` block in an ASP.NET Web Forms user control or page.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Because Razor is based on C#, it must be compiled from within a C# project ( *.csproj*). You can't compile *.razor* files from a Visual Basic project ( *.vbproj*). You can still reference Visual Basic projects from your Blazor project. The opposite is true too.

For a full Razor syntax reference, see [Razor syntax reference for ASP.NET Core](/aspnet/core/mvc/views/razor).

## <a name="use-components"></a>구성 요소 사용

Aside from normal HTML, components can also use other components as part of their rendering logic. The syntax for using a component in Razor is similar to using a user control in an ASP.NET Web Forms app. Components are specified using an element tag that matches the type name of the component. For example, you can add a `Counter` component like this:

```razor
<Counter />
```

Unlike ASP.NET Web Forms, components in Blazor:

- Don't use an element prefix (for example, `asp:`).
- Don't require registration on the page or in the *web.config*.

Think of Razor components like you would .NET types, because that's exactly what they are. If the assembly containing the component is referenced, then the component is available for use. To bring the component's namespace into scope, apply the `@using` directive:

```razor
@using MyComponentLib

<Counter />
```

As seen in the default Blazor projects, it's common to put `@using` directives into a *_Imports.razor* file so that they're imported into all *.razor* files in the same directory and in child directories.

If the namespace for a component isn't in scope, you can specify a component using its full type name, as you can in C#:

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>구성 요소 매개 변수

In ASP.NET Web Forms, you can flow parameters and data to controls using public properties. These properties can be set in markup using attributes or set directly in code. Blazor components work in a similar fashion, although the component properties must also be marked with the `[Parameter]` attribute to be considered component parameters.

The following `Counter` component defines a component parameter called `IncrementAmount` that can be used to specify the amount that the `Counter` should be incremented each time the button is clicked.

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

To specify a component parameter in Blazor, use an attribute as you would in ASP.NET Web Forms:

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>이벤트 처리기

Both ASP.NET Web Forms and Blazor provide an event-based programming model for handling UI events. Examples of such events include button clicks and text input. In ASP.NET Web Forms, you use HTML server controls to handle UI events exposed by the DOM, or you can handle events exposed by web server controls. The events are surfaced on the server through form post-back requests. Consider the following Web Forms button click example:

*Counter.ascx*

```aspx-csharp
<asp:Button ID="ClickMeButton" runat="server" Text="Click me!" OnClick="ClickMeButton_Click" />
```

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void ClickMeButton_Click(object sender, EventArgs e)
    {
        Console.WriteLine("The button was clicked!");
    }
}
```

In Blazor, you can register handlers for DOM UI events directly using directive attributes of the form `@on{event}`. `{event}` 자리 표시자는 이벤트의 이름을 나타냅니다. 예를 들어 다음과 같이 단추 클릭을 수신할 수 있습니다.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

이벤트 처리기는 선택적 이벤트 관련 인수를 수락 하 여 이벤트에 대 한 자세한 정보를 제공할 수 있습니다. 예를 들어 마우스 이벤트는 `MouseEventArgs` 인수를 사용할 수 있지만 반드시 필요한 것은 아닙니다.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

이벤트 처리기에 대 한 메서드 그룹을 참조 하는 대신 람다 식을 사용할 수 있습니다. 람다 식을 사용 하면 다른 범위 내 값을 닫을 수 있습니다.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

이벤트 처리기는 동기적 또는 비동기적으로 실행 될 수 있습니다. 예를 들어 다음 `OnClick` 이벤트 처리기는 비동기적으로 실행 됩니다.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

이벤트가 처리 된 후 구성 요소 상태 변경을 고려 하 여 구성 요소가 렌더링 됩니다. 비동기 이벤트 처리기를 사용 하면 처리기 실행이 완료 된 직후에 구성 요소가 렌더링 됩니다. 비동기 `Task` 완료 되 면 구성 요소가 *다시* 렌더링 됩니다. 비동기 실행 모드는 비동기 `Task` 진행 중인 동안 적절 한 UI를 렌더링할 수 있는 기회를 제공 합니다.

```razor
<button @onclick="Get message">Get message</button>

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

구성 요소는 `EventCallback<TValue>`형식의 구성 요소 매개 변수를 정의 하 여 자체 이벤트를 정의할 수도 있습니다. 이벤트 콜백은 선택적 인수, 동기 또는 비동기, 메서드 그룹 또는 람다 식 등 DOM UI 이벤트 처리기의 모든 변형을 지원 합니다.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>데이터 바인딩

Blazor는 UI 구성 요소에서 구성 요소의 상태에 데이터를 바인딩하는 간단한 메커니즘을 제공 합니다. 이 방식은 데이터 소스에서 UI 컨트롤로 데이터를 바인딩하는 ASP.NET Web Forms의 기능과 다릅니다. 데이터 처리 섹션에서 다양 한 데이터 원본의 데이터를 처리 [하](data.md) 는 방법을 다룹니다.

UI 구성 요소에서 구성 요소의 상태로 양방향 데이터 바인딩을 만들려면 `@bind` 지시문 특성을 사용 합니다. 다음 예제에서 확인란의 값은 `isChecked` 필드에 바인딩됩니다.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

구성 요소가 렌더링 되 면 확인란의 값이 `isChecked` 필드의 값으로 설정 됩니다. 사용자가 확인란을 설정/해제 하면 `onchange` 이벤트가 발생 하 고 `isChecked` 필드가 새 값으로 설정 됩니다. 이 경우 `@bind` 구문은 다음 태그와 동일 합니다.

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

바인딩에 사용 되는 이벤트를 변경 하려면 `@bind:event` 특성을 사용 합니다.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

구성 요소는 해당 매개 변수에 대 한 데이터 바인딩을 지원할 수도 있습니다. 데이터 바인딩하려면 바인딩 가능 매개 변수와 동일한 이름을 사용 하 여 이벤트 콜백 매개 변수를 정의 합니다. 이름에 "Changed" 접미사가 추가 됩니다.

*PasswordBox razor*

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

데이터 바인딩을 기본 UI 요소에 연결 하려면 `@bind` 특성을 사용 하는 대신 값을 설정 하 고 UI 요소에서 직접 이벤트를 처리 합니다.

구성 요소 매개 변수에 바인딩하려면 `@bind-{Parameter}` 특성을 사용 하 여 바인딩할 매개 변수를 지정 합니다.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>상태 변경

구성 요소의 상태가 일반적인 UI 이벤트 또는 이벤트 콜백 외부에서 변경 된 경우 구성 요소는 다시 렌더링 해야 한다는 것을 수동으로 신호로 보내야 합니다. 구성 요소의 상태가 변경 되었음을 알리려면 구성 요소에서 `StateHasChanged` 메서드를 호출 합니다.

아래 예제에서는 응용 프로그램의 다른 부분에서 업데이트할 수 있는 `AppState` 서비스의 메시지를 구성 요소에 표시 합니다. 구성 요소는 메시지가 업데이트 될 때마다 구성 요소가 렌더링 되도록 `AppState.OnChange` 이벤트를 사용 하 여 `StateHasChanged` 메서드를 등록 합니다.

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

## <a name="component-lifecycle"></a>구성 요소 수명 주기

ASP.NET Web Forms 프레임 워크에는 모듈, 페이지 및 컨트롤에 대 한 잘 정의 된 수명 주기 방법이 있습니다. 예를 들어 다음 컨트롤은 `Init`, `Load`및 `UnLoad` 수명 주기 이벤트에 대 한 이벤트 처리기를 구현 합니다.

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor 구성 요소에는 잘 정의 된 수명 주기도 있습니다. 구성 요소의 수명 주기를 사용 하 여 구성 요소 상태를 초기화 하 고 고급 구성 요소 동작을 구현할 수 있습니다.

모든 Blazor의 구성 요소 수명 주기 메서드에는 동기 버전과 비동기 버전이 모두 있습니다. 구성 요소 렌더링이 동기식입니다. 비동기 논리는 구성 요소 렌더링의 일부로 실행할 수 없습니다. 모든 비동기 논리는 `async` 수명 주기 메서드의 일부로 실행 해야 합니다.

### <a name="oninitialized"></a>OnInitialized 됨

`OnInitialized` 및 `OnInitializedAsync` 메서드는 구성 요소를 초기화 하는 데 사용 됩니다. 구성 요소는 일반적으로 처음 렌더링 된 후에 초기화 됩니다. 구성 요소가 초기화 된 후에는 최종적으로 삭제 되기 전에 여러 번 렌더링 될 수 있습니다. `OnInitialized` 메서드는 ASP.NET Web Forms 페이지 및 컨트롤의 `Page_Load` 이벤트와 비슷합니다.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>OnParametersSet

`OnParametersSet` 및 `OnParametersSetAsync` 메서드는 구성 요소가 부모 로부터 매개 변수를 수신 하 고 값이 속성에 할당 될 때 호출 됩니다. 이러한 메서드는 구성 요소 초기화 후와 *구성 요소가 렌더링 될*때마다 실행 됩니다.

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>OnAfterRender

`OnAfterRender` 및 `OnAfterRenderAsync` 메서드는 구성 요소가 렌더링을 완료 한 후에 호출 됩니다. 요소 및 구성 요소 참조가이 시점에 채워집니다 (아래 개념에 대 한 자세한 정보). 이 시점에서 브라우저와의 상호 작용을 사용 하도록 설정 합니다. DOM 및 JavaScript 실행과의 상호 작용은 안전 하 게 수행할 수 있습니다.

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

`OnAfterRender` 및 `OnAfterRenderAsync`는 *서버에서 사전 렌더링 시 호출 되지 않습니다*.

`firstRender` 매개 변수는 구성 요소가 처음 렌더링 될 때 `true` 됩니다. 그렇지 않으면 해당 값이 `false`됩니다.

### <a name="idisposable"></a>IDisposable

Blazor 구성 요소는 UI에서 구성 요소가 제거 될 때 리소스를 삭제 하기 위해 `IDisposable`를 구현할 수 있습니다. Razor 구성 요소는 `@implements` 지시어를 사용 하 여 `IDispose`를 구현할 수 있습니다.

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

## <a name="capture-component-references"></a>캡처 구성 요소 참조

ASP.NET Web Forms에서 해당 ID를 참조 하 여 코드에서 직접 컨트롤 인스턴스를 조작 하는 것이 일반적입니다. Blazor에서 구성 요소에 대 한 참조를 캡처 및 조작할 수도 있지만 일반적이 지 않습니다.

Blazor에서 구성 요소 참조를 캡처하려면 `@ref` 지시어 특성을 사용 합니다. 특성의 값은 참조 된 구성 요소와 형식이 같은 설정 가능한 필드의 이름과 일치 해야 합니다.

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

부모 구성 요소가 렌더링 되 면 필드는 자식 구성 요소 인스턴스로 채워집니다. 그런 다음 구성 요소 인스턴스의 메서드를 호출 하거나 다른 방식으로 조작할 수 있습니다.

구성 요소 참조를 사용 하 여 구성 요소 상태를 직접 조작 하지 않는 것이 좋습니다. 이렇게 하면 구성 요소가 올바른 시간에 자동으로 렌더링 되지 않습니다.

## <a name="capture-element-references"></a>캡처 요소 참조

Blazor 구성 요소는 요소에 대 한 참조를 캡처할 수 있습니다. ASP.NET Web Forms의 HTML 서버 컨트롤과 달리 Blazor의 요소 참조를 사용 하 여 DOM을 직접 조작할 수 없습니다. Blazor는 DOM diff 알고리즘을 사용 하 여 대부분의 DOM 상호 작용을 처리 합니다. Blazor의 캡처된 요소 참조는 불투명 합니다. 그러나 JavaScript interop 호출에서 특정 요소 참조를 전달 하는 데 사용 됩니다. JavaScript interop에 대 한 자세한 내용은 [ASP.NET Core Blazor javascript interop](/aspnet/core/blazor/javascript-interop)를 참조 하세요.

## <a name="templated-components"></a>템플릿 기반 구성 요소

ASP.NET Web Forms에서 *템플릿 기반 컨트롤*을 만들 수 있습니다. 개발자는 템플릿 기반 컨트롤을 사용 하 여 컨테이너 컨트롤을 렌더링 하는 데 사용 되는 HTML 부분을 지정할 수 있습니다. 템플릿 기반 서버 컨트롤을 작성 하는 메커니즘은 복잡 하지만 사용자 지정 가능한 방식으로 데이터를 렌더링 하는 강력한 시나리오를 가능 하 게 합니다. 템플릿 컨트롤의 예로는 `Repeater` 및 `DataList`가 있습니다.

Blazor 구성 요소는 `RenderFragment` 또는 `RenderFragment<T>`형식의 구성 요소 매개 변수를 정의 하 여 템플릿을 만들 수도 있습니다. `RenderFragment`는 구성 요소에서 렌더링할 수 있는 Razor 태그의 청크를 나타냅니다. `RenderFragment<T>`는 렌더링 조각이 렌더링 될 때 지정할 수 있는 매개 변수를 사용 하는 Razor 태그의 청크입니다.

### <a name="child-content"></a>자식 콘텐츠

Blazor 구성 요소는 자식 콘텐츠를 `RenderFragment` 캡처하고 구성 요소 렌더링의 일부로 해당 콘텐츠를 렌더링할 수 있습니다. 자식 콘텐츠를 캡처하려면 `RenderFragment` 형식의 구성 요소 매개 변수를 정의 하 고 `ChildContent`이름을 지정 합니다.

*ChildContentComponent. razor*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

그러면 부모 구성 요소가 일반적인 Razor 구문를 사용 하 여 자식 콘텐츠를 제공할 수 있습니다.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>템플릿 매개 변수

또한 템플릿 기반 Blazor 구성 요소는 `RenderFragment` 또는 `RenderFragment<T>`형식의 여러 구성 요소 매개 변수를 정의할 수 있습니다. `RenderFragment<T>`에 대 한 매개 변수는 호출 될 때 지정할 수 있습니다. 구성 요소에 대 한 제네릭 형식 매개 변수를 지정 하려면 `@typeparam` Razor 지시문을 사용 합니다.

*SimpleListView*

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

템플릿 기반 구성 요소를 사용 하는 경우 매개 변수의 이름과 일치 하는 자식 요소를 사용 하 여 템플릿 매개 변수를 지정할 수 있습니다. 요소로 전달 되는 `RenderFragment<T>` 형식의 구성 요소 인수에는 `context`라는 암시적 매개 변수가 있습니다. 자식 요소의 `Context` 특성을 사용 하 여이 구현 매개 변수의 이름을 변경할 수 있습니다. 형식 매개 변수의 이름과 일치 하는 특성을 사용 하 여 제네릭 형식 매개 변수를 지정할 수 있습니다. 가능 하면 형식 매개 변수가 유추 됩니다.

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

이 구성 요소의 출력은 다음과 같습니다.

```html
<h1>My list</h1>
<ul>
    <li>The message is: message1</li>
    <li>The message is: message2</li>
<ul>
```

## <a name="code-behind"></a>코드 숨김

Blazor 구성 요소는 일반적으로 단일 *razor* 파일로 작성 됩니다. 그러나 코드를 사용 하 여 코드와 태그를 분리 하는 것도 가능 합니다. 구성 요소 파일을 사용 하려면 구성 요소 C# 파일의 파일 이름과 일치 하지만 *.cs* 확장명이 추가 된 파일 (*Counter.razor.cs*)을 추가 합니다. 이 C# 파일을 사용 하 여 구성 요소에 대 한 기본 클래스를 정의 합니다. 기본 클래스의 이름을 원하는 대로 지정할 수 있지만 클래스 이름을 component 클래스와 동일 하 게 하는 것이 일반적 이지만 `Base` 확장 (`CounterBase`)이 추가 됩니다. 구성 요소 기반 클래스는 `ComponentBase`에서도 파생 되어야 합니다. 그런 다음 Razor 구성 요소 파일에서 `@inherits` 지시어를 추가 하 여 구성 요소 (`@inherits CounterBase`)에 대 한 기본 클래스를 지정 합니다.

*카운터. razor*

```razor
@inherits CounterBase

<h1>Counter</h1>

<p>Current count: @currentCount</p>

<button @onclick="IncrementCount">Click me</button>
```

*Counter.razor.cs*

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

기본 클래스에서 구성 요소의 멤버에 대 한 표시 여부를 `protected` 하거나 구성 요소 클래스에 표시 되도록 `public` 해야 합니다.

## <a name="additional-resources"></a>추가 자료

위의 Blazor 구성 요소에 대 한 모든 측면을 철저 하 게 처리 하지는 않습니다. [Razor 구성 요소 ASP.NET Core 만들고 사용](/aspnet/core/blazor/components)하는 방법에 대 한 자세한 내용은 Blazor 설명서를 참조 하세요.

>[!div class="step-by-step"]
>[이전](app-startup.md)
>[다음](pages-routing-layouts.md)
