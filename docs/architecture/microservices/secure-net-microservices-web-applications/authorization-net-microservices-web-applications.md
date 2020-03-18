---
title: .NET 마이크로 서비스 및 웹 애플리케이션의 권한 부여 정보
description: .NET 마이크로 서비스 및 웹 애플리케이션의 보안 - ASP.NET Core 애플리케이션의 기본 권한 부여 옵션인 역할 기반 및 정책 기반의 개요를 살펴볼 수 있습니다.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: f6b69faceac9a9b4819212cc04f89080f3ddad56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501772"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="69a86-103">.NET 마이크로 서비스 및 웹 애플리케이션의 권한 부여 정보</span><span class="sxs-lookup"><span data-stu-id="69a86-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="69a86-104">인증 후에는 ASP.NET Core Web API에서 액세스 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="69a86-105">이 프로세스를 사용하면 서비스에서 일부 인증된 사용자는 API를 사용할 수 있지만, 모든 사용자가 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="69a86-106">[권한 부여](/aspnet/core/security/authorization/introduction)는 사용자의 역할 또는 사용자 지정 정책에 따라 수행될 수 있습니다. 이 경우 클레임 또는 다른 추론 검사가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-106">[Authorization](/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="69a86-107">ASP.NET Core MVC 경로에 대한 액세스를 제한하는 것은 다음 예제와 같이 작업 메서드(또는 컨트롤러의 모든 작업에 권한 부여가 필요한 경우 컨트롤러의 클래스)에 Authorize 특성을 적용하는 것만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

<span data-ttu-id="69a86-108">기본적으로 매개 변수 없이 Authorize 특성을 추가하면 해당 컨트롤러 또는 작업에 대한 인증된 사용자의 액세스가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="69a86-109">특정 사용자만 사용할 수 있도록 API를 추가로 제한하려면 사용자에게 적합한 필수 역할 또는 정책을 지정하도록 특성을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implement-role-based-authorization"></a><span data-ttu-id="69a86-110">역할 기반 권한 부여 구현</span><span class="sxs-lookup"><span data-stu-id="69a86-110">Implement role-based authorization</span></span>

<span data-ttu-id="69a86-111">ASP.NET Core ID에는 기본 제공되는 역할에 대한 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="69a86-112">ASP.NET Core ID는 사용자 외에도 애플리케이션에서 사용하는 여러 역할에 대한 정보를 저장하고, 해당 역할에 할당된 사용자를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="69a86-113">이러한 할당은 지속형 스토리지의 역할을 업데이트하는 `RoleManager` 유형과 사용자에게 역할을 부여하거나 철회할 수 있는 `UserManager` 유형을 사용하여 프로그래밍 방식으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-113">These assignments can be changed programmatically with the `RoleManager` type that updates roles in persisted storage, and the `UserManager` type that can grant or revoke roles from users.</span></span>

<span data-ttu-id="69a86-114">JWT 전달자 토큰으로 인증하는 경우 ASP.NET Core JWT 전달자 인증 미들웨어는 토큰에 있는 역할 클레임에 따라 사용자의 역할을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-114">If you're authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="69a86-115">MVC 작업 또는 컨트롤러에 대한 액세스를 특정 역할의 사용자로 제한하려면 다음 코드 조각과 같이 Authorize 주석(특성)에 Roles 매개 변수를 포함하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize annotation (attribute), as shown in the following code fragment:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

<span data-ttu-id="69a86-116">이 예제에서는 Administrator 또는 PowerUser 역할의 사용자만 ControlPanel 컨트롤러의 API(예: SetTime 작업 실행)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="69a86-117">ShutDown API는 Administrator 역할의 사용자만 액세스할 수 있도록 추가로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="69a86-118">사용자가 여러 역할을 수행하도록 하려면 다음 예제와 같이 여러 개의 Authorize 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="69a86-119">이 예제에서 API1을 호출하려면 사용자가 다음을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-119">In this example, to call API1, a user must:</span></span>

- <span data-ttu-id="69a86-120">Adminstrator 또는 PowerUser 역할을 담당합니다. 그리고  </span><span class="sxs-lookup"><span data-stu-id="69a86-120">Be in the Administrator *or* PowerUser role, *and*</span></span>

- <span data-ttu-id="69a86-121">RemoteEmployee 역할을 담당합니다. *그리고*</span><span class="sxs-lookup"><span data-stu-id="69a86-121">Be in the RemoteEmployee role, *and*</span></span>

- <span data-ttu-id="69a86-122">CustomPolicy 권한 부여를 위한 사용자 지정 처리기를 충족시킵니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implement-policy-based-authorization"></a><span data-ttu-id="69a86-123">정책 기반 권한 부여 구현</span><span class="sxs-lookup"><span data-stu-id="69a86-123">Implement policy-based authorization</span></span>

<span data-ttu-id="69a86-124">사용자 지정 권한 부여 규칙은 [권한 부여 정책](https://docs.asp.net/en/latest/security/authorization/policies.html)을 사용하여 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="69a86-125">이 섹션에서는 개요를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-125">This section provides an overview.</span></span> <span data-ttu-id="69a86-126">자세한 내용은 [ASP.NET 권한 부여 워크샵](https://github.com/blowdart/AspNetAuthorizationWorkshop)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69a86-126">For more information, see the [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="69a86-127">사용자 지정 권한 정책은 service.AddAuthorization 메서드를 사용하여 Startup.ConfigureServices 메서드에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="69a86-128">이 메서드는 AuthorizationOptions 인수를 구성하는 대리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));

    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));

    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

<span data-ttu-id="69a86-129">이 예제와 같이 정책은 다양한 유형의 요구 사항과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="69a86-130">정책이 등록되면 정책 이름을 Authorize 특성의 Policy 인수(예: `[Authorize(Policy="EmployeesOnly")]`)로 전달하여 작업 또는 컨트롤러에 적용할 수 있습니다. 정책에는 하나의 요구 사항만 아니라 이 예제처럼 여러 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-130">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, `[Authorize(Policy="EmployeesOnly")]`) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="69a86-131">앞의 예제에서 첫 번째 AddPolicy 호출은 역할별로 권한을 부여하는 다른 방법일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="69a86-132">`[Authorize(Policy="AdministratorsOnly")]`가 API에 적용되면 Administrator 역할의 사용자만 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-132">If `[Authorize(Policy="AdministratorsOnly")]` is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="69a86-133">두 번째 <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> 호출은 사용자에게 특정 클레임이 있어야 한다고 요구하는 쉬운 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-133">The second <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="69a86-134"><xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> 메서드는 필요에 따라 클레임에 대한 예상 값도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-134">The <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="69a86-135">값이 지정되면 사용자가 올바른 유형의 클레임과 지정된 값 중 하나를 가지고 있는 경우에만 요구 사항이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="69a86-136">JWT 전달자 인증 미들웨어를 사용하는 경우 모든 JWT 속성을 사용자 클레임으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-136">If you're using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="69a86-137">여기서 보여 주는 가장 흥미로운 정책은 세 번째 `AddPolicy` 메서드에 있으며, 사용자 지정 권한 요구 사항을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-137">The most interesting policy shown here is in the third `AddPolicy` method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="69a86-138">사용자 지정 권한 부여 요구 사항을 사용하면 권한 부여가 수행되는 방식을 크게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="69a86-139">이렇게 하려면 다음 유형을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-139">For this to work, you must implement these types:</span></span>

- <span data-ttu-id="69a86-140"><xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement>에서 파생되고 요구 사항의 세부 정보를 지정하는 필드가 포함된 Requirements 유형.</span><span class="sxs-lookup"><span data-stu-id="69a86-140">A Requirements type that derives from <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="69a86-141">예제에서는 샘플 `MinimumAgeRequirement` 유형의 연령 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-141">In the example, this is an age field for the sample `MinimumAgeRequirement` type.</span></span>

- <span data-ttu-id="69a86-142"><xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>를 구현하는 처리기. 여기서 T는 처리기가 충족할 수 있는 <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-142">A handler that implements <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, where T is the type of <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> that the handler can satisfy.</span></span> <span data-ttu-id="69a86-143">처리기에서 <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> 메서드를 구현해야 합니다. 이 메서드는 지정된 컨텍스트(사용자에 대한 정보가 포함되어 있음)에서 요구 사항이 충족되는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-143">The handler must implement the <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="69a86-144">사용자가 요구 사항을 충족하는 경우 `context.Succeed`를 호출하면 사용자에게 권한이 있음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-144">If the user meets the requirement, a call to `context.Succeed` will indicate that the user is authorized.</span></span> <span data-ttu-id="69a86-145">사용자가 권한 부여 요구 사항을 충족시킬 수 있는 여러 가지 방법이 있는 경우 처리기를 여러 개 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="69a86-146">`AddPolicy` 호출에 사용자 지정 정책 요구 사항을 등록하는 것 외에도, 종속성 삽입(`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`)을 통해 사용자 지정 요구 사항 처리기를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-146">In addition to registering custom policy requirements with `AddPolicy` calls, you also need to register custom requirement handlers via Dependency Injection (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span></span>

<span data-ttu-id="69a86-147">`DateOfBirth` 클레임에 따라 사용자의 연령을 확인하기 위한 사용자 지정 권한 부여 요구 사항 및 처리기의 예제는 ASP.NET Core [권한 부여 문서](https://docs.asp.net/en/latest/security/authorization/policies.html)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a86-147">An example of a custom authorization requirement and handler for checking a user’s age (based on a `DateOfBirth` claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="69a86-148">추가 자료</span><span class="sxs-lookup"><span data-stu-id="69a86-148">Additional resources</span></span>

- <span data-ttu-id="69a86-149">**ASP.NET Core 인증** </span><span class="sxs-lookup"><span data-stu-id="69a86-149">**ASP.NET Core Authentication** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="69a86-150">**ASP.NET Core 권한 부여** </span><span class="sxs-lookup"><span data-stu-id="69a86-150">**ASP.NET Core Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- <span data-ttu-id="69a86-151">**역할 기반 권한 부여** </span><span class="sxs-lookup"><span data-stu-id="69a86-151">**Role-based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- <span data-ttu-id="69a86-152">**사용자 지정 정책 기반 권한 부여** </span><span class="sxs-lookup"><span data-stu-id="69a86-152">**Custom Policy-Based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
><span data-ttu-id="69a86-153">[이전](index.md)
>[다음](developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="69a86-153">[Previous](index.md)
[Next](developer-app-secrets-storage.md)</span></span>
