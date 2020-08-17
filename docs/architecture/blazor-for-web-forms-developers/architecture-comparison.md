---
title: ASP.NET Web Forms 및의 아키텍처 비교 Blazor
description: ASP.NET의 아키텍처가 Web Forms 하 고 비교 하는 방법을 알아봅니다 Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 9a8e78338aff53002647a10ed9007296e4682b5a
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267713"
---
# <a name="architecture-comparison-of-aspnet-web-forms-and-no-locblazor"></a><span data-ttu-id="c497e-103">ASP.NET Web Forms 및의 아키텍처 비교 Blazor</span><span class="sxs-lookup"><span data-stu-id="c497e-103">Architecture comparison of ASP.NET Web Forms and Blazor</span></span>

<span data-ttu-id="c497e-104">ASP.NET Web Forms 하 고 Blazor 개념은 매우 비슷하지만, 작업 방식에는 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-104">While ASP.NET Web Forms and Blazor have many similar concepts, there are differences in how they work.</span></span> <span data-ttu-id="c497e-105">이 장에서는 ASP.NET Web Forms 및의 내부 기능과 아키텍처를 검사 합니다 Blazor .</span><span class="sxs-lookup"><span data-stu-id="c497e-105">This chapter examines the inner workings and architectures of ASP.NET Web Forms and Blazor.</span></span>

## <a name="aspnet-web-forms"></a><span data-ttu-id="c497e-106">ASP.NET 웹 양식</span><span class="sxs-lookup"><span data-stu-id="c497e-106">ASP.NET Web Forms</span></span>

<span data-ttu-id="c497e-107">ASP.NET Web Forms 프레임 워크는 페이지 중심 아키텍처를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-107">The ASP.NET Web Forms framework is based on a page-centric architecture.</span></span> <span data-ttu-id="c497e-108">앱의 특정 위치에 대 한 각 HTTP 요청은 ASP.NET 응답 하는 별도의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-108">Each HTTP request for a location in the app is a separate page with which ASP.NET responds.</span></span> <span data-ttu-id="c497e-109">페이지가 요청 되 면 브라우저의 내용이 요청 된 페이지의 결과로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-109">As pages are requested, the contents of the browser are replaced with the results of the page requested.</span></span>

<span data-ttu-id="c497e-110">페이지는 다음 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-110">Pages consist of the following components:</span></span>

- <span data-ttu-id="c497e-111">HTML 태그</span><span class="sxs-lookup"><span data-stu-id="c497e-111">HTML markup</span></span>
- <span data-ttu-id="c497e-112">C# 또는 Visual Basic 코드</span><span class="sxs-lookup"><span data-stu-id="c497e-112">C# or Visual Basic code</span></span>
- <span data-ttu-id="c497e-113">논리 및 이벤트 처리 기능을 포함 하는 코드를 포함 하는 클래스</span><span class="sxs-lookup"><span data-stu-id="c497e-113">A code-behind class containing logic and event-handling capabilities</span></span>
- <span data-ttu-id="c497e-114">컨트롤</span><span class="sxs-lookup"><span data-stu-id="c497e-114">Controls</span></span>

<span data-ttu-id="c497e-115">컨트롤은 프로그래밍 방식으로 페이지에 배치 하 고 상호 작용할 수 있는 재사용 가능한 웹 UI 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-115">Controls are reusable units of web UI that can be programmatically placed and interacted with on a page.</span></span> <span data-ttu-id="c497e-116">페이지는 태그, 컨트롤 및 일부 코드를 포함 하는 *.aspx* 로 끝나는 파일로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-116">Pages are composed of files that end with *.aspx* containing markup, controls, and some code.</span></span> <span data-ttu-id="c497e-117">코드를 사용 하는 클래스는 사용 되는 프로그래밍 언어에 따라 기본 이름 및 *aspx.cs* 또는 *.aspx* 확장명이 동일한 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-117">The code-behind classes are in files with the same base name and an *.aspx.cs* or *.aspx.vb* extension, depending on the programming language used.</span></span> <span data-ttu-id="c497e-118">흥미롭게도 웹 서버는 *.aspx* 파일의 내용을 해석 하 고 변경 될 때마다 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-118">Interestingly, the web server interprets contents of the *.aspx* files and compiles them whenever they change.</span></span> <span data-ttu-id="c497e-119">웹 서버가 이미 실행 되 고 있는 경우에도이 재컴파일을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-119">This recompilation occurs even if the web server is already running.</span></span>

<span data-ttu-id="c497e-120">컨트롤은 태그를 사용 하 여 빌드하고 사용자 정의 컨트롤로 배달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-120">Controls can be built with markup and delivered as user controls.</span></span> <span data-ttu-id="c497e-121">사용자 정의 컨트롤은 클래스에서 파생 `UserControl` 되며 페이지와 비슷한 구조를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-121">A user control derives from the `UserControl` class and has a similar structure to the Page.</span></span> <span data-ttu-id="c497e-122">사용자 정의 컨트롤에 대 한 태그는 *.ascx* 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-122">Markup for user controls is stored in an *.ascx* file.</span></span> <span data-ttu-id="c497e-123">함께 제공 되는 코드 숨김이 있는 클래스는 *ascx.cs* 또는 *.ascx .vb* 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-123">An accompanying code-behind class resides in an *.ascx.cs* or *.ascx.vb* file.</span></span> <span data-ttu-id="c497e-124">`WebControl`또는 기본 클래스에서 상속 하 여 코드를 사용 하 여 컨트롤을 완전히 빌드할 수도 있습니다 `CompositeControl` .</span><span class="sxs-lookup"><span data-stu-id="c497e-124">Controls can also be built completely with code, by inheriting from either the `WebControl` or `CompositeControl` base class.</span></span>

<span data-ttu-id="c497e-125">페이지에는 광범위 한 이벤트 수명 주기도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-125">Pages also have an extensive event lifecycle.</span></span> <span data-ttu-id="c497e-126">각 페이지는 ASP.NET 런타임이 각 요청에 대해 페이지의 코드를 실행할 때 발생 하는 초기화, 로드, prerender 및 unload 이벤트에 대 한 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-126">Each page raises events for the initialization, load, prerender, and unload events that occur as the ASP.NET runtime executes the page's code for each request.</span></span>

<span data-ttu-id="c497e-127">페이지의 컨트롤은 일반적으로 컨트롤을 표시 한 동일한 페이지에 다시 게시 되 고, 라는 숨겨진 폼 필드의 페이로드를 함께 수행 `ViewState` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-127">Controls on a Page typically post-back to the same page that presented the control, and carry along with them a payload from a hidden form field called `ViewState`.</span></span> <span data-ttu-id="c497e-128">필드에는 `ViewState` 페이지에 렌더링 되 고 표시 된 시점의 컨트롤 상태에 대 한 정보가 들어 있습니다 .이 필드에는 ASP.NET 런타임이 서버에 제출 된 콘텐츠의 변경 내용을 비교 하 고 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-128">The `ViewState` field contains information about the state of the controls at the time they were rendered and presented on the page, allowing the ASP.NET runtime to compare and identify changes in the content submitted to the server.</span></span>

## Blazor

<span data-ttu-id="c497e-129">Blazor 클라이언트 쪽 웹 UI 프레임 워크는 각도 또는 반응 같은 JavaScript 프런트 엔드 프레임 워크의 특성과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-129">Blazor is a client-side web UI framework similar in nature to JavaScript front-end frameworks like Angular or React.</span></span> <span data-ttu-id="c497e-130">Blazor 사용자 상호 작용을 처리 하 고 필요한 UI 업데이트를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-130">Blazor handles user interactions and renders the necessary UI updates.</span></span> <span data-ttu-id="c497e-131">Blazor는 요청-회신 모델을 기반으로 *하지 않습니다* .</span><span class="sxs-lookup"><span data-stu-id="c497e-131">Blazor *isn't* based on a request-reply model.</span></span> <span data-ttu-id="c497e-132">사용자 상호 작용은 특정 HTTP 요청의 컨텍스트에 속하지 않는 이벤트로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-132">User interactions are handled as events that aren't in the context of any particular HTTP request.</span></span>

<span data-ttu-id="c497e-133">Blazor 앱은 HTML 페이지에서 렌더링 되는 하나 이상의 루트 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-133">Blazor apps consist of one or more root components that are rendered on an HTML page.</span></span>

![::: no-loc (Blazor)::: HTML의 구성 요소](./media/architecture-comparison/blazor-components-in-html.png)

<span data-ttu-id="c497e-135">사용자가 구성 요소를 렌더링할 위치를 지정 하는 방법과 구성 요소가 사용자 상호 작용을 위해 유선으로 연결 되는 방식을 지정 하는 방법은 [호스팅 모델](hosting-models.md) 에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-135">How the user specifies where components should render and how the components are then wired up for user interactions is [hosting model](hosting-models.md) specific.</span></span>

<span data-ttu-id="c497e-136">Blazor[구성 요소](components.md) 는 다시 사용할 수 있는 UI 부분을 나타내는 .net 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-136">Blazor [components](components.md) are .NET classes that represent a reusable piece of UI.</span></span> <span data-ttu-id="c497e-137">각 구성 요소는 자체 상태를 유지 하 고 다른 구성 요소 렌더링을 포함할 수 있는 자체 렌더링 논리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-137">Each component maintains its own state and specifies its own rendering logic, which can include rendering other components.</span></span> <span data-ttu-id="c497e-138">구성 요소는 구성 요소의 상태를 업데이트 하기 위한 특정 사용자 상호 작용에 대 한 이벤트 처리기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-138">Components specify event handlers for specific user interactions to update the component's state.</span></span>

<span data-ttu-id="c497e-139">구성 요소가 이벤트를 처리 한 후는 Blazor 구성 요소를 렌더링 하 고 렌더링 된 출력에서 변경 된 내용을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-139">After a component handles an event, Blazor renders the component and keeps track of what changed in the rendered output.</span></span> <span data-ttu-id="c497e-140">구성 요소는 DOM (문서 개체 모델)에 직접 렌더링 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-140">Components don't render directly to the Document Object Model (DOM).</span></span> <span data-ttu-id="c497e-141">대신,를 통해 `RenderTree` 변경 내용을 추적할 수 있도록 이라는 DOM의 메모리 내 표현으로 렌더링 Blazor 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-141">They instead render to an in-memory representation of the DOM called a `RenderTree` so that Blazor can track the changes.</span></span> <span data-ttu-id="c497e-142">Blazor 새로 렌더링 된 출력을 이전 출력과 비교 하 여 DOM에 효율적으로 적용 되는 UI 차이를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-142">Blazor compares the newly rendered output with the previous output to calculate a UI diff that it then applies efficiently to the DOM.</span></span>

![::: no loc (Blazor)::: DOM 상호 작용](./media/architecture-comparison/blazor-dom-interaction.png)

<span data-ttu-id="c497e-144">구성 요소는 정상적인 UI 이벤트 외부에서 상태가 변경 되는 경우 렌더링 되어야 함을 수동으로 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-144">Components can also manually indicate that they should be rendered if their state changes outside of a normal UI event.</span></span> <span data-ttu-id="c497e-145">Blazor는 `SynchronizationContext`를 사용하여 단일 논리적 실행 스레드를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-145">Blazor uses a `SynchronizationContext` to enforce a single logical thread of execution.</span></span> <span data-ttu-id="c497e-146">구성 요소의 수명 주기 메서드 및 Blazor에서 발생하는 모든 이벤트 콜백은 이 `SynchronizationContext`에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c497e-146">A component's lifecycle methods and any event callbacks that are raised by Blazor are executed on this `SynchronizationContext`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c497e-147">[이전](introduction.md)
>[다음](hosting-models.md)</span><span class="sxs-lookup"><span data-stu-id="c497e-147">[Previous](introduction.md)
[Next](hosting-models.md)</span></span>
