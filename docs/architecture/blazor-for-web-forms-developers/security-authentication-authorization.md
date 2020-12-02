---
title: '보안: ASP.NET Web Forms 및의 인증 및 권한 부여 Blazor'
description: ASP.NET Web Forms 및에서 인증 및 권한 부여를 처리 하는 방법에 대해 알아봅니다 Blazor .
author: ardalis
ms.author: daroth
no-loc:
- Blazor
ms.date: 11/20/2020
ms.openlocfilehash: 0344960237a5d9da61eb0d85987c44e136f1be48
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509847"
---
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a><span data-ttu-id="32831-103">보안: ASP.NET Web Forms 및 Blazor의 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="32831-103">Security: Authentication and Authorization in ASP.NET Web Forms and Blazor</span></span>

<span data-ttu-id="32831-104">ASP.NET Web Forms 응용 프로그램에서로 마이그레이션하려면 Blazor 응용 프로그램에 인증이 구성 된 것으로 가정 하 여 인증 및 권한 부여를 수행 하는 방법을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-104">Migrating from an ASP.NET Web Forms application to Blazor will almost certainly require updating how authentication and authorization are performed, assuming the application had authentication configured.</span></span> <span data-ttu-id="32831-105">이 장은 ASP.NET Web Forms 범용 공급자 모델 (멤버 자격, 역할 및 사용자 프로필)에서 마이그레이션하는 방법 및 앱에서 Id를 ASP.NET Core 하는 방법에 대해 설명 합니다 Blazor .</span><span class="sxs-lookup"><span data-stu-id="32831-105">This chapter will cover how to migrate from the ASP.NET Web Forms universal provider model (for membership, roles, and user profiles) and how to work with ASP.NET Core Identity from Blazor apps.</span></span> <span data-ttu-id="32831-106">이 장에서는 개략적인 단계 및 고려 사항에 대해 설명 하지만 참조 된 설명서에서 자세한 단계와 스크립트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-106">While this chapter will cover the high-level steps and considerations, the detailed steps and scripts may be found in the referenced documentation.</span></span>

## <a name="aspnet-universal-providers"></a><span data-ttu-id="32831-107">ASP.NET 유니버설 공급자</span><span class="sxs-lookup"><span data-stu-id="32831-107">ASP.NET universal providers</span></span>

<span data-ttu-id="32831-108">ASP.NET 2.0부터 ASP.NET Web Forms 플랫폼은 멤버 자격을 포함 하 여 다양 한 기능에 대 한 공급자 모델을 지원 했습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-108">Since ASP.NET 2.0, the ASP.NET Web Forms platform has supported a provider model for a variety of features, including membership.</span></span> <span data-ttu-id="32831-109">유니버설 멤버 자격 공급자는 선택적 역할 공급자와 함께 일반적으로 ASP.NET Web Forms 응용 프로그램과 함께 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-109">The universal membership provider, along with the optional role provider, is commonly deployed with ASP.NET Web Forms applications.</span></span> <span data-ttu-id="32831-110">지금까지 잘 작동 하는 인증 및 권한 부여를 관리 하는 강력 하 고 안전한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-110">It offers a robust and secure way to manage authentication and authorization that continues to work well today.</span></span> <span data-ttu-id="32831-111">이러한 범용 공급자의 최신 제공은 NuGet 패키지 ( [Microsoft. n. n. n. n.](https://www.nuget.org/packages/Microsoft.AspNet.Providers)n.)로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-111">The most recent offering of these universal providers is available as a NuGet package, [Microsoft.AspNet.Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).</span></span>

<span data-ttu-id="32831-112">Universal Providers는,, 및와 같은 테이블을 포함 하는 SQL database 스키마를 사용 `aspnet_Applications` `aspnet_Membership` `aspnet_Roles` `aspnet_Users` 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-112">The Universal Providers work with a SQL database schema that includes tables like `aspnet_Applications`, `aspnet_Membership`, `aspnet_Roles`, and `aspnet_Users`.</span></span> <span data-ttu-id="32831-113">[aspnet_regsql.exe 명령을](/previous-versions/ms229862(v=vs.140))실행 하 여 구성 하면 공급자가 기본 데이터를 사용 하는 데 필요한 모든 쿼리 및 명령을 제공 하는 테이블 및 저장 프로시저를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-113">When configured by running the [aspnet_regsql.exe command](/previous-versions/ms229862(v=vs.140)), the providers install tables and stored procedures that provide all of the necessary queries and commands to work with the underlying data.</span></span> <span data-ttu-id="32831-114">데이터베이스 스키마와 이러한 저장 프로시저는 새로운 ASP.NET Identity 및 ASP.NET Core Id 시스템과 호환 되지 않으므로 기존 데이터를 새 시스템으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-114">The database schema and these stored procedures are not compatible with newer ASP.NET Identity and ASP.NET Core Identity systems, so existing data must be migrated into the new system.</span></span> <span data-ttu-id="32831-115">그림 1에서는 유니버설 공급자에 대해 구성 된 예제 테이블 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32831-115">Figure 1 shows an example table schema configured for universal providers.</span></span>

![유니버설 공급자 스키마](./media/security/membership-tables.png)

<span data-ttu-id="32831-117">유니버설 공급자는 사용자, 멤버 자격, 역할 및 프로필을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-117">The universal provider handles users, membership, roles, and profiles.</span></span> <span data-ttu-id="32831-118">사용자에 게는 전역 고유 식별자와 사용자 이름, 사용자 이름 등의 기본 정보가 테이블에 저장 됩니다. `aspnet_Users`</span><span class="sxs-lookup"><span data-stu-id="32831-118">Users are assigned globally unique identifiers and basic information like userId, userName etc. are stored in the `aspnet_Users` table.</span></span> <span data-ttu-id="32831-119">암호, 암호 형식, 암호 솔트, 잠금 카운터 및 세부 정보 등의 인증 정보는 테이블에 저장 됩니다. `aspnet_Membership`</span><span class="sxs-lookup"><span data-stu-id="32831-119">Authentication information, such as password, password format, password salt, lockout counters and details, etc. are stored in the `aspnet_Membership` table.</span></span> <span data-ttu-id="32831-120">역할은 연결 테이블을 통해 사용자에 게 할당 되는 이름 및 고유 식별자로만 구성 되며 `aspnet_UsersInRoles` 다 대 다 관계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-120">Roles consist simply of names and unique identifiers, which are assigned to users via the `aspnet_UsersInRoles` association table, providing a many-to-many relationship.</span></span>

<span data-ttu-id="32831-121">기존 시스템에서 구성원 자격 외에 역할을 사용 하는 경우 사용자 계정, 연결 된 암호, 역할 및 역할 멤버 자격을 ASP.NET Core Id로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-121">If your existing system is using roles in addition to membership, you will need to migrate the user accounts, the associated passwords, the roles, and the role membership into ASP.NET Core Identity.</span></span> <span data-ttu-id="32831-122">대신 현재 역할 검사를 수행 하 고 있는 코드를 업데이트 하 여 선언적 필터, 특성 및/또는 태그 도우미를 대신 사용 하는 if 문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-122">You will also most likely need to update your code where you're currently performing role checks using if statements to instead leverage declarative filters, attributes, and/or tag helpers.</span></span> <span data-ttu-id="32831-123">이 챕터의 끝 부분에서 마이그레이션 고려 사항을 더 자세히 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-123">We will review migration considerations in greater detail at the end of this chapter.</span></span>

### <a name="authorization-configuration-in-web-forms"></a><span data-ttu-id="32831-124">Web Forms의 권한 부여 구성</span><span class="sxs-lookup"><span data-stu-id="32831-124">Authorization configuration in Web Forms</span></span>

<span data-ttu-id="32831-125">ASP.NET Web Forms 응용 프로그램의 특정 페이지에 대 한 권한 있는 액세스를 구성 하기 위해 일반적으로 익명 사용자가 특정 페이지 또는 폴더에 액세스할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-125">To configure authorized access to certain pages in an ASP.NET Web Forms application, typically you specify that certain pages or folders are inaccessible to anonymous users.</span></span> <span data-ttu-id="32831-126">이 구성은 web.config 파일에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-126">This configuration is done in the web.config file:</span></span>

```xml
<?xml version="1.0"?>
<configuration>
    <system.web>
      <authentication mode="Forms">
        <forms defaultUrl="~/home.aspx" loginUrl="~/login.aspx"
          slidingExpiration="true" timeout="2880"></forms>
      </authentication>

      <authorization>
        <deny users="?" />
      </authorization>
    </system.web>
</configuration>
```

<span data-ttu-id="32831-127">`authentication`구성 섹션은 응용 프로그램에 대 한 폼 인증을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-127">The `authentication` configuration section sets up the forms authentication for the application.</span></span> <span data-ttu-id="32831-128">`authorization`섹션은 전체 응용 프로그램에 대해 익명 사용자를 허용 하지 않는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-128">The `authorization` section is used to disallow anonymous users for the entire application.</span></span> <span data-ttu-id="32831-129">그러나 위치 별로 보다 세분화 된 권한 부여 규칙을 제공할 뿐만 아니라 역할 기반 권한 부여 확인을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-129">However, you can provide more granular authorization rules on a per-location basis as well as apply role-based authorization checks.</span></span>

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

<span data-ttu-id="32831-130">위의 구성을 첫 번째 구성과 결합 하면 익명 사용자가 로그인 페이지에 액세스 하 여 인증 되지 않은 사용자에 대 한 사이트 전체 제한을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-130">The above configuration, when combined with the first one, would allow anonymous users to access the login page, overriding the site-wide restriction on non-authenticated users.</span></span>

```xml
<location path="/admin">
  <system.web>
    <authorization>
      <allow roles="Administrators" />
      <deny users="*" />
    </authorization>
  </system.web>
</location>
```

<span data-ttu-id="32831-131">위의 구성은 다른 구성과 함께 사용 하는 경우 `/admin` 폴더 및 그 안의 모든 리소스를 "Administrators" 역할의 멤버에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-131">The above configuration, when combined with the others, restricts access to the `/admin` folder and all resources within it to members of the "Administrators" role.</span></span> <span data-ttu-id="32831-132">이 제한은 폴더 루트에 별도의 파일을 배치 하 여 적용할 수도 있습니다 `web.config` `/admin` .</span><span class="sxs-lookup"><span data-stu-id="32831-132">This restriction could also be applied by placing a separate `web.config` file within the `/admin` folder root.</span></span>

### <a name="authorization-code-in-web-forms"></a><span data-ttu-id="32831-133">Web Forms의 인증 코드</span><span class="sxs-lookup"><span data-stu-id="32831-133">Authorization code in Web Forms</span></span>

<span data-ttu-id="32831-134">를 사용 하 여 액세스를 구성 하는 것 외에 `web.config` 도 Web Forms 응용 프로그램에서 프로그래밍 방식으로 액세스 및 동작을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-134">In addition to configuring access using `web.config`, you can also programmatically configure access and behavior in your Web Forms application.</span></span> <span data-ttu-id="32831-135">예를 들어 특정 작업을 수행 하는 기능을 제한 하거나 사용자의 역할에 따라 특정 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-135">For instance, you can restrict the ability to perform certain operations or view certain data based on the user's role.</span></span>

<span data-ttu-id="32831-136">이 코드는 코드 지향 논리와 페이지 자체에서 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-136">This code can be used both in code-behind logic as well as in the page itself:</span></span>

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

<span data-ttu-id="32831-137">사용자 역할 멤버 자격을 확인 하는 것 외에도 인증 여부를 확인할 수 있습니다. 그러나이 작업은 위에서 설명한 위치 기반 구성을 사용 하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-137">In addition to checking user role membership, you can also determine if they are authenticated (though often this is better done using the location-based configuration covered above).</span></span> <span data-ttu-id="32831-138">다음은이 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-138">Below is an example of this approach.</span></span>

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if (!User.Identity.IsAuthenticated)
    {
        FormsAuthentication.RedirectToLoginPage();
    }
    if (!Roles.IsUserInRole(User.Identity.Name, "Administrators"))
    {
        MessageLabel.Text = "Only administrators can view this.";
        SecretPanel.Visible = false;
    }
}
```

<span data-ttu-id="32831-139">위의 코드에서는 RBAC (역할 기반 액세스 제어)를 사용 하 여 페이지의 특정 요소 (예:)가 `SecretPanel` 현재 사용자의 역할에 따라 표시 되는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-139">In the code above, role-based access control (RBAC) is used to determine whether certain elements of the page, such as a `SecretPanel`, are visible based on the current user's role.</span></span>

<span data-ttu-id="32831-140">일반적으로 ASP.NET Web Forms 응용 프로그램은 파일 내에서 보안을 구성 `web.config` 하 고 필요한 경우 `.aspx` 페이지 및 관련 코드 숨김이 있는 파일에 대 한 추가 검사를 추가 `.aspx.cs` 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-140">Typically, ASP.NET Web Forms applications configure security within the `web.config` file and then add additional checks where needed in `.aspx` pages and their related `.aspx.cs` code-behind files.</span></span> <span data-ttu-id="32831-141">대부분의 응용 프로그램은 일반적으로 추가 역할 공급자를 사용 하 여 유니버설 멤버 자격 공급자를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-141">Most applications leverage the universal membership provider, frequently with the additional role provider.</span></span>

## <a name="aspnet-core-identity"></a><span data-ttu-id="32831-142">ASP.NET Core ID</span><span class="sxs-lookup"><span data-stu-id="32831-142">ASP.NET Core Identity</span></span>

<span data-ttu-id="32831-143">인증 및 권한 부여를 사용 하는 경우에도 ASP.NET Core Id는 유니버설 공급자와 비교할 때 다른 추상화 및 가정 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-143">Although still tasked with authentication and authorization, ASP.NET Core Identity uses a different set of abstractions and assumptions when compared to the universal providers.</span></span> <span data-ttu-id="32831-144">예를 들어 새 Id 모델은 타사 인증을 지원 하므로 사용자는 소셜 미디어 계정 또는 다른 신뢰할 수 있는 인증 공급자를 사용 하 여 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-144">For example, the new Identity model supports third party authentication, allowing users to authenticate using a social media account or other trusted authentication provider.</span></span> <span data-ttu-id="32831-145">ASP.NET Core Identity는 로그인, 로그 아웃, 등록 등 일반적으로 필요한 페이지에 대 한 UI를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-145">ASP.NET Core Identity supports UI for commonly needed pages like login, logout, and register.</span></span> <span data-ttu-id="32831-146">데이터 액세스를 위해 EF Core를 활용 하 고 EF Core 마이그레이션을 사용 하 여 데이터 모델을 지 원하는 데 필요한 스키마를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-146">It leverages EF Core for its data access, and uses EF Core migrations to generate the necessary schema required to support its data model.</span></span> <span data-ttu-id="32831-147">[ASP.NET Core의 id 소개](/aspnet/core/security/authentication/identity) 에서는 ASP.NET Core id에 포함 된 기능과이를 사용 하 여 작업을 시작 하는 방법에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-147">This [introduction to Identity on ASP.NET Core](/aspnet/core/security/authentication/identity) provides a good overview of what is included with ASP.NET Core Identity and how to get started working with it.</span></span> <span data-ttu-id="32831-148">응용 프로그램 및 해당 데이터베이스에서 ASP.NET Core Id를 아직 설정 하지 않은 경우 시작 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-148">If you haven't already set up ASP.NET Core Identity in your application and its database, it will help you get started.</span></span>

### <a name="roles-claims-and-policies"></a><span data-ttu-id="32831-149">역할, 클레임 및 정책</span><span class="sxs-lookup"><span data-stu-id="32831-149">Roles, claims, and policies</span></span>

<span data-ttu-id="32831-150">유니버설 공급자와 ASP.NET Core Id는 모두 역할의 개념을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-150">Both the universal providers and ASP.NET Core Identity support the concept of roles.</span></span> <span data-ttu-id="32831-151">사용자에 대 한 역할을 만들고 역할에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-151">You can create roles for users and assign users to roles.</span></span> <span data-ttu-id="32831-152">사용자는 원하는 수의 역할에 속할 수 있으며 권한 부여 구현의 일부로 역할 멤버 자격을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-152">Users can belong to any number of roles, and you can verify role membership as part of your authorization implementation.</span></span>

<span data-ttu-id="32831-153">역할 외에도 ASP.NET Core identity는 클레임 및 정책의 개념을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-153">In addition to roles, ASP.NET Core identity supports the concepts of claims and policies.</span></span> <span data-ttu-id="32831-154">역할은 해당 역할의 사용자가 액세스할 수 있어야 하는 리소스 집합과 구체적으로 일치 해야 하지만 클레임은 단순히 사용자 id의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-154">While a role should specifically correspond to a set of resources a user in that role should be able to access, a claim is simply part of a user's identity.</span></span> <span data-ttu-id="32831-155">클레임은 주체가 어떤 작업을 수행할 수 있는지를 나타내는 이름 값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-155">A claim is a name value pair that represents what the subject is, not what the subject can do.</span></span>

<span data-ttu-id="32831-156">사용자의 클레임을 직접 검사 하 고 이러한 값을 기준으로 사용자에 게 리소스에 대 한 액세스 권한을 부여 해야 할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-156">It is possible to directly inspect a user's claims and determine based on these values whether a user should be given access to a resource.</span></span> <span data-ttu-id="32831-157">그러나 이러한 검사는 시스템 전체에서 반복적이 고 분산 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-157">However, such checks are often repetitive and scattered throughout the system.</span></span> <span data-ttu-id="32831-158">더 나은 방법은 *정책을* 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-158">A better approach is to define a *policy*.</span></span>

<span data-ttu-id="32831-159">권한 부여 정책은 하나 이상의 요구 사항으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-159">An authorization policy consists of one or more requirements.</span></span> <span data-ttu-id="32831-160">정책은의 메서드에서 권한 부여 서비스 구성의 일부로 등록 됩니다 `ConfigureServices` `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="32831-160">Policies are registered as part of the authorization service configuration in the `ConfigureServices` method of `Startup.cs`.</span></span> <span data-ttu-id="32831-161">예를 들어 다음 코드 조각은 "CanadiansOnly" 이라는 정책을 구성 합니다 .이 정책은 사용자에 게 값이 "캐나다" 인 Country 클레임이 있어야 한다는 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-161">For example, the following code snippet configures a policy called "CanadiansOnly", which has the requirement that the user has the Country claim with the value of "Canada".</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

<span data-ttu-id="32831-162">[설명서에서 사용자 지정 정책을 만드는 방법에 대해 자세히 알아볼](/aspnet/core/security/authorization/policies)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-162">You can [learn more about how to create custom policies in the documentation](/aspnet/core/security/authorization/policies).</span></span>

<span data-ttu-id="32831-163">정책 또는 역할을 사용 하는 경우에는 응용 프로그램의 특정 페이지에 지시문을 사용 하 여 Blazor 특성을 가진 역할이 나 정책이 필요 하도록 지정할 수 있습니다 `[Authorize]` `@attribute` .</span><span class="sxs-lookup"><span data-stu-id="32831-163">Whether you're using policies or roles, you can specify that a particular page in your Blazor application requires that role or policy with the `[Authorize]` attribute, applied with the `@attribute` directive.</span></span>

<span data-ttu-id="32831-164">역할 필요:</span><span class="sxs-lookup"><span data-stu-id="32831-164">Requiring a role:</span></span>

```csharp
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="32831-165">정책을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-165">Requiring a policy be satisfied:</span></span>

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

<span data-ttu-id="32831-166">사용자의 코드에서 사용자의 인증 상태, 역할 또는 클레임에 액세스 해야 하는 경우이 기능을 구현 하는 두 가지 기본 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-166">If you need access to a user's authentication state, roles, or claims in your code, there are two primary ways to achieve this functionality.</span></span> <span data-ttu-id="32831-167">첫 번째는 인증 상태를 연계 매개 변수로 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-167">The first is to receive the authentication state as a cascading parameter.</span></span> <span data-ttu-id="32831-168">두 번째는 삽입 된를 사용 하 여 상태에 액세스 하는 것입니다 `AuthenticationStateProvider` .</span><span class="sxs-lookup"><span data-stu-id="32831-168">The second is to access the state using an injected `AuthenticationStateProvider`.</span></span> <span data-ttu-id="32831-169">이러한 각 방법에 대 한 세부 정보는 [ Blazor 보안 설명서](/aspnet/core/blazor/security/)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-169">The details of each of these approaches are described in the [Blazor Security documentation](/aspnet/core/blazor/security/).</span></span>

<span data-ttu-id="32831-170">다음 코드에서는를 연계 매개 변수로 수신 하는 방법을 보여 줍니다 `AuthenticationState` .</span><span class="sxs-lookup"><span data-stu-id="32831-170">The following code shows how to receive the `AuthenticationState` as a cascading parameter:</span></span>

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

<span data-ttu-id="32831-171">이 매개 변수를 사용 하는 경우 다음 코드를 사용 하 여 사용자를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-171">With this parameter in place, you can get the user using this code:</span></span>

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

<span data-ttu-id="32831-172">다음 코드에서는을 삽입 하는 방법을 보여 줍니다 `AuthenticationStateProvider` .</span><span class="sxs-lookup"><span data-stu-id="32831-172">The following code shows how to inject the `AuthenticationStateProvider`:</span></span>

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

<span data-ttu-id="32831-173">공급자가 준비 되 면 다음 코드를 사용 하 여 사용자에 게 액세스 권한을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-173">With the provider in place, you can gain access to the user with the following code:</span></span>

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

<span data-ttu-id="32831-174">**참고:** `AuthorizeView` 이 챕터의 뒷부분에서 설명 하는 구성 요소는 사용자가 페이지 또는 구성 요소에서 볼 수 있는 내용을 제어 하는 선언적 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-174">**Note:** The `AuthorizeView` component, covered later in this chapter, provides a declarative way to control what a user sees on a page or component.</span></span>

<span data-ttu-id="32831-175">서버 응용 프로그램에서 사용자 및 클레임으로 작업 하려면 Blazor `UserManager<T>` `IdentityUser` 사용자에 대 한 클레임을 열거 하 고 수정 하는 데 사용할 수 있는를 삽입 해야 할 수도 있습니다 (기본값에 사용).</span><span class="sxs-lookup"><span data-stu-id="32831-175">To work with users and claims (in Blazor Server applications) you may also need to inject a `UserManager<T>` (use `IdentityUser` for default) which you can use to enumerate and modify claims for a user.</span></span> <span data-ttu-id="32831-176">먼저 형식을 삽입 하 고이를 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-176">First inject the type and assign it to a property:</span></span>

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

<span data-ttu-id="32831-177">그런 다음 사용자의 클레임을 사용 하 여 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-177">Then use it to work with the user's claims.</span></span> <span data-ttu-id="32831-178">다음 샘플에서는 사용자에 게 클레임을 추가 하 고 유지 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32831-178">The following sample shows how to add and persist a claim on a user:</span></span>

```csharp
private async Task AddCountryClaim()
{
    var authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
    var user = authState.User;
    var identityUser = await MyUserManager.FindByNameAsync(user.Identity.Name);

    if (!user.HasClaim(c => c.Type == ClaimTypes.Country))
    {
        // stores the claim in the cookie
        ClaimsIdentity id = new ClaimsIdentity();
        id.AddClaim(new Claim(ClaimTypes.Country, "Canada"));
        user.AddIdentity(id);

        // save the claim in the database
        await MyUserManager.AddClaimAsync(identityUser, new Claim(ClaimTypes.Country, "Canada"));
    }
}
```

<span data-ttu-id="32831-179">역할을 사용 해야 하는 경우에는 동일한 방법을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="32831-179">If you need to work with roles, follow the same approach.</span></span> <span data-ttu-id="32831-180">`RoleManager<T>` `IdentityRole` 역할 자체를 나열 하 고 관리 하려면 (기본 형식에 사용)를 삽입 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-180">You may need to inject a `RoleManager<T>` (use `IdentityRole` for default type) to list and manage the roles themselves.</span></span>

<span data-ttu-id="32831-181">**참고:** Blazor Weasembopprojects 프로젝트에서 또는 직접를 사용 하는 대신 이러한 작업을 수행할 수 있도록 서버 api를 제공 해야 `UserManager<T>` `RoleManager<T>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-181">**Note:** In Blazor WebAssembly projects, you will need to provide server APIs to perform these operations (instead of using `UserManager<T>` or `RoleManager<T>` directly).</span></span> <span data-ttu-id="32831-182">BlazorWeasembmbomclient 응용 프로그램은이 목적을 위해 노출 된 API 끝점을 안전 하 게 호출 하 여 클레임 및/또는 역할을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-182">A Blazor WebAssembly client application would manage claims and/or roles by securely calling API endpoints exposed for this purpose.</span></span>

### <a name="migration-guide"></a><span data-ttu-id="32831-183">마이그레이션 가이드</span><span class="sxs-lookup"><span data-stu-id="32831-183">Migration guide</span></span>

<span data-ttu-id="32831-184">ASP.NET Web Forms 및 유니버설 공급자에서 ASP.NET Core Id로 마이그레이션하려면 몇 가지 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-184">Migrating from ASP.NET Web Forms and universal providers to ASP.NET Core Identity requires several steps:</span></span>

1. <span data-ttu-id="32831-185">대상 데이터베이스에서 ASP.NET Core Id 데이터베이스 스키마 만들기</span><span class="sxs-lookup"><span data-stu-id="32831-185">Create ASP.NET Core Identity database schema in the destination database</span></span>
2. <span data-ttu-id="32831-186">유니버설 공급자 스키마에서 ASP.NET Core Identity 스키마로 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="32831-186">Migrate data from universal provider schema to ASP.NET Core Identity schema</span></span>
3. <span data-ttu-id="32831-187">에서 `web.config` 미들웨어 및 서비스 (일반적으로)로 구성을 마이그레이션합니다. `Startup.cs`</span><span class="sxs-lookup"><span data-stu-id="32831-187">Migrate configuration from the `web.config` to middleware and services, typically in `Startup.cs`</span></span>
4. <span data-ttu-id="32831-188">태그 도우미 및 새 id Api를 사용 하도록 컨트롤 및 조건을 사용 하 여 개별 페이지를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-188">Update individual pages using controls and conditionals to use tag helpers and new identity APIs.</span></span>

<span data-ttu-id="32831-189">이러한 각 단계는 다음 섹션에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-189">Each of these steps is described in detail in the following sections.</span></span>

### <a name="creating-the-aspnet-core-identity-schema"></a><span data-ttu-id="32831-190">ASP.NET Core Id 스키마 만들기</span><span class="sxs-lookup"><span data-stu-id="32831-190">Creating the ASP.NET Core Identity schema</span></span>

<span data-ttu-id="32831-191">ASP.NET Core Id에 사용 되는 필요한 테이블 구조를 만드는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-191">There are several ways to create the necessary table structure used for ASP.NET Core Identity.</span></span> <span data-ttu-id="32831-192">가장 간단한 방법은 새 ASP.NET Core 웹 응용 프로그램을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-192">The simplest is to create a new ASP.NET Core Web application.</span></span> <span data-ttu-id="32831-193">웹 응용 프로그램을 선택한 다음 인증을 변경 하 여 개별 사용자 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-193">Choose Web Application and then change Authentication to use Individual User Accounts.</span></span>

![개별 사용자 계정을 사용 하는 새 프로젝트](./media/security/individual-user-accounts.png)

<span data-ttu-id="32831-195">명령줄에서를 실행 하 여 동일한 작업을 수행할 수 있습니다 `dotnet new webapp -au Individual` .</span><span class="sxs-lookup"><span data-stu-id="32831-195">From the command line, you can do the same thing by running `dotnet new webapp -au Individual`.</span></span> <span data-ttu-id="32831-196">앱을 만든 후에는 앱을 실행 하 고 사이트에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-196">Once the app has been created, run it and register on the site.</span></span> <span data-ttu-id="32831-197">아래와 같은 페이지를 트리거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-197">You should trigger a page like the one shown below:</span></span>

![마이그레이션 적용 페이지](./media/security/apply-migrations-page.png)

<span data-ttu-id="32831-199">"마이그레이션 적용" 단추를 클릭 하면 필요한 데이터베이스 테이블이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-199">Click on the "Apply Migrations" button and the necessary database tables should be created for you.</span></span> <span data-ttu-id="32831-200">또한 다음과 같이 마이그레이션 파일이 프로젝트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-200">In addition, the migration files should appear in your project, as shown:</span></span>

![마이그레이션 파일](./media/security/migration-files.png)

<span data-ttu-id="32831-202">이 명령줄 도구를 사용 하 여 웹 응용 프로그램을 실행 하지 않고 직접 마이그레이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-202">You can run the migration yourself, without running the web application, using this command-line tool:</span></span>

```powershell
dotnet ef database update
```

<span data-ttu-id="32831-203">새 스키마를 기존 데이터베이스에 적용 하는 스크립트를 실행 하는 경우 명령줄에서 이러한 마이그레이션을 스크립팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-203">If you would rather run a script to apply the new schema to an existing database, you can script these migrations from the command-line.</span></span> <span data-ttu-id="32831-204">다음 명령을 실행 하 여 스크립트를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-204">Run this command to generate the script:</span></span>

```powershell
dotnet ef migrations script -o auth.sql
```

<span data-ttu-id="32831-205">위의 명령은 출력 파일에 SQL 스크립트를 생성 합니다 .이 스크립트는 원하는 `auth.sql` 모든 데이터베이스에 대해 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-205">The above command will produce a SQL script in the output file `auth.sql`, which can then be run against whatever database you like.</span></span> <span data-ttu-id="32831-206">명령을 실행 하는 데 문제가 있는 경우 `dotnet ef` [EF Core 도구가 시스템에 설치 되어 있는지 확인](/ef/core/miscellaneous/cli/dotnet)합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-206">If you have any trouble running `dotnet ef` commands, [make sure you have the EF Core tools installed on your system](/ef/core/miscellaneous/cli/dotnet).</span></span>

<span data-ttu-id="32831-207">원본 테이블에 추가 열이 있는 경우 새 스키마에서 이러한 열에 대해 가장 적합 한 위치를 식별 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-207">In the event you have additional columns on your source tables, you will need to identify the best location for these columns in the new schema.</span></span> <span data-ttu-id="32831-208">일반적으로 테이블에 있는 열은 `aspnet_Membership` 테이블에 매핑되어야 합니다 `AspNetUsers` .</span><span class="sxs-lookup"><span data-stu-id="32831-208">Generally, columns found on the `aspnet_Membership` table should be mapped to the `AspNetUsers` table.</span></span> <span data-ttu-id="32831-209">의 열은 `aspnet_Roles` 에 매핑되어야 `AspNetRoles` 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-209">Columns on `aspnet_Roles` should be mapped to `AspNetRoles`.</span></span> <span data-ttu-id="32831-210">테이블의 모든 추가 열이 `aspnet_UsersInRoles` 테이블에 추가 됩니다 `AspNetUserRoles` .</span><span class="sxs-lookup"><span data-stu-id="32831-210">Any additional columns on the `aspnet_UsersInRoles` table would be added to the `AspNetUserRoles` table.</span></span>

<span data-ttu-id="32831-211">또한 별도의 테이블에 추가 열을 추가 하는 것도 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-211">It's also worth considering putting any additional columns on separate tables.</span></span> <span data-ttu-id="32831-212">이후 마이그레이션에서 기본 id 스키마의 사용자 지정을 고려해 야 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-212">So that future migrations won't need to take into account such customizations of the default identity schema.</span></span>

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a><span data-ttu-id="32831-213">유니버설 공급자에서 ASP.NET Core Id로 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="32831-213">Migrating data from universal providers to ASP.NET Core Identity</span></span>

<span data-ttu-id="32831-214">대상 테이블 스키마가 준비 되 면 다음 단계는 사용자 및 역할 레코드를 새 스키마로 마이그레이션하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-214">Once you have the destination table schema in place, the next step is to migrate your user and role records to the new schema.</span></span> <span data-ttu-id="32831-215">새 열에 매핑되는 열을 포함 하 여 스키마 차이점의 전체 목록은 [여기](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-215">A complete list of the schema differences, including which columns map to which new columns, can be found [here](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span>

<span data-ttu-id="32831-216">사용자를 멤버 자격에서 새 id 테이블로 마이그레이션하려면 [설명서에 설명 된 단계를 수행](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-216">To migrate your users from membership to the new identity tables, you should [follow the steps described in the documentation](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span> <span data-ttu-id="32831-217">이러한 단계를 수행 하 고 스크립트를 제공 하면 사용자가 다음에 로그인 할 때 암호를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-217">After following these steps and the script provided, your users will need to change their password the next time they log in.</span></span>

<span data-ttu-id="32831-218">사용자 암호를 마이그레이션할 수 있지만 프로세스는 훨씬 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-218">It is possible to migrate user passwords but the process is much more involved.</span></span> <span data-ttu-id="32831-219">사용자가 마이그레이션 프로세스의 일부로 암호를 업데이트 하도록 요구 하 고 새로운 고유 암호를 사용 하도록 하는 것은 응용 프로그램의 전반적인 보안을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-219">Requiring users to update their passwords as part of the migration process, and encouraging them to use new, unique passwords, is likely to enhance the overall security of the application.</span></span>

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a><span data-ttu-id="32831-220">web.config에서 Startup.cs로 보안 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="32831-220">Migrating security settings from web.config to Startup.cs</span></span>

<span data-ttu-id="32831-221">위에서 설명한 것 처럼 ASP.NET 멤버 자격 및 역할 공급자는 응용 프로그램의 파일에 구성 됩니다 `web.config` .</span><span class="sxs-lookup"><span data-stu-id="32831-221">As noted above, ASP.NET membership and role providers are configured in the application's `web.config` file.</span></span> <span data-ttu-id="32831-222">ASP.NET Core 앱은 IIS에 연결 되지 않고 구성에 별도의 시스템을 사용 하기 때문에 이러한 설정을 다른 곳에서 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-222">Since ASP.NET Core apps are not tied to IIS and use a separate system for configuration, these settings must be configured elsewhere.</span></span> <span data-ttu-id="32831-223">대부분의 경우 ASP.NET Core Id는 파일에서 구성 됩니다 `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="32831-223">For the most part, ASP.NET Core Identity is configured in the `Startup.cs` file.</span></span> <span data-ttu-id="32831-224">이전에 만든 웹 프로젝트를 열고 (id 테이블 스키마 생성) 해당 파일을 검토 `Startup.cs` 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-224">Open the web project that was created earlier (to generate the identity table schema) and review its `Startup.cs` file.</span></span>

<span data-ttu-id="32831-225">기본 ConfigureServices 메서드는 EF Core 및 Id에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-225">The default ConfigureServices method adds support for EF Core and Identity:</span></span>

```csharp
// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
}
```

<span data-ttu-id="32831-226">`AddDefaultIdentity`확장 메서드는 기본 `ApplicationDbContext` 및 프레임 워크 형식을 사용 하도록 id를 구성 하는 데 사용 됩니다 `IdentityUser` .</span><span class="sxs-lookup"><span data-stu-id="32831-226">The `AddDefaultIdentity` extension method is used to configure Identity to use the default `ApplicationDbContext` and the framework's `IdentityUser` type.</span></span> <span data-ttu-id="32831-227">사용자 지정을 사용 하는 경우 `IdentityUser` 여기에서 해당 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-227">If you're using a custom `IdentityUser`, be sure to specify its type here.</span></span> <span data-ttu-id="32831-228">이러한 확장 메서드가 응용 프로그램에서 작동 하지 않는 경우 적절 한 using 문을 사용 하 고 필요한 NuGet 패키지를 참조 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-228">If these extension methods aren't working in your application, check that you have the appropriate using statements and that you have the necessary NuGet package references.</span></span> <span data-ttu-id="32831-229">예를 들어 프로젝트에 일부 버전의 `Microsoft.AspNetCore.Identity.EntityFrameworkCore` 및 패키지를 참조 해야 합니다 `Microsoft.AspNetCore.Identity.UI` .</span><span class="sxs-lookup"><span data-stu-id="32831-229">For example, your project should have some version of the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` and `Microsoft.AspNetCore.Identity.UI` packages referenced.</span></span>

<span data-ttu-id="32831-230">또한 `Startup.cs` 사이트에 대해 구성 된 필요한 미들웨어가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-230">Also in `Startup.cs` you should see the necessary middleware configured for the site.</span></span> <span data-ttu-id="32831-231">특히 `UseAuthentication` 및를 `UseAuthorization` 적절 한 위치에 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-231">Specifically, `UseAuthentication` and `UseAuthorization` should be set up, and in the proper location.</span></span>

```csharp

// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
        app.UseDatabaseErrorPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
        // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
        app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
}
```

<span data-ttu-id="32831-232">ASP.NET Identity는의 위치에 대 한 익명 또는 역할 기반 액세스를 구성 하지 않습니다 `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="32831-232">ASP.NET Identity does not configure anonymous or role-based access to locations from `Startup.cs`.</span></span> <span data-ttu-id="32831-233">ASP.NET Core의 필터에 대 한 위치 관련 권한 부여 구성 데이터를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-233">You will need to migrate any location-specific authorization configuration data to filters in ASP.NET Core.</span></span> <span data-ttu-id="32831-234">이러한 업데이트를 필요로 하는 폴더와 페이지를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="32831-234">Make note of which folders and pages will require such updates.</span></span> <span data-ttu-id="32831-235">다음 섹션에서 이러한 변경을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-235">You will make these changes in the next section.</span></span>

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a><span data-ttu-id="32831-236">ASP.NET Core Id 추상화를 사용 하도록 개별 페이지 업데이트</span><span class="sxs-lookup"><span data-stu-id="32831-236">Updating individual pages to use ASP.NET Core Identity abstractions</span></span>

<span data-ttu-id="32831-237">ASP.NET Web Forms 응용 프로그램에서 `web.config` 특정 페이지 또는 폴더에 대 한 액세스를 거부 하는 설정이 익명 사용자에 게 표시 되는 경우 해당 `[Authorize]` 페이지에 특성을 추가 하 여 이러한 변경 내용을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-237">In your ASP.NET Web Forms application, if you had `web.config` settings to deny access to certain pages or folders to anonymous users, you would migrate these changes by adding the `[Authorize]` attribute to such pages:</span></span>

```razor
@attribute [Authorize]
```

<span data-ttu-id="32831-238">특정 역할에 속한 사용자를 제외 하 고 더 이상 액세스를 거부 한 경우 역할을 지정 하는 특성을 추가 하 여이 동작을 마이그레이션할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-238">If you further had denied access except to those users belonging to a certain role, you would likewise migrate this behavior by adding an attribute specifying a role:</span></span>

```razor
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="32831-239">`[Authorize]`특성은 `@page` 라우터를 통해 도달한 구성 요소에 대해서만 작동 Blazor 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-239">The `[Authorize]` attribute only works on `@page` components that are reached via the Blazor Router.</span></span> <span data-ttu-id="32831-240">특성은 대신을 사용 해야 하는 자식 구성 요소에서 작동 하지 않습니다 `AuthorizeView` .</span><span class="sxs-lookup"><span data-stu-id="32831-240">The attribute does not work with child components, which should instead use `AuthorizeView`.</span></span>

<span data-ttu-id="32831-241">특정 사용자에 게 일부 코드를 표시할지 여부를 결정 하기 위한 페이지 태그 내 논리가 있는 경우이를 구성 요소로 바꿀 수 있습니다 `AuthorizeView` .</span><span class="sxs-lookup"><span data-stu-id="32831-241">If you have logic within page markup for determining whether to display some code to a certain user, you can replace this with the `AuthorizeView` component.</span></span> <span data-ttu-id="32831-242">[AuthorizeView 구성 요소](/aspnet/core/blazor/security#authorizeview-component) 는 사용자에 게 볼 수 있는 권한이 있는지 여부에 따라 UI를 선택적으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-242">The [AuthorizeView component](/aspnet/core/blazor/security#authorizeview-component) selectively displays UI depending on whether the user is authorized to see it.</span></span> <span data-ttu-id="32831-243">또한 `context` 사용자 정보에 액세스 하는 데 사용할 수 있는 변수를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-243">It also exposes a `context` variable that can be used to access user information.</span></span>

```razor
<AuthorizeView>
    <Authorized>
        <h1>Hello, @context.User.Identity.Name!</h1>
        <p>You can only see this content if you are authenticated.</p>
    </Authorized>
    <NotAuthorized>
        <h1>Authentication Failure!</h1>
        <p>You are not signed in.</p>
    </NotAuthorized>
</AuthorizeView>
```

<span data-ttu-id="32831-244">특성을 사용 하 여 구성 된에서 사용자에 액세스 하 여 절차적 논리 내에서 인증 상태에 액세스할 수 있습니다 `Task<AuthenticationState` `[CascadingParameter]` .</span><span class="sxs-lookup"><span data-stu-id="32831-244">You can access the authentication state within procedural logic by accessing the user from a `Task<AuthenticationState` configured with the `[CascadingParameter]` attribute.</span></span> <span data-ttu-id="32831-245">이 구성을 통해 사용자에 대 한 액세스 권한을 얻을 수 있으며,이를 통해 인증 여부와 특정 역할에 속하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32831-245">This configuration will get you access to the user, which can let you determine if they are authenticated and if they belong to a particular role.</span></span> <span data-ttu-id="32831-246">정책 procedurally를 평가 해야 하는 경우의 인스턴스를 삽입 하 `IAuthorizationService` 고이에 대 한 메서드를 호출할 수 있습니다 `AuthorizeAsync` .</span><span class="sxs-lookup"><span data-stu-id="32831-246">If you need to evaluate a policy procedurally, you can inject an instance of the `IAuthorizationService` and calls the `AuthorizeAsync` method on it.</span></span> <span data-ttu-id="32831-247">다음 샘플 코드에서는 사용자 정보를 가져오고 권한 있는 사용자가 정책에 의해 제한 된 작업을 수행할 수 있도록 하는 방법을 보여 줍니다 `content-editor` .</span><span class="sxs-lookup"><span data-stu-id="32831-247">The following sample code demonstrates how to get user information and allow an authorized user to perform a task restricted by the `content-editor` policy.</span></span>

```razor
@using Microsoft.AspNetCore.Authorization
@inject IAuthorizationService AuthorizationService

<button @onclick="@DoSomething">Do something important</button>

@code {
    [CascadingParameter]
    private Task<AuthenticationState> authenticationStateTask { get; set; }

    private async Task DoSomething()
    {
        var user = (await authenticationStateTask).User;

        if (user.Identity.IsAuthenticated)
        {
            // Perform an action only available to authenticated (signed-in) users.
        }

        if (user.IsInRole("admin"))
        {
            // Perform an action only available to users in the 'admin' role.
        }

        if ((await AuthorizationService.AuthorizeAsync(user, "content-editor"))
            .Succeeded)
        {
            // Perform an action only available to users satisfying the
            // 'content-editor' policy.
        }
    }
}
```

<span data-ttu-id="32831-248">`AuthenticationState`첫 번째는 이와 같이 연계 된 매개 변수에 바인딩하기 전에 연계 값으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-248">The `AuthenticationState` first need to be set up as a cascading value before it can be bound to a cascading parameter like this.</span></span> <span data-ttu-id="32831-249">일반적으로이 작업은 구성 요소를 사용 하 여 수행 `CascadingAuthenticationState` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32831-249">That's typically done using the `CascadingAuthenticationState` component.</span></span> <span data-ttu-id="32831-250">이 구성은 일반적으로 다음에서 수행 됩니다 `App.razor` .</span><span class="sxs-lookup"><span data-stu-id="32831-250">This configuration is typically done in `App.razor`:</span></span>

```razor
<CascadingAuthenticationState>
    <Router AppAssembly="@typeof(Program).Assembly">
        <Found Context="routeData">
            <AuthorizeRouteView RouteData="@routeData"
                DefaultLayout="@typeof(MainLayout)" />
        </Found>
        <NotFound>
            <LayoutView Layout="@typeof(MainLayout)">
                <p>Sorry, there's nothing at this address.</p>
            </LayoutView>
        </NotFound>
    </Router>
</CascadingAuthenticationState>
```

## <a name="summary"></a><span data-ttu-id="32831-251">요약</span><span class="sxs-lookup"><span data-stu-id="32831-251">Summary</span></span>

<span data-ttu-id="32831-252">Blazor ASP.NET Core와 동일한 보안 모델을 사용 합니다 .이는 ASP.NET Core Id입니다.</span><span class="sxs-lookup"><span data-stu-id="32831-252">Blazor uses the same security model as ASP.NET Core, which is ASP.NET Core Identity.</span></span> <span data-ttu-id="32831-253">유니버설 공급자에서 ASP.NET Core Id로의 마이그레이션은 비교적 간단 합니다. 원래 데이터 스키마에 너무 많은 사용자 지정이 적용 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-253">Migrating from universal providers to ASP.NET Core Identity is relatively straightforward, assuming not too much customization was applied to the original data schema.</span></span> <span data-ttu-id="32831-254">데이터를 마이그레이션한 후에는 응용 프로그램에서 인증 및 권한 부여 작업을 Blazor 잘 설명 하 고, 대부분의 보안 요구 사항에 대 한 프로그래밍 방식의 지원 뿐만 아니라 구성 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="32831-254">Once the data has been migrated, working with authentication and authorization in Blazor apps is well documented, with configurable as well as programmatic support for most security requirements.</span></span>

## <a name="references"></a><span data-ttu-id="32831-255">참조</span><span class="sxs-lookup"><span data-stu-id="32831-255">References</span></span>

- [<span data-ttu-id="32831-256">ASP.NET Core의 Id 소개</span><span class="sxs-lookup"><span data-stu-id="32831-256">Introduction to Identity on ASP.NET Core</span></span>](/aspnet/core/security/authentication/identity)
- [<span data-ttu-id="32831-257">ASP.NET Membership authentication에서 ASP.NET Core 2.0 Id로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="32831-257">Migrate from ASP.NET Membership authentication to ASP.NET Core 2.0 Identity</span></span>](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [<span data-ttu-id="32831-258">ASP.NET Core 인증 및 Id 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="32831-258">Migrate Authentication and Identity to ASP.NET Core</span></span>](/aspnet/core/migration/identity)
- [<span data-ttu-id="32831-259">ASP.NET Core Blazor 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="32831-259">ASP.NET Core Blazor authentication and authorization</span></span>](/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
><span data-ttu-id="32831-260">[이전](config.md)
>[다음](migration.md)</span><span class="sxs-lookup"><span data-stu-id="32831-260">[Previous](config.md)
[Next](migration.md)</span></span>
