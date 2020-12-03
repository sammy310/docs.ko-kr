---
title: '호환성이 손상되는 변경: 보안: 쿠키 이름 인코딩이 제거됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 보안: 쿠키 이름 인코딩이 제거됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 3cd40d2b04d0cdf0863e3a3fb6d790c2b35692bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760032"
---
# <a name="security-cookie-name-encoding-removed"></a>보안: 쿠키 이름 인코딩이 제거됨

[HTTP 쿠키 표준](https://tools.ietf.org/html/rfc6265#section-4.1.1)에서는 쿠키 이름과 값에 특정 문자만 허용합니다. 허용되지 않는 문자를 지원하기 위해 ASP.NET Core에서 다음 작업을 수행합니다.

* 응답 쿠키를 만드는 경우 인코딩합니다.
* 요청 쿠키를 읽는 경우 디코딩합니다.

ASP.NET Core 5.0에서는 보안 문제에 대한 응답으로 이 인코딩 동작이 변경되었습니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 8

## <a name="old-behavior"></a>이전 동작

응답 쿠키 이름이 인코딩됩니다. 요청 쿠키 이름이 디코딩됩니다.

## <a name="new-behavior"></a>새 동작

쿠키 이름의 인코딩 및 디코딩이 제거되었습니다. [지원되는 이전 ASP.NET Core 버전](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)에 대해 팀은 현재 위치에서 디코딩 문제를 완화할 계획입니다. 또한 잘못된 쿠키 이름으로 <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType>을 호출하면 <xref:System.ArgumentException> 형식의 예외가 throw됩니다. 쿠키 값의 인코딩 및 디코딩은 변경되지 않고 그대로 유지됩니다.

## <a name="reason-for-change"></a>변경 이유

[여러 개의 웹 프레임워크](https://github.com/advisories/GHSA-j6w9-fv6q-3q52)에서 문제가 발견되었습니다. 인코딩 및 디코딩을 통해 공격자가 `__Host-` 등의 예약된 접두사를 `__%48ost-` 등의 인코딩된 값으로 스푸핑하여 [쿠키 접두사](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00)라는 보안 기능을 무시할 수 있었습니다. 이 공격을 수행하려면 웹 사이트에 XSS(교차 사이트 스크립팅) 취약성과 같은 스푸핑된 쿠키를 삽입하기 위한 보조 익스플로잇이 필요합니다. 해당 접두사는 ASP.NET Core 또는 `Microsoft.Owin` 라이브러리나 템플릿에서 기본적으로 사용되지 않습니다.

## <a name="recommended-action"></a>권장 조치

프로젝트를 ASP.NET Core 5.0 이상으로 이동하는 경우 해당 쿠키 이름이 [토큰 사양 요구 사항](https://tools.ietf.org/html/rfc2616#section-2.2)을 준수하는지 확인합니다. 즉, 컨트롤과 구분 기호를 제외하고 ASCII 문자를 사용해야 합니다(`"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`). 쿠키 이름 또는 다른 HTTP 헤더에 비ASCII 문자를 사용하면 서버에서 예외가 발생하거나 클라이언트에서 부적절한 라운드트립이 발생할 수 있습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
