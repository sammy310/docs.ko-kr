---
ms.openlocfilehash: 3f702febc78488b9413ec9303ded211493650f02
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198511"
---
### <a name="mvc-precompilation-tool-deprecated"></a>MVC: 미리 컴파일 도구가 사용되지 않음

ASP.NET Core 1.1에서는 Razor 파일( *.cshtml* 파일)의 게시 시간 컴파일 지원을 추가하기 위해 `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation`(MVC 미리 컴파일 도구) 패키지가 도입되었습니다. ASP.NET Core 2.1에서는 [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1)가 미리 컴파일 도구의 기능을 확장하기 위해 도입되었습니다. Razor SDK는 Razor 파일의 빌드 및 게시 시간 컴파일에 대한 지원을 추가했습니다. SDK는 앱 시작 시간을 개선하면서 빌드 시 *.cshtml* 파일의 정확성을 확인합니다. Razor SDK는 기본적으로 켜져 있으며 사용을 시작하는 데 제스처는 필요하지 않습니다.

ASP.NET Core 3.0에서는 ASP.NET Core 1.1-era MVC 미리 컴파일 도구가 제거되었습니다. 이전 패키지 버전은 패치 릴리스에서 중요한 버그 및 보안 픽스를 계속 받습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` 패키지는 MVC Razor 뷰를 미리 컴파일하는 데 사용되었습니다.

#### <a name="new-behavior"></a>새 동작

Razor SDK는 기본적으로 이 기능을 지원합니다. `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` 패키지가 더 이상 업데이트되지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

Razor SDK는 더 많은 기능을 제공하고 빌드 시 *.cshtml* 파일의 정확성을 확인합니다. 또한 SDK는 앱 시작 시간을 개선합니다.

#### <a name="recommended-action"></a>권장 작업

ASP.NET Core 2.1 이상 사용자의 경우 [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0)에서 미리 컴파일에 대한 기본 지원을 사용하도록 업데이트합니다. 버그 또는 누락된 기능으로 인해 Razor SDK로 마이그레이션할 수 없는 경우 [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues)에서 문제를 엽니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

### Affected APIs

Not detectable via API analysis

-->
