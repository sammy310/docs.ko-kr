---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394204"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a>공유 프레임워크: 제거된 Microsoft.AspNetCore.All

ASP.NET Core 3.0부터 `Microsoft.AspNetCore.All` 메타패키지 및 일치하는 `Microsoft.AspNetCore.All` 공유 프레임워크가 더 이상 생성되지 않습니다. 이 패키지는 ASP.NET Core 2.2에서 사용할 수 있으며 ASP.NET Core 2.1에서 서비스 업데이트를 계속 받을 수 있습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

앱은 `Microsoft.AspNetCore.All` 메타패키지를 사용하여 .NET Core에서 `Microsoft.AspNetCore.All` 공유 프레임워크를 대상으로 할 수 있습니다.

#### <a name="new-behavior"></a>새 동작

.NET Core 3.0에는 `Microsoft.AspNetCore.All` 공유 프레임워크가 포함되어 있지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

`Microsoft.AspNetCore.All` 메타패키지에는 많은 수의 외부 종속성이 포함되어 있습니다.

#### <a name="recommended-action"></a>권장 조치

`Microsoft.AspNetCore.App` 프레임워크를 사용하도록 프로젝트를 마이그레이션합니다. 이전에 `Microsoft.AspNetCore.All`에서 사용할 수 있었던 구성 요소는 NuGet에서 계속 사용할 수 있습니다. 이러한 구성 요소는 이제 공유 프레임워크에 포함되지 않고 앱과 함께 배포됩니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
