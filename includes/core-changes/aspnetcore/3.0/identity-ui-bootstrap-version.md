---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032569"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a>ID: UI의 기본 부트스트랩 버전이 변경됨

ASP.NET Core 3.0부터 ID UI는 기본적으로 부트스트랩 버전 4를 사용합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` 메서드 호출은 `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`와 동일했습니다.

#### <a name="new-behavior"></a>새 동작

`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` 메서드 호출은 `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`와 동일합니다.

#### <a name="reason-for-change"></a>변경 이유

부트스트랩 4는 ASP.NET Core 3.0 기간 동안 릴리스되었습니다.

#### <a name="recommended-action"></a>권장 조치

기본 ID UI를 사용하고 다음 예제와 같이 `Startup.ConfigureServices`에 추가한 경우 이 변경 내용의 영향을 받게 됩니다.

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

다음 작업 중 하나를 수행합니다.

- [마이그레이션 가이드](https://getbootstrap.com/docs/4.0/migration)를 사용하여 부트스트랩 4를 사용하도록 앱을 마이그레이션합니다.
- 부트스트랩 3의 사용을 적용하도록 `Startup.ConfigureServices`를 업데이트합니다. 예를 들어:

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
