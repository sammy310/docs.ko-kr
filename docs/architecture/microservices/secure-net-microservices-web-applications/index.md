---
title: .NET 마이크로 서비스 및 웹 애플리케이션 보안
description: .NET 마이크로 서비스 및 웹 애플리케이션 보안 - ASP.NET Core 웹 애플리케이션의 인증 옵션을 살펴봅니다.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 5e9b616e0443e85c016401a51efc3b04d2329e3b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771992"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="f4e85-103">.NET 마이크로 서비스 및 웹 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="f4e85-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="f4e85-104">항목에서는 이와 같은 여러 설명서를 쉽게 사용할 수 있는 마이크로 서비스 및 웹 애플리케이션의 보안에 대한 많은 측면이 있으므로 이 섹션에서는 인증, 권한 및 애플리케이션 비밀에 집중하도록 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="f4e85-105">.NET 마이크로 서비스 및 웹 애플리케이션의 인증 구현</span><span class="sxs-lookup"><span data-stu-id="f4e85-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="f4e85-106">서비스에서 게시된 리소스 및 API는 종종 특정 신뢰할 수 있는 사용자 또는 클라이언트로 제한되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="f4e85-107">이러한 API 수준 신뢰 결정을 만드는 첫 번째 단계는 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="f4e85-108">인증은 사용자의 ID를 안정적으로 확인하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-108">Authentication is the process of reliably verify a user’s identity.</span></span>

<span data-ttu-id="f4e85-109">마이크로 서비스 시나리오에서 일반적으로 인증은 중앙에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="f4e85-110">API 게이트웨이를 사용하는 경우 그림 9-1에 표시된 것처럼 게이트웨이는 인증에 적합한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="f4e85-111">이 방법을 사용하는 경우 메시지를 인증하는 데 추가 보안을 사용하지 않는 한 (API 게이트웨이 없이) 개별 마이크로 서비스에 직접 연결할 수 없습니다. 인증하는 메시지의 출처는 반드시 게이트웨이가 아니어도 무방합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![API 게이트웨이는 인증을 중앙 집중 방식으로 관리하는 경우 마이크로 서비스에 요청을 전달할 때 사용자 정보를 추가합니다.](./media/image1.png)

<span data-ttu-id="f4e85-113">**그림 9-1**.</span><span class="sxs-lookup"><span data-stu-id="f4e85-113">**Figure 9-1**.</span></span> <span data-ttu-id="f4e85-114">API 게이트웨이를 통한 중앙 집중식 인증</span><span class="sxs-lookup"><span data-stu-id="f4e85-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="f4e85-115">서비스에 직접 액세스할 수 있는 경우 Azure Active Directory 또는 STS(보안 토큰 서비스)로 작동하는 전용 인증 마이크로 서비스와 같은 인증 서비스를 사용하여 사용자를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-115">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="f4e85-116">신뢰 결정은 보안 토큰 또는 쿠키를 통해 서비스 간에 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-116">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="f4e85-117">(필요한 경우 [쿠키 공유](/aspnet/core/security/cookie-sharing)를 구현하여 이러한 토큰을 ASP.NET Core 애플리케이션 간에 공유할 수 있습니다.) 그림 9-2에서는 이 패턴을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-117">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![마이크로 서비스에 직접 액세스하는 경우 인증 및 권한 부여를 포함하는 트러스트는 마이크로 서비스 간에 공유되고, 전용 마이크로 서비스에서 발급한 보안 토큰에서 처리됩니다.](./media/image2.png)

<span data-ttu-id="f4e85-119">**그림9-2**</span><span class="sxs-lookup"><span data-stu-id="f4e85-119">**Figure 9-2**.</span></span> <span data-ttu-id="f4e85-120">ID 마이크로 서비스에 의한 인증. 인증 토큰을 사용하여 신뢰가 공유됨</span><span class="sxs-lookup"><span data-stu-id="f4e85-120">Authentication by identity microservice; trust is shared using an authorization token</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="f4e85-121">ASP.NET Core ID를 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="f4e85-121">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="f4e85-122">애플리케이션의 사용자를 식별하기 위한 ASP.NET Core의 기본 메커니즘은 [ASP.NET Core ID](/aspnet/core/security/authentication/identity) 멤버 자격 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-122">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="f4e85-123">ASP.NET ID는 사용자 정보(로그인 정보, 역할 및 클레임 포함)를 개발자가 구성한 데이터 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-123">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="f4e85-124">일반적으로 ASP.NET Core ID 데이터 저장소는 `Microsoft.AspNetCore.Identity.EntityFrameworkCore` 패키지에서 제공된 Entity Framework 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-124">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="f4e85-125">그러나 사용자 지정 저장소 또는 타사 패키지를 사용하여 Azure Table Storage, CosmosDB 또는 다른 위치에 ID 정보를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-125">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

<span data-ttu-id="f4e85-126">다음은 선택된 개별 사용자 계정 인증을 사용하여 ASP.NET Core 웹 애플리케이션 프로젝트 템플릿에서 가져온 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-126">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="f4e85-127">Startup.ConfigureServices 메서드에서 EntityFramework.Core를 사용하여 ASP.NET Core ID를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-127">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="f4e85-128">ASP.NET Core ID가 구성되면 서비스의 `Startup.Configure` 메서드에서 app.UseIdentity를 호출하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-128">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s `Startup.Configure` method.</span></span>

<span data-ttu-id="f4e85-129">ASP.NET Core ID를 통해 다음과 같은 몇 가지 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-129">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="f4e85-130">UserManager 형식(userManager.CreateAsync)을 사용하여 새 사용자 정보를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-130">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="f4e85-131">SignInManager 형식을 사용하여 사용자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-131">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="f4e85-132">직접 로그인하려면 `signInManager.SignInAsync`를 사용하거나, 사용자의 암호가 올바른지 확인한 다음, 로그인하려면 `signInManager.PasswordSignInAsync`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-132">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user’s password is correct and then sign them in.</span></span>

- <span data-ttu-id="f4e85-133">브라우저의 후속 요청에 로그인한 사용자의 ID와 클레임이 포함되도록 (ASP.NET Core ID 미들웨어에서 읽는) 쿠키에 저장된 정보를 기반으로 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-133">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="f4e85-134">ASP.NET Core ID도 [2단계 인증](/aspnet/core/security/authentication/2fa)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-134">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="f4e85-135">ASP.NET Core ID는 로컬 사용자 데이터 저장소를 사용하며 (MVC 웹 애플리케이션에서는 전형적인 방식인) 쿠키를 사용하여 요청 사이의 ID를 유지하는 인증 시나리오를 위해 권장되는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-135">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="f4e85-136">외부 공급자를 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="f4e85-136">Authenticate with external providers</span></span>

<span data-ttu-id="f4e85-137">ASP.NET Core는 [외부 인증 공급자](/aspnet/core/security/authentication/social/)를 사용하여 사용자가 [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) 흐름을 통해 로그인할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-137">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="f4e85-138">즉, 사용자가 Microsoft, Google, Facebook 또는 Twitter와 같은 공급 기업의 기존 인증 프로세스를 사용하여 로그인하고 애플리케이션에서 ASP.NET Core ID와 해당 ID를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-138">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="f4e85-139">외부 인증을 사용하려면 애플리케이션의 HTTP 요청 처리 파이프라인에서 적절한 인증 미들웨어를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-139">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="f4e85-140">이 미들웨어는 인증 공급자의 URI 경로 반환 요청 처리, ID 정보 캡처, SignInManager.GetExternalLoginInfo 메서드를 통해 사용 가능하도록 설정하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-140">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="f4e85-141">인기 있는 외부 인증 공급 기업 및 해당 공급 기업과 연결된 NuGet 패키지는 다음 표에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-141">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="f4e85-142">**공급 기업**</span><span class="sxs-lookup"><span data-stu-id="f4e85-142">**Provider**</span></span>  | <span data-ttu-id="f4e85-143">**패키지**</span><span class="sxs-lookup"><span data-stu-id="f4e85-143">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="f4e85-144">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="f4e85-144">**Microsoft**</span></span> | <span data-ttu-id="f4e85-145">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="f4e85-145">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="f4e85-146">**Google**</span><span class="sxs-lookup"><span data-stu-id="f4e85-146">**Google**</span></span>    | <span data-ttu-id="f4e85-147">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="f4e85-147">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="f4e85-148">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="f4e85-148">**Facebook**</span></span>  | <span data-ttu-id="f4e85-149">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="f4e85-149">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="f4e85-150">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="f4e85-150">**Twitter**</span></span>   | <span data-ttu-id="f4e85-151">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="f4e85-151">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="f4e85-152">모든 경우에 미들웨어는 `Startup.Configure`의 `app.Use{ExternalProvider}Authentication`과 유사한 등록 메서드에 대한 호출에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-152">In all cases, the middleware is registered with a call to a registration method similar to `app.Use{ExternalProvider}Authentication` in `Startup.Configure`.</span></span> <span data-ttu-id="f4e85-153">이러한 등록 메서드에서는 공급자의 필요에 따라 애플리케이션 ID 및 비밀 정보(예: 암호)가 포함된 옵션 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-153">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="f4e85-154">외부 인증 공급자는 사용자 ID에 액세스하는 데 필요한 애플리케이션을 사용자에게 안내하기 위해 ([ASP.NET Core 설명서](/aspnet/core/security/authentication/social/)에서 설명한 것처럼) 등록할 애플리케이션을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-154">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="f4e85-155">미들웨어가 `Startup.Configure`에 등록되면 모든 컨트롤러 작업에서 사용자에게 로그인을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-155">Once the middleware is registered in `Startup.Configure`, you can prompt users to sign in from any controller action.</span></span> <span data-ttu-id="f4e85-156">이 작업을 수행하려면 인증 공급 기업의 이름 및 리디렉션 URL을 포함하는 `AuthenticationProperties` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-156">To do this, you create an `AuthenticationProperties` object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="f4e85-157">그런 다음, `AuthenticationProperties` 개체를 전달하는 챌린지 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-157">You then return a Challenge response that passes the `AuthenticationProperties` object.</span></span> <span data-ttu-id="f4e85-158">다음 코드에서는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-158">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="f4e85-159">redirectUrl 매개 변수는 사용자가 인증되면 외부 공급자가 리디렉션해야 하는 URL을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-159">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="f4e85-160">URL은 다음 단순화된 예제와 같이 외부 ID 정보를 기반으로 사용자가 로그인하는 작업을 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-160">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="f4e85-161">Visual Studio에서 ASP.NET Core 웹 애플리케이션 프로젝트를 만들 때 **개별 사용자 계정** 인증 옵션을 선택한 경우 그림 9-3에 표시된 것처럼 외부 공급 기업을 통해 로그인하는 데 필요한 모든 코드는 이미 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-161">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 9-3.</span></span>

![인증을 변경하는 단추를 강조 표시하는 새 ASP.NET Core 웹 애플리케이션의 대화 상자입니다.](./media/image3.png)

<span data-ttu-id="f4e85-163">**그림 9-3**</span><span class="sxs-lookup"><span data-stu-id="f4e85-163">**Figure 9-3**.</span></span> <span data-ttu-id="f4e85-164">웹 애플리케이션 프로젝트를 만들 경우 외부 인증 사용 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="f4e85-164">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="f4e85-165">이전에 나열된 외부 인증 공급자뿐만 아니라 더욱 많은 외부 인증 공급자 사용에 대한 미들웨어를 제공하는 타사 패키지도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-165">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="f4e85-166">자세한 목록은 GitHub에서 [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) 리포지토리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f4e85-166">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="f4e85-167">또한, 몇 가지 특별한 요구를 해결하려면 사용자 고유의 외부 인증 미들웨어를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-167">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="f4e85-168">전달자 토큰을 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="f4e85-168">Authenticate with bearer tokens</span></span>

<span data-ttu-id="f4e85-169">ASP.NET Core ID(또는 ID 및 외부 인증 공급자)를 사용한 인증은 사용자 정보를 쿠키에 저장하는 것이 적합한 다수의 웹 애플리케이션 시나리오에 대해 효과적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-169">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="f4e85-170">그러나 다른 시나리오의 경우 쿠키는 데이터를 유지하고 전송하는 자연스러운 방법이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-170">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="f4e85-171">예를 들어 SPA(단일 페이지 애플리케이션), 네이티브 클라이언트 또는 다른 웹 API에서 액세스할 수 있는 RESTful 엔드포인트를 노출하는 ASP.NET Core 웹 API에서는 쿠키 대신 일반적으로 전달자 토큰 인증을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-171">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="f4e85-172">이러한 유형의 애플리케이션은 쿠키와는 작동하지 않지만 간편하게 전달자 토큰을 검색하여 후속 요청의 인증 헤더에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-172">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="f4e85-173">토큰 인증을 사용하기 위해 ASP.NET Core는 [OAuth 2.0](https://oauth.net/2/) 및 [OpenID Connect](https://openid.net/connect/) 사용에 대한 몇 가지 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-173">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="f4e85-174">OpenID Connect 또는 OAuth 2.0 ID 공급 기업을 사용한 인증</span><span class="sxs-lookup"><span data-stu-id="f4e85-174">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="f4e85-175">사용자 정보가 Azure Active Directory 또는 OpenID Connect 또는 OAuth 2.0을 지원하는 다른 ID 솔루션에 저장되는 경우 **Microsoft.AspNetCore.Authentication.OpenIdConnect** 패키지를 사용하여 OpenID Connect 워크플로를 통해 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-175">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="f4e85-176">예를 들어 eShopOnContainers의 Identity.Api 마이크로 서비스에 대해 인증하려면 ASP.NET Core 웹 애플리케이션에서는 `Startup.cs`의 다음 간단한 예제에 표시된 것처럼 해당 패키지의 미들웨어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-176">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

<span data-ttu-id="f4e85-177">이 워크플로를 사용하면 모든 사용자 정보 스토리지 및 인증이 ID 서비스에서 처리되므로 ASP.NET Core ID 미들웨어가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-177">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="f4e85-178">ASP.NET Core 서비스에서 보안 토큰 발급</span><span class="sxs-lookup"><span data-stu-id="f4e85-178">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="f4e85-179">로컬 ASP.NET Core ID 사용자를 위해 외부 ID 공급자를 사용하는 대신 보안 토큰 발급을 선호하는 경우 일부 훌륭한 타사 라이브러리를 적절하게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-179">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="f4e85-180">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) 및 [OpenIddict](https://github.com/openiddict/openiddict-core)는 ASP.NET Core ID와 쉽게 통합하여 ASP.NET Core 서비스에서 보안 토큰을 발급할 수 있도록 허용하는 OpenID Connect 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-180">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="f4e85-181">[IdentityServer4 설명서](https://identityserver4.readthedocs.io/en/latest/)에는 라이브러리 사용에 대한 자세한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-181">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="f4e85-182">그러나 IdentityServer4를 사용하여 토큰을 발급하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-182">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="f4e85-183">Startup.Configure 메서드에서 app.UseIdentityServer를 호출하여 IdentityServer4를 애플리케이션의 HTTP 요청 처리 파이프라인에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-183">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="f4e85-184">이렇게 하면 라이브러리 서버에서 /connect/token과 같은 OpenID Connect 및 OAuth2 엔드포인트에 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-184">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="f4e85-185">services.AddIdentityServer를 호출하여 Startup.ConfigureServices에서 IdentityServer4를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-185">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="f4e85-186">다음 데이터를 설정하여 ID 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-186">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="f4e85-187">서명에 사용할 [자격 증명](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html)</span><span class="sxs-lookup"><span data-stu-id="f4e85-187">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="f4e85-188">액세스를 위해 사용자가 요청할 수 있는 [ID 및 API 리소스](https://identityserver4.readthedocs.io/en/latest/topics/resources.html)</span><span class="sxs-lookup"><span data-stu-id="f4e85-188">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="f4e85-189">API 리소스는 사용자가 액세스 토큰을 사용하여 액세스할 수 있는 보호된 데이터 또는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-189">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="f4e85-190">웹 API 리소스의 예로는 권한 부여가 필요한 웹 API(또는 API 집합)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-190">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="f4e85-191">ID 리소스는 사용자를 식별하기 위해 클라이언트에게 제공되는 정보(클레임)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-191">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="f4e85-192">클레임에는 사용자 이름, 전자 메일 주소 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-192">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="f4e85-193">토큰을 요청하기 위해 [클라이언트](https://identityserver4.readthedocs.io/en/latest/topics/clients.html)가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-193">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="f4e85-194">[ASP.NET Core ID](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) 또는 대체 요소와 같은 사용자 정보에 대한 스토리지 메커니즘.</span><span class="sxs-lookup"><span data-stu-id="f4e85-194">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="f4e85-195">IdentityServer4가 사용할 클라이언트와 리소스를 지정할 때 적절한 형식의 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션을 메모리 내 클라이언트 또는 리소스 저장소를 사용하는 메서드로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-195">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="f4e85-196">또는 더 복잡한 시나리오의 경우 종속성 주입을 통해 클라이언트 또는 리소스 공급자 형식을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-196">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="f4e85-197">사용자 지정 IClientStore 형식에서 제공한 메모리 내 리소스 및 클라이언트를 사용하는 IdentityServer4를 위한 샘플 구성은 다음 예제처럼 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-197">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a><span data-ttu-id="f4e85-198">보안 토큰 사용</span><span class="sxs-lookup"><span data-stu-id="f4e85-198">Consume security tokens</span></span>

<span data-ttu-id="f4e85-199">OpenID Connect 엔드포인트에 대해 인증하거나 고유 보안 토큰을 발행하는 방법은 일부 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-199">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="f4e85-200">그러나 다른 서비스에서 제공받은 유효한 보안 토큰이 있는 사용자의 액세스를 제한해야 하는 서비스에는 어떤 방법을 사용해야 할까요?</span><span class="sxs-lookup"><span data-stu-id="f4e85-200">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="f4e85-201">해당 시나리오의 경우 JWT 토큰을 처리하는 인증 미들웨어를 **Microsoft.AspNetCore.Authentication.JwtBearer** 패키지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-201">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="f4e85-202">JWT는 “[JSON Web Token](https://tools.ietf.org/html/rfc7519)”을 의미하며 보안 클레임 통신을 위한 일반적인 보안 토큰 형식(RFC 7519에 의해 정의됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-202">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="f4e85-203">미들웨어를 통해 이러한 토큰을 사용하는 방법의 간단한 예제는 eShopOnContainers의 Ordering.Api 마이크로 서비스에서 가져온 이 코드 조각처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-203">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="f4e85-204">이 사용에 대한 매개 변수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-204">The parameters in this usage are:</span></span>

- <span data-ttu-id="f4e85-205">`Audience`는 들어오는 토큰의 수신기 또는 토큰에서 액세스 권한을 부여하는 리소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-205">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="f4e85-206">이 매개 변수에서 지정한 값이 토큰의 매개 변수와 일치하지 않는 경우 토큰이 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-206">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="f4e85-207">`Authority`는 토큰 발행 인증 서버의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-207">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="f4e85-208">JWT 전달자 인증 미들웨어는 이 URI를 사용하여 토큰 시그니처의 유효성을 검사하는 데 사용되는 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-208">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="f4e85-209">또한 미들웨어는 토큰의 `iss` 매개 변수가 이 URI와 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-209">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="f4e85-210">다른 매개 변수 `RequireHttpsMetadata`는 테스트 목적으로 사용하는 것이 적합합니다. 이 매개 변수를 false로 설정하여 인증서가 없는 환경에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-210">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="f4e85-211">실제 배포에서 JWT 전달자 토큰은 항상 HTTPS를 통해서만 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-211">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="f4e85-212">미들웨어가 준비되면 JWT 토큰은 인증 헤더에서 자동으로 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-212">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="f4e85-213">그런 다음, 토큰은 deserialize되고 (`Audience` 및 `Authority` 매개 변수를 사용하여) 유효성 검사가 진행되며 나중에 MVC 작업 또는 인증 필터에서 참조하는 사용자 정보로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-213">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="f4e85-214">JWT 전달자 인증 미들웨어는 인증 기관을 사용할 수 없는 경우 로컬 인증서를 사용하여 토큰의 유효성을 검사하는 상황과 같은 고급 시나리오도 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-214">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="f4e85-215">이 시나리오의 경우 `JwtBearerOptions` 개체에서 `TokenValidationParameters` 개체를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4e85-215">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f4e85-216">추가 자료</span><span class="sxs-lookup"><span data-stu-id="f4e85-216">Additional resources</span></span>

- <span data-ttu-id="f4e85-217">**애플리케이션 간 쿠키 공유하기** </span><span class="sxs-lookup"><span data-stu-id="f4e85-217">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="f4e85-218">**ID 소개** </span><span class="sxs-lookup"><span data-stu-id="f4e85-218">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="f4e85-219">**Rick Anderson. SMS를 사용한 2단계 인증** </span><span class="sxs-lookup"><span data-stu-id="f4e85-219">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="f4e85-220">**Facebook, Google 및 기타 외부 공급 기업을 통해 인증 사용** </span><span class="sxs-lookup"><span data-stu-id="f4e85-220">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="f4e85-221">**Michell Anicas. OAuth 2 소개** </span><span class="sxs-lookup"><span data-stu-id="f4e85-221">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="f4e85-222">**AspNet.Security.OAuth.Providers**(ASP.NET OAuth 공급자를 위한 GitHub 리포지토리) </span><span class="sxs-lookup"><span data-stu-id="f4e85-222">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="f4e85-223">**Danny Strockis. ASP.NET Core 웹앱에 Azure AD 통합** </span><span class="sxs-lookup"><span data-stu-id="f4e85-223">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app** </span></span>\
  <https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/>

- <span data-ttu-id="f4e85-224">**IdentityServer4. 공식 설명서** </span><span class="sxs-lookup"><span data-stu-id="f4e85-224">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="f4e85-225">[이전](../implement-resilient-applications/monitor-app-health.md)
>[다음](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="f4e85-225">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
