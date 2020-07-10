---
title: 모듈, 처리기 및 미들웨어
description: 모듈, 처리기 및 미들웨어를 사용 하 여 HTTP 요청을 처리 하는 방법을 알아봅니다.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 10/11/2019
ms.openlocfilehash: ff2b3fd41316a1c8c20a0eed9a585e5fd2733af3
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173187"
---
# <a name="modules-handlers-and-middleware"></a><span data-ttu-id="d169d-103">모듈, 처리기 및 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-103">Modules, handlers, and middleware</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d169d-104">ASP.NET Core 앱은 일련의 *미들웨어*를 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-104">An ASP.NET Core app is built upon a series of *middleware*.</span></span> <span data-ttu-id="d169d-105">미들웨어는 요청 및 응답을 처리 하기 위해 파이프라인으로 정렬 되는 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-105">Middleware is handlers that are arranged into a pipeline to handle requests and responses.</span></span> <span data-ttu-id="d169d-106">Web Forms 앱에서 HTTP 처리기와 모듈은 유사한 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-106">In a Web Forms app, HTTP handlers and modules solve similar problems.</span></span> <span data-ttu-id="d169d-107">ASP.NET Core 모듈, 처리기, *Global.asax.cs*및 앱 수명 주기가 미들웨어로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-107">In ASP.NET Core, modules, handlers, *Global.asax.cs*, and the app life cycle are replaced with middleware.</span></span> <span data-ttu-id="d169d-108">이 장에서는 앱의 컨텍스트에서 미들웨어에 대해 알아봅니다 Blazor .</span><span class="sxs-lookup"><span data-stu-id="d169d-108">In this chapter, you'll learn what middleware in the context of a Blazor app.</span></span>

## <a name="overview"></a><span data-ttu-id="d169d-109">개요</span><span class="sxs-lookup"><span data-stu-id="d169d-109">Overview</span></span>

<span data-ttu-id="d169d-110">ASP.NET Core 요청 파이프라인은 하나씩 차례로 호출되는 요청 대리자 시퀀스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-110">The ASP.NET Core request pipeline consists of a sequence of request delegates, called one after the other.</span></span> <span data-ttu-id="d169d-111">다음 다이어그램은 그 개념을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-111">The following diagram demonstrates the concept.</span></span> <span data-ttu-id="d169d-112">실행 스레드는 검은색 화살표를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-112">The thread of execution follows the black arrows.</span></span>

![pipeline](media/middleware/request-delegate-pipeline.png)

<span data-ttu-id="d169d-114">이전 다이어그램에는 수명 주기 이벤트 개념이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-114">The preceding diagram lacks a concept of lifecycle events.</span></span> <span data-ttu-id="d169d-115">이 개념은 ASP.NET Web Forms 요청이 처리 되는 방식에 기초 합니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-115">This concept is foundational to how ASP.NET Web Forms requests are handled.</span></span> <span data-ttu-id="d169d-116">이 시스템을 사용 하면 발생 하는 프로세스를 보다 쉽게 파악할 수 있으며 미들웨어를 언제 든 지 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-116">This system makes it easier to reason about what process is occurring and allows middleware to be inserted at any point.</span></span> <span data-ttu-id="d169d-117">미들웨어는 요청 파이프라인에 추가 된 순서 대로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-117">Middleware executes in the order in which it's added to the request pipeline.</span></span> <span data-ttu-id="d169d-118">일반적으로 *Startup.cs*에서 구성 파일 대신 코드에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-118">They're also added in code instead of configuration files, usually in *Startup.cs*.</span></span>

## <a name="katana"></a><span data-ttu-id="d169d-119">Katana</span><span class="sxs-lookup"><span data-stu-id="d169d-119">Katana</span></span>

<span data-ttu-id="d169d-120">Katana에 익숙한 독자는 ASP.NET Core에 익숙해질 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-120">Readers familiar with Katana will feel comfortable in ASP.NET Core.</span></span> <span data-ttu-id="d169d-121">실제로 Katana는 ASP.NET Core 파생 되는 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-121">In fact, Katana is a framework from which ASP.NET Core derives.</span></span> <span data-ttu-id="d169d-122">ASP.NET 4.x에 대해 비슷한 미들웨어 및 파이프라인 패턴이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-122">It introduced similar middleware and pipeline patterns for ASP.NET 4.x.</span></span> <span data-ttu-id="d169d-123">Katana 용으로 설계 된 미들웨어는 ASP.NET Core 파이프라인을 사용 하도록 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-123">Middleware designed for Katana can be adapted to work with the ASP.NET Core pipeline.</span></span>

## <a name="common-middleware"></a><span data-ttu-id="d169d-124">일반적인 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-124">Common middleware</span></span>

<span data-ttu-id="d169d-125">ASP.NET 4.x에는 많은 모듈이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-125">ASP.NET 4.x includes many modules.</span></span> <span data-ttu-id="d169d-126">마찬가지로 ASP.NET Core에도 많은 미들웨어 구성 요소가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-126">In a similar fashion, ASP.NET Core has many middleware components available as well.</span></span> <span data-ttu-id="d169d-127">IIS 모듈은 일부 경우에 ASP.NET Core 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-127">IIS modules may be used in some cases with ASP.NET Core.</span></span> <span data-ttu-id="d169d-128">다른 경우에는 네이티브 ASP.NET Core 미들웨어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-128">In other cases, native ASP.NET Core middleware may be available.</span></span>

<span data-ttu-id="d169d-129">다음 표에서는 ASP.NET Core의 대체 미들웨어 및 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-129">The following table lists replacement middleware and components in ASP.NET Core.</span></span>

|<span data-ttu-id="d169d-130">모듈</span><span class="sxs-lookup"><span data-stu-id="d169d-130">Module</span></span>                 |<span data-ttu-id="d169d-131">ASP.NET 4.x 모듈</span><span class="sxs-lookup"><span data-stu-id="d169d-131">ASP.NET 4.x module</span></span>           |<span data-ttu-id="d169d-132">ASP.NET Core 옵션</span><span class="sxs-lookup"><span data-stu-id="d169d-132">ASP.NET Core option</span></span>|
|-----------------------|-----------------------------|-------------------|
|<span data-ttu-id="d169d-133">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="d169d-133">HTTP errors</span></span>            |`CustomErrorModule`          |[<span data-ttu-id="d169d-134">상태 코드 페이지 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-134">Status Code Pages Middleware</span></span>](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|<span data-ttu-id="d169d-135">기본 문서</span><span class="sxs-lookup"><span data-stu-id="d169d-135">Default document</span></span>       |`DefaultDocumentModule`      |[<span data-ttu-id="d169d-136">기본 파일 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-136">Default Files Middleware</span></span>](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|<span data-ttu-id="d169d-137">디렉터리 검색</span><span class="sxs-lookup"><span data-stu-id="d169d-137">Directory browsing</span></span>     |`DirectoryListingModule`     |[<span data-ttu-id="d169d-138">디렉터리 검색 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-138">Directory Browsing Middleware</span></span>](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|<span data-ttu-id="d169d-139">동적 압축</span><span class="sxs-lookup"><span data-stu-id="d169d-139">Dynamic compression</span></span>    |`DynamicCompressionModule`   |[<span data-ttu-id="d169d-140">응답 압축 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-140">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="d169d-141">실패 한 요청 추적</span><span class="sxs-lookup"><span data-stu-id="d169d-141">Failed requests tracing</span></span>|`FailedRequestsTracingModule`|[<span data-ttu-id="d169d-142">ASP.NET Core 로깅</span><span class="sxs-lookup"><span data-stu-id="d169d-142">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|<span data-ttu-id="d169d-143">파일 캐싱</span><span class="sxs-lookup"><span data-stu-id="d169d-143">File caching</span></span>           |`FileCacheModule`            |[<span data-ttu-id="d169d-144">응답 캐싱 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-144">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="d169d-145">HTTP 캐싱</span><span class="sxs-lookup"><span data-stu-id="d169d-145">HTTP caching</span></span>           |`HttpCacheModule`            |[<span data-ttu-id="d169d-146">응답 캐싱 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-146">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="d169d-147">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="d169d-147">HTTP logging</span></span>           |`HttpLoggingModule`          |[<span data-ttu-id="d169d-148">ASP.NET Core 로깅</span><span class="sxs-lookup"><span data-stu-id="d169d-148">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index)|
|<span data-ttu-id="d169d-149">HTTP 리디렉션</span><span class="sxs-lookup"><span data-stu-id="d169d-149">HTTP redirection</span></span>       |`HttpRedirectionModule`      |[<span data-ttu-id="d169d-150">URL 재작성 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-150">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="d169d-151">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="d169d-151">ISAPI filters</span></span>          |`IsapiFilterModule`          |[<span data-ttu-id="d169d-152">미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-152">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="d169d-153">ISAPI</span><span class="sxs-lookup"><span data-stu-id="d169d-153">ISAPI</span></span>                  |`IsapiModule`                |[<span data-ttu-id="d169d-154">미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-154">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="d169d-155">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="d169d-155">Request filtering</span></span>      |`RequestFilteringModule`     |[<span data-ttu-id="d169d-156">URL 재작성 미들웨어 IRule</span><span class="sxs-lookup"><span data-stu-id="d169d-156">URL Rewriting Middleware IRule</span></span>](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|<span data-ttu-id="d169d-157">URL 재작성&#8224;</span><span class="sxs-lookup"><span data-stu-id="d169d-157">URL rewriting&#8224;</span></span>   |`RewriteModule`              |[<span data-ttu-id="d169d-158">URL 재작성 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-158">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="d169d-159">정적 압축</span><span class="sxs-lookup"><span data-stu-id="d169d-159">Static compression</span></span>     |`StaticCompressionModule`    |[<span data-ttu-id="d169d-160">응답 압축 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-160">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="d169d-161">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d169d-161">Static content</span></span>         |`StaticFileModule`           |[<span data-ttu-id="d169d-162">정적 파일 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-162">Static File Middleware</span></span>](/aspnet/core/fundamentals/static-files)|
|<span data-ttu-id="d169d-163">URL 권한 부여</span><span class="sxs-lookup"><span data-stu-id="d169d-163">URL authorization</span></span>      |`UrlAuthorizationModule`     |[<span data-ttu-id="d169d-164">ASP.NET Core ID</span><span class="sxs-lookup"><span data-stu-id="d169d-164">ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity)|

<span data-ttu-id="d169d-165">이 목록은 완전 하지는 않지만 두 프레임 워크 사이에 존재 하는 매핑에 대해 아이디어를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-165">This list isn't exhaustive but should give an idea of what mapping exists between the two frameworks.</span></span> <span data-ttu-id="d169d-166">자세한 목록은 [ASP.NET Core를 사용 하는 IIS 모듈](/aspnet/core/host-and-deploy/iis/modules)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d169d-166">For a more detailed list, see [IIS modules with ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span></span>

## <a name="custom-middleware"></a><span data-ttu-id="d169d-167">사용자 지정 미들웨어</span><span class="sxs-lookup"><span data-stu-id="d169d-167">Custom middleware</span></span>

<span data-ttu-id="d169d-168">기본 제공 미들웨어는 앱에 필요한 모든 시나리오를 처리 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-168">Built-in middleware may not handle all scenarios needed for an app.</span></span> <span data-ttu-id="d169d-169">이러한 경우 고유한 미들웨어를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-169">In such cases, it makes sense to create your own middleware.</span></span> <span data-ttu-id="d169d-170">미들웨어를 정의 하는 방법에는 여러 가지가 있으며 간단한 대리자가 가장 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-170">There are multiple ways of defining middleware, with the simplest being a simple delegate.</span></span> <span data-ttu-id="d169d-171">쿼리 문자열에서 문화권 요청을 수락 하는 다음 미들웨어를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d169d-171">Consider the following middleware, which accepts a culture request from a query string:</span></span>

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

<span data-ttu-id="d169d-172">미들웨어는 인터페이스를 구현 하거나 미들웨어 규칙을 따라 클래스로 정의할 수도 있습니다 `IMiddleware` .</span><span class="sxs-lookup"><span data-stu-id="d169d-172">Middleware can also be defined as class, either by implementing the `IMiddleware` interface or by following middleware convention.</span></span> <span data-ttu-id="d169d-173">자세한 내용은 [사용자 지정 ASP.NET Core 미들웨어 작성](/aspnet/core/fundamentals/middleware/write)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d169d-173">For more information, see [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d169d-174">[이전](data.md)
>[다음](config.md)</span><span class="sxs-lookup"><span data-stu-id="d169d-174">[Previous](data.md)
[Next](config.md)</span></span>
