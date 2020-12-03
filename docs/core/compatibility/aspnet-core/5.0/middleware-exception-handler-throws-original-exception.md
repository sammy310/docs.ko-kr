---
title: '호환성이 손상되는 변경: 미들웨어: 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어가 원래 예외를 throw함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Middleware: 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어가 원래 예외를 throw함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759978"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a>미들웨어: 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어가 원래 예외를 throw함

ASP.NET Core 5.0 전에 예외 발생 시 [예외 처리기 미들웨어](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A)는 구성된 처리기를 실행합니다. <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>를 통해 구성된 예외 처리기를 찾을 수 없는 경우에는 HTTP 404 응답이 생성됩니다. 응답은 다음과 같은 점에서 잘못된 응답입니다.

* 사용자 오류인 것 같습니다.
* 서버에서 예외가 발생했다는 사실을 모호하게 합니다.

ASP.NET Core 5.0에서 잘못된 오류를 해결하기 위해 예외 처리기를 찾을 수 없는 경우 `ExceptionHandlerMiddleware`는 원래 예외를 throw합니다. 따라서 서버에서 HTTP 500 응답이 생성됩니다. 발생한 오류를 디버그할 때 서버 로그에서 응답을 검토하는 것이 더 쉽습니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 RC 1

## <a name="old-behavior"></a>이전 동작

구성된 예외 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어는 HTTP 404 응답을 생성합니다.

## <a name="new-behavior"></a>새 동작

구성된 예외 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어는 원래 예외를 throw합니다.

## <a name="reason-for-change"></a>변경 이유

HTTP 404 오류는 예외가 서버에서 발생했음을 명확히 나타내지 않습니다. 이 변경으로 인해 다음을 명확히 하는 HTTP 500 오류가 생성됩니다.

* 문제가 사용자 오류로 인해 발생하지 않았습니다.
* 서버에서 예외가 발생했습니다.

## <a name="recommended-action"></a>권장 조치

API의 변경이 없습니다. 모든 기존 앱은 계속 컴파일되고 실행됩니다. throw된 예외는 서버에서 처리됩니다. 예를 들어 [Kestrel](/aspnet/core/fundamentals/servers/kestrel) 또는 [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys)에 의해 예외가 HTTP 500 오류 응답으로 변환됩니다.

## <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
