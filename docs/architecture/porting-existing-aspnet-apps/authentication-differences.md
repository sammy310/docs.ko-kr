---
title: ASP.NET MVC와 ASP.NET Core 간의 인증 및 권한 부여 비교
description: ASP.NET MVC와 ASP.NET Core 간의 인증 및 권한 부여의 차이에 대 한 요약입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c8f3314186b7408e40d3a79cbc922a29eb75c5d2
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401819"
---
# <a name="compare-authentication-and-authorization-between-aspnet-mvc-and-aspnet-core"></a>ASP.NET MVC와 ASP.NET Core 간의 인증 및 권한 부여 비교

ASP.NET MVC 5에서 인증은 *App_Start* 폴더의 *Startup.Auth.cs* 에서 구성 됩니다. ASP.NET Core MVC에서이 구성은에서 발생 `Startup.cs` 합니다. 에서 요청 파이프라인에 추가 된 미들웨어를 사용 하 여 인증 및 권한 부여를 수행 합니다 `ConfigureServices` .

```csharp
// inside Startup.ConfigureServices

app.UseRouting();

app.UseAuthentication();
app.UseAuthorization();

app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

미들웨어 파이프라인에서 적절 한 순서로 auth 미들웨어를 추가 하는 것이 중요 합니다. 미들웨어에 게이를 수행 하는 요청만 영향을 받습니다. 예를 들어,에 대 한 호출이 `UseStaticFiles()` 여기에 표시 된 코드 위에 배치 된 경우 인증 및 권한 부여로 보호 되지 않습니다.

ASP.NET MVC 및 Web API에서 앱은 종종 속성을 사용 하 여 현재 사용자를 참조 `ClaimsPrincipal.Current` 합니다. 이 속성은 ASP.NET Core 설정 되지 않으며,이 속성에 의존 하는 앱의 모든 동작은 현재에 [](/aspnet/core/migration/claimsprincipal-current) 대 `User` 한 속성을 사용 하거나 현재에 대 `ControllerBase` 한 액세스를 가져오고 `HttpContext` 해당 속성을 참조 `User` 하 여 ClaimsPrincipal에서 마이그레이션해야 합니다. 이러한 방법 중 하나를 선택 하지 않으면 서비스는 사용자를 인수로 요청할 수 있습니다 .이 경우 응용 프로그램의 다른 위치에서 해당 사용자를 제공 해야 합니다. 그렇지 않으면를 `IHttpContextAccessor` 요청 하 여를 가져오는 데 사용할 수 있습니다 `HttpContext` .

## <a name="authorization"></a>권한 부여

권한 부여는 지정 된 사용자가 앱 내에서 수행할 수 있는 작업을 정의 합니다. 인증과는 별개로 사용자를 식별 하는 것과 관련 된 것입니다. ASP.NET Core는 간단한 선언적 역할과 권한 부여를 위한 풍부한 정책 기반 모델을 제공 합니다. 리소스가 권한 부여를 요구 하도록 지정 하는 것은 `[Authorize]` 작업 또는 컨트롤러에 특성을 추가 하는 것 만큼 간단 합니다. MVC 뷰에서 Razor Pages으로 마이그레이션하는 경우 [시작 시 Razor Pages를 구성할 때 권한 부여 규칙을 지정](/aspnet/core/security/authorization/razor-pages-authorization)해야 합니다.

ASP.NET Core 권한 부여는 인증 된 사용자를 허용 하는 동시에 익명 사용자를 금지 하는 것 처럼 간단할 수 있습니다. 또는 역할 기반, 클레임 기반 또는 정책 기반 권한 부여 방법을 지원 하도록 확장할 수 있습니다. 이러한 접근 방식에 대 한 자세한 내용은 [ASP.NET Core의 권한 부여](/aspnet/core/security/authorization/introduction)에 대 한 설명서를 참조 하세요. 그 중 하나가 현재 권한 부여 방법과 밀접 하 게 일치 하는 것을 알 수 있습니다.

## <a name="references"></a>참조

- [ASP.NET MVC를 사용 하 여 보안, 인증 및 권한 부여](/aspnet/mvc/overview/security/)
- [ASP.NET Core 인증 및 Id 마이그레이션](/aspnet/mvc/overview/security/)
- [ClaimsPrincipal에서 마이그레이션](/aspnet/core/migration/claimsprincipal-current)
- [ASP.NET Core 권한 부여 소개](/aspnet/core/security/authorization/introduction)

>[!div class="step-by-step"]
>[이전](webapi-differences.md)
>[다음](identity-differences.md)
