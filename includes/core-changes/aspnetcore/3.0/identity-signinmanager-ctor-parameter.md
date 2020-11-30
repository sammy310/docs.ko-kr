---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032560"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>ID: SignInManager 생성자는 새 매개 변수를 허용합니다.

ASP.NET Core 3.0부터 새 `IUserConfirmation<TUser>` 매개 변수가 `SignInManager` 생성자에 추가되었습니다. 자세한 내용은 [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

변경에 대한 동기는 ID에 새 이메일/확인 흐름에 대한 지원을 추가하는 것이었습니다.

#### <a name="recommended-action"></a>권장 조치

`SignInManager`를 수동으로 구성하는 경우 `IUserConfirmation`의 구현을 제공하거나 종속성 주입에서 하나를 가져와 제공합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
