---
title: 상태 관리
description: ASP.NET Web Forms 및 Blazor에서 상태를 관리 하는 다양 한 방법을 알아봅니다.
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: bac2f00330113725f09259ca31bdf857a8769f24
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062342"
---
# <a name="state-management"></a><span data-ttu-id="ec87e-103">상태 관리</span><span class="sxs-lookup"><span data-stu-id="ec87e-103">State management</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ec87e-104">상태 관리는 Web Forms 응용 프로그램의 주요 개념으로, 뷰 상태, 세션 상태, 응용 프로그램 상태 및 포스트백 기능을 통해 쉽게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-104">State management is a key concept of Web Forms applications, facilitated through View State, Session State, Application State, and Postback features.</span></span> <span data-ttu-id="ec87e-105">프레임 워크의 이러한 상태 저장 기능은 응용 프로그램에 필요한 상태 관리를 숨기고 응용 프로그램 개발자가 해당 기능을 제공 하는 데 집중할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-105">These stateful features of the framework helped to hide the state management required for an application and allow application developers to focus on delivering their functionality.</span></span> <span data-ttu-id="ec87e-106">ASP.NET Core 및 Blazor를 사용 하는 경우 이러한 기능 중 일부는 재배치 되 고 일부는 완전히 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-106">With ASP.NET Core and Blazor, some of these features have been relocated and some have been removed altogether.</span></span> <span data-ttu-id="ec87e-107">이 장에서는 상태를 유지 관리 하 고 Blazor의 새로운 기능을 사용 하 여 동일한 기능을 제공 하는 방법을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-107">This chapter reviews how to maintain state and deliver the same functionality with the new features in Blazor.</span></span>

## <a name="request-state-management-with-viewstate"></a><span data-ttu-id="ec87e-108">ViewState를 사용 하 여 상태 관리 요청</span><span class="sxs-lookup"><span data-stu-id="ec87e-108">Request state management with ViewState</span></span>

<span data-ttu-id="ec87e-109">Web Forms 응용 프로그램에서 상태 관리를 논의할 때 많은 개발자가 ViewState를 즉시 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-109">When discussing state management in Web Forms application, many developers will immediately think of ViewState.</span></span> <span data-ttu-id="ec87e-110">Web Forms에서 ViewState는 인코딩된 텍스트 블록을 브라우저에 앞뒤로 전송 하 여 HTTP 요청 간의 콘텐츠 상태를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-110">In Web Forms, ViewState manages the state of the content between HTTP requests by sending a large encoded block of text back and forth to the browser.</span></span> <span data-ttu-id="ec87e-111">ViewState 필드는 많은 요소가 포함 된 페이지의 콘텐츠로 인해 잠재적으로 크기가 몇 메가바이트까지 확장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-111">The ViewState field could be overwhelmed with content from a page containing many elements, potentially expanding to several megabytes in size.</span></span>

<span data-ttu-id="ec87e-112">Blazor 서버를 사용 하면 앱에서 서버와 지속적으로 연결을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-112">With Blazor Server, the app maintains an ongoing connection with the server.</span></span> <span data-ttu-id="ec87e-113">*회로*라고 하는 앱의 상태는 연결이 활성 상태인 것으로 간주 되는 동안 서버 메모리에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-113">The app's state, called a *circuit*, is held in server memory while the connection is considered active.</span></span> <span data-ttu-id="ec87e-114">상태는 사용자가 앱 또는 앱의 특정 페이지에서 벗어날 때만 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-114">State will only be disposed when the user navigates away from the app or a particular page in the app.</span></span> <span data-ttu-id="ec87e-115">활성 구성 요소의 모든 멤버는 서버와의 상호 작용 간에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-115">All members of the active components are available between interactions with the server.</span></span>

<span data-ttu-id="ec87e-116">이 기능에는 다음과 같은 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-116">There are several advantages of this feature:</span></span>

- <span data-ttu-id="ec87e-117">구성 요소 상태는 쉽게 사용할 수 있으며 상호 작용 간에 다시 작성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-117">Component state is readily available and not rebuilt between interactions.</span></span>
- <span data-ttu-id="ec87e-118">상태는 브라우저에 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-118">State isn't transmitted to the browser.</span></span>

<span data-ttu-id="ec87e-119">그러나 메모리 내 구성 요소 상태 지 속성에는 다음과 같은 몇 가지 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-119">However, there are some disadvantages to in-memory component state persistence to be aware of:</span></span>

- <span data-ttu-id="ec87e-120">요청 간에 서버가 다시 시작 되 면 상태가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-120">If the server restarts between request, state is lost.</span></span>
- <span data-ttu-id="ec87e-121">응용 프로그램 웹 서버 부하 분산 솔루션은 동일한 브라우저의 모든 요청이 동일한 서버로 반환 되도록 고정 세션을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-121">Your application web server load-balancing solution must include sticky sessions to ensure that all requests from the same browser return to the same server.</span></span> <span data-ttu-id="ec87e-122">요청이 다른 서버로 이동 하면 상태가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-122">If a request goes to a different server, state will be lost.</span></span>
- <span data-ttu-id="ec87e-123">서버에서 구성 요소 상태를 지 속성은 웹 서버에서 메모리가 부족 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-123">Persistence of component state on the server can lead to memory pressure on the web server.</span></span>

<span data-ttu-id="ec87e-124">위의 이유로 인해 구성 요소의 상태를 사용 하 여 서버에 메모리 내에 상주 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ec87e-124">For the preceding reasons, don't rely on just the state of the component to reside in-memory on the server.</span></span> <span data-ttu-id="ec87e-125">응용 프로그램에는 요청 간 데이터를 위한 일부 지원 데이터 저장소도 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-125">Your application should also include some backing data store for data between requests.</span></span> <span data-ttu-id="ec87e-126">이 전략의 몇 가지 간단한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-126">Some simple examples of this strategy:</span></span>

- <span data-ttu-id="ec87e-127">쇼핑 카트 응용 프로그램에서 카트에 추가 된 새 항목의 콘텐츠를 데이터베이스 레코드에 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-127">In a shopping cart application, persist the content of new items added to the cart in a database record.</span></span> <span data-ttu-id="ec87e-128">서버의 상태가 손실 된 경우 데이터베이스 레코드에서 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-128">If the state on the server is lost, you can reconstitute it from the database records.</span></span>
- <span data-ttu-id="ec87e-129">다중 파트 웹 양식에서 사용자는 응용 프로그램이 각 요청 간에 값을 기억할 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-129">In a multi-part web form, your users will expect your application to remember values between each request.</span></span> <span data-ttu-id="ec87e-130">여러 부분으로 구성 된 폼이 완료 될 때 최종 폼 응답 구조에 데이터를 인출 하 고 어셈블할 수 있도록 각 사용자의 게시물 간에 데이터를 데이터 저장소에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-130">Write the data between each of your user's posts to a data store so that they can be fetched and assembled into the final form response structure when the multi-part form is completed.</span></span>

<span data-ttu-id="ec87e-131">Blazor apps에서 상태를 관리 하는 방법에 대 한 자세한 내용은 [ASP.NET Core Blazor state management](/aspnet/core/blazor/state-management)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec87e-131">For additional details on managing state in Blazor apps, see [ASP.NET Core Blazor state management](/aspnet/core/blazor/state-management).</span></span>

## <a name="maintain-state-with-session"></a><span data-ttu-id="ec87e-132">세션을 사용 하 여 상태 유지</span><span class="sxs-lookup"><span data-stu-id="ec87e-132">Maintain state with Session</span></span>

<span data-ttu-id="ec87e-133">Web Forms 개발자는 사전 개체를 사용 하 여 현재 작동 중인 사용자에 대 한 정보를 유지할 수 있습니다 <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ec87e-133">Web Forms developers could maintain information about the currently acting user with the <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> dictionary object.</span></span> <span data-ttu-id="ec87e-134">문자열 키가 있는 개체를에 추가 하는 것은 쉽지만 `Session` 사용자가 응용 프로그램과 상호 작용 하는 동안 나중에 해당 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-134">It's easy enough to add an object with a string key to the `Session`, and that object would be available at a later time during the user's interactions with the application.</span></span> <span data-ttu-id="ec87e-135">HTTP와 상호 작용 하는 관리를 제거 하려고 하면 개체를 사용 하 여 `Session` 상태를 쉽게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-135">In an attempt to eliminate managing interacting with HTTP, the `Session` object made it easy to maintain state.</span></span>

<span data-ttu-id="ec87e-136">.NET Framework 개체의 서명이 `Session` ASP.NET Core 개체와 다릅니다 `Session` .</span><span class="sxs-lookup"><span data-stu-id="ec87e-136">The signature of the .NET Framework `Session` object isn't the same as the ASP.NET Core `Session` object.</span></span> <span data-ttu-id="ec87e-137">새 세션 상태 기능을 마이그레이션하고 사용 하도록 결정 하기 전에 [새 ASP.NET Core 세션에 대 한 설명서를](/dotnet/api/microsoft.aspnetcore.http.isession) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec87e-137">Consider [the documentation for the new ASP.NET Core Session](/dotnet/api/microsoft.aspnetcore.http.isession) before deciding to migrate and use the new session state feature.</span></span>

<span data-ttu-id="ec87e-138">세션은 ASP.NET Core 및 Blazor 서버에서 사용할 수 있지만 데이터 리포지토리의 데이터를 적절 하 게 저장 하는 데 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-138">Session is available in ASP.NET Core and Blazor Server, but is discouraged from use in favor of storing data in a data repository appropriately.</span></span> <span data-ttu-id="ec87e-139">방문자가 개인 정보 문제로 인해 응용 프로그램에서 HTTP 쿠키 사용을 거부 하는 경우에도 세션 상태가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-139">Session state is also not functional if visitors decline the use HTTP cookies in your application due to privacy concerns.</span></span>

<span data-ttu-id="ec87e-140">ASP.NET Core 및 세션 상태 구성은 [ASP.NET Core 문서의 세션 및 상태 관리](/aspnet/core/fundamentals/app-state#session-state)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-140">Configuration for ASP.NET Core and Session state is available in the [Session and state management in ASP.NET Core article](/aspnet/core/fundamentals/app-state#session-state).</span></span>

## <a name="application-state"></a><span data-ttu-id="ec87e-141">애플리케이션 상태</span><span class="sxs-lookup"><span data-stu-id="ec87e-141">Application state</span></span>

<span data-ttu-id="ec87e-142">`Application`Web Forms 프레임 워크의 개체는 응용 프로그램 범위 구성과 상태를 상호 작용 하기 위한 대규모의 다중 요청 리포지토리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-142">The `Application` object in the Web Forms framework provides a massive, cross-request repository for interacting with application-scope configuration and state.</span></span> <span data-ttu-id="ec87e-143">응용 프로그램 상태는 요청 하는 사용자에 관계 없이 모든 요청에서 참조 되는 다양 한 응용 프로그램 구성 속성을 저장 하는 데 적합 한 위치 였습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-143">Application state was an ideal place to store various application configuration properties that would be referenced by all requests, regardless of the user making the request.</span></span> <span data-ttu-id="ec87e-144">개체의 문제는 `Application` 데이터가 여러 서버에 유지 되지 않았기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-144">The problem with the `Application` object was that data didn't persist across multiple servers.</span></span> <span data-ttu-id="ec87e-145">응용 프로그램 개체의 상태가 다시 시작 사이에서 손실 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-145">The state of the application object was lost between restarts.</span></span>

<span data-ttu-id="ec87e-146">와 마찬가지로 `Session` 여러 서버 인스턴스에서 액세스할 수 있는 영구 백업 저장소로 데이터를 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-146">As with `Session`, it's recommended that data move to a persistent backing store that could be accessed by multiple server instances.</span></span> <span data-ttu-id="ec87e-147">요청 및 사용자 간에 액세스할 수 있는 휘발성 데이터가 있는 경우이 정보나 상호 작용이 필요한 구성 요소에 삽입할 수 있는 단일 서비스에 해당 데이터를 쉽게 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-147">If there is volatile data that you would like to be able to access across requests and users, you could easily store it in a singleton service that can be injected into components that require this information or interaction.</span></span>

<span data-ttu-id="ec87e-148">응용 프로그램 상태를 유지 관리 하는 개체를 생성 하는 것은 다음 구현과 유사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-148">The construction of an object to maintain application state and its consumption could resemble the following implementation:</span></span>

```csharp
public class MyApplicationState
{
    public int VisitorCounter { get; private set; } = 0;

    public void IncrementCounter() => VisitorCounter += 1;
}
```

```csharp
app.AddSingleton<MyApplicationState>();
```

```razor
@inject MyApplicationState AppState

<label>Total Visitors: @AppState.VisitorCounter</label>
```

<span data-ttu-id="ec87e-149">`MyApplicationState`개체는 서버에서 한 번만 만들어지므로 값은 `VisitorCounter` 인출 되 고 구성 요소의 레이블에서 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-149">The `MyApplicationState` object is created only once on the server, and the value `VisitorCounter` is fetched and output in the component's label.</span></span> <span data-ttu-id="ec87e-150">지 속성 `VisitorCounter` 및 확장성을 위해 지원 되는 데이터 저장소에서 값을 유지 하 고 검색 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-150">The `VisitorCounter` value should be persisted and retrieved from a backing data store for durability and scalability.</span></span>

## <a name="in-the-browser"></a><span data-ttu-id="ec87e-151">브라우저에서</span><span class="sxs-lookup"><span data-stu-id="ec87e-151">In the browser</span></span>

<span data-ttu-id="ec87e-152">응용 프로그램 데이터는 나중에 사용할 수 있도록 사용자의 장치에 클라이언트 쪽으로 저장 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-152">Application data can also be stored client-side on the user's device so that is available later.</span></span> <span data-ttu-id="ec87e-153">사용자 브라우저의 여러 범위에 있는 데이터의 지 속성을 허용 하는 두 가지 브라우저 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-153">There are two browser features that allow for persistence of data in different scopes of the user's browser:</span></span>

- <span data-ttu-id="ec87e-154">`localStorage`-사용자의 전체 브라우저로 범위가 한정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-154">`localStorage` - scoped to the user's entire browser.</span></span> <span data-ttu-id="ec87e-155">페이지를 다시 로드 하는 경우 브라우저를 닫았다가 다시 열거나 동일한 URL을 사용 하 여 다른 탭을 열면 브라우저에서 동일 하 게 제공 됩니다. `localStorage`</span><span class="sxs-lookup"><span data-stu-id="ec87e-155">If the page is reloaded, the browser is closed and reopened, or another tab is opened with the same URL then the same `localStorage` is provided by the browser</span></span>
- <span data-ttu-id="ec87e-156">`sessionStorage`-사용자의 현재 브라우저 탭으로 범위가 지정 됩니다. 탭이 다시 로드 되 면 상태는 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-156">`sessionStorage` - scoped to the user's current browser tab. If the tab is reloaded, the state persists.</span></span> <span data-ttu-id="ec87e-157">그러나 사용자가 응용 프로그램에 다른 탭을 열거나 브라우저를 닫고 다시 열면 상태가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-157">However, if the user opens another tab to your application or closes and reopens the browser the state is lost.</span></span>

<span data-ttu-id="ec87e-158">이러한 기능과 상호 작용 하는 사용자 지정 JavaScript 코드를 작성 하거나이 기능을 제공 하는 데 사용할 수 있는 여러 NuGet 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-158">You can write some custom JavaScript code to interact with these features, or there are a number of NuGet packages that you can use that provide this functionality.</span></span> <span data-ttu-id="ec87e-159">이러한 패키지 중 하나는 [AspNetCore. ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec87e-159">One such package is [Microsoft.AspNetCore.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage).</span></span>

<span data-ttu-id="ec87e-160">이 패키지를 활용 하 여 및와 상호 작용 하는 방법에 대 한 지침은 `localStorage` `sessionStorage` [Blazor State Management](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec87e-160">For instructions on utilizing this package to interact with `localStorage` and `sessionStorage`, see the [Blazor State Management](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) article.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ec87e-161">[이전](pages-routing-layouts.md)
>[다음](forms-validation.md)</span><span class="sxs-lookup"><span data-stu-id="ec87e-161">[Previous](pages-routing-layouts.md)
[Next](forms-validation.md)</span></span>
