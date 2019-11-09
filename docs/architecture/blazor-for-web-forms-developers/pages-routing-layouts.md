---
title: 페이지, 라우팅, 레이아웃
description: Blazor에서 페이지를 만들고 클라이언트 쪽 라우팅을 사용 하며 페이지 레이아웃을 관리 하는 방법에 대해 알아봅니다.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: 693eee270a46ccb56ed5fef8fced1d4a1cf1974f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "73841236"
---
# <a name="pages-routing-and-layouts"></a><span data-ttu-id="4ddc6-103">페이지, 라우팅, 레이아웃</span><span class="sxs-lookup"><span data-stu-id="4ddc6-103">Pages, routing, and layouts</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="4ddc6-104">ASP.NET Web Forms 앱은 *.aspx* 파일에 정의 된 페이지로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-104">ASP.NET Web Forms apps are composed of pages defined in *.aspx* files.</span></span> <span data-ttu-id="4ddc6-105">각 페이지의 주소는 프로젝트의 실제 파일 경로를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-105">Each page's address is based on its physical file path in the project.</span></span> <span data-ttu-id="4ddc6-106">브라우저에서 페이지를 요청 하면 페이지 내용이 서버에서 동적으로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-106">When a browser makes a request to the page, the contents of the page are dynamically rendered on the server.</span></span> <span data-ttu-id="4ddc6-107">페이지의 HTML 태그와 해당 서버 컨트롤 모두에 대 한 렌더링 계정</span><span class="sxs-lookup"><span data-stu-id="4ddc6-107">The rendering accounts for both the page's HTML markup and its server controls.</span></span>

<span data-ttu-id="4ddc6-108">Blazor에서 앱의 각 페이지는 일반적으로 하나 이상의 지정 된 경로를 사용 하 여 *razor* 파일에 정의 된 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-108">In Blazor, each page in the app is a component, typically defined in a *.razor* file, with one or more specified routes.</span></span> <span data-ttu-id="4ddc6-109">라우팅은 주로 특정 서버 요청을 포함 하지 않고 클라이언트 쪽에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-109">Routing mostly happens client-side without involving a specific server request.</span></span> <span data-ttu-id="4ddc6-110">브라우저는 먼저 앱의 루트 주소에 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-110">The browser first makes a request to the root address of the app.</span></span> <span data-ttu-id="4ddc6-111">그러면 Blazor 앱의 루트 `Router` 구성 요소가 탐색 요청 가로채기와 올바른 구성 요소를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-111">A root `Router` component in the Blazor app then handles intercepting navigation requests and them to the correct component.</span></span>

<span data-ttu-id="4ddc6-112">Blazor는 *딥 링크*도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-112">Blazor also supports *deep linking*.</span></span> <span data-ttu-id="4ddc6-113">브라우저에서 앱의 루트 이외의 특정 경로를 요청 하면 딥 링크가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-113">Deep linking occurs when the browser makes a request to a specific route other than the root of the app.</span></span> <span data-ttu-id="4ddc6-114">서버로 전송 되는 딥 링크에 대 한 요청은 Blazor 앱으로 라우팅됩니다. 그러면 요청 클라이언트 쪽이 올바른 구성 요소로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-114">Requests for deep links sent to the server are routed to the Blazor app, which then routes the request client-side to the correct component.</span></span>

<span data-ttu-id="4ddc6-115">ASP.NET Web Forms의 간단한 페이지에는 다음과 같은 태그가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-115">A simple page in ASP.NET Web Forms might contain the following markup:</span></span>

<span data-ttu-id="4ddc6-116">*이름 .aspx*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-116">*Name.aspx*</span></span>

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

<span data-ttu-id="4ddc6-117">*Name.aspx.cs*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-117">*Name.aspx.cs*</span></span>

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

<span data-ttu-id="4ddc6-118">Blazor 앱의 해당 페이지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-118">The equivalent page in a Blazor app would look like this:</span></span>

<span data-ttu-id="4ddc6-119">*이름. razor*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-119">*Name.razor*</span></span>

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

## <a name="create-pages"></a><span data-ttu-id="4ddc6-120">페이지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ddc6-120">Create pages</span></span>

<span data-ttu-id="4ddc6-121">Blazor에서 페이지를 만들려면 구성 요소를 만들고 `@page` Razor 지시어를 추가 하 여 구성 요소에 대 한 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-121">To create a page in Blazor, create a component and add the `@page` Razor directive to specify the route for the component.</span></span> <span data-ttu-id="4ddc6-122">`@page` 지시어는 해당 구성 요소에 추가할 경로 템플릿인 단일 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-122">The `@page` directive takes a single parameter, which is the route template to add to that component.</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="4ddc6-123">경로 템플릿 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-123">The route template parameter is required.</span></span> <span data-ttu-id="4ddc6-124">ASP.NET Web Forms와 달리 Blazor 구성 요소에 대 한 경로는 파일 위치에서 유추 *되지 않습니다* (이 기능은 나중에 추가 될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="4ddc6-124">Unlike ASP.NET Web Forms, the route to a Blazor component *isn't* inferred from its file location (although that may be a feature added in the future).</span></span>

<span data-ttu-id="4ddc6-125">경로 템플릿 구문은 ASP.NET Web Forms의 라우팅에 사용 되는 것과 동일한 기본 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-125">The route template syntax is the same basic syntax used for routing in ASP.NET Web Forms.</span></span> <span data-ttu-id="4ddc6-126">경로 매개 변수는 중괄호를 사용 하 여 템플릿에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-126">Route parameters are specified in the template using braces.</span></span> <span data-ttu-id="4ddc6-127">Blazor는 경로 값을 같은 이름의 구성 요소 매개 변수에 바인딩합니다 (대/소문자 구분 안 함).</span><span class="sxs-lookup"><span data-stu-id="4ddc6-127">Blazor will bind route values to component parameters with the same name (case-insensitive).</span></span>

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

<span data-ttu-id="4ddc6-128">경로 매개 변수 값에 제약 조건을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-128">You can also specify constraints on the value of the route parameter.</span></span> <span data-ttu-id="4ddc6-129">예를 들어 제품 ID를 `int`으로 제한 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-129">For example, to constrain the product ID to be an `int`:</span></span>

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

<span data-ttu-id="4ddc6-130">Blazor에서 지 원하는 경로 제약 조건의 전체 목록은 [경로 제약 조건](/aspnet/core/blazor/routing#route-constraints)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-130">For a full list of the route constraints supported by Blazor, see [Route constraints](/aspnet/core/blazor/routing#route-constraints).</span></span>

## <a name="router-component"></a><span data-ttu-id="4ddc6-131">라우터 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4ddc6-131">Router component</span></span>

<span data-ttu-id="4ddc6-132">Blazor의 라우팅은 `Router` 구성 요소에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-132">Routing in Blazor is handled by the `Router` component.</span></span> <span data-ttu-id="4ddc6-133">`Router` 구성 요소는 일반적으로 앱의 루트 구성 요소 (*응용 프로그램 razor*)에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-133">The `Router` component is typically used in the app's root component (*App.razor*).</span></span>

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

<span data-ttu-id="4ddc6-134">`Router` 구성 요소는 지정 된 `AppAssembly` 및 선택적으로 지정 된 `AdditionalAssemblies`에서 라우팅 가능한 구성 요소를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-134">The `Router` component discovers the routable components in the specified `AppAssembly` and in the optionally specified `AdditionalAssemblies`.</span></span> <span data-ttu-id="4ddc6-135">브라우저가 탐색 하는 경우 `Router`은 탐색을 가로채서 경로가 주소와 일치 하는 경우 추출 된 `RouteData`를 사용 하 여 `Found` 매개 변수의 내용을 렌더링 합니다. 그렇지 않은 경우 `Router` `NotFound` 매개 변수를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-135">When the browser navigates, the `Router` intercepts the navigation and renders the contents of its `Found` parameter with the extracted `RouteData` if a route matches the address, otherwise the `Router` renders its `NotFound` parameter.</span></span>

<span data-ttu-id="4ddc6-136">`RouteView` 구성 요소는 `RouteData`에 지정 된 일치 하는 구성 요소가 있는 경우 해당 레이아웃과의 렌더링을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-136">The `RouteView` component handles rendering the matched component specified by the `RouteData` with its layout if it has one.</span></span> <span data-ttu-id="4ddc6-137">일치 하는 구성 요소에 레이아웃이 없으면 선택적으로 지정 된 `DefaultLayout`이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-137">If the matched component doesn't have a layout, then the optionally specified `DefaultLayout` is used.</span></span>

<span data-ttu-id="4ddc6-138">`LayoutView` 구성 요소는 지정 된 레이아웃 내에서 자식 콘텐츠를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-138">The `LayoutView` component renders its child content within the specified layout.</span></span> <span data-ttu-id="4ddc6-139">이 챕터의 뒷부분에서 레이아웃에 대해 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-139">We'll look at layouts more in detail later in this chapter.</span></span>

## <a name="navigation"></a><span data-ttu-id="4ddc6-140">탐색</span><span class="sxs-lookup"><span data-stu-id="4ddc6-140">Navigation</span></span>

<span data-ttu-id="4ddc6-141">ASP.NET Web Forms에서는 브라우저에 리디렉션 응답을 반환 하 여 다른 페이지로의 탐색을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-141">In ASP.NET Web Forms, you trigger navigation to a different page by returning a redirect response to the browser.</span></span> <span data-ttu-id="4ddc6-142">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-142">For example:</span></span>

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

<span data-ttu-id="4ddc6-143">일반적으로 Blazor에서 리디렉션 응답을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-143">Returning a redirect response isn't typically possible in Blazor.</span></span> <span data-ttu-id="4ddc6-144">Blazor는 요청-회신 모델을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-144">Blazor doesn't use a request-reply model.</span></span> <span data-ttu-id="4ddc6-145">그러나 JavaScript를 사용할 때와 마찬가지로 브라우저 탐색을 직접 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-145">You can, however, trigger browser navigations directly, as you can with JavaScript.</span></span>

<span data-ttu-id="4ddc6-146">Blazor는 다음과 같은 작업에 사용할 수 있는 `NavigationManager` 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-146">Blazor provides a `NavigationManager` service that can be used to:</span></span>

- <span data-ttu-id="4ddc6-147">현재 브라우저 주소 가져오기</span><span class="sxs-lookup"><span data-stu-id="4ddc6-147">Get the current browser address</span></span>
- <span data-ttu-id="4ddc6-148">기본 주소 가져오기</span><span class="sxs-lookup"><span data-stu-id="4ddc6-148">Get the base address</span></span>
- <span data-ttu-id="4ddc6-149">트리거 탐색</span><span class="sxs-lookup"><span data-stu-id="4ddc6-149">Trigger navigations</span></span>
- <span data-ttu-id="4ddc6-150">주소가 변경 되 면 알림 받기</span><span class="sxs-lookup"><span data-stu-id="4ddc6-150">Get notified when the address changes</span></span>

<span data-ttu-id="4ddc6-151">다른 주소로 이동 하려면 `NavigateTo` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-151">To navigate to a different address, use the `NavigateTo` method:</span></span>

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

<span data-ttu-id="4ddc6-152">모든 `NavigationManager` 멤버에 대 한 설명은 [URI 및 탐색 상태 도우미](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-152">For a description of all `NavigationManager` members, see [URI and navigation state helpers](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span></span>

## <a name="base-urls"></a><span data-ttu-id="4ddc6-153">기본 Url</span><span class="sxs-lookup"><span data-stu-id="4ddc6-153">Base URLs</span></span>

<span data-ttu-id="4ddc6-154">Blazor 앱이 기본 경로 아래에 배포 되는 경우 work to work 속성의 `<base>` 태그를 사용 하 여 페이지 메타 데이터에서 기준 URL을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-154">If your Blazor app is deployed under a base path, then you need to specify the base URL in the page metadata using the `<base>` tag for routing to work property.</span></span> <span data-ttu-id="4ddc6-155">응용 프로그램의 호스트 페이지가 Razor를 사용 하 여 서버에서 렌더링 되는 경우 `~/` 구문을 사용 하 여 앱의 기본 주소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-155">If the host page for the app is server-rendered using Razor, then you can use the `~/` syntax to specify the app's base address.</span></span> <span data-ttu-id="4ddc6-156">호스트 페이지가 정적 HTML 인 경우에는 기본 URL을 명시적으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-156">If the host page is static HTML, then you need to specify the base URL explicitly.</span></span>

```html
<base href="~/" />
```

## <a name="page-layout"></a><span data-ttu-id="4ddc6-157">페이지 레이아웃</span><span class="sxs-lookup"><span data-stu-id="4ddc6-157">Page layout</span></span>

<span data-ttu-id="4ddc6-158">ASP.NET Web Forms의 페이지 레이아웃은 마스터 페이지에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-158">Page layout in ASP.NET Web Forms is handled by Master Pages.</span></span> <span data-ttu-id="4ddc6-159">마스터 페이지는 개별 페이지에서 제공할 수 있는 하나 이상의 콘텐츠 자리 표시자를 사용 하 여 템플릿을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-159">Master Pages define a template with one or more content placeholders that can then be supplied by individual pages.</span></span> <span data-ttu-id="4ddc6-160">마스터 페이지는 *.master* 파일에 정의 되 고 `<%@ Master %>` 지시문으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-160">Master Pages are defined in *.master* files and start with the `<%@ Master %>` directive.</span></span> <span data-ttu-id="4ddc6-161">*.Master* 파일의 내용은 *.aspx* 페이지와 같이 코딩 되지만, `<asp:ContentPlaceHolder>` 컨트롤을 추가 하 여 페이지가 콘텐츠를 제공할 수 있는 위치를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-161">The content of the *.master* files is coded as you would an *.aspx* page, but with the addition of `<asp:ContentPlaceHolder>` controls to mark where pages can supply content.</span></span>

<span data-ttu-id="4ddc6-162">*사이트 마스터*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-162">*Site.master*</span></span>

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

<span data-ttu-id="4ddc6-163">Blazor에서는 레이아웃 구성 요소를 사용 하 여 페이지 레이아웃을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-163">In Blazor, you handle page layout using layout components.</span></span> <span data-ttu-id="4ddc6-164">레이아웃 구성 요소는 `LayoutComponentBase`에서 상속 하며,이 속성은 페이지의 내용을 렌더링 하는 데 사용할 수 있는 `RenderFragment`형식의 단일 `Body` 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-164">Layout components inherit from `LayoutComponentBase`, which defines a single `Body` property of type `RenderFragment`, which can be used to render the contents of the page.</span></span>

<span data-ttu-id="4ddc6-165">*MainLayout. razor*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-165">*MainLayout.razor*</span></span>

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

<span data-ttu-id="4ddc6-166">레이아웃이 있는 페이지가 렌더링 되 면 레이아웃이 해당 `Body` 속성을 렌더링 하는 위치에서 지정 된 레이아웃의 내용 내에 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-166">When the page with a layout is rendered, the page is rendered within the contents of the specified layout at the location where the layout renders its `Body` property.</span></span>

<span data-ttu-id="4ddc6-167">페이지에 레이아웃을 적용 하려면 `@layout` 지시문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-167">To apply a layout to a page, use the `@layout` directive:</span></span>

```razor
@layout MainLayout
```

<span data-ttu-id="4ddc6-168">*_Imports razor* 파일을 사용 하 여 폴더 및 하위 폴더의 모든 구성 요소에 대 한 레이아웃을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-168">You can specify the layout for all components in a folder and subfolders using an *_Imports.razor* file.</span></span> <span data-ttu-id="4ddc6-169">또한 [라우터 구성 요소](#router-component)를 사용 하 여 모든 페이지에 대 한 기본 레이아웃을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-169">You can also specify a default layout for all your pages using the [Router component](#router-component).</span></span>

<span data-ttu-id="4ddc6-170">마스터 페이지는 여러 콘텐츠 자리 표시자를 정의할 수 있지만 Blazor의 레이아웃에는 단일 `Body` 속성만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-170">Master Pages can define multiple content placeholders, but layouts in Blazor only have a single `Body` property.</span></span> <span data-ttu-id="4ddc6-171">Blazor 레이아웃 구성 요소에 대 한 이러한 제한 사항은 향후 릴리스에서 해결 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-171">This limitation of Blazor layout components will hopefully be addressed in a future release.</span></span>

<span data-ttu-id="4ddc6-172">ASP.NET Web Forms의 마스터 페이지는 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-172">Master Pages in ASP.NET Web Forms can be nested.</span></span> <span data-ttu-id="4ddc6-173">즉, 마스터 페이지에서 마스터 페이지를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-173">That is, a Master Page may also use a Master Page.</span></span> <span data-ttu-id="4ddc6-174">Blazor의 레이아웃 구성 요소가 중첩 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-174">Layout components in Blazor may be nested too.</span></span> <span data-ttu-id="4ddc6-175">레이아웃 구성 요소에 레이아웃 구성 요소를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-175">You can apply a layout component to a layout component.</span></span> <span data-ttu-id="4ddc6-176">내부 레이아웃의 콘텐츠는 외부 레이아웃 내에서 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-176">The contents of the inner layout will be rendered within the outer layout.</span></span>

<span data-ttu-id="4ddc6-177">*ChildLayout. razor*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-177">*ChildLayout.razor*</span></span>

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

<span data-ttu-id="4ddc6-178">*인덱스. razor*</span><span class="sxs-lookup"><span data-stu-id="4ddc6-178">*Index.razor*</span></span>

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

<span data-ttu-id="4ddc6-179">그러면 페이지에 대해 렌더링 된 출력이 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-179">The rendered output for the page would then be:</span></span>

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

<span data-ttu-id="4ddc6-180">Blazor의 레이아웃은 일반적으로 페이지에 대 한 루트 HTML 요소 (`<html>`, `<body>`, `<head>`등)를 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-180">Layouts in Blazor don't typically define the root HTML elements for a page (`<html>`, `<body>`, `<head>`, and so on).</span></span> <span data-ttu-id="4ddc6-181">루트 HTML 요소는 응용 프로그램의 초기 HTML 콘텐츠를 렌더링 하는 데 사용 되는 Blazor 앱의 호스트 페이지에서 대신 정의 됩니다 ( [부트스트랩 Blazor](project-structure.md#bootstrap-blazor)참조).</span><span class="sxs-lookup"><span data-stu-id="4ddc6-181">The root HTML elements are instead defined in a Blazor app's host page, which is used to render the initial HTML content for the app (see [Bootstrap Blazor](project-structure.md#bootstrap-blazor)).</span></span> <span data-ttu-id="4ddc6-182">호스트 페이지는 주변 태그를 사용 하 여 앱에 대 한 여러 루트 구성 요소를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-182">The host page can render multiple root components for the app with surrounding markup.</span></span>

<span data-ttu-id="4ddc6-183">페이지를 포함 하 여 Blazor의 구성 요소는 `<script>` 태그를 렌더링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-183">Components in Blazor, including pages, can't render `<script>` tags.</span></span> <span data-ttu-id="4ddc6-184">이 렌더링 제한은 `<script>` 태그를 한 번만 로드 한 다음 변경할 수 없기 때문에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-184">This rendering restriction exists because `<script>` tags get loaded once and then can't be changed.</span></span> <span data-ttu-id="4ddc6-185">Razor 구문를 사용 하 여 동적으로 태그를 렌더링 하려고 하면 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-185">Unexpected behavior may occur if you try to render the tags dynamically using Razor syntax.</span></span> <span data-ttu-id="4ddc6-186">대신 모든 `<script>` 태그를 앱의 호스트 페이지에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddc6-186">Instead, all `<script>` tags should be added to the app's host page.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4ddc6-187">[이전](components.md)
>[다음](state-management.md)</span><span class="sxs-lookup"><span data-stu-id="4ddc6-187">[Previous](components.md)
[Next](state-management.md)</span></span>
