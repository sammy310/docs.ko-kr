---
ms.openlocfilehash: a8146db1fb54d63d4716b879ce793f7d817cef59
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937271"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a>공유 프레임워크: Microsoft.AspNetCore.App에서 제거되는 어셈블리

ASP.NET Core 3.0부터 ASP.NET Core 공유 프레임워크(`Microsoft.AspNetCore.App`)에는 Microsoft에서 완전히 개발하고, 지원하고, 서비스를 제공하는 자사 어셈블리만 포함되어 있습니다.

#### <a name="change-description"></a>변경 내용 설명

이러한 변경은 ASP.NET Core "플랫폼"의 경계를 다시 정의하는 것으로 간주합니다. 공유 프레임워크는 [GitHub를 통해 누구나 원본으로 빌드](https://github.com/dotnet/source-build)할 수 있으며, .NET Core 공유 프레임워크의 기존 이점을 앱에 계속 제공합니다. 몇 가지 이점으로 더 작은 배포 크기, 중앙 집중식 패치, 더 빠른 시작 시간 등이 있습니다.

변경의 일부로 몇 가지 주목할 만한 호환성이 손상되는 변경이 `Microsoft.AspNetCore.App`에 도입되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

프로젝트는 프로젝트 파일의 `<PackageReference>` 요소를 통해 `Microsoft.AspNetCore.App`을 참조했습니다.

또한 `Microsoft.AspNetCore.App`에는 다음과 같은 하위 구성 요소가 포함되었습니다.

- Json.NET(`Newtonsoft.Json`)
- Entity Framework Core(접두사가 `Microsoft.EntityFrameworkCore.`인 어셈블리)
- Roslyn(`Microsoft.CodeAnalysis`)

#### <a name="new-behavior"></a>새 동작

`Microsoft.AspNetCore.App`에 대한 참조에는 더 이상 프로젝트 파일의 `<PackageReference>` 요소가 필요하지 않습니다. .NET Core SDK는 `<PackageReference>`의 사용을 대체하는 `<FrameworkReference>`라는 새 요소를 지원합니다.

자세한 내용은 [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612)를 참조하세요.

Entity Framework Core는 NuGet 패키지로 제공됩니다. 이 변경은 배송 모델을 .NET의 다른 모든 데이터 액세스 라이브러리와 맞춥니다. 다양한 .NET 플랫폼을 지원하면서 계속 혁신할 수 있는 가장 간단한 경로인 Entity Framework Core를 제공합니다. Entity Framework Core를 공유 프레임워크 밖으로 이동하더라도 Microsoft에서 개발하고, 지원하고, 서비스를 제공하는 라이브러리의 상태에는 영향을 주지 않습니다. [.NET Core 지원 정책](https://www.microsoft.com/net/platform/support-policy)에서는 이를 계속 다루고 있습니다.

Json.NET 및 Entity Framework Core는 ASP.NET Core를 계속 사용합니다. 그러나 공유 프레임워크에는 포함되지 않습니다.

자세한 내용은 [.NET Core 3.0에서 JSON의 미래](https://github.com/dotnet/announcements/issues/90)를 참조하세요. 또한 공유 프레임워크에서 제거된 [이진 파일의 전체 목록](https://github.com/dotnet/aspnetcore/issues/3755)도 참조하세요.

#### <a name="reason-for-change"></a>변경 이유

이 변경으로 인해 `Microsoft.AspNetCore.App`의 사용이 간소화되고 NuGet 패키지와 공유 프레임워크 간의 중복이 줄어듭니다.

이 변경의 동기에 대한 자세한 내용은 [이 블로그 게시물](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/)을 참조하세요.

#### <a name="recommended-action"></a>권장 조치

프로젝트에서 `Microsoft.AspNetCore.App`의 어셈블리를 NuGet 패키지로 사용할 필요가 없습니다. ASP.NET Core 공유 프레임워크의 대상 지정 및 사용을 간소화하기 위해 ASP.NET Core 1.0 이후에 제공된 많은 NuGet 패키지가 더 이상 생성되지 않습니다. 이러한 패키지에서 제공하는 API는 `<FrameworkReference>`를 `Microsoft.AspNetCore.App`에 사용하여 앱에서 계속 사용할 수 있습니다. 일반적인 API의 예로 Kestrel, MVC 및 Razor가 있습니다.

이 변경은 ASP.NET Core 2.x의 `Microsoft.AspNetCore.App`을 통해 참조되는 모든 이진 파일에 적용되지 않습니다. 주목할 만한 예외는 다음과 같습니다.

- .NET Standard를 계속 대상으로 하는 `Microsoft.Extensions` 라이브러리는 NuGet 패키지로 사용할 수 있습니다(https://github.com/dotnet/extensions) 참조).
- `Microsoft.AspNetCore.App`의 일부가 아닌 ASP.NET Core 팀에서 생성한 API입니다. 예를 들어 NuGet 패키지로 사용할 수 있는 구성 요소는 다음과 같습니다.
  - Entity Framework Core
  - 타사 통합 기능을 제공하는 API
  - 실험적 기능
  - [공유 프레임워크에 있어야 하는 요구 사항을 충족](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)시킬 수 없는 종속성이 있는 API
- Json.NET 지원을 유지하는 MVC 확장. API는 Json.NET 및 MVC 사용을 지원하기 위해 NuGet 패키지로 제공됩니다.
- SignalR .NET 클라이언트는 .NET Standard를 계속 지원하며 NuGet 패키지로 제공됩니다. 이는 Xamarin 및 UWP와 같은 많은 .NET 런타임에서 사용하기 위한 것입니다.

자세한 내용은 [3.0에서 공유 프레임워크 어셈블리용 패키지 생성 중지](https://github.com/dotnet/aspnetcore/issues/3756)를 참조하세요. 토론은 [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757)을 참조하세요.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
