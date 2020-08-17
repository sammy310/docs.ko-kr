---
title: 페이지, 라우팅, 레이아웃
description: 에서 페이지 Blazor 를 만들고, 클라이언트 쪽 라우팅을 사용 하 고, 페이지 레이아웃을 관리 하는 방법에 대해 알아봅니다.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/19/2019
ms.openlocfilehash: 714ba0be7c2014895a75250a47e6ce448863eb6c
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267791"
---
# <a name="pages-routing-and-layouts"></a>페이지, 라우팅, 레이아웃

ASP.NET Web Forms 앱은 *.aspx* 파일에 정의 된 페이지로 구성 됩니다. 각 페이지의 주소는 프로젝트의 실제 파일 경로를 기반으로 합니다. 브라우저에서 페이지를 요청 하면 페이지 내용이 서버에서 동적으로 렌더링 됩니다. 페이지의 HTML 태그와 해당 서버 컨트롤 모두에 대 한 렌더링 계정

에서 Blazor 앱의 각 페이지는 일반적으로 하나 이상의 지정 된 경로를 사용 하 여 *razor* 파일에 정의 된 구성 요소입니다. 라우팅은 주로 특정 서버 요청을 포함 하지 않고 클라이언트 쪽에서 발생 합니다. 브라우저는 먼저 앱의 루트 주소에 요청을 만듭니다. `Router`그러면 앱의 루트 구성 요소가 Blazor 탐색 요청 가로채기와 올바른 구성 요소를 처리 합니다.

Blazor 는 *딥 링크*도 지원 합니다. 브라우저에서 앱의 루트 이외의 특정 경로를 요청 하면 딥 링크가 발생 합니다. 서버로 전송 되는 딥 링크에 대 한 요청은 앱으로 라우팅됩니다 Blazor . 그러면 요청 클라이언트 쪽이 올바른 구성 요소로 라우팅됩니다.

ASP.NET Web Forms의 간단한 페이지에는 다음과 같은 태그가 포함 될 수 있습니다.

*이름 .aspx*

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

*Name.aspx.cs*

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

앱의 해당 페이지는 Blazor 다음과 같습니다.

*이름. razor*

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a>페이지 만들기

에서 페이지를 만들려면 Blazor 구성 요소를 만들고 Razor 지시문을 추가 `@page` 하 여 구성 요소에 대 한 경로를 지정 합니다. `@page`지시문은 해당 구성 요소에 추가할 경로 템플릿인 단일 매개 변수를 사용 합니다.

```razor
@page "/counter"
```

경로 템플릿 매개 변수는 필수입니다. ASP.NET Web Forms와 달리 구성 요소에 대 한 경로는 Blazor 파일 위치에서 유추 *되지 않습니다* (나중에 추가 된 기능 일 수 있음).

경로 템플릿 구문은 ASP.NET Web Forms의 라우팅에 사용 되는 것과 동일한 기본 구문입니다. 경로 매개 변수는 중괄호를 사용 하 여 템플릿에 지정 됩니다. Blazor 은 경로 값을 같은 이름의 구성 요소 매개 변수에 바인딩합니다 (대/소문자 구분 안 함).

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

경로 매개 변수 값에 제약 조건을 지정할 수도 있습니다. 예를 들어 제품 ID를로 제한 하려면 다음을 `int` 수행 합니다.

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

에서 지 원하는 경로 제약 조건의 전체 목록은 Blazor [경로 제약 조건](/aspnet/core/blazor/routing#route-constraints)을 참조 하세요.

## <a name="router-component"></a>라우터 구성 요소

에서 라우팅은 Blazor 구성 요소에 의해 처리 됩니다 `Router` . `Router`구성 요소는 일반적으로 앱의 루트 구성 요소 (*응용 프로그램 razor*)에서 사용 됩니다.

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

`Router`구성 요소는 지정 된 및 선택적으로 지정 된에서 라우팅 가능한 구성 요소를 검색 합니다 `AppAssembly` `AdditionalAssemblies` . 브라우저가 탐색 하면는 탐색을 `Router` 가로채서 `Found` 경로가 주소와 일치 하는 경우 추출 된로 매개 변수의 내용을 렌더링 합니다 `RouteData` . 그렇지 않으면가 `Router` 해당 매개 변수를 렌더링 합니다 `NotFound` .

`RouteView`구성 요소는에 지정 된 일치 하는 구성 요소가 있는 `RouteData` 경우 해당 레이아웃을 사용 하 여 렌더링을 처리 합니다. 일치 하는 구성 요소에 레이아웃이 없으면 선택적으로 지정 된 `DefaultLayout` 가 사용 됩니다.

`LayoutView`구성 요소는 지정 된 레이아웃 내에서 자식 콘텐츠를 렌더링 합니다. 이 챕터의 뒷부분에서 레이아웃에 대해 자세히 살펴보겠습니다.

## <a name="navigation"></a>탐색

ASP.NET Web Forms에서는 브라우저에 리디렉션 응답을 반환 하 여 다른 페이지로의 탐색을 트리거합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

에서는 일반적으로 리디렉션 응답을 반환할 수 없습니다 Blazor . Blazor 는 요청-회신 모델을 사용 하지 않습니다. 그러나 JavaScript를 사용할 때와 마찬가지로 브라우저 탐색을 직접 트리거할 수 있습니다.

Blazor`NavigationManager`는 다음과 같은 작업에 사용할 수 있는 서비스를 제공 합니다.

- 현재 브라우저 주소 가져오기
- 기본 주소 가져오기
- 트리거 탐색
- 주소가 변경 되 면 알림 받기

다른 주소로 이동 하려면 메서드를 사용 합니다 `NavigateTo` .

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

모든 멤버에 대 한 설명은 `NavigationManager` [URI 및 탐색 상태 도우미](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers)를 참조 하세요.

## <a name="base-urls"></a>기준 URL

Blazor앱이 기본 경로 아래에 배포 되는 경우 `<base>` work to work 속성에 대 한 태그를 사용 하 여 페이지 메타 데이터에서 기준 URL을 지정 해야 합니다. 응용 프로그램의 호스트 페이지가 Razor를 사용 하 여 서버에서 렌더링 되는 경우 `~/` 구문을 사용 하 여 앱의 기본 주소를 지정할 수 있습니다. 호스트 페이지가 정적 HTML 인 경우에는 기본 URL을 명시적으로 지정 해야 합니다.

```html
<base href="~/" />
```

## <a name="page-layout"></a>페이지 레이아웃

ASP.NET Web Forms의 페이지 레이아웃은 마스터 페이지에서 처리 됩니다. 마스터 페이지는 개별 페이지에서 제공할 수 있는 하나 이상의 콘텐츠 자리 표시자를 사용 하 여 템플릿을 정의 합니다. 마스터 페이지는 *.master* 파일에 정의 되 고 지시문으로 시작 합니다. `<%@ Master %>` *.Master* 파일의 내용은 *.aspx* 페이지와 같이 코딩 되지만 `<asp:ContentPlaceHolder>` 페이지가 콘텐츠를 제공할 수 있는 위치를 표시 하는 컨트롤을 추가 합니다.

*Site.master*

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

에서는 Blazor 레이아웃 구성 요소를 사용 하 여 페이지 레이아웃을 처리 합니다. 레이아웃 구성 요소는에서 상속 하며,이 `LayoutComponentBase` `Body` 속성은 `RenderFragment` 페이지의 콘텐츠를 렌더링 하는 데 사용할 수 있는 형식의 단일 속성을 정의 합니다.

*MainLayout. razor*

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

레이아웃이 있는 페이지가 렌더링 되 면 레이아웃이 해당 속성을 렌더링 하는 위치의 지정 된 레이아웃 내용 내에서 페이지가 렌더링 됩니다 `Body` .

레이아웃을 페이지에 적용 하려면 지시문을 사용 합니다 `@layout` .

```razor
@layout MainLayout
```

*_Imports razor* 파일을 사용 하 여 폴더 및 하위 폴더의 모든 구성 요소에 대 한 레이아웃을 지정할 수 있습니다. 또한 [라우터 구성 요소](#router-component)를 사용 하 여 모든 페이지에 대 한 기본 레이아웃을 지정할 수 있습니다.

마스터 페이지는 여러 콘텐츠 자리 표시자를 정의할 수 있지만의 레이아웃에 Blazor 는 단일 `Body` 속성만 있습니다. 레이아웃 구성 요소에 대 한 이러한 제한 사항은 Blazor 향후 릴리스에서 해결 될 예정입니다.

ASP.NET Web Forms의 마스터 페이지는 중첩할 수 있습니다. 즉, 마스터 페이지에서 마스터 페이지를 사용할 수도 있습니다. 의 레이아웃 구성 요소가 Blazor 중첩 될 수도 있습니다. 레이아웃 구성 요소에 레이아웃 구성 요소를 적용할 수 있습니다. 내부 레이아웃의 콘텐츠는 외부 레이아웃 내에서 렌더링 됩니다.

*ChildLayout. razor*

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

*인덱스. razor*

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

그러면 페이지에 대해 렌더링 된 출력이 다음과 같이 됩니다.

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

의 레이아웃은 Blazor 일반적으로 페이지 ( `<html>` ,, `<body>` 등)에 대 한 루트 HTML 요소를 정의 하지 않습니다 `<head>` . 루트 HTML 요소는 응용 프로그램의 Blazor 초기 HTML 콘텐츠를 렌더링 하는 데 사용 되는 앱의 호스트 페이지에서 대신 정의 됩니다 ( [부트스트랩 Blazor ](project-structure.md#bootstrap-blazor)참조). 호스트 페이지는 주변 태그를 사용 하 여 앱에 대 한 여러 루트 구성 요소를 렌더링할 수 있습니다.

페이지를 비롯 한의 구성 요소 Blazor 는 태그를 렌더링할 수 없습니다 `<script>` . 이 렌더링 제한은 `<script>` 태그를 한 번만 로드 한 다음 변경할 수 없기 때문에 존재 합니다. Razor 구문를 사용 하 여 동적으로 태그를 렌더링 하려고 하면 예기치 않은 동작이 발생할 수 있습니다. 대신 모든 `<script>` 태그를 앱의 호스트 페이지에 추가 해야 합니다.

>[!div class="step-by-step"]
>[이전](components.md)
>[다음](state-management.md)
