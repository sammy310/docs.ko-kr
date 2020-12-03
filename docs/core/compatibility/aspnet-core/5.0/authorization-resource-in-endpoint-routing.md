---
title: '호환성이 손상되는 변경: 권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. 권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760008"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a>권한 부여: 엔드포인트 라우팅의 리소스가 HttpContext임

ASP.NET Core 3.1에서 엔드포인트 라우팅을 사용하는 경우 권한 부여에 사용되는 리소스는 엔드포인트입니다. 이 방법만으로 경로 데이터(<xref:Microsoft.AspNetCore.Routing.RouteData>)에 대한 액세스 권한을 얻을 수는 없었습니다. 이전에는 MVC에서 엔드포인트(<xref:Microsoft.AspNetCore.Http.Endpoint>) 및 경로 데이터 둘 다에 대한 액세스를 허용하는 <xref:Microsoft.AspNetCore.Http.HttpContext> 리소스가 전달되었습니다. 이렇게 변경하면 권한 부여에 전달되는 리소스가 항상 `HttpContext`입니다.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 7

## <a name="old-behavior"></a>이전 동작

엔드포인트 라우팅과 권한 부여 미들웨어(<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) 또는 [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) 특성을 사용하는 경우 권한 부여에 전달되는 리소스는 일치하는 엔드포인트입니다.

## <a name="new-behavior"></a>새 동작

엔드포인트 라우팅이 권한 부여에 `HttpContext`를 전달합니다.

## <a name="reason-for-change"></a>변경 이유

`HttpContext`에서 엔드포인트에 액세스할 수 있습니다. 그러나 엔드포인트에서 경로 데이터 등에 액세스할 수 있는 방법이 없었습니다. 비엔드포인트 라우팅의 기능이 손실되었습니다.

## <a name="recommended-action"></a>권장 조치

앱에서 엔드포인트 리소스를 사용하는 경우 `HttpContext`에 대해 <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A>를 호출하여 엔드포인트에 계속 액세스합니다.

ASP.NET Core 5.0 미리 보기 8 이상에서는 <xref:System.AppContext.SetSwitch%2A>를 사용하여 이전 동작으로 되돌릴 수 있습니다. 예를 들어:

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
