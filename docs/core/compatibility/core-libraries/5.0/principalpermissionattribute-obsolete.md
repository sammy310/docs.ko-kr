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
# <a name="principalpermissionattribute-is-obsolete-as-error"></a><span data-ttu-id="ee77d-103">PrincipalPermissionAttribute는 오류로 인해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-103">PrincipalPermissionAttribute is obsolete as error</span></span>

<span data-ttu-id="ee77d-104"><xref:System.Security.Permissions.PrincipalPermissionAttribute> 생성자는 사용되지 않으며 컴파일 시간 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="ee77d-105">이 특성을 인스턴스화하거나 메서드에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-105">You cannot instantiate this attribute or apply it to a method.</span></span>

## <a name="change-description"></a><span data-ttu-id="ee77d-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="ee77d-106">Change description</span></span>

<span data-ttu-id="ee77d-107">.NET Framework 및 .NET Core에서 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 사용하여 메서드를 주석 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-107">On .NET Framework and .NET Core, you can annotate methods with the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute.</span></span> <span data-ttu-id="ee77d-108">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-108">For example:</span></span>

```csharp
[PrincipalPermission(SecurityAction.Demand, Role = "Administrators")]
public void MyMethod()
{
    // Code that should only run when the current user is an administrator.
}
```

<span data-ttu-id="ee77d-109">.NET 5부터 메서드에 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-109">Starting in .NET 5, you cannot apply the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to a method.</span></span> <span data-ttu-id="ee77d-110">특성의 생성자는 사용되지 않으며 컴파일 시간 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-110">The constructor for the attribute is obsolete and produces a compile-time error.</span></span> <span data-ttu-id="ee77d-111">다른 사용 중지 경고와 달리 이 오류는 표시되지 않도록 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-111">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ee77d-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ee77d-112">Reason for change</span></span>

<span data-ttu-id="ee77d-113"><xref:System.Security.Permissions.SecurityAttribute>를 서브클래스하는 다른 형식처럼 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 형식은 . NET의 CAS(코드 액세스 보안) 인프라에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-113">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> type, like other types that subclass <xref:System.Security.Permissions.SecurityAttribute>, is part of .NET's Code Access Security (CAS) infrastructure.</span></span> <span data-ttu-id="ee77d-114">.NET Framework 2.x - 4.x에서는 애플리케이션이 완전 신뢰 시나리오에서 실행되는 경우에도 런타임은 메서드 항목에 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 주석을 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-114">In .NET Framework 2.x - 4.x, the runtime enforces <xref:System.Security.Permissions.PrincipalPermissionAttribute> annotations on method entry, even if the application is running under a full-trust scenario.</span></span> <span data-ttu-id="ee77d-115">.NET Core 및 .NET 5 이상에서는 CAS 특성을 지원하지 않으며 런타임에서는 해당 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-115">.NET Core and .NET 5 and later don't support CAS attributes, and the runtime ignores them.</span></span>

<span data-ttu-id="ee77d-116">.NET Framework와 .NET Core 및 .NET 5 간의 관련 동작 차이로 인해, 액세스가 차단되어야 했지만 실제로는 허용되어 “열기 실패” 시나리오가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-116">This difference in behavior from .NET Framework to .NET Core and .NET 5 can result in a "fail open" scenario, where access should have been blocked but instead has been allowed.</span></span> <span data-ttu-id="ee77d-117">“열기 실패” 시나리오를 방지하기 위해 .NET 5 이상을 대상으로 하는 코드에는 더 이상 해당 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-117">To prevent the "fail open" scenario, you can no longer apply the attribute in code that targets .NET 5 or later.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ee77d-118">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ee77d-118">Version introduced</span></span>

<span data-ttu-id="ee77d-119">5.0</span><span class="sxs-lookup"><span data-stu-id="ee77d-119">5.0</span></span>

## <a name=""></a><span data-ttu-id="ee77d-120"><a id="permission-action">권장 작업</a></span><span class="sxs-lookup"><span data-stu-id="ee77d-120"><a id="permission-action">Recommended action</a></span></span>

<span data-ttu-id="ee77d-121">사용 중지 오류가 발생하는 경우 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-121">If you encounter the obsoletion error, you must take action.</span></span>

- <span data-ttu-id="ee77d-122">**ASP.NET MVC 작업 메서드에 특성을 적용하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="ee77d-122">**If you're applying the attribute to an ASP.NET MVC action method:**</span></span>

  <span data-ttu-id="ee77d-123">ASP.NET의 기본 제공 권한 부여 인프라를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-123">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="ee77d-124">다음 코드에서는 <xref:System.Web.Mvc.AuthorizeAttribute> 특성을 사용하여 컨트롤러를 주석 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-124">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="ee77d-125">ASP.NET 런타임은 작업을 수행하기 전에 사용자에게 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-125">The ASP.NET runtime will authorize the user before performing the action.</span></span>

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

  <span data-ttu-id="ee77d-126">자세한 내용은 [ASP.NET Core의 역할 기반 권한 부여](/aspnet/core/security/authorization/roles) 및 [ASP.NET Core의 권한 부여 소개](/aspnet/core/security/authorization/introduction)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee77d-126">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="ee77d-127">**웹앱의 컨텍스트 외부에 있는 라이브러리 코드에 특성을 적용하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="ee77d-127">**If you're applying the attribute to library code outside the context of a web app:**</span></span>

  <span data-ttu-id="ee77d-128">메서드의 시작 부분에서 수동으로 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-128">Perform the checks manually at the beginning of your method.</span></span> <span data-ttu-id="ee77d-129"><xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> 메서드를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee77d-129">This can be done by using the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="ee77d-130">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ee77d-130">Affected APIs</span></span>

- <xref:System.Security.Permissions.PrincipalPermissionAttribute?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `T:System.Security.Permissions.PrincipalPermissionAttribute`

-->
