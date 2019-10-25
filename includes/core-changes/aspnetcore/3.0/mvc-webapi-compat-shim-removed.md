---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394402"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a>MVC: 웹 API 호환성 shim이 제거됨

ASP.NET Core 3.0부터는 `Microsoft.AspNetCore.Mvc.WebApiCompatShim` 패키지를 더 이상 사용할 수 없습니다.

#### <a name="change-description"></a>변경 내용 설명

`Microsoft.AspNetCore.Mvc.WebApiCompatShim`(WebApiCompatShim) 패키지는 ASP.NET Core에서 ASP.NET 4.x Web API 2와의 부분 호환성을 제공하여 기존 Web API 구현을 ASP.NET Core로 마이그레이션하는 것을 간소화합니다. 그러나 WebApiCompatShim을 사용하는 앱은 최신 ASP.NET Core 릴리스에서 제공되는 API 관련 기능의 이점을 활용하지 못합니다. 이러한 기능에는 향상된 Open API 사양 생성, 표준화된 오류 처리 및 클라이언트 코드 생성이 포함됩니다. 3\.0에서 API 노력에 더 집중하기 위해 WebApiCompatShim이 제거되었습니다. WebApiCompatShim을 사용하는 기존 앱은 최신 `[ApiController]` 모델로 마이그레이션해야 합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

Web API 호환성 shim은 마이그레이션 도구였습니다. ASP.NET Core에 추가된 새로운 기능에 대한 사용자 액세스를 제한합니다.

#### <a name="recommended-action"></a>권장 작업

이 shim의 사용을 제거하고 ASP.NET Core 자체의 유사한 기능으로 직접 마이그레이션합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
