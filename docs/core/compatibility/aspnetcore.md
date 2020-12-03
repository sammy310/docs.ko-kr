---
title: ASP.NET Core 호환성이 손상되는 변경
titleSuffix: ''
description: ASP.NET Core 3.0 및 3.1의 호환성이 손상되는 변경을 나열합니다.
ms.date: 11/03/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 40dfda77dd51ed46366ec6cd8f6598070e8ce846
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "96032443"
---
# <a name="aspnet-core-breaking-changes-for-versions-30-and-31"></a><span data-ttu-id="108a8-103">ASP.NET Core 버전 3.0 및 3.1의 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="108a8-103">ASP.NET Core breaking changes for versions 3.0 and 3.1</span></span>

<span data-ttu-id="108a8-104">ASP.NET Core는 .NET Core에서 사용되는 웹앱 개발 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="108a8-105">특정 버전의 호환성이 손상되는 변경에 해당하는 다음 링크 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-105">Select one of the following links for breaking changes in a specific version:</span></span>

* [<span data-ttu-id="108a8-106">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="108a8-106">ASP.NET Core 3.1</span></span>](#aspnet-core-31)
* [<span data-ttu-id="108a8-107">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="108a8-107">ASP.NET Core 3.0</span></span>](#aspnet-core-30)

<span data-ttu-id="108a8-108">이 페이지에는 ASP.NET Core 3.0 및 3.1의 다음과 같은 호환성이 손상되는 변경이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-108">The following breaking changes in ASP.NET Core 3.0 and 3.1 are documented on this page:</span></span>

- [<span data-ttu-id="108a8-109">사용되지 않는 위조 방지, CORS, 진단, MVC 및 라우팅 API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-109">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="108a8-110">인증: Google + 사용 중단</span><span class="sxs-lookup"><span data-stu-id="108a8-110">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="108a8-111">인증: HttpContext.Authentication 인증 속성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-111">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="108a8-112">인증: Newtonsoft.json 형식이 대체됨</span><span class="sxs-lookup"><span data-stu-id="108a8-112">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="108a8-113">인증: OAuthHandler ExchangeCodeAsync 서명이 변경됨</span><span class="sxs-lookup"><span data-stu-id="108a8-113">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="108a8-114">권한 부여: AddAuthorization 오버로드가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="108a8-114">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="108a8-115">권한 부여: AuthorizationFilterContext.Filters에서 IAllowAnonymous 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-115">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="108a8-116">권한 부여: IAuthorizationPolicyProvider 구현에는 새 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-116">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="108a8-117">캐싱: CompactOnMemoryPressure 속성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-117">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="108a8-118">캐싱: Microsoft.Extensions.Caching.SqlServer는 새 SqlClient 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-118">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="108a8-119">데이터 보호: DataProtection.Blobs에서 새로운 Azure Storage API 사용</span><span class="sxs-lookup"><span data-stu-id="108a8-119">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionblobs-uses-new-azure-storage-apis)
- [<span data-ttu-id="108a8-120">호스팅: Windows Hosting Bundle에서 AspNetCoreModule V1이 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-120">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="108a8-121">호스팅: 제네릭 호스트는 시작 생성자 주입을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-121">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="108a8-122">호스팅: IIS Out of Process 앱에 대해 HTTPS 리디렉션 사용</span><span class="sxs-lookup"><span data-stu-id="108a8-122">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="108a8-123">호스팅: IHostingEnvironment 및 IApplicationLifetime 형식이 바뀜</span><span class="sxs-lookup"><span data-stu-id="108a8-123">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="108a8-124">호스팅: WebHostBuilder 종속성에서 제거되는 ObjectPoolProvider</span><span class="sxs-lookup"><span data-stu-id="108a8-124">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="108a8-125">HTTP: 브라우저 SameSite 변경 내용이 인증에 영향</span><span class="sxs-lookup"><span data-stu-id="108a8-125">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="108a8-126">HTTP: DefaultHttpContext 확장성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-126">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="108a8-127">HTTP: HeaderNames 필드가 정적 읽기 전용으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="108a8-127">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="108a8-128">HTTP: 응답 본문 인프라 변경</span><span class="sxs-lookup"><span data-stu-id="108a8-128">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="108a8-129">HTTP: 일부 쿠키 SameSite 기본값이 변경됨</span><span class="sxs-lookup"><span data-stu-id="108a8-129">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="108a8-130">HTTP: 기본적으로 사용하지 않도록 설정된 동기 IO</span><span class="sxs-lookup"><span data-stu-id="108a8-130">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="108a8-131">ID: AddDefaultUI 메서드 오버로드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-131">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="108a8-132">ID: UI 부트스트랩 버전 변경</span><span class="sxs-lookup"><span data-stu-id="108a8-132">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="108a8-133">ID: SignInAsync는 인증되지 않은 ID에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-133">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="108a8-134">ID: SignInManager 생성자는 새 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-134">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="108a8-135">ID: UI는 정적 웹 자산 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-135">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="108a8-136">Kestrel: 연결 어댑터가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-136">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="108a8-137">Kestrel: 빈 HTTPS 어셈블리가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-137">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="108a8-138">Kestrel: 요청 후행부 헤더가 새 컬렉션으로 이동됨</span><span class="sxs-lookup"><span data-stu-id="108a8-138">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="108a8-139">Kestrel: 전송 추상화 계층 변경</span><span class="sxs-lookup"><span data-stu-id="108a8-139">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="108a8-140">지역화: 사용되지 않음으로 표시된 API</span><span class="sxs-lookup"><span data-stu-id="108a8-140">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="108a8-141">로깅: DebugLogger 클래스를 내부적으로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="108a8-141">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="108a8-142">MVC: 컨트롤러 작업 비동기 접미사가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-142">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="108a8-143">MVC: JsonResult를 Microsoft.AspNetCore.Mvc.Core로 이동</span><span class="sxs-lookup"><span data-stu-id="108a8-143">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="108a8-144">MVC: 미리 컴파일 도구가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="108a8-144">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="108a8-145">MVC: 형식이 내부로 변경됨</span><span class="sxs-lookup"><span data-stu-id="108a8-145">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="108a8-146">MVC: 웹 API 호환성 shim이 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-146">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="108a8-147">Razor: RazorTemplateEngine API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-147">Razor: RazorTemplateEngine API removed</span></span>](#razor-razortemplateengine-api-removed)
- [<span data-ttu-id="108a8-148">Razor: 런타임 컴파일이 패키지로 이동됨</span><span class="sxs-lookup"><span data-stu-id="108a8-148">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="108a8-149">세션 상태: 사용되지 않는 API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-149">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="108a8-150">공유 프레임워크: Microsoft.AspNetCore.App에서 어셈블리 제거</span><span class="sxs-lookup"><span data-stu-id="108a8-150">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="108a8-151">공유 프레임워크: 제거된 Microsoft.AspNetCore.All이 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-151">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="108a8-152">SignalR: HandshakeProtocol.SuccessHandshakeData가 대체됨</span><span class="sxs-lookup"><span data-stu-id="108a8-152">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="108a8-153">SignalR: HubConnection 메서드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="108a8-153">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="108a8-154">SignalR: HubConnectionContext 생성자가 변경됨</span><span class="sxs-lookup"><span data-stu-id="108a8-154">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="108a8-155">SignalR: JavaScript 클라이언트 패키지 이름 변경</span><span class="sxs-lookup"><span data-stu-id="108a8-155">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="108a8-156">SignalR: 사용되지 않는 API</span><span class="sxs-lookup"><span data-stu-id="108a8-156">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="108a8-157">SPA: SpaServices 및 NodeServices 콘솔 로거 대체 기본 변경</span><span class="sxs-lookup"><span data-stu-id="108a8-157">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="108a8-158">SPA: 사용되지 않는 것으로 표시된 SpaServices 및 NodeServices</span><span class="sxs-lookup"><span data-stu-id="108a8-158">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="108a8-159">대상 프레임워크: 지원되지 않는 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="108a8-159">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-31"></a><span data-ttu-id="108a8-160">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="108a8-160">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="108a8-161">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="108a8-161">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

<span data-ttu-id="108a8-162">\*\*_</span><span class="sxs-lookup"><span data-stu-id="108a8-162">\*\*_</span></span>

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

_*_

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

_*_

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

_*_

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

_*_

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

_*_

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

_*_

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

_*_

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

_*_

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

_*_

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

_*_

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

_*_

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

_*_

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

_*_

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

_*_

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

_*_

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

_*_

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

_*_

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

_*_

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

_*_

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

_*_

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

_*_

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

_*_

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

_*_

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

_*_

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

_*_

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

_*_

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

_*_

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

_*_

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

_*_

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

_*_

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

_*_

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

_*_

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

_*_

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

_*_

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

_*_

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

_*_

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

_*_

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

_*_

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

_*_

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

_*_

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

_*_

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

_*_

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

_*_

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

_*_

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

_*_

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

_*_

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

_*_

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

<span data-ttu-id="108a8-163">_\*\*</span><span class="sxs-lookup"><span data-stu-id="108a8-163">_\*\*</span></span>
