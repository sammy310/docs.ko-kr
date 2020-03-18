---
ms.openlocfilehash: 9d138f79fcede4acac837f8d7793aa343ced737c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78290739"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: DefaultHttpContext 확장성이 제거됨

ASP.NET Core 3.0 성능 향상의 일환으로 `DefaultHttpContext`의 확장성이 제거되었습니다. 클래스는 이제 `sealed`입니다. 자세한 내용은 [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504)를 참조하세요.

단위 테스트에 `Mock<DefaultHttpContext>`가 사용되는 경우에는 대신 `Mock<HttpContext>` 또는 `new DefaultHttpContext()`를 사용합니다.

토론은 [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

클래스는 `DefaultHttpContext`에서 파생될 수 있습니다.

#### <a name="new-behavior"></a>새 동작

클래스는 `DefaultHttpContext`에서 파생될 수 없습니다.

#### <a name="reason-for-change"></a>변경 이유

확장성은 처음에는 `HttpContext`의 풀링을 허용하기 위해 제공되었지만 불필요 한 복잡성을 야기하고 기타 최적화를 방해했습니다.

#### <a name="recommended-action"></a>권장 조치

단위 테스트에서 `Mock<DefaultHttpContext>`를 사용하는 경우, 대신 `Mock<HttpContext>`를 사용합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
