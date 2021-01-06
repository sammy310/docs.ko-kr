---
title: SYSLIB0002 오류
description: 컴파일 시간 오류 SYSLIB0002를 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 774675e96d11a8e1b5d82767695d0defd1e8cfad
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596348"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a><span data-ttu-id="dc1bd-103">SYSLIB0002: PrincipalPermissionAttribute가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="dc1bd-103">SYSLIB0002: PrincipalPermissionAttribute is obsolete</span></span>

<span data-ttu-id="dc1bd-104"><xref:System.Security.Permissions.PrincipalPermissionAttribute> 생성자는 .NET 5.0부터 사용되지 않고 컴파일 시간 오류 `SYSLIB0002`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces compile-time error `SYSLIB0002`, starting in .NET 5.0.</span></span> <span data-ttu-id="dc1bd-105">이 특성을 인스턴스화하거나 메서드에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-105">You cannot instantiate this attribute or apply it to a method.</span></span>

<span data-ttu-id="dc1bd-106">다른 사용 중지 경고와 달리 이 오류는 표시되지 않도록 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-106">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="dc1bd-107">해결 방법</span><span class="sxs-lookup"><span data-stu-id="dc1bd-107">Workarounds</span></span>

- <span data-ttu-id="dc1bd-108">ASP.NET MVC 작업 메서드에 특성을 적용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="dc1bd-108">If you're applying the attribute to an ASP.NET MVC action method:</span></span>

  <span data-ttu-id="dc1bd-109">ASP.NET의 기본 제공 권한 부여 인프라를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-109">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="dc1bd-110">다음 코드에서는 <xref:System.Web.Mvc.AuthorizeAttribute> 특성을 사용하여 컨트롤러를 주석 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-110">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="dc1bd-111">ASP.NET 런타임은 작업을 수행하기 전에 사용자에게 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-111">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="dc1bd-112">자세한 내용은 [ASP.NET Core의 역할 기반 권한 부여](/aspnet/core/security/authorization/roles) 및 [ASP.NET Core의 권한 부여 소개](/aspnet/core/security/authorization/introduction)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-112">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="dc1bd-113">웹앱의 컨텍스트 외부에 있는 라이브러리 코드에 특성을 적용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="dc1bd-113">If you're applying the attribute to library code outside the context of a web app:</span></span>

  <span data-ttu-id="dc1bd-114"><xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> 메서드를 호출하여 메서드 시작 부분에서 수동으로 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-114">Perform the checks manually at the beginning of your method by calling the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="dc1bd-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="dc1bd-115">See also</span></span>

- [<span data-ttu-id="dc1bd-116">PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1bd-116">PrincipalPermissionAttribute is obsolete as error</span></span>](../core-libraries/5.0/principalpermissionattribute-obsolete.md)
