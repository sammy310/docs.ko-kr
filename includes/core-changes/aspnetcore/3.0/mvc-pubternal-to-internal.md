---
ms.openlocfilehash: 09fd95ba5f3aee59f2abdfbb4e64eb6202e2b873
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394423"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a>MVC: "Pubternal" 유형이 내부로 변경됨

ASP.NET Core 3.0에서는 MVC의 모든 "pubternal" 형식이 지원되는 네임스페이스에서 `public` 또는 필요에 따라 `internal`로 업데이트되었습니다.

#### <a name="change-description"></a>변경 내용 설명

ASP.NET Core에서 "pubternal" 형식은 `public`으로 선언되었지만 `.Internal` 접미사가 지정된 네임스페이스에 있습니다. 이러한 형식은 `public`이지만 지원 정책이 없으며 호환성이 손상되는 변경이 적용됩니다. 아쉽게도 이러한 형식의 우발적 사용이 일반적으로 발생하므로 이러한 프로젝트에 대한 호환성이 손상되는 변경이 발생하고 프레임워크를 유지 관리하는 기능이 제한됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

MVC의 일부 형식은 `public`이지만 `.Internal` 네임스페이스에 있습니다. 이러한 형식에는 지원 정책이 없었으며 호환성이 손상되는 변경이 적용되었습니다.

#### <a name="new-behavior"></a>새 동작

이러한 모든 형식은 지원되는 네임스페이스에서 `public`으로 업데이트되거나 `internal`로 표시됩니다.

#### <a name="reason-for-change"></a>변경 이유

"pubternal" 형식의 우발적 사용이 일반적으로 발생하므로 이러한 프로젝트에 대한 호환성이 손상되는 변경이 발생하고 프레임워크를 유지 관리하는 기능이 제한됩니다.

#### <a name="recommended-action"></a>권장 작업

실제로 `public`이 되고 지원되는 새 네임스페이스로 이동한 형식을 사용하는 경우 새 네임스페이스와 일치하도록 참조를 업데이트합니다.

`internal`로 표시된 형식을 사용하는 경우에는 다른 방법을 찾아야 합니다. 이전에 "pubternal" 형식은 공용으로 지원되지 않았습니다. 이러한 네임스페이스의 앱에 중요한 특정 형식이 있는 경우 [aspnet/AspNetCore ](https://github.com/aspnet/AspNetCore/issues)에서 문제를 해결합니다. 요청된 형식 `public`을 만드는 것을 고려할 수 있습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

이 변경 내용에는 다음 네임스페이스의 형식이 포함됩니다.

- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

-->
