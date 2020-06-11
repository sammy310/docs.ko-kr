---
ms.openlocfilehash: 2094da7ec94028c112d6683620ac1146a1544dab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446976"
---
### <a name="localization-pubternal-apis-removed"></a>지역화: "Pubternal" API가 제거됨

ASP.NET Core의 공용 API 노출 영역을 보다 효율적으로 유지 관리하기 위해 일부 :::no-loc text="\"pubternal\""::: 지역화 API가 제거되었습니다. :::no-loc text="\"pubternal\""::: API는 `public` 액세스 한정자를 포함하고 있으며 [internal](/dotnet/csharp/language-reference/keywords/internal) 의도를 암시하는 네임스페이스에서 정의됩니다.

자세한 내용은 [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 6

#### <a name="old-behavior"></a>이전 동작

다음 API는 `public`이었습니다.

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- 다음 매개 변수 형식 중 하나를 허용하는 `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` 생성자 오버로드:
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a>새 동작

다음 목록에서는 변경 내용을 간략하게 설명합니다.

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`가 `Microsoft.Extensions.Localization.AssemblyWrapper`가 되었으며 이제 `internal`입니다.
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`가 `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`가 되었으며 이제 `internal`입니다.
- 다음 매개 변수 형식 중 하나를 허용하는 `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` 생성자 오버로드가 이제 `internal`입니다.
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a>변경 이유

`public` API 노출 영역에서 :::no-loc text="\"pubternal\""::: 형식이 제거되었습니다([aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882)에서 더 자세히 설명). 이러한 변경은 해당 디자인 결정에 따라 더 많은 클래스를 조정합니다. 해당 클래스는 팀의 내부 테스트를 위한 확장 지점으로 사용됩니다.

#### <a name="recommended-action"></a>권장 조치

발생할 가능성은 거의 없지만 일부 앱은 의도적으로 또는 실수로 :::no-loc text="\"pubternal\""::: 형식에 의존할 수도 있습니다. 형식에서 마이그레이션하는 방법을 확인하려면 [새 동작](#new-behavior) 섹션을 참조하세요.

이 변경 전에 공용 API에서 허용되었지만 지금은 허용되지 않는 시나리오를 확인했다면 [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues)에서 이슈를 제출하세요.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
