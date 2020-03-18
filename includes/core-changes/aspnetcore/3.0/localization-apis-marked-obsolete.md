---
ms.openlocfilehash: 8cb0aca991f5adfe4561ef56090cb9f7b2e56283
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902039"
---
### <a name="localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete"></a>지역화: 사용되지 않는 것으로 표시된 ResourceManagerWithCultureStringLocalizer 및 WithCulture

[ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) 클래스 및 [WithCulture](https://github.com/aspnet/Localization/blob/master/src/Microsoft.Extensions.Localization/ResourceManagerStringLocalizer.cs#L154-L170) 인터페이스 멤버는 특히 고유한 `IStringLocalizer` 구현을 만들 때 지역화 사용자에게 혼동의 원인이 됩니다. 이러한 항목은 사용자에게 `IStringLocalizer` 인스턴스가 "언어별, 리소스별"이라는 인상을 줍니다. 실제로 인스턴스는 "리소스별"이어야 합니다. 검색된 언어는 실행 시 `CultureInfo.CurrentUICulture`에 의해 결정됩니다. 혼동의 원인을 제거하기 위해 API는 ASP.NET Core 3.0 Preview 3에서 사용되지 않는 것으로 표시되었습니다. API는 이후 릴리스에서 제거됩니다.

컨텍스트는 [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324)를 참조하세요. 토론은 [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

메서드가 `Obsolete`로 표시되지 않았습니다.

#### <a name="new-behavior"></a>새 동작

메서드는 `Obsolete`로 표시됩니다.

#### <a name="reason-for-change"></a>변경 이유

API는 권장되지 않는 사용 사례를 나타냅니다. 지역화 디자인에 대한 혼동이 있었습니다.

#### <a name="recommended-action"></a>권장 조치

대신 `ResourceManagerStringLocalizer`를 사용하는 것이 좋습니다. `CurrentCulture`에서 문화권을 설정하도록 합니다. 옵션이 아닌 경우 [ResourceManagerWithCultureStringLocalizer](https://github.com/aspnet/Localization/blob/43b974482c7b703c92085c6f68b3b23d8fe32720/src/Microsoft.Extensions.Localization/ResourceManagerWithCultureStringLocalizer.cs#L18) 복사본을 만들고 사용합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer>
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
