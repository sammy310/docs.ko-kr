---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74101235"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="6a512-101">권한 부여: AddAuthorization 오버로드가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="6a512-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="6a512-102">`Microsoft.AspNetCore.Authorization`에 상주하는 데 사용되는 핵심 `AddAuthorization` 메서드가 `AddAuthorizationCore`로 이름이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="6a512-103">이전 `AddAuthorization` 메서드는 여전히 존재하지만, 대신 `Microsoft.AspNetCore.Authorization.Policy` 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="6a512-104">두 방법을 모두 사용하는 앱은 영향을 받지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="6a512-105">[공유 프레임워크에서 설명한 대로 `Microsoft.AspNetCore.Authorization.Policy`은(는) 독립 실행형 패키지가 아닌 공유 프레임워크에 제공됩니다. Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)에서 제거된 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="6a512-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6a512-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6a512-106">Version introduced</span></span>

<span data-ttu-id="6a512-107">3.0</span><span class="sxs-lookup"><span data-stu-id="6a512-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6a512-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6a512-108">Old behavior</span></span>
<span data-ttu-id="6a512-109">`AddAuthorization` 메서드가 `Microsoft.AspNetCore.Authorization`에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6a512-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="6a512-110">New behavior</span></span>

<span data-ttu-id="6a512-111">`AddAuthorization` 메서드가 `Microsoft.AspNetCore.Authorization.Policy`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="6a512-112">`AddAuthorizationCore`는 이전 메서드의 새 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6a512-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6a512-113">Reason for change</span></span>

<span data-ttu-id="6a512-114">`AddAuthorization`는 권한 부여에 필요한 모든 일반 서비스를 추가하는 데 더 나은 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6a512-115">권장 작업</span><span class="sxs-lookup"><span data-stu-id="6a512-115">Recommended action</span></span>

<span data-ttu-id="6a512-116">`Microsoft.AspNetCore.Authorization.Policy`에 대한 참조를 추가하거나 대신 `AddAuthorizationCore`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a512-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="6a512-117">범주</span><span class="sxs-lookup"><span data-stu-id="6a512-117">Category</span></span>

<span data-ttu-id="6a512-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6a512-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a512-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6a512-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
