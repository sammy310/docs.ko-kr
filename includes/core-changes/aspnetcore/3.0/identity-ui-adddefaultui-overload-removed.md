---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522677"
---
### <a name="identity-adddefaultui-method-overload-removed"></a>ID: AddDefaultUI 메서드 오버로드가 제거됨

ASP.NET Core 3.0부터는 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> 메서드 오버로드가 더 이상 존재하지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

이 변경 내용은 정적 웹 자산 기능을 채택한 결과입니다.

#### <a name="recommended-action"></a>권장 작업

오버로드 대신 <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType>을 호출합니다. 부트스트랩 3을 사용하는 경우 프로젝트 파일의 `<PropertyGroup>` 요소에 다음 줄을 추가합니다.

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
