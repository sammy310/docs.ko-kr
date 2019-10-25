---
ms.openlocfilehash: a916af91670dc9c5ceb2ff759cd8ae308fb2c2dc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393913"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel: 연결 어댑터가 제거됨

"pubternal" API를 `public`으로 이동하는 과정의 일부로, `IConnectionAdapter`의 개념이 Kestrel에서 제거되었습니다. 연결 어댑터는 연결 미들웨어(ASP.NET Core 파이프라인의 HTTP 미들웨어와 유사하지만 하위 수준 연결용)로 대체되고 있습니다. HTTPS 및 연결 로깅은 연결 어댑터에서 연결 미들웨어로 이동했습니다. 이러한 확장 메서드는 계속해서 원활하게 작동하지만 구현 세부 정보는 변경되었습니다.

자세한 내용은 [aspnet/AspNetCore#11412](https://github.com/aspnet/AspNetCore/pull/11412)를 참조하세요. 자세한 내용은 [aspnet/AspNetCore#11475](https://github.com/aspnet/AspNetCore/issues/11475)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`IConnectionAdapter`를 사용하여 kestrel 확장성 구성 요소를 만들었습니다.

#### <a name="new-behavior"></a>새 동작

kestrel 확장성 구성 요소는 [미들웨어](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f)로 만들었습니다.

#### <a name="reason-for-change"></a>변경 이유

이 변경은 보다 유연한 확장성 아키텍처를 제공하기 위한 것입니다.

#### <a name="recommended-action"></a>권장 작업

[여기에](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f) 표시된 대로 새 미들웨어 패턴을 사용하도록 `IConnectionAdapter`의 구현을 변환합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
