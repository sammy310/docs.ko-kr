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
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a>보안: ASP.NET Web Forms 및 Blazor의 인증 및 권한 부여

ASP.NET Web Forms 응용 프로그램에서로 마이그레이션하려면 Blazor 응용 프로그램에 인증이 구성 된 것으로 가정 하 여 인증 및 권한 부여를 수행 하는 방법을 업데이트 해야 합니다. 이 장은 ASP.NET Web Forms 범용 공급자 모델 (멤버 자격, 역할 및 사용자 프로필)에서 마이그레이션하는 방법 및 앱에서 Id를 ASP.NET Core 하는 방법에 대해 설명 합니다 Blazor . 이 장에서는 개략적인 단계 및 고려 사항에 대해 설명 하지만 참조 된 설명서에서 자세한 단계와 스크립트를 찾을 수 있습니다.

## <a name="aspnet-universal-providers"></a>ASP.NET 유니버설 공급자

ASP.NET 2.0부터 ASP.NET Web Forms 플랫폼은 멤버 자격을 포함 하 여 다양 한 기능에 대 한 공급자 모델을 지원 했습니다. 유니버설 멤버 자격 공급자는 선택적 역할 공급자와 함께 일반적으로 ASP.NET Web Forms 응용 프로그램과 함께 배포 됩니다. 지금까지 잘 작동 하는 인증 및 권한 부여를 관리 하는 강력 하 고 안전한 방법을 제공 합니다. 이러한 범용 공급자의 최신 제공은 NuGet 패키지 ( [Microsoft. n. n. n. n.](https://www.nuget.org/packages/Microsoft.AspNet.Providers)n.)로 제공 됩니다.

Universal Providers는,, 및와 같은 테이블을 포함 하는 SQL database 스키마를 사용 `aspnet_Applications` `aspnet_Membership` `aspnet_Roles` `aspnet_Users` 합니다. [aspnet_regsql.exe 명령을](/previous-versions/ms229862(v=vs.140))실행 하 여 구성 하면 공급자가 기본 데이터를 사용 하는 데 필요한 모든 쿼리 및 명령을 제공 하는 테이블 및 저장 프로시저를 설치 합니다. 데이터베이스 스키마와 이러한 저장 프로시저는 새로운 ASP.NET Identity 및 ASP.NET Core Id 시스템과 호환 되지 않으므로 기존 데이터를 새 시스템으로 마이그레이션해야 합니다. 그림 1에서는 유니버설 공급자에 대해 구성 된 예제 테이블 스키마를 보여 줍니다.

![유니버설 공급자 스키마](./media/security/membership-tables.png)

유니버설 공급자는 사용자, 멤버 자격, 역할 및 프로필을 처리 합니다. 사용자에 게는 전역 고유 식별자와 사용자 이름, 사용자 이름 등의 기본 정보가 테이블에 저장 됩니다. `aspnet_Users` 암호, 암호 형식, 암호 솔트, 잠금 카운터 및 세부 정보 등의 인증 정보는 테이블에 저장 됩니다. `aspnet_Membership` 역할은 연결 테이블을 통해 사용자에 게 할당 되는 이름 및 고유 식별자로만 구성 되며 `aspnet_UsersInRoles` 다 대 다 관계를 제공 합니다.

기존 시스템에서 구성원 자격 외에 역할을 사용 하는 경우 사용자 계정, 연결 된 암호, 역할 및 역할 멤버 자격을 ASP.NET Core Id로 마이그레이션해야 합니다. 대신 현재 역할 검사를 수행 하 고 있는 코드를 업데이트 하 여 선언적 필터, 특성 및/또는 태그 도우미를 대신 사용 하는 if 문을 사용 해야 합니다. 이 챕터의 끝 부분에서 마이그레이션 고려 사항을 더 자세히 검토 합니다.

### <a name="authorization-configuration-in-web-forms"></a>Web Forms의 권한 부여 구성

ASP.NET Web Forms 응용 프로그램의 특정 페이지에 대 한 권한 있는 액세스를 구성 하기 위해 일반적으로 익명 사용자가 특정 페이지 또는 폴더에 액세스할 수 없도록 지정 합니다. 이 구성은 web.config 파일에서 수행 됩니다.

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

`authentication`구성 섹션은 응용 프로그램에 대 한 폼 인증을 설정 합니다. `authorization`섹션은 전체 응용 프로그램에 대해 익명 사용자를 허용 하지 않는 데 사용 됩니다. 그러나 위치 별로 보다 세분화 된 권한 부여 규칙을 제공할 뿐만 아니라 역할 기반 권한 부여 확인을 적용할 수 있습니다.

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

위의 구성을 첫 번째 구성과 결합 하면 익명 사용자가 로그인 페이지에 액세스 하 여 인증 되지 않은 사용자에 대 한 사이트 전체 제한을 재정의할 수 있습니다.

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

위의 구성은 다른 구성과 함께 사용 하는 경우 `/admin` 폴더 및 그 안의 모든 리소스를 "Administrators" 역할의 멤버에 대 한 액세스를 제한 합니다. 이 제한은 폴더 루트에 별도의 파일을 배치 하 여 적용할 수도 있습니다 `web.config` `/admin` .

### <a name="authorization-code-in-web-forms"></a>Web Forms의 인증 코드

를 사용 하 여 액세스를 구성 하는 것 외에 `web.config` 도 Web Forms 응용 프로그램에서 프로그래밍 방식으로 액세스 및 동작을 구성할 수 있습니다. 예를 들어 특정 작업을 수행 하는 기능을 제한 하거나 사용자의 역할에 따라 특정 데이터를 볼 수 있습니다.

이 코드는 코드 지향 논리와 페이지 자체에서 모두 사용할 수 있습니다.

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

사용자 역할 멤버 자격을 확인 하는 것 외에도 인증 여부를 확인할 수 있습니다. 그러나이 작업은 위에서 설명한 위치 기반 구성을 사용 하는 것이 더 좋습니다. 다음은이 방법의 예입니다.

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

위의 코드에서는 RBAC (역할 기반 액세스 제어)를 사용 하 여 페이지의 특정 요소 (예:)가 `SecretPanel` 현재 사용자의 역할에 따라 표시 되는지 여부를 확인 합니다.

일반적으로 ASP.NET Web Forms 응용 프로그램은 파일 내에서 보안을 구성 `web.config` 하 고 필요한 경우 `.aspx` 페이지 및 관련 코드 숨김이 있는 파일에 대 한 추가 검사를 추가 `.aspx.cs` 합니다. 대부분의 응용 프로그램은 일반적으로 추가 역할 공급자를 사용 하 여 유니버설 멤버 자격 공급자를 활용 합니다.

## <a name="aspnet-core-identity"></a>ASP.NET Core ID

인증 및 권한 부여를 사용 하는 경우에도 ASP.NET Core Id는 유니버설 공급자와 비교할 때 다른 추상화 및 가정 집합을 사용 합니다. 예를 들어 새 Id 모델은 타사 인증을 지원 하므로 사용자는 소셜 미디어 계정 또는 다른 신뢰할 수 있는 인증 공급자를 사용 하 여 인증할 수 있습니다. ASP.NET Core Identity는 로그인, 로그 아웃, 등록 등 일반적으로 필요한 페이지에 대 한 UI를 지원 합니다. 데이터 액세스를 위해 EF Core를 활용 하 고 EF Core 마이그레이션을 사용 하 여 데이터 모델을 지 원하는 데 필요한 스키마를 생성 합니다. [ASP.NET Core의 id 소개](/aspnet/core/security/authentication/identity) 에서는 ASP.NET Core id에 포함 된 기능과이를 사용 하 여 작업을 시작 하는 방법에 대 한 개요를 제공 합니다. 응용 프로그램 및 해당 데이터베이스에서 ASP.NET Core Id를 아직 설정 하지 않은 경우 시작 하는 데 도움이 됩니다.

### <a name="roles-claims-and-policies"></a>역할, 클레임 및 정책

유니버설 공급자와 ASP.NET Core Id는 모두 역할의 개념을 지원 합니다. 사용자에 대 한 역할을 만들고 역할에 사용자를 할당할 수 있습니다. 사용자는 원하는 수의 역할에 속할 수 있으며 권한 부여 구현의 일부로 역할 멤버 자격을 확인할 수 있습니다.

역할 외에도 ASP.NET Core identity는 클레임 및 정책의 개념을 지원 합니다. 역할은 해당 역할의 사용자가 액세스할 수 있어야 하는 리소스 집합과 구체적으로 일치 해야 하지만 클레임은 단순히 사용자 id의 일부입니다. 클레임은 주체가 어떤 작업을 수행할 수 있는지를 나타내는 이름 값 쌍입니다.

사용자의 클레임을 직접 검사 하 고 이러한 값을 기준으로 사용자에 게 리소스에 대 한 액세스 권한을 부여 해야 할지 여부를 결정할 수 있습니다. 그러나 이러한 검사는 시스템 전체에서 반복적이 고 분산 되는 경우가 많습니다. 더 나은 방법은 *정책을* 정의 하는 것입니다.

권한 부여 정책은 하나 이상의 요구 사항으로 구성 됩니다. 정책은의 메서드에서 권한 부여 서비스 구성의 일부로 등록 됩니다 `ConfigureServices` `Startup.cs` . 예를 들어 다음 코드 조각은 "CanadiansOnly" 이라는 정책을 구성 합니다 .이 정책은 사용자에 게 값이 "캐나다" 인 Country 클레임이 있어야 한다는 요구 사항이 있습니다.

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

[설명서에서 사용자 지정 정책을 만드는 방법에 대해 자세히 알아볼](/aspnet/core/security/authorization/policies)수 있습니다.

정책 또는 역할을 사용 하는 경우에는 응용 프로그램의 특정 페이지에 지시문을 사용 하 여 Blazor 특성을 가진 역할이 나 정책이 필요 하도록 지정할 수 있습니다 `[Authorize]` `@attribute` .

역할 필요:

```csharp
@attribute [Authorize(Roles ="administrators")]
```

정책을 충족 해야 합니다.

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

사용자의 코드에서 사용자의 인증 상태, 역할 또는 클레임에 액세스 해야 하는 경우이 기능을 구현 하는 두 가지 기본 방법이 있습니다. 첫 번째는 인증 상태를 연계 매개 변수로 받는 것입니다. 두 번째는 삽입 된를 사용 하 여 상태에 액세스 하는 것입니다 `AuthenticationStateProvider` . 이러한 각 방법에 대 한 세부 정보는 [ Blazor 보안 설명서](/aspnet/core/blazor/security/)에 설명 되어 있습니다.

다음 코드에서는를 연계 매개 변수로 수신 하는 방법을 보여 줍니다 `AuthenticationState` .

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

이 매개 변수를 사용 하는 경우 다음 코드를 사용 하 여 사용자를 가져올 수 있습니다.

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

다음 코드에서는을 삽입 하는 방법을 보여 줍니다 `AuthenticationStateProvider` .

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

공급자가 준비 되 면 다음 코드를 사용 하 여 사용자에 게 액세스 권한을 얻을 수 있습니다.

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

**참고:** `AuthorizeView` 이 챕터의 뒷부분에서 설명 하는 구성 요소는 사용자가 페이지 또는 구성 요소에서 볼 수 있는 내용을 제어 하는 선언적 방법을 제공 합니다.

서버 응용 프로그램에서 사용자 및 클레임으로 작업 하려면 Blazor `UserManager<T>` `IdentityUser` 사용자에 대 한 클레임을 열거 하 고 수정 하는 데 사용할 수 있는를 삽입 해야 할 수도 있습니다 (기본값에 사용). 먼저 형식을 삽입 하 고이를 속성에 할당 합니다.

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

그런 다음 사용자의 클레임을 사용 하 여 작업 합니다. 다음 샘플에서는 사용자에 게 클레임을 추가 하 고 유지 하는 방법을 보여 줍니다.

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

역할을 사용 해야 하는 경우에는 동일한 방법을 따릅니다. `RoleManager<T>` `IdentityRole` 역할 자체를 나열 하 고 관리 하려면 (기본 형식에 사용)를 삽입 해야 할 수도 있습니다.

**참고:** Blazor Weasembopprojects 프로젝트에서 또는 직접를 사용 하는 대신 이러한 작업을 수행할 수 있도록 서버 api를 제공 해야 `UserManager<T>` `RoleManager<T>` 합니다. BlazorWeasembmbomclient 응용 프로그램은이 목적을 위해 노출 된 API 끝점을 안전 하 게 호출 하 여 클레임 및/또는 역할을 관리 합니다.

### <a name="migration-guide"></a>마이그레이션 가이드

ASP.NET Web Forms 및 유니버설 공급자에서 ASP.NET Core Id로 마이그레이션하려면 몇 가지 단계가 필요 합니다.

1. 대상 데이터베이스에서 ASP.NET Core Id 데이터베이스 스키마 만들기
2. 유니버설 공급자 스키마에서 ASP.NET Core Identity 스키마로 데이터 마이그레이션
3. 에서 `web.config` 미들웨어 및 서비스 (일반적으로)로 구성을 마이그레이션합니다. `Startup.cs`
4. 태그 도우미 및 새 id Api를 사용 하도록 컨트롤 및 조건을 사용 하 여 개별 페이지를 업데이트 합니다.

이러한 각 단계는 다음 섹션에서 자세히 설명합니다.

### <a name="creating-the-aspnet-core-identity-schema"></a>ASP.NET Core Id 스키마 만들기

ASP.NET Core Id에 사용 되는 필요한 테이블 구조를 만드는 방법에는 여러 가지가 있습니다. 가장 간단한 방법은 새 ASP.NET Core 웹 응용 프로그램을 만드는 것입니다. 웹 응용 프로그램을 선택한 다음 인증을 변경 하 여 개별 사용자 계정을 사용 합니다.

![개별 사용자 계정을 사용 하는 새 프로젝트](./media/security/individual-user-accounts.png)

명령줄에서를 실행 하 여 동일한 작업을 수행할 수 있습니다 `dotnet new webapp -au Individual` . 앱을 만든 후에는 앱을 실행 하 고 사이트에 등록 합니다. 아래와 같은 페이지를 트리거해야 합니다.

![마이그레이션 적용 페이지](./media/security/apply-migrations-page.png)

"마이그레이션 적용" 단추를 클릭 하면 필요한 데이터베이스 테이블이 생성 됩니다. 또한 다음과 같이 마이그레이션 파일이 프로젝트에 표시 됩니다.

![마이그레이션 파일](./media/security/migration-files.png)

이 명령줄 도구를 사용 하 여 웹 응용 프로그램을 실행 하지 않고 직접 마이그레이션을 실행할 수 있습니다.

```powershell
dotnet ef database update
```

새 스키마를 기존 데이터베이스에 적용 하는 스크립트를 실행 하는 경우 명령줄에서 이러한 마이그레이션을 스크립팅할 수 있습니다. 다음 명령을 실행 하 여 스크립트를 생성 합니다.

```powershell
dotnet ef migrations script -o auth.sql
```

위의 명령은 출력 파일에 SQL 스크립트를 생성 합니다 .이 스크립트는 원하는 `auth.sql` 모든 데이터베이스에 대해 실행 될 수 있습니다. 명령을 실행 하는 데 문제가 있는 경우 `dotnet ef` [EF Core 도구가 시스템에 설치 되어 있는지 확인](/ef/core/miscellaneous/cli/dotnet)합니다.

원본 테이블에 추가 열이 있는 경우 새 스키마에서 이러한 열에 대해 가장 적합 한 위치를 식별 해야 합니다. 일반적으로 테이블에 있는 열은 `aspnet_Membership` 테이블에 매핑되어야 합니다 `AspNetUsers` . 의 열은 `aspnet_Roles` 에 매핑되어야 `AspNetRoles` 합니다. 테이블의 모든 추가 열이 `aspnet_UsersInRoles` 테이블에 추가 됩니다 `AspNetUserRoles` .

또한 별도의 테이블에 추가 열을 추가 하는 것도 고려해 야 합니다. 이후 마이그레이션에서 기본 id 스키마의 사용자 지정을 고려해 야 할 필요가 없습니다.

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a>유니버설 공급자에서 ASP.NET Core Id로 데이터 마이그레이션

대상 테이블 스키마가 준비 되 면 다음 단계는 사용자 및 역할 레코드를 새 스키마로 마이그레이션하는 것입니다. 새 열에 매핑되는 열을 포함 하 여 스키마 차이점의 전체 목록은 [여기](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)에서 찾을 수 있습니다.

사용자를 멤버 자격에서 새 id 테이블로 마이그레이션하려면 [설명서에 설명 된 단계를 수행](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)해야 합니다. 이러한 단계를 수행 하 고 스크립트를 제공 하면 사용자가 다음에 로그인 할 때 암호를 변경 해야 합니다.

사용자 암호를 마이그레이션할 수 있지만 프로세스는 훨씬 더 복잡 합니다. 사용자가 마이그레이션 프로세스의 일부로 암호를 업데이트 하도록 요구 하 고 새로운 고유 암호를 사용 하도록 하는 것은 응용 프로그램의 전반적인 보안을 향상 시킬 수 있습니다.

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a>web.config에서 Startup.cs로 보안 설정 마이그레이션

위에서 설명한 것 처럼 ASP.NET 멤버 자격 및 역할 공급자는 응용 프로그램의 파일에 구성 됩니다 `web.config` . ASP.NET Core 앱은 IIS에 연결 되지 않고 구성에 별도의 시스템을 사용 하기 때문에 이러한 설정을 다른 곳에서 구성 해야 합니다. 대부분의 경우 ASP.NET Core Id는 파일에서 구성 됩니다 `Startup.cs` . 이전에 만든 웹 프로젝트를 열고 (id 테이블 스키마 생성) 해당 파일을 검토 `Startup.cs` 합니다.

기본 ConfigureServices 메서드는 EF Core 및 Id에 대 한 지원을 추가 합니다.

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

`AddDefaultIdentity`확장 메서드는 기본 `ApplicationDbContext` 및 프레임 워크 형식을 사용 하도록 id를 구성 하는 데 사용 됩니다 `IdentityUser` . 사용자 지정을 사용 하는 경우 `IdentityUser` 여기에서 해당 형식을 지정 해야 합니다. 이러한 확장 메서드가 응용 프로그램에서 작동 하지 않는 경우 적절 한 using 문을 사용 하 고 필요한 NuGet 패키지를 참조 하는지 확인 합니다. 예를 들어 프로젝트에 일부 버전의 `Microsoft.AspNetCore.Identity.EntityFrameworkCore` 및 패키지를 참조 해야 합니다 `Microsoft.AspNetCore.Identity.UI` .

또한 `Startup.cs` 사이트에 대해 구성 된 필요한 미들웨어가 표시 되어야 합니다. 특히 `UseAuthentication` 및를 `UseAuthorization` 적절 한 위치에 설정 해야 합니다.

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

ASP.NET Identity는의 위치에 대 한 익명 또는 역할 기반 액세스를 구성 하지 않습니다 `Startup.cs` . ASP.NET Core의 필터에 대 한 위치 관련 권한 부여 구성 데이터를 마이그레이션해야 합니다. 이러한 업데이트를 필요로 하는 폴더와 페이지를 기록해 둡니다. 다음 섹션에서 이러한 변경을 수행 합니다.

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a>ASP.NET Core Id 추상화를 사용 하도록 개별 페이지 업데이트

ASP.NET Web Forms 응용 프로그램에서 `web.config` 특정 페이지 또는 폴더에 대 한 액세스를 거부 하는 설정이 익명 사용자에 게 표시 되는 경우 해당 `[Authorize]` 페이지에 특성을 추가 하 여 이러한 변경 내용을 마이그레이션합니다.

```razor
@attribute [Authorize]
```

특정 역할에 속한 사용자를 제외 하 고 더 이상 액세스를 거부 한 경우 역할을 지정 하는 특성을 추가 하 여이 동작을 마이그레이션할 수도 있습니다.

```razor
@attribute [Authorize(Roles ="administrators")]
```

`[Authorize]`특성은 `@page` 라우터를 통해 도달한 구성 요소에 대해서만 작동 Blazor 합니다. 특성은 대신을 사용 해야 하는 자식 구성 요소에서 작동 하지 않습니다 `AuthorizeView` .

특정 사용자에 게 일부 코드를 표시할지 여부를 결정 하기 위한 페이지 태그 내 논리가 있는 경우이를 구성 요소로 바꿀 수 있습니다 `AuthorizeView` . [AuthorizeView 구성 요소](/aspnet/core/blazor/security#authorizeview-component) 는 사용자에 게 볼 수 있는 권한이 있는지 여부에 따라 UI를 선택적으로 표시 합니다. 또한 `context` 사용자 정보에 액세스 하는 데 사용할 수 있는 변수를 노출 합니다.

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

특성을 사용 하 여 구성 된에서 사용자에 액세스 하 여 절차적 논리 내에서 인증 상태에 액세스할 수 있습니다 `Task<AuthenticationState` `[CascadingParameter]` . 이 구성을 통해 사용자에 대 한 액세스 권한을 얻을 수 있으며,이를 통해 인증 여부와 특정 역할에 속하는지 여부를 확인할 수 있습니다. 정책 procedurally를 평가 해야 하는 경우의 인스턴스를 삽입 하 `IAuthorizationService` 고이에 대 한 메서드를 호출할 수 있습니다 `AuthorizeAsync` . 다음 샘플 코드에서는 사용자 정보를 가져오고 권한 있는 사용자가 정책에 의해 제한 된 작업을 수행할 수 있도록 하는 방법을 보여 줍니다 `content-editor` .

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

`AuthenticationState`첫 번째는 이와 같이 연계 된 매개 변수에 바인딩하기 전에 연계 값으로 설정 해야 합니다. 일반적으로이 작업은 구성 요소를 사용 하 여 수행 `CascadingAuthenticationState` 됩니다. 이 구성은 일반적으로 다음에서 수행 됩니다 `App.razor` .

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

## <a name="summary"></a>요약

Blazor ASP.NET Core와 동일한 보안 모델을 사용 합니다 .이는 ASP.NET Core Id입니다. 유니버설 공급자에서 ASP.NET Core Id로의 마이그레이션은 비교적 간단 합니다. 원래 데이터 스키마에 너무 많은 사용자 지정이 적용 된 것으로 가정 합니다. 데이터를 마이그레이션한 후에는 응용 프로그램에서 인증 및 권한 부여 작업을 Blazor 잘 설명 하 고, 대부분의 보안 요구 사항에 대 한 프로그래밍 방식의 지원 뿐만 아니라 구성 가능 합니다.

## <a name="references"></a>참조

- [ASP.NET Core의 Id 소개](/aspnet/core/security/authentication/identity)
- [ASP.NET Membership authentication에서 ASP.NET Core 2.0 Id로 마이그레이션](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [ASP.NET Core 인증 및 Id 마이그레이션](/aspnet/core/migration/identity)
- [ASP.NET Core Blazor 인증 및 권한 부여](/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
>[이전](config.md)
>[다음](migration.md)
