---
title: ASP.NET Core 호환성이 손상되는 변경
titleSuffix: ''
description: ASP.NET Core의 호환성이 손상되는 변경을 나열합니다.
ms.date: 06/11/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: a6ddf97f907a1cba57e51d6fd516d1f94272f725
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803279"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="8bca8-103">ASP.NET Core 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="8bca8-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="8bca8-104">ASP.NET Core는 .NET Core에서 사용되는 웹앱 개발 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="8bca8-105">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="8bca8-106">사용되지 않는 위조 방지, CORS, 진단, MVC 및 라우팅 API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="8bca8-107">인증: Google + 사용 중단</span><span class="sxs-lookup"><span data-stu-id="8bca8-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="8bca8-108">인증: HttpContext.Authentication 인증 속성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="8bca8-109">인증: Newtonsoft.json 형식이 대체됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="8bca8-110">인증: OAuthHandler ExchangeCodeAsync 서명이 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="8bca8-111">권한 부여: AddAuthorization 오버로드가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="8bca8-112">권한 부여: AuthorizationFilterContext.Filters에서 IAllowAnonymous 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="8bca8-113">권한 부여: IAuthorizationPolicyProvider 구현에는 새 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="8bca8-114">Azure: Microsoft 접두사가 있는 Azure 통합 패키지가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-114">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="8bca8-115">캐싱: CompactOnMemoryPressure 속성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-115">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="8bca8-116">캐싱: Microsoft.Extensions.Caching.SqlServer는 새 SqlClient 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-116">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="8bca8-117">캐싱: ResponseCaching “pubternal” 유형이 내부로 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-117">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="8bca8-118">데이터 보호: DataProtection.AzureStorage는 새로운 Azure Storage API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-118">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="8bca8-119">확장: 일부 NuGet 패키지에 영향을 주는 패키지 참조 변경 내용</span><span class="sxs-lookup"><span data-stu-id="8bca8-119">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="8bca8-120">호스팅: Windows Hosting Bundle에서 AspNetCoreModule V1이 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-120">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="8bca8-121">호스팅: 제네릭 호스트는 시작 생성자 주입을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-121">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="8bca8-122">호스팅: IIS Out of Process 앱에 대해 HTTPS 리디렉션 사용</span><span class="sxs-lookup"><span data-stu-id="8bca8-122">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="8bca8-123">호스팅: IHostingEnvironment 및 IApplicationLifetime 형식이 바뀜</span><span class="sxs-lookup"><span data-stu-id="8bca8-123">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="8bca8-124">호스팅: WebHostBuilder 종속성에서 제거되는 ObjectPoolProvider</span><span class="sxs-lookup"><span data-stu-id="8bca8-124">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="8bca8-125">HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-125">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="8bca8-126">HTTP: 브라우저 SameSite 변경 내용이 인증에 영향</span><span class="sxs-lookup"><span data-stu-id="8bca8-126">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="8bca8-127">HTTP: DefaultHttpContext 확장성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-127">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="8bca8-128">HTTP: HeaderNames 필드가 정적 읽기 전용으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-128">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="8bca8-129">HTTP: IHttpClientFactory 로그 정수 상태 코드에서 생성된 HttpClient 인스턴스</span><span class="sxs-lookup"><span data-stu-id="8bca8-129">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="8bca8-130">HTTP: 응답 본문 인프라 변경</span><span class="sxs-lookup"><span data-stu-id="8bca8-130">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="8bca8-131">HTTP: 일부 쿠키 SameSite 기본값이 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-131">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="8bca8-132">HTTP: 기본적으로 사용하지 않도록 설정된 동기 IO</span><span class="sxs-lookup"><span data-stu-id="8bca8-132">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="8bca8-133">ID: AddDefaultUI 메서드 오버로드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-133">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="8bca8-134">ID: UI 부트스트랩 버전 변경</span><span class="sxs-lookup"><span data-stu-id="8bca8-134">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="8bca8-135">ID: SignInAsync는 인증되지 않은 ID에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-135">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="8bca8-136">ID: SignInManager 생성자는 새 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-136">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="8bca8-137">ID: UI는 정적 웹 자산 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-137">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="8bca8-138">Kestrel: 런타임의 구성 변경 내용이 기본적으로 검색됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-138">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="8bca8-139">Kestrel: 연결 어댑터가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-139">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="8bca8-140">Kestrel: 지원되는 기본 TLS 프로토콜 버전 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-140">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="8bca8-141">Kestrel: 빈 HTTPS 어셈블리가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-141">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="8bca8-142">Kestrel: 요청 후행부 헤더가 새 컬렉션으로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-142">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="8bca8-143">Kestrel: 전송 추상화 계층 변경</span><span class="sxs-lookup"><span data-stu-id="8bca8-143">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="8bca8-144">지역화: 사용되지 않음으로 표시된 API</span><span class="sxs-lookup"><span data-stu-id="8bca8-144">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="8bca8-145">지역화: “Pubternal” API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-145">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="8bca8-146">지역화: ResourceManagerWithCultureStringLocalizer 클래스 및 WithCulture 인터페이스 멤버가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-146">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="8bca8-147">로깅: DebugLogger 클래스를 내부적으로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="8bca8-147">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="8bca8-148">MVC: 컨트롤러 작업 비동기 접미사가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-148">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="8bca8-149">MVC: JsonResult를 Microsoft.AspNetCore.Mvc.Core로 이동</span><span class="sxs-lookup"><span data-stu-id="8bca8-149">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="8bca8-150">MVC: 미리 컴파일 도구가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="8bca8-150">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="8bca8-151">MVC: 형식이 내부로 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-151">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="8bca8-152">MVC: 웹 API 호환성 shim이 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-152">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="8bca8-153">Razor: 런타임 컴파일이 패키지로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-153">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="8bca8-154">세션 상태: 사용되지 않는 API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-154">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="8bca8-155">공유 프레임워크: Microsoft.AspNetCore.App에서 어셈블리 제거</span><span class="sxs-lookup"><span data-stu-id="8bca8-155">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="8bca8-156">공유 프레임워크: 제거된 Microsoft.AspNetCore.All이 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-156">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="8bca8-157">SignalR: HandshakeProtocol.SuccessHandshakeData가 대체됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-157">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="8bca8-158">SignalR: HubConnection 메서드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-158">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="8bca8-159">SignalR: HubConnectionContext 생성자가 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-159">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="8bca8-160">SignalR: JavaScript 클라이언트 패키지 이름 변경</span><span class="sxs-lookup"><span data-stu-id="8bca8-160">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="8bca8-161">SignalR: MessagePack 허브 프로토콜이 MessagePack 2.x 패키지로 이동됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-161">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="8bca8-162">SignalR: MessagePack 허브 프로토콜 옵션 형식이 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-162">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="8bca8-163">SignalR: 사용되지 않는 API</span><span class="sxs-lookup"><span data-stu-id="8bca8-163">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="8bca8-164">SignalR: UseSignalR 및 UseConnections 메서드가 제거됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-164">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="8bca8-165">SPA: SpaServices 및 NodeServices 콘솔 로거 대체 기본 변경</span><span class="sxs-lookup"><span data-stu-id="8bca8-165">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="8bca8-166">SPA: 사용되지 않는 것으로 표시된 SpaServices 및 NodeServices</span><span class="sxs-lookup"><span data-stu-id="8bca8-166">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="8bca8-167">정적 파일: CSV 콘텐츠 형식이 표준 규격으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="8bca8-167">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="8bca8-168">대상 프레임워크: 지원되지 않는 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8bca8-168">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="8bca8-169">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="8bca8-169">ASP.NET Core 5.0</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="8bca8-170">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8bca8-170">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="8bca8-171">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8bca8-171">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

***

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

***

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

***

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

***

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

***

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

***

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

***

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

***

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

***

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

***

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

***

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

***

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

***

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

***

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

***

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

***

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

***

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

***

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

***

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

***

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

***

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

***

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

***

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

***

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

***

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

***

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

***

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

***

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

***

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

***

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

***

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

***

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

***

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

***

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

***

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

***

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

***

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

***

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

***

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

***

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

***

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

***

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

***

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

***

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

***

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

***

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

***

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

***
