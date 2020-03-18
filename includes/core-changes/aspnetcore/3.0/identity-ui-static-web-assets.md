---
ms.openlocfilehash: c5e4b5619394f99a419fe48aee190ad741ea8c0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "73041661"
---
### <a name="identity-ui-uses-static-web-assets-feature"></a>ID: UI는 정적 웹 자산 기능을 사용합니다.

ASP.NET Core 3.0에는 정적 웹 자산 기능이 도입되었으며 ID UI에서 이를 채택했습니다.

#### <a name="change-description"></a>변경 내용 설명

ID UI가 정적 웹 자산 기능을 채택한 결과는 다음과 같습니다.

- 프레임워크 선택은 프로젝트 파일에서 `IdentityUIFrameworkVersion` 속성을 사용하여 수행됩니다.
- 부트스트랩 4는 ID UI의 기본 UI 프레임워크입니다. 부트스트랩 3은 수명이 다되었으므로 지원되는 버전으로 마이그레이션하는 것을 고려해야 합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

ID UI의 기본 UI 프레임워크는 **부트스트랩 3**입니다. `Startup.ConfigureServices`에서 `AddDefaultUI` 메서드 호출에 대한 매개 변수를 사용하여 UI 프레임워크를 구성할 수 있습니다.

#### <a name="new-behavior"></a>새 동작

ID UI의 기본 UI 프레임워크는 **부트스트랩 4**입니다. UI 프레임워크는 `AddDefaultUI` 메서드 호출 대신 프로젝트 파일에 구성되어야 합니다.

#### <a name="reason-for-change"></a>변경 이유

정적 웹 자산 기능을 채택하려면 UI 프레임워크 구성이 MSBuild로 이동해야 했습니다. 포함할 프레임워크를 결정하는 것은 런타임 결정이 아니라 빌드 시간 결정입니다.

#### <a name="recommended-action"></a>권장 조치

사이트 UI를 검토하여 새 부트스트랩 4 구성 요소가 호환되는지 확인합니다. 필요한 경우 `IdentityUIFrameworkVersion` MSBuild 속성을 사용하여 부트스트랩 3으로 되돌립니다. 프로젝트 파일의 `<PropertyGroup>` 요소에 속성을 추가합니다.

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
