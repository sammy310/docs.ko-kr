---
title: SYSLIB0002 오류
description: 컴파일 시간 오류 SYSLIB0002를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 53eb51d5e525c463e5698710bdb6fa0c0907e43c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440779"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a>SYSLIB0002: PrincipalPermissionAttribute가 사용되지 않음

<xref:System.Security.Permissions.PrincipalPermissionAttribute> 생성자는 .NET 5.0부터 사용되지 않고 컴파일 시간 오류 `SYSLIB0002`를 생성합니다. 이 특성을 인스턴스화하거나 메서드에 적용할 수 없습니다.

다른 사용 중지 경고와 달리 이 오류는 표시되지 않도록 할 수 없습니다.

## <a name="workarounds"></a>해결 방법

- ASP.NET MVC 작업 메서드에 특성을 적용하는 경우:

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

- 웹앱의 컨텍스트 외부에 있는 라이브러리 코드에 특성을 적용하는 경우:

  <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> 메서드를 호출하여 메서드 시작 부분에서 수동으로 검사를 수행합니다.

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>추가 정보

- [PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.](3.1-5.0.md#principalpermissionattribute-is-obsolete-as-error)
