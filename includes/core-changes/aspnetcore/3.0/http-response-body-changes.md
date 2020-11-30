---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032540"
---
### <a name="http-response-body-infrastructure-changes"></a>HTTP: 응답 본문 인프라 변경

HTTP 응답 본문을 지원하는 인프라가 변경되었습니다. `HttpResponse`를 직접 사용하는 경우 코드를 변경할 필요가 없습니다. `HttpResponse.Body`를 래핑 또는 대체하거나 `HttpContext.Features`에 액세스하는 경우 자세히 읽어보세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

HTTP 응답 본문과 관련된 세 가지 API가 있습니다.

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a>새 동작

`HttpResponse.Body`를 바꾸면 `StreamResponseBodyFeature`를 사용하여 전체 `IHttpResponseBodyFeature`를 지정된 스트림 주변의 래퍼로 대체하여 모든 예상 API에 대한 기본 구현을 제공합니다. 원래 스트림으로 다시 설정하면 이 변경 내용이 되돌려집니다.

#### <a name="reason-for-change"></a>변경 이유

응답 본문 API를 새로운 단일 기능 인터페이스로 결합하는 것이 좋습니다.

#### <a name="recommended-action"></a>권장 조치

이전에 `IHttpResponseFeature.Body`, `IHttpSendFileFeature` 또는 `IHttpBufferingFeature`를 사용했던 `IHttpResponseBodyFeature`를 사용합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
