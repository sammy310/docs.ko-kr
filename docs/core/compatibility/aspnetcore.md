---
title: ASP.NET Core 호환성이 손상되는 변경
titleSuffix: ''
description: ASP.NET Core의 호환성이 손상되는 변경을 나열합니다.
ms.date: 01/10/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: c54735cd53fb9cb48eb84045791ccc559fe683cd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093177"
---
# <a name="aspnet-core-breaking-changes"></a>ASP.NET Core 호환성이 손상되는 변경

ASP.NET Core는 .NET Core에서 사용되는 웹앱 개발 기능을 제공합니다.

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

- [HTTP: 브라우저 SameSite 변경 내용이 인증에 영향](#http-browser-samesite-changes-impact-authentication)
- [사용되지 않는 위조 방지, CORS, 진단, MVC 및 라우팅 API가 제거됨](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [인증: Google + 사용 중단](#authentication-google-deprecated-and-replaced)
- [인증: HttpContext.Authentication 인증 속성이 제거됨](#authentication-httpcontextauthentication-property-removed)
- [인증: Newtonsoft.json 형식이 대체됨](#authentication-newtonsoftjson-types-replaced)
- [인증: OAuthHandler ExchangeCodeAsync 서명이 변경됨](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [권한 부여: AddAuthorization 오버로드가 다른 어셈블리로 이동됨](#authorization-addauthorization-overload-moved-to-different-assembly)
- [권한 부여: AuthorizationFilterContext.Filters에서 IAllowAnonymous 제거됨](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [권한 부여: IAuthorizationPolicyProvider 구현에는 새 메서드가 필요합니다.](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [캐싱: CompactOnMemoryPressure 속성이 제거됨](#caching-compactonmemorypressure-property-removed)
- [캐싱: Microsoft.Extensions.Caching.SqlServer는 새 SqlClient 패키지를 사용합니다.](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [캐싱: ResponseCaching “pubternal” 유형이 내부로 변경됨](#caching-responsecaching-pubternal-types-changed-to-internal)
- [데이터 보호: DataProtection.AzureStorage는 새로운 Azure Storage API를 사용합니다.](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [호스팅: Windows Hosting Bundle에서 AspNetCoreModule V1이 제거됨](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [호스팅: 제네릭 호스트는 시작 생성자 주입을 제한합니다.](#hosting-generic-host-restricts-startup-constructor-injection)
- [호스팅: IIS Out of Process 앱에 대해 HTTPS 리디렉션 사용](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [호스팅: IHostingEnvironment 및 IApplicationLifetime 형식이 바뀜](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [호스팅: WebHostBuilder 종속성에서 제거되는 ObjectPoolProvider](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [HTTP: DefaultHttpContext 확장성이 제거됨](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: HeaderNames 필드가 정적 읽기 전용으로 변경됨](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: 응답 본문 인프라 변경](#http-response-body-infrastructure-changes)
- [HTTP: 일부 쿠키 SameSite 기본값이 변경됨](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: 기본적으로 사용하지 않도록 설정된 동기 IO](#http-synchronous-io-disabled-in-all-servers)
- [ID: AddDefaultUI 메서드 오버로드가 제거됨](#identity-adddefaultui-method-overload-removed)
- [ID: UI 부트스트랩 버전 변경](#identity-default-bootstrap-version-of-ui-changed)
- [ID: SignInAsync는 인증되지 않은 ID에 대해 예외를 throw합니다.](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [ID: SignInManager 생성자는 새 매개 변수를 허용합니다.](#identity-signinmanager-constructor-accepts-new-parameter)
- [ID: UI는 정적 웹 자산 기능을 사용합니다.](#identity-ui-uses-static-web-assets-feature)
- [Kestrel: 연결 어댑터가 제거됨](#kestrel-connection-adapters-removed)
- [Kestrel: 빈 HTTPS 어셈블리가 제거됨](#kestrel-empty-https-assembly-removed)
- [Kestrel: 요청 후행부 헤더가 새 컬렉션으로 이동됨](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Kestrel: 전송 추상화 계층 변경](#kestrel-transport-abstractions-removed-and-made-public)
- [지역화: 사용되지 않음으로 표시된 API](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [로깅: DebugLogger 클래스를 내부적으로 만들었습니다.](#logging-debuglogger-class-made-internal)
- [MVC: 컨트롤러 작업 비동기 접미사가 제거됨](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult를 Microsoft.AspNetCore.Mvc.Core로 이동](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: 미리 컴파일 도구가 사용되지 않음](#mvc-precompilation-tool-deprecated)
- [MVC: 형식이 내부로 변경됨](#mvc-pubternal-types-changed-to-internal)
- [MVC: 웹 API 호환성 shim이 제거됨](#mvc-web-api-compatibility-shim-removed)
- [Razor: 런타임 컴파일이 패키지로 이동됨](#razor-runtime-compilation-moved-to-a-package)
- [세션 상태: 사용되지 않는 API가 제거됨](#session-state-obsolete-apis-removed)
- [공유 프레임워크: Microsoft.AspNetCore.App에서 어셈블리 제거](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [공유 프레임워크: 제거된 Microsoft.AspNetCore.All이 제거됨](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: HandshakeProtocol.SuccessHandshakeData가 대체됨](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: HubConnection 메서드가 제거됨](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: HubConnectionContext 생성자가 변경됨](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: JavaScript 클라이언트 패키지 이름 변경](#signalr-javascript-client-package-name-changed)
- [SignalR: 사용되지 않는 API](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SPA: 사용되지 않는 것으로 표시된 SpaServices 및 NodeServices](#spas-spaservices-and-nodeservices-marked-obsolete)
- [SPA: SpaServices 및 NodeServices 콘솔 로거 대체 기본 변경](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [대상 프레임워크: 지원되지 않는 .NET Framework](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-31"></a>ASP.NET Core 3.1

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a>ASP.NET Core 3.0

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
