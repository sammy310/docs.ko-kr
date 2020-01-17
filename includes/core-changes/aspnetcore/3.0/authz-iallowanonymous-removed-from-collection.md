---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901800"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a>권한 부여: AuthorizationFilterContext.Filters에서 IAllowAnonymous 제거됨

ASP.NET Core 3.0을 기준으로 MVC에서 컨트롤러 및 작업 메서드에서 검색된 [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) 특성에 대해 [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter)를 추가하지 않습니다. 이 변경 사항은 <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>의 파생에 대해 로컬로 처리하지만 <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> 및 <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> 구현에 대해 호환성이 손상됩니다. [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) 특성에 래핑된 이러한 구현은 구성 및 종속성 주입이 모두 필요한 경우 강력한 형식의 특성 기반 권한 부여를 달성하는 [일반적](https://stackoverflow.com/a/41348219/608220)이고 지원되는 방식입니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

<xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous>가 [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) 컬렉션에 표시되었습니다. 인터페이스의 현재 상태에 대한 테스트는 개별 컨트롤러 메서드에서 필터를 재정의하거나 사용하지 않도록 설정하는 유효한 방법이었습니다.

#### <a name="new-behavior"></a>새 동작

`AuthorizationFilterContext.Filters` 컬렉션에 `IAllowAnonymous`가 더 이상 표시되지 않습니다. 이전 동작에 의존하는 `IAsyncAuthorizationFilter` 구현은 일반적으로 일시적인 HTTP 401 Unauthorized 또는 HTTP 403 Forbidden 응답의 원인이 됩니다.

#### <a name="reason-for-change"></a>변경 이유

새 엔드포인트 라우팅 전략은 ASP.NET Core 3.0에서 도입되었습니다.

#### <a name="recommended-action"></a>권장 조치

`IAllowAnonymous`에 대한 엔드포인트 메타데이터를 검색합니다. 예:

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

이 기법에 대한 예는 [HasAllowAnonymous 메서드](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236)에 표시됩니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

#### Affected APIs

Not detectable via API analysis

-->
