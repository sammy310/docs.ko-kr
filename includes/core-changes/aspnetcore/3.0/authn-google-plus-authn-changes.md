---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032452"
---
### <a name="authentication-google-deprecated-and-replaced"></a><span data-ttu-id="85ede-101">인증: Google+가 더 이상 사용되지 않고 대체됨</span><span class="sxs-lookup"><span data-stu-id="85ede-101">Authentication: Google+ deprecated and replaced</span></span>

<span data-ttu-id="85ede-102">Google은 2019년 1월 28일부터 앱에 대한 Google+ 로그인을 [종료](https://developers.google.com/+/api-shutdown)하기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-102">Google is starting to [shut down](https://developers.google.com/+/api-shutdown) Google+ Sign-in for apps as early as January 28, 2019.</span></span>

#### <a name="change-description"></a><span data-ttu-id="85ede-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="85ede-103">Change description</span></span>

<span data-ttu-id="85ede-104">ASP.NET 4.x 및 ASP.NET Core는 Google+ 로그인 API를 사용하여 웹앱에서 Google 계정 사용자를 인증하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-104">ASP.NET 4.x and ASP.NET Core have been using the Google+ Sign-in APIs to authenticate Google account users in web apps.</span></span> <span data-ttu-id="85ede-105">영향을 받는 NuGet 패키지는 [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/)이며 ASP.NET Web Forms 및 MVC가 있는 `Microsoft.Owin`의 경우 [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/)입니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-105">The affected NuGet packages are [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) for ASP.NET Core and [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) for `Microsoft.Owin` with ASP.NET Web Forms and MVC.</span></span>

<span data-ttu-id="85ede-106">Google의 대체 API는 다른 데이터 원본 및 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-106">Google's replacement APIs use a different data source and format.</span></span> <span data-ttu-id="85ede-107">아래에 제공된 완화 및 솔루션은 구조적 변경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-107">The mitigations and solutions provided below account for the structural changes.</span></span> <span data-ttu-id="85ede-108">앱은 데이터 자체가 여전히 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-108">Apps should verify the data itself still satisfies their requirements.</span></span> <span data-ttu-id="85ede-109">예를 들어 이름, 이메일 주소, 프로필 링크 및 프로필 사진은 이전과는 약간 다른 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-109">For example, names, email addresses, profile links, and profile photos may provide subtly different values than before.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="85ede-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="85ede-110">Version introduced</span></span>

<span data-ttu-id="85ede-111">모든 버전.</span><span class="sxs-lookup"><span data-stu-id="85ede-111">All versions.</span></span> <span data-ttu-id="85ede-112">이 변경 내용은 ASP.NET Core 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-112">This change is external to ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="85ede-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="85ede-113">Recommended action</span></span>

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a><span data-ttu-id="85ede-114">ASP.NET Web Forms 및 MVC를 사용한 Owin</span><span class="sxs-lookup"><span data-stu-id="85ede-114">Owin with ASP.NET Web Forms and MVC</span></span>

<span data-ttu-id="85ede-115">`Microsoft.Owin` 3.1.0 이상의 경우 임시 완화가 [여기에](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635) 간략하게 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-115">For `Microsoft.Owin` 3.1.0 and later, a temporary mitigation is outlined [here](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635).</span></span> <span data-ttu-id="85ede-116">앱은 데이터 형식의 변경 내용을 확인하기 위해 완화를 사용하여 테스트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-116">Apps should complete testing with the mitigation to check for changes in the data format.</span></span> <span data-ttu-id="85ede-117">수정 내용이 있는 `Microsoft.Owin` 4.0.1을 릴리스할 계획이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-117">There are plans to release `Microsoft.Owin` 4.0.1 with a fix.</span></span> <span data-ttu-id="85ede-118">이전 버전을 사용하는 앱은 버전 4.0.1로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-118">Apps using any prior version should update to version 4.0.1.</span></span>

##### <a name="aspnet-core-1x"></a><span data-ttu-id="85ede-119">ASP.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="85ede-119">ASP.NET Core 1.x</span></span>

<span data-ttu-id="85ede-120">[ASP.NET Web Forms 및 MVC를 사용한 Owin](#owin-with-aspnet-web-forms-and-mvc)의 완화를 ASP.NET Core 1.x에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-120">The mitigation in [Owin with ASP.NET Web Forms and MVC](#owin-with-aspnet-web-forms-and-mvc) can be adapted to ASP.NET Core 1.x.</span></span> <span data-ttu-id="85ede-121">1\.x가 [수명 종료](https://dotnet.microsoft.com/platform/support-policy) 상태에 도달했기 때문에 NuGet 패키지 패치가 계획되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-121">NuGet package patches aren't planned because 1.x has reached [end of life](https://dotnet.microsoft.com/platform/support-policy) status.</span></span>

##### <a name="aspnet-core-2x"></a><span data-ttu-id="85ede-122">ASP.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="85ede-122">ASP.NET Core 2.x</span></span>

<span data-ttu-id="85ede-123">`Microsoft.AspNetCore.Authentication.Google` 버전 2.x의 경우 `Startup.ConfigureServices`의 `AddGoogle`에 대한 기존 호출을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-123">For `Microsoft.AspNetCore.Authentication.Google` version 2.x, replace your existing call to `AddGoogle` in `Startup.ConfigureServices` with the following code:</span></span>

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

<span data-ttu-id="85ede-124">2월 2.1 및 2.2 패치는 이전의 재구성을 새 기본값으로 통합했습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-124">The February 2.1 and 2.2 patches incorporated the preceding reconfiguration as the new default.</span></span> <span data-ttu-id="85ede-125">[수명 종료](https://dotnet.microsoft.com/platform/support-policy)에 도달했기 때문에 ASP.NET Core 2.0의 패치가 계획되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-125">No patch is planned for ASP.NET Core 2.0 since it has reached [end of life](https://dotnet.microsoft.com/platform/support-policy).</span></span>

##### <a name="aspnet-core-30"></a><span data-ttu-id="85ede-126">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="85ede-126">ASP.NET Core 3.0</span></span>

<span data-ttu-id="85ede-127">ASP.NET Core 2.x에 제공된 완화는 ASP.NET Core 3.0에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-127">The mitigation given for ASP.NET Core 2.x can also be used for ASP.NET Core 3.0.</span></span> <span data-ttu-id="85ede-128">향후 3.0 미리 보기에서 `Microsoft.AspNetCore.Authentication.Google` 패키지가 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-128">In future 3.0 previews, the `Microsoft.AspNetCore.Authentication.Google` package may be removed.</span></span> <span data-ttu-id="85ede-129">사용자는 대신 `Microsoft.AspNetCore.Authentication.OpenIdConnect`로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-129">Users would be directed to `Microsoft.AspNetCore.Authentication.OpenIdConnect` instead.</span></span> <span data-ttu-id="85ede-130">다음 코드는 `Startup.ConfigureServices`에서 `AddGoogle`을 `AddOpenIdConnect`로 바꾸는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-130">The following code shows how to replace `AddGoogle` with `AddOpenIdConnect` in `Startup.ConfigureServices`.</span></span> <span data-ttu-id="85ede-131">이 대체 항목은 ASP.NET Core 2.0 이상에서 사용할 수 있으며, 필요에 따라 ASP.NET Core 1.x에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85ede-131">This replacement can be used with ASP.NET Core 2.0 and later and can be adapted for ASP.NET Core 1.x as needed.</span></span>

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a><span data-ttu-id="85ede-132">범주</span><span class="sxs-lookup"><span data-stu-id="85ede-132">Category</span></span>

<span data-ttu-id="85ede-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="85ede-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="85ede-134">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="85ede-134">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
