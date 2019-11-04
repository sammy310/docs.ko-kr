---
ms.openlocfilehash: 4dcb357570cb6597fde86c9e8f2acb74364cfaa3
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198506"
---
### <a name="session-state-obsolete-apis-removed"></a><span data-ttu-id="2924b-101">세션 상태: 사용되지 않는 API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="2924b-101">Session state: Obsolete APIs removed</span></span>

<span data-ttu-id="2924b-102">세션 쿠키를 구성하는 데 사용되지 않는 API가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2924b-102">Obsolete APIs for configuring session cookies were removed.</span></span> <span data-ttu-id="2924b-103">자세한 내용은 [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2924b-103">For more information, see [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2924b-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2924b-104">Version introduced</span></span>

<span data-ttu-id="2924b-105">3.0</span><span class="sxs-lookup"><span data-stu-id="2924b-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2924b-106">변경 이유</span><span class="sxs-lookup"><span data-stu-id="2924b-106">Reason for change</span></span>

<span data-ttu-id="2924b-107">이 변경 내용은 쿠키를 사용하는 기능을 구성하기 위해 API 간에 일관성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="2924b-107">This change enforces consistency across APIs for configuring features that use cookies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2924b-108">권장 작업</span><span class="sxs-lookup"><span data-stu-id="2924b-108">Recommended action</span></span>

<span data-ttu-id="2924b-109">제거된 API의 사용을 새 대체 항목으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2924b-109">Migrate usage of the removed APIs to their newer replacements.</span></span> <span data-ttu-id="2924b-110">`Startup.ConfigureServices`에서 다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2924b-110">Consider the following example in `Startup.ConfigureServices`:</span></span>

```csharp
public void ConfigureServices(ServiceCollection services)
{
    services.AddSession(options =>
    {
        // Removed obsolete APIs
        options.CookieName = "SessionCookie";
        options.CookieDomain = "contoso.com";
        options.CookiePath = "/";
        options.CookieHttpOnly = true;
        options.CookieSecure = CookieSecurePolicy.Always;

        // new API
        options.Cookie.Name = "SessionCookie";
        options.Cookie.Domain = "contoso.com";
        options.Cookie.Path = "/";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
    });
}
```

#### <a name="category"></a><span data-ttu-id="2924b-111">범주</span><span class="sxs-lookup"><span data-stu-id="2924b-111">Category</span></span>

<span data-ttu-id="2924b-112">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2924b-112">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2924b-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2924b-113">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieName?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure?displayProperty=fullName>

<!-- 

#### Affected APIs

- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieName`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure`

-->
