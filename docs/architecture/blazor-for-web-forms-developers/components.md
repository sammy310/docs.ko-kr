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
# <a name="build-reusable-ui-components-with-blazor"></a>블레이저로 재사용 가능한 UI 구성 요소 빌드

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Web Forms의 가장 아름다운 점 중 하나는 재사용 가능한 UI(사용자 인터페이스) 코드를 재사용 가능한 UI 컨트롤로 캡슐화하는 방법입니다. *.ascx* 파일을 사용하여 태그에서 사용자 지정 사용자 컨트롤을 정의할 수 있습니다. 또한 전체 디자이너 지원을 통해 코드에서 정교한 서버 컨트롤을 빌드할 수도 있습니다.

Blazor는 *구성 요소를*통해 UI 캡슐화도 지원합니다. 구성 요소:

- UI의 독립형 청크입니다.
- 자체 상태 및 렌더링 논리를 유지 합니다.
- UI 이벤트 처리기를 정의하고, 입력 데이터에 바인딩하고, 자체 수명 주기를 관리할 수 있습니다.
- 일반적으로 Razor 구문을 사용하여 *.razor* 파일에 정의됩니다.

## <a name="an-introduction-to-razor"></a>면도기 소개

Razor는 HTML 및 C#을 기반으로 하는 경량 마크업 템플릿 언어입니다. Razor를 사용하면 태그와 C# 코드 간에 원활하게 전환하여 구성 요소 렌더링 논리를 정의할 수 있습니다. *.razor* 파일을 컴파일하면 렌더링 논리가 .NET 클래스의 구조화 된 방식으로 캡처됩니다. 컴파일된 클래스의 이름은 *.razor* 파일 이름에서 가져옵니다. 네임스페이스는 프로젝트 및 폴더 경로의 기본 네임스페이스에서 가져온 것이거나 `@namespace` 지시문을 사용하여 네임스페이스를 명시적으로 지정할 수 있습니다(아래 Razor 지시문에 대해 자세히 참조).

구성 요소의 렌더링 논리는 C#을 사용하여 추가된 동적 논리가 있는 일반 HTML 태그를 사용하여 작성됩니다. 문자는 `@` C#으로 전환하는 데 사용됩니다. 면도기는 일반적으로 HTML로 다시 전환 한 경우 알아내는 것에 대해 똑똑합니다. 예를 들어 다음 구성 요소는 `<p>` 현재 시간으로 태그를 렌더링합니다.

```razor
<p>@DateTime.Now</p>
```

C# 식의 시작과 끝을 명시적으로 지정하려면 괄호를 사용합니다.

```razor
<p>@(DateTime.Now)</p>
```

또한 Razor를 사용하면 렌더링 논리에서 C# 제어 흐름을 쉽게 사용할 수 있습니다. 예를 들어 다음과 같은 일부 HTML을 조건부로 렌더링할 수 있습니다.

```razor
@if (value % 2 == 0)
{
    <p>The value was even.</p>
}
```

또는 다음과 같이 일반 C# `foreach` 루프를 사용하여 항목 목록을 생성할 수 있습니다.

```razor
<ul>
@foreach (var item in items)
{
    <li>@item.Text</li>
}
</ul>
```

Razor 지시문은 ASP.NET 웹 양식의 지시문과 마찬가지로 Razor 구성 요소가 컴파일되는 방식의 여러 측면을 제어합니다. 예를 들어 구성 요소의 다음을 포함합니다.

- 네임스페이스
- 기본 클래스
- 구현된 인터페이스
- 제네릭 매개 변수
- 가져온 네임스페이스
- 경로

Razor 지시문은 `@` 문자로 시작하며 일반적으로 파일 시작 시 새 줄의 시작 부분에 사용됩니다. 예를 들어 `@namespace` 지시문은 구성 요소의 네임스페이스를 정의합니다.

```razor
@namespace MyComponentNamespace
```

다음 표에는 Blazor에 사용되는 다양한 Razor 지시문과 ASP.NET Web Forms 등가물(있는 경우)이 요약되어 있습니다.

|지시문    |Description|예제|동등한 웹 양식|
|-------------|-----------|-------|--------------------|
|`@attribute` |구성 요소에 클래스 수준 특성 추가|`@attribute [Authorize]`|None|
|`@code`      |구성 요소에 클래스 멤버 추가|`@code { ... }`|`<script runat="server">...</script>`|
|`@implements`|지정된 인터페이스 구현|`@implements IDisposable`|코드 숨김 사용|
|`@inherits`  |지정된 기본 클래스에서 상속|`@inherits MyComponentBase`|`<%@ Control Inherits="MyUserControlBase" %>`|
|`@inject`    |구성 요소에 서비스 삽입|`@inject IJSRuntime JS`|None|
|`@layout`    |구성 요소에 대한 레이아웃 구성 요소를 지정합니다.|`@layout MainLayout`|`<%@ Page MasterPageFile="~/Site.Master" %>`|
|`@namespace` |구성 요소의 네임스페이스 설정|`@namespace MyNamespace`|None|
|`@page`      |구성 요소의 배선을 지정합니다.|`@page "/product/{id}"`|`<%@ Page %>`|
|`@typeparam` |구성 요소에 대한 제네릭 형식 매개 변수 지정|`@typeparam TItem`|코드 숨김 사용|
|`@using`     |범위로 가져올 네임스페이스 지정|`@using MyComponentNamespace`|*web.config에* 네임스페이스 추가|

또한 Razor 구성 요소는 요소에 대한 *지시문 특성을* 광범위하게 사용하여 구성 요소가 컴파일되는 방식(이벤트 처리, 데이터 바인딩, 구성 요소 & 요소 참조 등)의 다양한 측면을 제어합니다. 지시문 특성은 모두 괄호 안의 값이 선택 사항인 일반적인 일반 구문을 따릅니다.

```razor
@directive(-suffix(:name))(="value")
```

다음 표에는 Blazor에서 사용되는 Razor 지시문에 대한 다양한 특성이 요약되어 있습니다.

|특성    |Description|예제|
|-------------|-----------|-------|
|`@attributes`|특성 사전 렌더링|`<input @attributes="ExtraAttributes" />`|
|`@bind`      |양방향 데이터 바인딩 생성    |`<input @bind="username" @bind:event="oninput" />`|
|`@on{event}` |지정된 이벤트에 대한 이벤트 처리기를 추가합니다.|`<button @onclick="IncrementCount">Click me!</button>`|
|`@key`       |컬렉션의 요소를 보존하기 위해 디핑 알고리즘에서 사용할 키를 지정합니다.|`<DetailsEditor @key="person" Details="person.Details" />`|
|`@ref`       |구성 요소 또는 HTML 요소에 대한 참조 캡처|`<MyDialog @ref="myDialog" />`|

Blazor (,`@onclick`및 `@bind` `@ref`기타)에서 사용하는 다양한 지시문 속성은 아래 및 이후 장에서 다룹니다.

*.aspx* 및 *.ascx* 파일에 사용되는 많은 구문에는 Razor에 병렬 구문이 있습니다. 다음은 ASP.NET 웹 양식 및 Razor에 대한 구문에 대한 간단한 비교입니다.

|기능                      |웹 양식           |구문               |Razor         |구문 |
|-----------------------------|--------------------|---------------------|--------------|-------|
|지시문                   |`<%@ [directive] %>`|`<%@ Page %>`        |`@[directive]`|`@page`|
|코드 블록                  |`<% %>`             |`<% int x = 123; %>` |`@{ }`        |`@{ int x = 123; }`|
|표현식<br>(HTML 인코딩)|`<%: %>`            |`<%:DateTime.Now %>` |암시적:`@`<br>명시적:`@()`|`@DateTime.Now`<br>`@(DateTime.Now)`|
|주석                     |`<%-- --%>`         |`<%-- Commented --%>`|`@* *@`       |`@* Commented *@`|
|데이터 바인딩                 |`<%# %>`            |`<%# Bind("Name") %>`|`@bind`       |`<input @bind="username" />`|

Razor 구성 요소 클래스에 멤버를 `@code` 추가하려면 지시문을 사용합니다. 이 기술은 ASP.NET Web `<script runat="server">...</script>` Forms 사용자 컨트롤 또는 페이지에서 블록을 사용하는 것과 유사합니다.

```razor
@code {
    int count = 0;

    void IncrementCount()
    {
        count++;
    }
}
```

Razor는 C#을 기반으로 하므로 C#*프로젝트(.csproj)* 내에서 컴파일해야 합니다. Visual Basic*프로젝트(.vbproj)에서는* *.razor* 파일을 컴파일할 수 없습니다. 블레이저 프로젝트에서 Visual Basic 프로젝트를 계속 참조할 수 있습니다. 그 반대의 경우도 마찬가지입니다.

전체 Razor 구문 참조는 [ASP.NET 코어에 대한 Razor 구문 참조를](/aspnet/core/mvc/views/razor)참조하십시오.

## <a name="use-components"></a>구성 요소 사용

일반 HTML 외에도 구성 요소는 렌더링 논리의 일부로 다른 구성 요소를 사용할 수도 있습니다. Razor에서 구성 요소를 사용하는 구문은 ASP.NET Web Forms 앱에서 사용자 컨트롤을 사용하는 것과 유사합니다. 구성 요소는 구성 요소의 형식 이름과 일치하는 요소 태그를 사용하여 지정됩니다. 예를 들어 다음과 같은 `Counter` 구성 요소를 추가할 수 있습니다.

```razor
<Counter />
```

ASP.NET 웹 양식과 달리 Blazor의 구성 요소는 다음과 같은 것입니다.

- 요소 접두사(예: )를 `asp:`사용하지 마십시오.
- 페이지 또는 *web.config에서*등록할 필요가 없습니다.

.NET 형식과 같은 Razor 구성 요소를 생각해 보십시오. 구성요소를 포함하는 어셈블리가 참조되면 구성요소를 사용할 수 있습니다. 구성 요소의 네임스페이스를 범위로 `@using` 가져오려면 지시문을 적용합니다.

```razor
@using MyComponentLib

<Counter />
```

기본 Blazor 프로젝트에서 볼 수 있듯이 지시문을 `@using` *_Imports.razor* 파일에 넣어 동일한 디렉터리 및 자식 디렉터리의 모든 *.razor* 파일로 가져오는 것이 일반적입니다.

구성 요소의 네임스페이스가 범위에 없는 경우 C#에서와 같이 전체 형식 이름을 사용하여 구성 요소를 지정할 수 있습니다.

```razor
<MyComponentLib.Counter />
```

## <a name="component-parameters"></a>구성 요소 매개 변수

웹 양식 ASP.NET 매개 변수와 데이터를 공용 속성을 사용하여 컨트롤로 플로우는 수 있습니다. 이러한 속성은 특성을 사용하여 태그로 설정하거나 코드에서 직접 설정할 수 있습니다. Blazor 구성 요소는 유사한 방식으로 작동하지만 구성 요소 속성도 구성 요소 매개 변수로 간주할 `[Parameter]` 특성으로 표시되어야 합니다.

다음 `Counter` 구성 요소는 단추를 `IncrementAmount` 클릭할 때마다 `Counter` 증분해야 하는 양을 지정하는 데 사용할 수 있는 구성 요소 매개 변수를 정의합니다.

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

Blazor에서 구성 요소 매개 변수를 지정하려면 ASP.NET 웹 양식에서와 마찬가지로 특성을 사용합니다.

```razor
<Counter IncrementAmount="10" />
```

## <a name="event-handlers"></a>이벤트 처리기

ASP.NET 웹 양식과 Blazor 모두 UI 이벤트를 처리하기 위한 이벤트 기반 프로그래밍 모델을 제공합니다. 이러한 이벤트의 예로는 단추 클릭 및 텍스트 입력이 있습니다. 웹 양식 ASP.NET HTML 서버 컨트롤을 사용하여 DOM에서 노출되는 UI 이벤트를 처리하거나 웹 서버 컨트롤에서 노출되는 이벤트를 처리할 수 있습니다. 이벤트는 포스트백 양식 요청을 통해 서버에 표시됩니다. 다음 웹 양식 단추 클릭 예제를 살펴보겠습니다.

*카운터.ascx*

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

Blazor에서 폼의 `@on{event}`지시문 특성을 사용하여 DOM UI 이벤트에 대한 처리기를 직접 등록할 수 있습니다. `{event}` 자리 표시자는 이벤트의 이름을 나타냅니다. 예를 들어 다음과 같은 단추 클릭을 들을 수 있습니다.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick()
    {
        Console.WriteLine("The button was clicked!);
    }
}
```

이벤트 처리기는 선택적 이벤트별 인수를 수락하여 이벤트에 대한 자세한 정보를 제공할 수 있습니다. 예를 들어 마우스 이벤트는 `MouseEventArgs` 인수를 사용할 수 있지만 필수는 아닙니다.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    void OnClick(MouseEventArgs e)
    {
        Console.WriteLine($"Mouse clicked at {e.ScreenX}, {e.ScreenY}.");
    }
}
```

이벤트 처리기에 대한 메서드 그룹을 참조하는 대신 lambda 식을 사용할 수 있습니다. 람다 식을 사용하면 다른 범위 내 값을 닫을 수 있습니다.

```razor
@foreach (var buttonLabel in buttonLabels)
{
    <button @onclick="() => Console.WriteLine($"The {buttonLabel} button was clicked!")">@buttonLabel</button>
}
```

이벤트 처리기는 동기 또는 비동기적으로 실행할 수 있습니다. 예를 들어 다음 `OnClick` 이벤트 처리기는 비동기적으로 실행됩니다.

```razor
<button @onclick="OnClick">Click me!</button>

@code {
    async Task OnClick()
    {
        var result = await Http.GetAsync("api/values");
    }
}
```

이벤트가 처리되면 구성 요소 상태 변경을 고려하여 구성 요소가 렌더링됩니다. 비동기 이벤트 처리기를 사용하면 처리기 실행이 완료된 직후 에 구성 요소가 렌더링됩니다. 비동기가 `Task` 완료되면 구성 요소가 *다시* 렌더링됩니다. 이 비동기 실행 모드는 비동기가 `Task` 진행 중인 동안 적절한 UI를 렌더링할 수 있는 기회를 제공합니다.

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

구성 요소는 형식의 `EventCallback<TValue>`구성 요소 매개 변수를 정의하여 자체 이벤트를 정의할 수도 있습니다. 이벤트 콜백은 선택적 인수, 동기 또는 비동기, 메서드 그룹 또는 람다 식과 같은 DOM UI 이벤트 처리기의 모든 변형을 지원합니다.

```razor
<button class="btn btn-primary" @onclick="OnClick">Click me!</button>

@code {
    [Parameter]
    public EventCallback<MouseEventArgs> OnClick { get; set; }
}
```

## <a name="data-binding"></a>데이터 바인딩

Blazor는 UI 구성 요소에서 구성 요소의 상태에 데이터를 바인딩하는 간단한 메커니즘을 제공합니다. 이 방법은 데이터 원본에서 UI 컨트롤로 데이터를 바인딩하기 위해 ASP.NET Web Forms의 기능과 다릅니다. 데이터 처리 섹션에서 다른 데이터 원본의 데이터 처리에 대해 [다룹니다.](data.md)

UI 구성 요소에서 구성 요소의 상태로 양방향 데이터 바인딩을 `@bind` 만들려면 지시문 특성을 사용합니다. 다음 예제에서는 확인란의 값이 `isChecked` 필드에 바인딩됩니다.

```razor
<input type="checkbox" @bind="isChecked" />

@code {
    bool isChecked;
}
```

구성 요소가 렌더링되면 확인란의 값이 `isChecked` 필드 값으로 설정됩니다. 사용자가 확인란을 전환하면 `onchange` 이벤트가 발생되고 필드가 `isChecked` 새 값으로 설정됩니다. 이 `@bind` 경우 구문은 다음 태그와 같습니다.

```razor
<input value="@isChecked" @onchange="(UIChangeEventArgs e) => isChecked = e.Value" />
```

바인딩에 사용되는 이벤트를 변경하려면 특성을 `@bind:event` 사용합니다.

```razor
<input @bind="text" @bind:event="oninput" />
<p>@text</p>

@code {
    string text;
}
```

구성 요소는 매개 변수에 대한 데이터 바인딩을 지원할 수도 있습니다. 데이터 바인딩하려면 바인딩 가능한 매개 변수와 이름이 같은 이벤트 콜백 매개 변수를 정의합니다. "변경된" 접미사가 이름에 추가됩니다.

*암호 상자.면도기*

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

데이터 바인딩을 기본 UI 요소에 연결하려면 값을 설정하고 특성을 사용하는 대신 UI `@bind` 요소에서 직접 이벤트를 처리합니다.

구성 요소 매개 변수에 `@bind-{Parameter}` 바인딩하려면 특성을 사용하여 바인딩할 매개 변수를 지정합니다.

```razor
<PasswordBox @bind-Password="password" />

@code {
    string password;
}
```

## <a name="state-changes"></a>상태 변경

컴포넌트의 상태가 일반 UI 이벤트 또는 이벤트 콜백 외부에서 변경된 경우 구성 요소는 수동으로 다시 렌더링해야 한다는 신호를 보내야 합니다. 구성 요소의 상태가 변경되었음을 알리려면 `StateHasChanged` 구성 요소의 메서드를 호출합니다.

아래 예제에서 구성 요소는 앱의 `AppState` 다른 부분에서 업데이트할 수 있는 서비스의 메시지를 표시합니다. 구성 요소는 메시지가 `StateHasChanged` 업데이트될 `AppState.OnChange` 때마다 구성 요소가 렌더링되도록 해당 메서드를 이벤트에 등록합니다.

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

ASP.NET Web Forms 프레임워크에는 모듈, 페이지 및 컨트롤에 대해 잘 정의된 수명 주기 메서드가 있습니다. 예를 들어 다음 컨트롤은 `Init`에 `Load`대한 이벤트 처리기를 구현합니다. `UnLoad`

*Counter.ascx.cs*

```csharp
public partial class Counter : System.Web.UI.UserControl
{
    protected void Page_Init(object sender, EventArgs e) { ... }
    protected void Page_Load(object sender, EventArgs e) { ... }
    protected void Page_UnLoad(object sender, EventArgs e) { ... }
}
```

Blazor 구성 요소에는 잘 정의된 수명 주기도 있습니다. 구성 요소의 수명 주기를 사용하여 구성 요소 상태를 초기화하고 고급 구성 요소 동작을 구현할 수 있습니다.

Blazor의 모든 구성 요소 수명 주기 메서드에는 동기 버전과 비동기 버전이 모두 있습니다. 구성 요소 렌더링은 동기입니다. 구성 요소 렌더링의 일부로 비동기 논리를 실행할 수 없습니다. 모든 비동기 논리는 `async` 수명 주기 메서드의 일부로 실행되어야 합니다.

### <a name="oninitialized"></a>초기화

`OnInitialized` 및 `OnInitializedAsync` 메서드는 구성 요소를 초기화하는 데 사용됩니다. 구성 요소는 일반적으로 처음 렌더링된 후 초기화됩니다. 구성 요소가 초기화되면 결국 삭제되기 전에 여러 번 렌더링될 수 있습니다. 이 `OnInitialized` 메서드는 ASP.NET `Page_Load` 웹 양식 페이지 및 컨트롤의 이벤트와 유사합니다.

```csharp
protected override void OnInitialized() { ... }
protected override async Task OnInitializedAsync() { await ... }
```

### <a name="onparametersset"></a>온매개 변수 집합

및 `OnParametersSet` `OnParametersSetAsync` 메서드는 구성 요소가 부모로부터 매개 변수를 수신하고 값이 속성에 할당될 때 호출됩니다. 이러한 메서드는 구성 요소 초기화 후 및 구성 요소가 *렌더링될 때마다 실행됩니다.*

```csharp
protected override void OnParametersSet() { ... }
protected override async Task OnParametersSetAsync() { await ... }
```

### <a name="onafterrender"></a>온애프터렌더

`OnAfterRender` 및 `OnAfterRenderAsync` 메서드는 구성 요소 렌더링이 완료된 후 호출됩니다. 요소 및 구성 요소 참조는 이 시점에서 채워집니다(아래 이러한 개념에 대한 자세한 내용은 참조). 이 시점에서 브라우저와의 상호 작용이 활성화됩니다. DOM 및 JavaScript 실행과의 상호 작용은 안전하게 이루어질 수 있습니다.

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

`OnAfterRender``OnAfterRenderAsync` *서버에서 사전 렌더링할 때 호출되지 않습니다.*

`firstRender` 매개 변수는 `true` 구성 요소가 처음 렌더링될 때입니다. 그렇지 않으면 해당 `false`값은 .

### <a name="idisposable"></a>IDisposable

Blazor 구성 `IDisposable` 요소는 UI에서 구성 요소를 제거할 때 리소스를 삭제하도록 구현할 수 있습니다. Razor 구성 요소는 `IDispose` 지시문을 `@implements` 사용하여 구현할 수 있습니다.

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

## <a name="capture-component-references"></a>구성 요소 참조 캡처

ASP.NET Web Forms에서는 코드에서 해당 ID를 참조하여 컨트롤 인스턴스를 직접 조작하는 것이 일반적입니다. Blazor에서는 훨씬 덜 일반적이지만 구성 요소에 대한 참조를 캡처하고 조작할 수도 있습니다.

Blazor에서 구성 요소 참조를 `@ref` 캡처하려면 지시문 특성을 사용합니다. 특성값은 설정된 필드의 이름과 참조된 구성 요소와 동일한 형식과 일치해야 합니다.

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

상위 구성 요소가 렌더링되면 필드는 자식 구성 요소 인스턴스로 채워집니다. 그런 다음 구성 요소 인스턴스를 호출하거나 조작할 수 있습니다.

구성 요소 참조를 사용하여 구성 요소 상태를 직접 조작하는 것은 권장되지 않습니다. 이렇게 하면 올바른 시간에 구성 요소가 자동으로 렌더링되지 않습니다.

## <a name="capture-element-references"></a>요소 참조 캡처

Blazor 구성 요소는 요소에 대한 참조를 캡처할 수 있습니다. ASP.NET 웹 양식의 HTML 서버 컨트롤과 달리 Blazor의 요소 참조를 사용하여 DOM을 직접 조작할 수 없습니다. Blazor는 DOM 디핑 알고리즘을 사용하여 대부분의 DOM 상호 작용을 처리합니다. 블레이저에서 캡처된 요소 참조는 불투명합니다. 그러나 JavaScript 인터오프 호출에서 특정 요소 참조를 전달하는 데 사용됩니다. 자바 스크립트 interop에 대한 자세한 내용은 [ASP.NET 코어 블레이저 자바 스크립트 인터옵을](/aspnet/core/blazor/javascript-interop)참조하십시오.

## <a name="templated-components"></a>템플릿 기반 구성 요소

ASP.NET 웹 양식에서 *템플릿 컨트롤을*만들 수 있습니다. 템플릿 컨트롤을 사용하면 개발자가 컨테이너 컨트롤을 렌더링하는 데 사용되는 HTML 의 일부를 지정할 수 있습니다. 템플릿 서버 컨트롤을 빌드하는 방법은 복잡하지만 사용자 사용자 지정 가능한 방식으로 데이터를 렌더링하기 위한 강력한 시나리오를 사용할 수 있습니다. 템플릿 컨트롤의 예는 `Repeater` `DataList`다음과 같습니다.

Blazor 구성 요소는 형식 `RenderFragment` 또는 `RenderFragment<T>`의 구성 요소 매개 변수를 정의하여 템플릿을 만들 수도 있습니다. A는 `RenderFragment` 구성 요소에서 렌더링할 수 있는 Razor 태그 의 청크를 나타냅니다. A는 `RenderFragment<T>` 렌더링 조각이 렌더링될 때 지정할 수 있는 매개 변수를 취하는 Razor 태그의 청크입니다.

### <a name="child-content"></a>하위 콘텐츠

Blazor 구성 요소는 자식 `RenderFragment` 콘텐츠를 a로 캡처하고 해당 콘텐츠를 구성 요소 렌더링의 일부로 렌더링할 수 있습니다. 자식 콘텐츠를 캡처하려면 형식의 `RenderFragment` 구성 요소 `ChildContent`매개 변수를 정의하고 이름을 지정합니다.

*차일드콘텐츠컴포넌트.면도기*

```razor
<h1>Component with child content</h1>

<div>@ChildContent</div>

@code {
    [Parameter]
    public RenderFragment ChildContent { get; set; }
}
```

그런 다음 부모 구성 요소는 일반 Razor 구문을 사용하여 자식 콘텐츠를 제공할 수 있습니다.

```razor
<ChildContentComponent>
    <p>The time is @DateTime.Now</p>
</ChildContentComponent>
```

### <a name="template-parameters"></a>템플릿 매개 변수

템플릿 블레이저 구성 요소는 형식 `RenderFragment` 또는 `RenderFragment<T>`의 여러 구성 요소 매개 변수를 정의할 수도 있습니다. a의 `RenderFragment<T>` 매개 변수는 호출될 때 지정할 수 있습니다. 구성 요소에 대한 제네릭 형식 `@typeparam` 매개 변수를 지정하려면 Razor 지시문을 사용합니다.

*심플리스트뷰.면도기*

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

템플릿 구성 요소를 사용하는 경우 매개 변수의 이름과 일치하는 자식 요소를 사용하여 템플릿 매개 변수를 지정할 수 있습니다. 요소로 전달 `RenderFragment<T>` 된 형식의 구성 요소 `context`인수에는 암시적 매개 변수가 있습니다. 자식 요소의 특성을 사용하여 `Context` 이 구현 매개 변수의 이름을 변경할 수 있습니다. 모든 제네릭 형식 매개 변수는 형식 매개 변수의 이름과 일치하는 특성을 사용하여 지정할 수 있습니다. 가능한 경우 형식 매개 변수가 유추됩니다.

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

Blazor 구성 요소는 일반적으로 단일 *.razor* 파일에서 작성됩니다. 그러나 코드 숨김 파일을 사용하여 코드와 태그를 분리할 수도 있습니다. 구성 요소 파일을 사용하려면 구성 요소 파일의 파일 이름과 일치하지만 *.cs* 확장자(Counter.razor.cs)가 추가된 C# 파일을 추가합니다.*Counter.razor.cs* C# 파일을 사용하여 구성요소에 대한 기본 클래스를 정의합니다. 기본 클래스의 이름을 원하는 대로 지정할 수 있지만 클래스의 이름을 구성 요소 클래스와 동일하지만 확장이 추가된 경우()를 `Base` `CounterBase`지정하는 것이 일반적입니다. 구성 요소 기반 클래스도 `ComponentBase`에서 파생되어야 합니다. 그런 다음 Razor 구성 요소 `@inherits` 파일에서 지시문을 추가하여 구성`@inherits CounterBase`요소()에 대한 기본 클래스를 지정합니다.

*카운터.면도기*

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

기본 클래스에서 구성 요소 멤버의 가시성은 `protected` 구성 `public` 요소 클래스에 표시되거나 표시되어야 합니다.

## <a name="additional-resources"></a>추가 리소스

앞의 Blazor 구성 요소의 모든 측면의 철저 한 치료 되지 않습니다. [핵심 면도기 구성 요소를 만들고 사용하는](/aspnet/core/blazor/components)방법에 ASP.NET 자세한 내용은 Blazor 설명서를 참조하십시오.

>[!div class="step-by-step"]
>[이전](app-startup.md)
>[다음](pages-routing-layouts.md)
