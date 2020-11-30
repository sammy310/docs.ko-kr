---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032897"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a><span data-ttu-id="16afe-101">SPA: 사용되지 않는 것으로 표시된 SpaServices 및 NodeServices</span><span class="sxs-lookup"><span data-stu-id="16afe-101">SPAs: SpaServices and NodeServices marked obsolete</span></span>

<span data-ttu-id="16afe-102">다음 NuGet 패키지의 내용은 ASP.NET Core 2.1 이후 모두 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-102">The contents of the following NuGet packages have all been unnecessary since ASP.NET Core 2.1.</span></span> <span data-ttu-id="16afe-103">따라서 다음 패키지는 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-103">Consequently, the following packages are being marked as obsolete:</span></span>

- [<span data-ttu-id="16afe-104">Microsoft.AspNetCore.SpaServices</span><span class="sxs-lookup"><span data-stu-id="16afe-104">Microsoft.AspNetCore.SpaServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/)
- [<span data-ttu-id="16afe-105">Microsoft.AspNetCore.NodeServices</span><span class="sxs-lookup"><span data-stu-id="16afe-105">Microsoft.AspNetCore.NodeServices</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/)

<span data-ttu-id="16afe-106">동일한 이유로 다음 npm 모듈은 더 이상 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-106">For the same reason, the following npm modules are being marked as deprecated:</span></span>

- [<span data-ttu-id="16afe-107">aspnet-angular</span><span class="sxs-lookup"><span data-stu-id="16afe-107">aspnet-angular</span></span>](https://www.npmjs.com/package/aspnet-angular)
- [<span data-ttu-id="16afe-108">aspnet-prerendering</span><span class="sxs-lookup"><span data-stu-id="16afe-108">aspnet-prerendering</span></span>](https://www.npmjs.com/package/aspnet-prerendering)
- [<span data-ttu-id="16afe-109">aspnet-webpack</span><span class="sxs-lookup"><span data-stu-id="16afe-109">aspnet-webpack</span></span>](https://www.npmjs.com/package/aspnet-webpack)
- [<span data-ttu-id="16afe-110">aspnet-webpack-react</span><span class="sxs-lookup"><span data-stu-id="16afe-110">aspnet-webpack-react</span></span>](https://www.npmjs.com/package/aspnet-webpack-react)
- [<span data-ttu-id="16afe-111">domain-task</span><span class="sxs-lookup"><span data-stu-id="16afe-111">domain-task</span></span>](https://www.npmjs.com/package/domain-task)

<span data-ttu-id="16afe-112">이전 패키지 및 npm 모듈은 나중에 .NET 5에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-112">The preceding packages and npm modules will later be removed in .NET 5.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="16afe-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="16afe-113">Version introduced</span></span>

<span data-ttu-id="16afe-114">3.0</span><span class="sxs-lookup"><span data-stu-id="16afe-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="16afe-115">이전 동작</span><span class="sxs-lookup"><span data-stu-id="16afe-115">Old behavior</span></span>

<span data-ttu-id="16afe-116">사용되지 않는 패키지 및 npm 모듈은 ASP.NET Core를 다양한 SPA(단일 페이지 앱) 프레임워크와 통합하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-116">The deprecated packages and npm modules were intended to integrate ASP.NET Core with various Single-Page App (SPA) frameworks.</span></span> <span data-ttu-id="16afe-117">이러한 프레임워크에는 Angular, React 및 Redux를 사용한 React가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-117">Such frameworks include Angular, React, and React with Redux.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="16afe-118">새 동작</span><span class="sxs-lookup"><span data-stu-id="16afe-118">New behavior</span></span>

<span data-ttu-id="16afe-119">[Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet 패키지에 새 통합 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-119">A new integration mechanism exists in the [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) NuGet package.</span></span> <span data-ttu-id="16afe-120">패키지는 ASP.NET Core 2.1 이후 Angular 및 React 프로젝트 템플릿의 기반으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-120">The package remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="16afe-121">변경 이유</span><span class="sxs-lookup"><span data-stu-id="16afe-121">Reason for change</span></span>

<span data-ttu-id="16afe-122">ASP.NET Core는 Angular, React 및 Redux를 React를 포함한 다양한 SPA(단일 페이지 앱) 프레임워크와의 통합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-122">ASP.NET Core supports integration with various Single-Page App (SPA) frameworks, including Angular, React, and React with Redux.</span></span> <span data-ttu-id="16afe-123">처음에 이러한 프레임워크와의 통합은 서버 쪽 렌더링 및 Webpack과의 통합과 같은 시나리오를 처리하는 ASP.NET Core 관련 구성 요소를 사용하여 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-123">Initially, integration with these frameworks was accomplished with ASP.NET Core-specific components that handled scenarios like server-side prerendering and integration with Webpack.</span></span> <span data-ttu-id="16afe-124">시간이 지남에 따라 업계 표준이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-124">As time went on, industry standards changed.</span></span> <span data-ttu-id="16afe-125">각 SPA 프레임워크는 자체 표준 명령줄 인터페이스를 릴리스했습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-125">Each of the SPA frameworks released their own standard command-line interfaces.</span></span> <span data-ttu-id="16afe-126">예를 들어 Angular CLI 및 create-react-app입니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-126">For example, Angular CLI and create-react-app.</span></span>

<span data-ttu-id="16afe-127">2018년 5월에 ASP.NET Core 2.1이 릴리스되었을 때 팀은 표준 변경에 대응했습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-127">When ASP.NET Core 2.1 was released in May 2018, the team responded to the change in standards.</span></span> <span data-ttu-id="16afe-128">SPA 프레임워크 자체 도구 체인과 통합하는 새롭고 간단한 방법이 제공되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-128">A newer and simpler way to integrate with the SPA frameworks' own toolchains was provided.</span></span> <span data-ttu-id="16afe-129">새로운 통합 메커니즘은 `Microsoft.AspNetCore.SpaServices.Extensions` 패키지에 존재하며 ASP.NET Core 2.1 이후 Angular 및 React 프로젝트 템플릿의 기반으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-129">The new integration mechanism exists in the package `Microsoft.AspNetCore.SpaServices.Extensions` and remains the basis of the Angular and React project templates since ASP.NET Core 2.1.</span></span>

<span data-ttu-id="16afe-130">이전 ASP.NET Core 관련 구성 요소는 관련이 없으며 권장되지 않는다는 것을 명확하게 하기 위해 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-130">To clarify that the older ASP.NET Core-specific components are irrelevant and not recommended:</span></span>

- <span data-ttu-id="16afe-131">2\.1 이전 통합 메커니즘은 사용되지 않는 것으로 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-131">The pre-2.1 integration mechanism is marked as obsolete.</span></span>
- <span data-ttu-id="16afe-132">지원되는 npm 패키지는 더 이상 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-132">The supporting npm packages are marked as deprecated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="16afe-133">권장 조치</span><span class="sxs-lookup"><span data-stu-id="16afe-133">Recommended action</span></span>

<span data-ttu-id="16afe-134">이러한 패키지를 사용하는 경우 다음 기능을 사용하도록 앱을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-134">If you're using these packages, update your apps to use the functionality:</span></span>

- <span data-ttu-id="16afe-135">`Microsoft.AspNetCore.SpaServices.Extensions` 패키지에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-135">In the `Microsoft.AspNetCore.SpaServices.Extensions` package.</span></span>
- <span data-ttu-id="16afe-136">사용 중인 SPA 프레임워크에서 제공됨</span><span class="sxs-lookup"><span data-stu-id="16afe-136">Provided by the SPA frameworks you're using</span></span>

<span data-ttu-id="16afe-137">서버 쪽 렌더링 및 핫 모듈 재로드와 같은 기능을 사용하려면 해당 SPA 프레임워크에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16afe-137">To enable features like server-side prerendering and hot module reload, see the documentation for the corresponding SPA framework.</span></span> <span data-ttu-id="16afe-138">`Microsoft.AspNetCore.SpaServices.Extensions`의 기능은 사용되지 않는 것이 *아니며* 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="16afe-138">The functionality in `Microsoft.AspNetCore.SpaServices.Extensions` is *not* obsolete and will continue to be supported.</span></span>

#### <a name="category"></a><span data-ttu-id="16afe-139">범주</span><span class="sxs-lookup"><span data-stu-id="16afe-139">Category</span></span>

<span data-ttu-id="16afe-140">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="16afe-140">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="16afe-141">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="16afe-141">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
