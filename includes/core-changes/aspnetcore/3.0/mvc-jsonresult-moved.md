---
ms.openlocfilehash: 1356f3eee5e2d8090d7d96aafc07a19507a1aff1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721597"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult를 Microsoft.AspNetCore.Mvc.Core로 이동

`JsonResult`가 `Microsoft.AspNetCore.Mvc.Core` 어셈블리로 이동했습니다. 이 형식은 [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json)에서 정의되었습니다. 대부분 사용자의 문제를 해결하기 위해 어셈블리 수준 [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) 특성이 `Microsoft.AspNetCore.Mvc.Formatters.Json`에 추가되었습니다. 타사 라이브러리를 사용하는 앱에서 문제가 발생할 수 있습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0 미리 보기 6

#### <a name="old-behavior"></a>이전 동작

2\.2 기반 라이브러리를 사용하는 앱이 성공적으로 빌드됩니다.

#### <a name="new-behavior"></a>새 동작

2\.2 기반 라이브러리를 사용하는 앱이 컴파일에 실패합니다. 다음 텍스트의 변형을 포함하는 오류가 제공됩니다.

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

이러한 문제의 예는 [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220)을 참조하세요.

#### <a name="reason-for-change"></a>변경 이유

플랫폼 수준이 [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325)에서 설명하는 것과 같이 ASP.NET Core의 컴퍼지션으로 변경됩니다.

#### <a name="recommended-action"></a>권장 조치

`Microsoft.AspNetCore.Mvc.Formatters.Json` 2.2 버전에 대해 컴파일된 라이브러리를 다시 컴파일하여 모든 소비자에 대한 문제를 해결해야 할 수 있습니다. 영향을 받는 경우 라이브러리 작성자에게 문의하세요. ASP.NET Core 3.0을 대상으로 하는 라이브러리의 재컴파일을 요청합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
