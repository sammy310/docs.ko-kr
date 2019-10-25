---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394256"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="0fd0c-101">인증: Newtonsoft.json 형식이 대체됨</span><span class="sxs-lookup"><span data-stu-id="0fd0c-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="0fd0c-102">ASP.NET Core 3.0에서는 인증 API에 사용된 `Newtonsoft.Json` 형식이 `System.Text.Json` 형식으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="0fd0c-103">다음 경우를 제외하고 인증 패키지의 기본 사용량은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="0fd0c-104">OAuth 공급자에서 파생된 클래스(예: [aspnet-contribaspnet](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers)의 클래스)입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="0fd0c-105">고급 클레임 조작 구현.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="0fd0c-106">자세한 내용은 [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-106">For more information, see [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105).</span></span> <span data-ttu-id="0fd0c-107">자세한 내용은 [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-107">For discussion, see [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0fd0c-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0fd0c-108">Version introduced</span></span>

<span data-ttu-id="0fd0c-109">3.0</span><span class="sxs-lookup"><span data-stu-id="0fd0c-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0fd0c-110">권장 작업</span><span class="sxs-lookup"><span data-stu-id="0fd0c-110">Recommended action</span></span>

<span data-ttu-id="0fd0c-111">파생 OAuth 구현의 경우 가장 일반적인 변경 내용은 [여기에](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) 표시된 것처럼 `CreateTicketAsync` 재정의에서 `JObject.Parse`를 `JsonDocument.Parse`로 바꾸는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="0fd0c-112">`JsonDocument`는 `IDisposable`를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="0fd0c-113">다음 목록에서는 알려진 변경 내용을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="0fd0c-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType>은 `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="0fd0c-115">`ClaimAction`의 모든 파생 구현은 이와 유사하게 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="0fd0c-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType>는 `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="0fd0c-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType>는 `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="0fd0c-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext>에는 하나의 이전 생성자를 제거했으며 다른 생성자는 `JObject`를 `JsonElement`로 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="0fd0c-119">`User` 속성과 `RunClaimActions` 메서드가 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="0fd0c-120">이제 <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)>는 `JObject` 대신 `JsonDocument` 형식의 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="0fd0c-121">`Response` 속성이 일치하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="0fd0c-122">이제 `OAuthTokenResponse`는 삭제 가능하며 `OAuthHandler`에 의해 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="0fd0c-123">`ExchangeCodeAsync`를 재정의하는 파생 OAuth 구현은 `JsonDocument` 또는 `OAuthTokenResponse`를 삭제할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="0fd0c-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType>이 `JObject`에서 `JsonDocument`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="0fd0c-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType>이 `JObject`에서 `JsonElement`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="0fd0c-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType>가 `JObject` 수락에서 `JsonElement`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fd0c-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="0fd0c-127">범주</span><span class="sxs-lookup"><span data-stu-id="0fd0c-127">Category</span></span>

<span data-ttu-id="0fd0c-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0fd0c-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0fd0c-129">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0fd0c-129">Affected APIs</span></span>

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
