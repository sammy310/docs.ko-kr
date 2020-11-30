---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032459"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a><span data-ttu-id="30b86-101">인증: OAuthHandler ExchangeCodeAsync 서명이 변경됨</span><span class="sxs-lookup"><span data-stu-id="30b86-101">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>

<span data-ttu-id="30b86-102">ASP.NET Core 3.0에서 `OAuthHandler.ExchangeCodeAsync`의 서명이 다음에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-102">In ASP.NET Core 3.0, the signature of `OAuthHandler.ExchangeCodeAsync` was changed from:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

<span data-ttu-id="30b86-103">대상:</span><span class="sxs-lookup"><span data-stu-id="30b86-103">To:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a><span data-ttu-id="30b86-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="30b86-104">Version introduced</span></span>

<span data-ttu-id="30b86-105">3.0</span><span class="sxs-lookup"><span data-stu-id="30b86-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="30b86-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="30b86-106">Old behavior</span></span>

<span data-ttu-id="30b86-107">`code` 및 `redirectUri` 문자열은 별도의 인수로 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-107">The `code` and `redirectUri` strings were passed as separate arguments.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="30b86-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="30b86-108">New behavior</span></span>

<span data-ttu-id="30b86-109">`Code` 및 `RedirectUri`는 `OAuthCodeExchangeContext` 생성자를 통해 설정할 수 있는 `OAuthCodeExchangeContext`의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-109">`Code` and `RedirectUri` are properties on `OAuthCodeExchangeContext` that can be set via the `OAuthCodeExchangeContext` constructor.</span></span> <span data-ttu-id="30b86-110">새 `OAuthCodeExchangeContext` 형식은 `OAuthHandler.ExchangeCodeAsync`에 전달된 유일한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-110">The new `OAuthCodeExchangeContext` type is the only argument passed to `OAuthHandler.ExchangeCodeAsync`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="30b86-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="30b86-111">Reason for change</span></span>

<span data-ttu-id="30b86-112">이러한 변경으로 인해 추가 매개 변수가 중단되지 않은 방식으로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-112">This change allows additional parameters to be provided in a non-breaking manner.</span></span> <span data-ttu-id="30b86-113">새 `ExchangeCodeAsync` 오버로드를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-113">There's no need to create new `ExchangeCodeAsync` overloads.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="30b86-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="30b86-114">Recommended action</span></span>

<span data-ttu-id="30b86-115">적절한 `code` 및 `redirectUri` 값을 사용하여 `OAuthCodeExchangeContext`를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-115">Construct an `OAuthCodeExchangeContext` with the appropriate `code` and `redirectUri` values.</span></span> <span data-ttu-id="30b86-116"><xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> 인스턴스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-116">An <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> instance must be provided.</span></span> <span data-ttu-id="30b86-117">이 단일 `OAuthCodeExchangeContext` 인스턴스는 여러 인수 대신 `OAuthHandler.ExchangeCodeAsync`에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30b86-117">This single `OAuthCodeExchangeContext` instance can be passed to `OAuthHandler.ExchangeCodeAsync` instead of multiple arguments.</span></span>

#### <a name="category"></a><span data-ttu-id="30b86-118">범주</span><span class="sxs-lookup"><span data-stu-id="30b86-118">Category</span></span>

<span data-ttu-id="30b86-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30b86-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="30b86-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="30b86-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
