---
title: '호환성이 손상되는 변경: 이제 쿠키 경로 처리가 RFC 6265를 준수함'
description: RFC 6265에 정의된 경로 처리 알고리즘이 Cookie 및 CookieContainer 클래스에 대해 구현된 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 08/18/2020
ms.openlocfilehash: 4aea06f434c4bbbef7d94b4b39ff647dd954745e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759700"
---
# <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>이제 쿠키 경로 처리가 RFC 6265를 준수함

[RFC 6265](https://tools.ietf.org/html/rfc6265)에 정의된 경로 처리 알고리즘은 <xref:System.Net.Cookie> 및 <xref:System.Net.CookieContainer> 클래스에 대해 구현되었습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="change-description"></a>변경 내용 설명

- 이제 <xref:System.Net.Cookie.Path> 속성에 요청 경로를 접두사로 사용하지 않아도 됩니다.
- <xref:System.Net.Cookie.Path>의 기본값 계산과 경로 일치 알고리즘은 RFC 6265의 [섹션 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4)에 정의된 대로 구현되었습니다.

## <a name="recommended-action"></a>권장 조치

대부분의 경우 아무 동작도 수행할 필요가 없습니다. 그러나 코드가 <xref:System.Net.Cookie.Path> 유효성 검사에 종속된 경우 코드에서 필요한 유효성 검사를 구현해야 합니다. 코드가 <xref:System.Net.Cookie.Path>의 기본값 계산에 종속된 경우 기본값을 사용하는 대신 <xref:System.Net.Cookie.Path> 값을 수동으로 지정하는 것이 좋습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

### Category

Networking

-->
