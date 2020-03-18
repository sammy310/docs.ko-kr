---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901581"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a>호스팅: Windows Hosting Bundle에서 AspNetCoreModule V1이 제거됨

ASP.NET Core 3.0부터 Windows Hosting Bundle에는 ANCM(AspNetCoreModule) V1이 포함되어 있지 않습니다.

ANCM V2는 ANCM OutOfProcess와 역호환되며 ASP.NET Core 3.0 앱에서 사용하는 것이 좋습니다.

토론은 [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

ANCM V1은 Windows Hosting Bundle에 포함되어 있습니다.

#### <a name="new-behavior"></a>새 동작

ANCM V1은 Windows Hosting Bundle에 포함되어 있지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

ANCM V2는 ANCM OutOfProcess와 역호환되며 ASP.NET Core 3.0 앱에서 사용하는 것이 좋습니다.

#### <a name="recommended-action"></a>권장 조치

ASP.NET Core 3.0 앱에서 ANCM V2를 사용합니다.

ANCM V1이 필요한 경우 ASP.NET Core 2.1 또는 2.2 Windows Hosting Bundle을 사용하여 설치할 수 있습니다.

이 변경으로 인해 다음과 같은 ASP.NET Core 3.0 앱이 중단됩니다.

- `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`에서 ANCM V1을 사용하도록 명시적으로 선택했습니다.
- `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`를 사용하여 사용자 지정 *web .config* 파일을 만듭니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
