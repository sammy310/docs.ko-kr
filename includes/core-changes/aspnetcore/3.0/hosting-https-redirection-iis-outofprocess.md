---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032510"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a><span data-ttu-id="e355a-101">호스팅: IIS Out of Process 앱에 대해 HTTPS 리디렉션 사용</span><span class="sxs-lookup"><span data-stu-id="e355a-101">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>

<span data-ttu-id="e355a-102">IIS Out of Process를 통해 호스팅하기 위한 [ASP.NET Core 모듈(ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module)의 버전 13.0.19218.0은 ASP.NET Core 3.0 및 2.2 앱에 대한 기존 HTTPS 리디렉션 기능을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-102">Version 13.0.19218.0 of the [ASP.NET Core Module (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) for hosting via IIS out-of-process enables an existing HTTPS redirection feature for ASP.NET Core 3.0 and 2.2 apps.</span></span>

<span data-ttu-id="e355a-103">토론은 [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e355a-103">For discussion, see [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e355a-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e355a-104">Version introduced</span></span>

<span data-ttu-id="e355a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="e355a-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e355a-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="e355a-106">Old behavior</span></span>

<span data-ttu-id="e355a-107">ASP.NET Core 2.1 프로젝트 템플릿은 먼저 <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> 및 <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>와 같은 HTTPS 미들웨어 메서드에 대한 지원을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-107">The ASP.NET Core 2.1 project template first introduced support for HTTPS middleware methods like <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> and <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>.</span></span> <span data-ttu-id="e355a-108">개발 중인 앱은 기본 포트 443을 사용하지 않으므로 HTTPS 리디렉션을 사용하도록 설정하려면 구성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-108">Enabling HTTPS redirection required the addition of configuration, since apps in development don't use the default port of 443.</span></span> <span data-ttu-id="e355a-109">[HSTS(HTTP Strict Transport Security)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)는 요청이 HTTPS를 이미 사용하고 있을 경우에만 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-109">[HTTP Strict Transport Security (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) is active only if the request is already using HTTPS.</span></span> <span data-ttu-id="e355a-110">localhost는 기본적으로 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-110">Localhost is skipped by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e355a-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="e355a-111">New behavior</span></span>

<span data-ttu-id="e355a-112">ASP.NET Core 3.0에서 IIS HTTPS 시나리오는 [향상](https://github.com/dotnet/AspNetCore/pull/4685)되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-112">In ASP.NET Core 3.0, the IIS HTTPS scenario was [enhanced](https://github.com/dotnet/AspNetCore/pull/4685).</span></span> <span data-ttu-id="e355a-113">향상된 기능을 사용하면 앱이 서버의 HTTPS 포트를 검색하고 기본적으로 `UseHttpsRedirection` 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-113">With the enhancement, an app could discover the server's HTTPS ports and make `UseHttpsRedirection` work by default.</span></span> <span data-ttu-id="e355a-114">In Process 구성 요소는 `IServerAddresses` 기능을 사용하여 포트 검색을 완료했습니다. In Process 라이브러리가 프레임워크를 통해 버전이 지정되었기 때문에 이 기능은 ASP.NET Core 3.0 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-114">The in-process component accomplished port discovery with the `IServerAddresses` feature, which only affects ASP.NET Core 3.0 apps because the in-process library is versioned with the framework.</span></span> <span data-ttu-id="e355a-115">`ASPNETCORE_HTTPS_PORT` 환경 변수를 자동으로 추가하도록 Out of Process 구성 요소가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-115">The out-of-process component changed to automatically add the `ASPNETCORE_HTTPS_PORT` environment variable.</span></span> <span data-ttu-id="e355a-116">Out of Process 구성 요소가 전역적으로 공유되기 때문에 이 변경은 ASP.NET Core 2.2 및 3.0 앱 모두에 영향을 미쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-116">This change affected both ASP.NET Core 2.2 and 3.0 apps because the out-of-process component is shared globally.</span></span> <span data-ttu-id="e355a-117">ASP.NET Core 2.1 앱은 기본적으로 이전 버전의 버전을 ANCM을 사용하므로 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-117">ASP.NET Core 2.1 apps aren't affected because they use a prior version of ANCM by default.</span></span>

<span data-ttu-id="e355a-118">ASP.NET Core 3.0.1과 3.1.0 Preview 3에서 이전 동작을 수정하여 ASP.NET Core 2.x의 동작 변경을 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-118">The preceding behavior was modified in ASP.NET Core 3.0.1 and 3.1.0 Preview 3 to reverse the behavior changes in ASP.NET Core 2.x.</span></span> <span data-ttu-id="e355a-119">해당 변경 내용은 IIS Out of Process 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-119">These changes only affect IIS out-of-process apps.</span></span>

<span data-ttu-id="e355a-120">위에서 설명한 대로 ASP.NET Core 3.0.0을 설치하면 ASP.NET Core 2.x 앱에서 `UseHttpsRedirection` 미들웨어도 활성화되는 부작용이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-120">As detailed above, installing ASP.NET Core 3.0.0 had the side effect of also activating the `UseHttpsRedirection` middleware in ASP.NET Core 2.x apps.</span></span> <span data-ttu-id="e355a-121">ASP.NET Core 3.0.1 및 3.1.0 Preview 3을 설치해도 ASP.NET Core 2.x 앱에 더 이상 영향을 주지 않도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-121">A change was made to ANCM in ASP.NET Core 3.0.1 and 3.1.0 Preview 3 such that installing them no longer has this effect on ASP.NET Core 2.x apps.</span></span> <span data-ttu-id="e355a-122">ASP.NET Corea 3.0.0에서 ANCM이 채운 `ASPNETCORE_HTTPS_PORT` 환경 변수가 ASP.NET Core 3.0.1 및 3.1.0 Preview 3의 `ASPNETCORE_ANCM_HTTPS_PORT`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-122">The `ASPNETCORE_HTTPS_PORT` environment variable that ANCM populated in ASP.NET Core 3.0.0 was changed to `ASPNETCORE_ANCM_HTTPS_PORT` in ASP.NET Core 3.0.1 and 3.1.0 Preview 3.</span></span> <span data-ttu-id="e355a-123">`UseHttpsRedirection`는 새로운 변수와 이전 변수를 모두 이해하기 위해 이 릴리스에서도 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-123">`UseHttpsRedirection` was also updated in these releases to understand both the new and old variables.</span></span> <span data-ttu-id="e355a-124">ASP.NET Core 2.x는 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-124">ASP.NET Core 2.x won't be updated.</span></span> <span data-ttu-id="e355a-125">그 결과, 기본적으로 사용하지 않도록 설정된 이전 동작으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-125">As a result, it reverts to the previous behavior of being disabled by default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e355a-126">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e355a-126">Reason for change</span></span>

<span data-ttu-id="e355a-127">ASP.NET Core 3.0 기능이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-127">Improved ASP.NET Core 3.0 functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e355a-128">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e355a-128">Recommended action</span></span>

<span data-ttu-id="e355a-129">모든 클라이언트가 HTTPS를 사용하도록 하려면 작업이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-129">No action is required if you want all clients to use HTTPS.</span></span> <span data-ttu-id="e355a-130">일부 클라이언트가 HTTPS를 사용하도록 허용하려면 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-130">To allow some clients to use HTTP, take one of the following steps:</span></span>

* <span data-ttu-id="e355a-131">프로젝트의 `Startup.Configure` 메서드에서 `UseHttpsRedirection` 및 `UseHsts`에 대한 호출을 제거하고 앱을 다시 배포하세요.</span><span class="sxs-lookup"><span data-stu-id="e355a-131">Remove the calls to `UseHttpsRedirection` and `UseHsts` from your project's `Startup.Configure` method, and redeploy the app.</span></span>
* <span data-ttu-id="e355a-132">*web.config* 파일에서 `ASPNETCORE_HTTPS_PORT` 환경 변수를 빈 문자열로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="e355a-132">In your *web.config* file, set the `ASPNETCORE_HTTPS_PORT` environment variable to an empty string.</span></span> <span data-ttu-id="e355a-133">변경은 앱을 다시 배포하지 않고 서버에서 직접 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-133">This change can occur directly on the server without redeploying the app.</span></span> <span data-ttu-id="e355a-134">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="e355a-134">For example:</span></span>

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

<span data-ttu-id="e355a-135">`UseHttpsRedirection`은 여전히 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-135">`UseHttpsRedirection` can still be:</span></span>

* <span data-ttu-id="e355a-136">`ASPNETCORE_HTTPS_PORT` 환경 변수를 적절한 포트 번호(대부분의 프로덕션 시나리오에서 443)로 설정하여 ASP.NET Core 2.x에서 수동으로 활성화했습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-136">Activated manually in ASP.NET Core 2.x by setting the `ASPNETCORE_HTTPS_PORT` environment variable to the appropriate port number (443 in most production scenarios).</span></span>
* <span data-ttu-id="e355a-137">빈 문자열 값으로 `ASPNETCORE_ANCM_HTTPS_PORT`를 정의하여 ASP.NET Core 3.x에서 비활성화했습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-137">Deactivated in ASP.NET Core 3.x by defining `ASPNETCORE_ANCM_HTTPS_PORT` with an empty string value.</span></span> <span data-ttu-id="e355a-138">이 값은 앞의 `ASPNETCORE_HTTPS_PORT` 예제와 동일한 방식으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-138">This value is set in the same fashion as the preceding `ASPNETCORE_HTTPS_PORT` example.</span></span>

<span data-ttu-id="e355a-139">ASP.NET Core 3.0.0 앱을 실행하는 컴퓨터는 ASP.NET Core 3.1.0 Preview 3 ANCM을 설치하기 전에 ASP.NET Core 3.0.1 런타임을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-139">Machines running ASP.NET Core 3.0.0 apps should install the ASP.NET Core 3.0.1 runtime before installing the ASP.NET Core 3.1.0 Preview 3 ANCM.</span></span> <span data-ttu-id="e355a-140">이렇게 하면 `UseHttpsRedirection`이 ASP.NET Core 3.0 앱에 대해 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-140">Doing so ensures that `UseHttpsRedirection` continues to operate as expected for the ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="e355a-141">Azure App Service에서는 ANCM이 전역 특성 때문에 런타임과 별도의 일정으로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-141">In Azure App Service, ANCM deploys on a separate schedule from the runtime because of its global nature.</span></span> <span data-ttu-id="e355a-142">ANCM은 ASP.NET Core 3.0.1 및 3.1.0가 배포된 후 해당 변경과 함께 Azure에 배포되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e355a-142">ANCM was deployed to Azure with these changes after ASP.NET Core 3.0.1 and 3.1.0 were deployed.</span></span>

#### <a name="category"></a><span data-ttu-id="e355a-143">범주</span><span class="sxs-lookup"><span data-stu-id="e355a-143">Category</span></span>

<span data-ttu-id="e355a-144">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e355a-144">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e355a-145">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e355a-145">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
