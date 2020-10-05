---
ms.openlocfilehash: a9545c66d3873b5114fe66e13c77ddc28e20020e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077607"
---
### <a name="blazor-protectedbrowserstorage-feature-moved-to-shared-framework"></a><span data-ttu-id="6be94-101">Blazor: ProtectedBrowserStorage 기능을 공유 프레임워크로 이동함</span><span class="sxs-lookup"><span data-stu-id="6be94-101">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>

<span data-ttu-id="6be94-102">ASP.NET Core 5.0 RC2 릴리스의 일부로 `ProtectedBrowserStorage` 기능을 ASP.NET Core 공유 프레임워크로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-102">As part of the ASP.NET Core 5.0 RC2 release, the `ProtectedBrowserStorage` feature moved to the ASP.NET Core shared framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6be94-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6be94-103">Version introduced</span></span>

<span data-ttu-id="6be94-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="6be94-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6be94-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6be94-105">Old behavior</span></span>

<span data-ttu-id="6be94-106">ASP.NET Core 5.0 Preview 8에서 이 기능은 [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) 패키지의 일부로 사용할 수 있지만 Blazor WebAssembly에서만 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-106">In ASP.NET Core 5.0 Preview 8, the feature is available as a part of the [Microsoft.AspNetCore.Components.Web.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web.Extensions) package but was only usable in Blazor WebAssembly.</span></span>

<span data-ttu-id="6be94-107">ASP.NET Core 5.0 RC1에서는 이 기능을 `Microsoft.AspNetCore.App` 공유 프레임워크를 참조하는 [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) 패키지의 일부로 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-107">In ASP.NET Core 5.0 RC1, the feature is available as part of the [Microsoft.AspNetCore.Components.ProtectedBrowserStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.ProtectedBrowserStorage) package, which references the `Microsoft.AspNetCore.App` shared framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6be94-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="6be94-108">New behavior</span></span>

<span data-ttu-id="6be94-109">ASP.NET Core 5.0 RC2에서는 이 기능을 참조하고 사용하는 데 NuGet 패키지 참조가 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-109">In ASP.NET Core 5.0 RC2, a NuGet package reference is no longer needed to reference and use the feature.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6be94-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6be94-110">Reason for change</span></span>

<span data-ttu-id="6be94-111">고객에게 공유 프레임워크로의 이동이 필요한 사용자 환경에 더욱 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-111">The move to the shared framework is a better fit for the user experience customers expect.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6be94-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6be94-112">Recommended action</span></span>

<span data-ttu-id="6be94-113">ASP.NET Core 5.0 RC1에서 업그레이드하는 경우 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="6be94-113">If upgrading from ASP.NET Core 5.0 RC1, complete the following steps:</span></span>

1. <span data-ttu-id="6be94-114">프로젝트에서 `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` 패키지 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-114">Remove the `Microsoft.AspNetCore.Components.ProtectedBrowserStorage` package reference from the project.</span></span>
1. <span data-ttu-id="6be94-115">`using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;`을 `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-115">Replace `using Microsoft.AspNetCore.Components.ProtectedBrowserStorage;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="6be94-116">`Startup` 클래스에서 `AddProtectedBrowserStorage`에 대한 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-116">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

<span data-ttu-id="6be94-117">ASP.NET Core 5.0 Preview 8에서 업그레이드하는 경우 다음 단계를 완료하세요.</span><span class="sxs-lookup"><span data-stu-id="6be94-117">If upgrading from ASP.NET Core 5.0 Preview 8, complete the following steps:</span></span>

1. <span data-ttu-id="6be94-118">프로젝트에서 `Microsoft.AspNetCore.Components.Web.Extensions` 패키지 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-118">Remove the `Microsoft.AspNetCore.Components.Web.Extensions` package reference from the project.</span></span>
1. <span data-ttu-id="6be94-119">`using Microsoft.AspNetCore.Components.Web.Extensions;`을 `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-119">Replace `using Microsoft.AspNetCore.Components.Web.Extensions;` with `using Microsoft.AspNetCore.Components.Server.ProtectedBrowserStorage;`.</span></span>
1. <span data-ttu-id="6be94-120">`Startup` 클래스에서 `AddProtectedBrowserStorage`에 대한 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6be94-120">Remove the call to `AddProtectedBrowserStorage` from your `Startup` class.</span></span>

#### <a name="category"></a><span data-ttu-id="6be94-121">범주</span><span class="sxs-lookup"><span data-stu-id="6be94-121">Category</span></span>

<span data-ttu-id="6be94-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6be94-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6be94-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6be94-123">Affected APIs</span></span>

<span data-ttu-id="6be94-124">없음</span><span class="sxs-lookup"><span data-stu-id="6be94-124">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
