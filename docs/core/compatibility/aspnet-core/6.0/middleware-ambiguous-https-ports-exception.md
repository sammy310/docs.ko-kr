---
title: '호환성이 손상되는 변경: 미들웨어: HTTPS 리디렉션 미들웨어가 모호한 HTTPS 포트에 대해 예외 throw'
description: 'ASP.NET Core 6.0의 호환성이 손상되는 변경에 관해 알아보기. Middleware: HTTPS 리디렉션 미들웨어가 모호한 HTTPS 포트에 대해 예외 throw'
author: scottaddie
ms.author: scaddie
ms.date: 02/04/2021
ms.openlocfilehash: 1f49e0df7eaa2eecd83643c9596e745109a340b7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488236"
---
# <a name="middleware-https-redirection-middleware-throws-exception-on-ambiguous-https-ports"></a>미들웨어: HTTPS 리디렉션 미들웨어가 모호한 HTTPS 포트에 대해 예외 throw

ASP.NET Core 6.0에서 [HTTPS 리디렉션 미들웨어](xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A)는 서버 구성에서 여러 HTTPS 포트를 찾을 경우 <xref:System.InvalidOperationException> 형식의 예외를 throw합니다. 예외 메시지에는 “IServerAddressesFeature에서 HTTPS 포트를 확인할 수 없습니다. 값이 여러 개 있습니다. HttpsRedirectionOptions.HttpsPort에서 원하는 포트를 명시적으로 설정합니다.”라는 텍스트가 포함됩니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#29222](https://github.com/dotnet/aspnetcore/issues/29222)를 참조하세요.

## <a name="version-introduced"></a>도입된 버전

6.0

## <a name="old-behavior"></a>이전 동작

HTTPS 리디렉션 미들웨어는 포트를 사용하여 명시적으로 구성되지 않은 경우 첫 번째 요청 중에 <xref:Microsoft.AspNetCore.Hosting.Server.Features.IServerAddressesFeature>를 검색하여 리디렉션해야 하는 HTTPS 포트를 결정합니다.

HTTPS 포트가 없거나 여러 개별 포트가 있으면 사용해야 하는 포트가 분명하지 않습니다. 미들웨어는 경고를 로그하며 사용하지 않도록 설정됩니다. HTTP 요청은 정상적으로 처리됩니다.

## <a name="new-behavior"></a>새 동작

HTTPS 리디렉션 미들웨어는 포트를 사용하여 명시적으로 구성되지 않은 경우 첫 번째 요청 중에 `IServerAddressesFeature`를 검색하여 리디렉션해야 하는 HTTPS 포트를 결정합니다.

HTTPS 포트가 없어도 미들웨어는 여전히 경고를 로그하며 사용하지 않도록 설정됩니다. HTTP 요청은 정상적으로 처리됩니다. 이 동작은 다음을 지원합니다.

* HTTPS를 사용하지 않는 개발 시나리오.
* 서버에 도달하기 전에 TLS가 종료되는 호스티드 시나리오.

여러 개별 포트가 있는 경우 사용해야 하는 포트가 분명하지 않습니다. 미들웨어는 예외를 throw하고 HTTP 요청에 실패합니다.

## <a name="reason-for-change"></a>변경 이유

이 변경은 HTTPS가 사용 가능한 것으로 알려진 경우 암호화되지 않은 HTTP 연결을 통해 잠재적으로 중요한 데이터가 제공되지 않도록 합니다.

## <a name="recommended-action"></a>권장 조치

서버에 여러 개별 HTTPS 포트가 있을 때 HTTPS 리디렉션을 사용하도록 설정하려면 구성에서 하나의 포트를 지정해야 합니다. 자세한 내용은 [포트 구성](/aspnet/core/security/enforcing-ssl?view=aspnetcore-5.0&preserve-view=true#port-configuration)을 참조하세요.

앱에서 HTTPS 리디렉션 미들웨어가 필요하지 않은 경우 *Startup.cs* 에서 `UseHttpsRedirection`을 제거합니다.

올바른 HTTPS 포트를 동적으로 선택해야 하는 경우 GitHub 이슈 [dotnet/aspnetcore#21291](https://github.com/dotnet/aspnetcore/issues/21291)에서 피드백을 제공합니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A?displayProperty=nameWithType>

<!--

## Category

ASP.NET Core

## Affected APIs

`Overload:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection`

-->
