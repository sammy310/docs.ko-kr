---
title: '호환성이 손상되는 변경: PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.'
description: PrincipalPermissionAttribute 생성자가 사용되지 않고 컴파일 시간 오류를 생성하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 7568883935633e98b884b553efccf50504448b77
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257234"
---
# <a name="principalpermissionattribute-is-obsolete-as-error"></a>PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.

<xref:System.Security.Permissions.PrincipalPermissionAttribute> 생성자는 사용되지 않으며 컴파일 시간 오류를 생성합니다. 이 특성을 인스턴스화하거나 메서드에 적용할 수 없습니다.

## <a name="change-description"></a>변경 내용 설명

.NET Framework 및 .NET Core에서 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 사용하여 메서드를 주석 처리할 수 있습니다. 다음은 그 예입니다.

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

.NET 5부터 메서드에 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 적용할 수 없습니다. 특성의 생성자는 사용되지 않으며 컴파일 시간 오류를 생성합니다. 다른 사용 중지 경고와 달리 이 오류는 표시되지 않도록 할 수 없습니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.Security.Permissions.SecurityAttribute>를 서브클래스하는 다른 형식처럼 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 형식은 . NET의 CAS(코드 액세스 보안) 인프라에 속합니다. .NET Framework 2.x - 4.x에서는 애플리케이션이 완전 신뢰 시나리오에서 실행되는 경우에도 런타임은 메서드 항목에 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 주석을 강제 적용합니다. .NET Core 및 .NET 5 이상에서는 CAS 특성을 지원하지 않으며 런타임에서는 해당 특성을 무시합니다.

.NET Framework와 .NET Core 및 .NET 5 간의 관련 동작 차이로 인해, 액세스가 차단되어야 했지만 실제로는 허용되어 “열기 실패” 시나리오가 발생할 수 있습니다. “열기 실패” 시나리오를 방지하기 위해 .NET 5 이상을 대상으로 하는 코드에는 더 이상 해당 특성을 적용할 수 없습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name=""></a><a id="permission-action">권장 작업</a>

사용 중지 오류가 발생하는 경우 조치를 취해야 합니다.

- **ASP.NET MVC 작업 메서드에 특성을 적용하는 경우:**

  ASP.NET의 기본 제공 권한 부여 인프라를 사용하는 것이 좋습니다. 다음 코드에서는 <xref:System.Web.Mvc.AuthorizeAttribute> 특성을 사용하여 컨트롤러를 주석 처리하는 방법을 보여 줍니다. ASP.NET 런타임은 작업을 수행하기 전에 사용자에게 권한을 부여합니다.

  ```csharp
  using Microsoft.AspNetCore.Authorization;

  namespace MySampleApp
  {
      [Authorize(Roles = "Administrator")]
      public class AdministrationController : Controller
      {
          public ActionResult MyAction()
          {
              // This code won't run unless the current user
              // is in the 'Administrator' role.
          }
      }
  }
  ```

  자세한 내용은 [ASP.NET Core의 역할 기반 권한 부여](/aspnet/core/security/authorization/roles) 및 [ASP.NET Core의 권한 부여 소개](/aspnet/core/security/authorization/introduction)를 참조하세요.

- **웹앱의 컨텍스트 외부에 있는 라이브러리 코드에 특성을 적용하는 경우:**

  메서드의 시작 부분에서 수동으로 검사를 수행합니다. <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> 메서드를 사용하여 이 작업을 수행할 수 있습니다.

  ```csharp
  using System.Threading;

  void DoSomething()
  {
      if (Thread.CurrentPrincipal == null
          || !Thread.CurrentPrincipal.IsInRole("Administrators"))
      {
          throw new Exception("User is anonymous or isn't an admin.");
      }

      // Code that should run only when user is an administrator.
  }
  ```

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
