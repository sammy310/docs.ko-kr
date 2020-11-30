---
ms.openlocfilehash: 9bdfcca2fd03e24a636be3340f5057dc3f39358e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032490"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="1a8f8-101">인증: Newtonsoft.json 형식이 대체됨</span><span class="sxs-lookup"><span data-stu-id="1a8f8-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="1a8f8-102">ASP.NET Core 3.0에서는 인증 API에 사용된 `Newtonsoft.Json` 형식이 `System.Text.Json` 형식으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="1a8f8-103">다음 경우를 제외하고 인증 패키지의 기본 사용량은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="1a8f8-104">OAuth 공급자에서 파생된 클래스(예: [aspnet-contribaspnet](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers)의 클래스)입니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="1a8f8-105">고급 클레임 조작 구현.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="1a8f8-106">자세한 내용은 [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-106">For more information, see [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105).</span></span> <span data-ttu-id="1a8f8-107">토론은 [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-107">For discussion, see [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1a8f8-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1a8f8-108">Version introduced</span></span>

<span data-ttu-id="1a8f8-109">3.0</span><span class="sxs-lookup"><span data-stu-id="1a8f8-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1a8f8-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="1a8f8-110">Recommended action</span></span>

<span data-ttu-id="1a8f8-111">파생 OAuth 구현의 경우 가장 일반적인 변경 내용은 [여기에](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) 표시된 것처럼 `CreateTicketAsync` 재정의에서 `JObject.Parse`를 `JsonDocument.Parse`로 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="1a8f8-112">`JsonDocument`는 `IDisposable`를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="1a8f8-113">다음 목록에서는 알려진 변경 내용을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="1a8f8-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType>은 `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="1a8f8-115">`ClaimAction`의 모든 파생 구현은 이와 유사하게 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="1a8f8-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType>은 `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="1a8f8-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType>은 `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="1a8f8-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext>에는 하나의 이전 생성자를 제거했으며 다른 생성자는 `JObject`를 `JsonElement`로 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="1a8f8-119">`User` 속성과 `RunClaimActions` 메서드가 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="1a8f8-120">이제 <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)>는 `JObject` 대신 `JsonDocument` 형식의 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="1a8f8-121">`Response` 속성이 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="1a8f8-122">이제 `OAuthTokenResponse`는 삭제 가능하며 `OAuthHandler`에 의해 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="1a8f8-123">`ExchangeCodeAsync`를 재정의하는 파생 OAuth 구현은 `JsonDocument` 또는 `OAuthTokenResponse`를 삭제할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="1a8f8-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType>이 `JObject`에서 `JsonDocument`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="1a8f8-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType>이 `JObject`에서 `JsonElement`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="1a8f8-126">[TwitterHandler.CreateTicketAsync(ClaimsIdentity,AuthenticationProperties,AccessToken,JObject)](/dotnet/api/microsoft.aspnetcore.authentication.twitter.twitterhandler.createticketasync?view=aspnetcore-2.2#Microsoft_AspNetCore_Authentication_Twitter_TwitterHandler_CreateTicketAsync_System_Security_Claims_ClaimsIdentity_Microsoft_AspNetCore_Authentication_AuthenticationProperties_Microsoft_AspNetCore_Authentication_Twitter_AccessToken_Newtonsoft_Json_Linq_JObject_)의 마지막 매개 변수가 `JObject`에서 `JsonElement`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-126">The last parameter of [TwitterHandler.CreateTicketAsync(ClaimsIdentity,AuthenticationProperties,AccessToken,JObject)](/dotnet/api/microsoft.aspnetcore.authentication.twitter.twitterhandler.createticketasync?view=aspnetcore-2.2#Microsoft_AspNetCore_Authentication_Twitter_TwitterHandler_CreateTicketAsync_System_Security_Claims_ClaimsIdentity_Microsoft_AspNetCore_Authentication_AuthenticationProperties_Microsoft_AspNetCore_Authentication_Twitter_AccessToken_Newtonsoft_Json_Linq_JObject_) changed from `JObject` to `JsonElement`.</span></span> <span data-ttu-id="1a8f8-127">대체 메서드는 <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,System.Text.Json.JsonElement)?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="1a8f8-127">The replacement method is <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,System.Text.Json.JsonElement)?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="1a8f8-128">범주</span><span class="sxs-lookup"><span data-stu-id="1a8f8-128">Category</span></span>

<span data-ttu-id="1a8f8-129">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1a8f8-129">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1a8f8-130">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1a8f8-130">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
