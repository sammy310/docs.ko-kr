---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393965"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a><span data-ttu-id="51278-101">ID: UI의 기본 부트스트랩 버전이 변경됨</span><span class="sxs-lookup"><span data-stu-id="51278-101">Identity: Default Bootstrap version of UI changed</span></span>

<span data-ttu-id="51278-102">ASP.NET Core 3.0부터 ID UI는 기본적으로 부트스트랩 버전 4를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51278-102">Starting in ASP.NET Core 3.0, Identity UI defaults to using version 4 of Bootstrap.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="51278-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="51278-103">Version introduced</span></span>

<span data-ttu-id="51278-104">3.0</span><span class="sxs-lookup"><span data-stu-id="51278-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="51278-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="51278-105">Old behavior</span></span>

<span data-ttu-id="51278-106">`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` 메서드 호출은 `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`와 동일했습니다.</span><span class="sxs-lookup"><span data-stu-id="51278-106">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call was the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="51278-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="51278-107">New behavior</span></span>

<span data-ttu-id="51278-108">`services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` 메서드 호출은 `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="51278-108">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call is the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="51278-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="51278-109">Reason for change</span></span>

<span data-ttu-id="51278-110">부트스트랩 4는 ASP.NET Core 3.0 기간 동안 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51278-110">Bootstrap 4 was released during ASP.NET Core 3.0 timeframe.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="51278-111">권장 작업</span><span class="sxs-lookup"><span data-stu-id="51278-111">Recommended action</span></span>

<span data-ttu-id="51278-112">기본 ID UI를 사용하고 다음 예제와 같이 `Startup.ConfigureServices`에 추가한 경우 이 변경 내용의 영향을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51278-112">You're impacted by this change if you use the default Identity UI and have added it in `Startup.ConfigureServices` as shown in the following example:</span></span>

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

<span data-ttu-id="51278-113">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="51278-113">Take one of the following actions:</span></span>

- <span data-ttu-id="51278-114">[마이그레이션 가이드](https://getbootstrap.com/docs/4.0/migration)를 사용하여 부트스트랩 4를 사용하도록 앱을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="51278-114">Migrate your app to use Bootstrap 4 using their [migration guide](https://getbootstrap.com/docs/4.0/migration).</span></span>
- <span data-ttu-id="51278-115">부트스트랩 3의 사용을 적용하도록 `Startup.ConfigureServices`를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="51278-115">Update `Startup.ConfigureServices` to enforce usage of Bootstrap 3.</span></span> <span data-ttu-id="51278-116">예:</span><span class="sxs-lookup"><span data-stu-id="51278-116">For example:</span></span>

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a><span data-ttu-id="51278-117">범주</span><span class="sxs-lookup"><span data-stu-id="51278-117">Category</span></span>

<span data-ttu-id="51278-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="51278-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="51278-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="51278-119">Affected APIs</span></span>

<span data-ttu-id="51278-120">없음</span><span class="sxs-lookup"><span data-stu-id="51278-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
