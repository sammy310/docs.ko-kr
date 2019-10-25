---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394108"
---
### <a name="kestrel-empty-https-assembly-removed"></a>Kestrel: 빈 HTTPS 어셈블리가 제거됨

<xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> 어셈블리가 제거되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 2.1에서 `Microsoft.AspNetCore.Server.Kestrel.Https`의 내용이 <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>으로 이동했습니다. 이 변경은 `[TypeForwardedTo]` 특성을 사용하여 중단되지 않는 방식으로 수행되었습니다.

#### <a name="recommended-action"></a>권장 작업

- `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0를 참조하는 라이브러리는 모든 ASP.NET Core 종속성을 2.1 이상으로 업데이트해야 합니다. 그렇지 않으면 ASP.NET Core 3.0 앱에 로드될 때 중단될 수 있습니다.
- ASP.NET Core 2.1 이상을 대상으로 하는 앱 및 라이브러리는 `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet 패키지에 대한 직접 참조를 모두 제거해야 합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
