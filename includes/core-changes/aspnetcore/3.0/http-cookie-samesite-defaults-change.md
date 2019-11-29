---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74282521"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a>HTTP: 일부 쿠키 SameSite 기본값이 없음으로 변경됨

`SameSite`은(는) 일부 CSRF(교차 사이트 요청 위조) 공격을 완화하는 데 도움이 되는 쿠키의 옵션입니다. 처음에 이 옵션을 도입했을 때 다양한 ASP.NET Core API에서 일관되지 않은 기본값이 사용되었습니다. 이와 같은 불일치로 혼란스러운 결과가 발생했습니다. ASP.NET Core 3.0부터, 이 기본값은 효율적으로 정렬되었습니다. 구성 요소별로 이 기능을 설정해야 합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

유사한 ASP.NET Core API에서 다른 기본 <xref:Microsoft.AspNetCore.Http.SameSiteMode> 값을 사용했습니다. 불일치에 대한 예는 기본값인 `SameSiteMode.None` 및 `SameSiteMode.Lax`(으)로 각각 설정된 `HttpResponse.Cookies.Append(String, String)` 및 `HttpResponse.Cookies.Append(String, String, CookieOptions)`에서 볼 수 있습니다.

#### <a name="new-behavior"></a>새 동작

영향을 받는 모든 API의 기본값은 `SameSiteMode.None`입니다.

#### <a name="reason-for-change"></a>변경 이유

`SameSite`을(를) 옵트인 기능으로 설정하도록 기본값이 변경되었습니다.

#### <a name="recommended-action"></a>권장 작업

쿠키를 내보내는 각 구성 요소는 `SameSite`이(가) 시나리오에 적합한지 여부를 결정해야 합니다. 영향을 받는 API의 사용을 검토하고 필요에 따라 `SameSite`을(를) 다시 구성합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
