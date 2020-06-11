---
ms.openlocfilehash: b1fb9647091cecb80b9c2f04ec9b6bb156eb39ba
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84466833"
---
### <a name="pubternal-apis-removed"></a>"Pubternal" API가 제거됨

ASP.NET Core의 공용 API 노출 영역을 보다 효율적으로 유지 관리하기 위해 `*.Internal` 네임스페이스(:::no-loc text="\"pubternal\""::: API라고 함)에 있는 대부분의 형식이 진정한 내부용이 되었습니다. 이러한 네임스페이스의 멤버는 공용 API로 지원되지 않았습니다. 이러한 API는 마이너 릴리스에서 중단 가능성이 있었고 실제로 자주 중단되었습니다. ASP.NET Core 3.0으로 업데이트할 때 이러한 API에 종속된 코드가 중단됩니다.

자세한 내용은 [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) 및 [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

영향을 받는 API가 `public` 액세스 한정자로 표시되고 `*.Internal` 네임스페이스에 존재합니다.

#### <a name="new-behavior"></a>새 동작

영향을 받는 API가 [internal](/dotnet/csharp/language-reference/keywords/internal) 액세스 한정자로 표시되며, 해당 어셈블리 외부의 코드에서 이 API를 더 이상 사용할 수 없습니다.

#### <a name="reason-for-change"></a>변경 이유

이러한 :::no-loc text="\"pubternal\""::: API에 대한 지침은 다음과 같은 특성이 있었습니다.

* 예고 없이 변경될 수 있었습니다.
* 호환성이 손상되는 변경을 방지하기 위해 .NET 정책에 적용되지 않았습니다.

API를 `public`으로 유지하여(`*.Internal` 네임스페이스에서도) 고객이 혼동할 수 있었습니다.

#### <a name="recommended-action"></a>권장 조치

이러한 :::no-loc text="\"pubternal\""::: API 사용을 중지합니다. 대체 API에 대한 질문이 있는 경우 [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) 리포지토리에서 문제를 여세요.

예를 들어 ASP.NET Core 2.2 프로젝트에서 다음 HTTP 요청 버퍼링 코드가 있습니다. `EnableRewind` 확장 메서드는 `Microsoft.AspNetCore.Http.Internal` 네임스페이스에 있습니다.

```csharp
HttpContext.Request.EnableRewind();
```

ASP.NET Core 3.0 프로젝트에서 `EnableRewind` 호출을 `EnableBuffering` 확장 메서드에 대한 호출로 바꿉니다. 요청 버퍼링 기능은 이전과 동일하게 작동합니다. `EnableBuffering`은 이제 `internal` API를 호출합니다.

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

네임 스페이스 이름에 `Internal` 세그먼트가 있는 `Microsoft.AspNetCore.*` 및 `Microsoft.Extensions.*` 네임스페이스의 모든 API. 예를 들어:

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
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
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
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
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
