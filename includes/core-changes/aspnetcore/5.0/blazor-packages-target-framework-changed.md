---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416262"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="003aa-101">Blazor: NuGet 패키지의 대상 프레임워크가 변경됨</span><span class="sxs-lookup"><span data-stu-id="003aa-101">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="003aa-102">Blazor 3.2 WebAssembly 프로젝트는 .NET Standard 2.1(`<TargetFramework>netstandard2.1</TargetFramework>`)을 대상으로 컴파일되었습니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-102">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="003aa-103">ASP.NET Core 5.0에서는 Blazor Server 및 Blazor WebAssembly 프로젝트가 모두 .NET 5.0(`<TargetFramework>net5.0</TargetFramework>`)을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-103">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="003aa-104">대상 프레임워크 변경에 맞추기 위해 다음 Blazor 패키지는 더 이상 .NET Standard 2.1을 대상으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-104">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* [<span data-ttu-id="003aa-105">Microsoft.AspNetCore.Components</span><span class="sxs-lookup"><span data-stu-id="003aa-105">Microsoft.AspNetCore.Components</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [<span data-ttu-id="003aa-106">Microsoft.AspNetCore.Components.Authorization</span><span class="sxs-lookup"><span data-stu-id="003aa-106">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="003aa-107">Microsoft.AspNetCore.Components.Forms</span><span class="sxs-lookup"><span data-stu-id="003aa-107">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [<span data-ttu-id="003aa-108">Microsoft.AspNetCore.Components.Web</span><span class="sxs-lookup"><span data-stu-id="003aa-108">Microsoft.AspNetCore.Components.Web</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [<span data-ttu-id="003aa-109">Microsoft.AspNetCore.Components.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="003aa-109">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="003aa-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span><span class="sxs-lookup"><span data-stu-id="003aa-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="003aa-111">Microsoft.JSInterop</span><span class="sxs-lookup"><span data-stu-id="003aa-111">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="003aa-112">Microsoft.JSInterop.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="003aa-112">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="003aa-113">Microsoft.Authentication.WebAssembly.Msal</span><span class="sxs-lookup"><span data-stu-id="003aa-113">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="003aa-114">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="003aa-114">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="003aa-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="003aa-115">Version introduced</span></span>

<span data-ttu-id="003aa-116">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="003aa-116">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="003aa-117">이전 동작</span><span class="sxs-lookup"><span data-stu-id="003aa-117">Old behavior</span></span>

<span data-ttu-id="003aa-118">Blazor 3.1 및 3.2에서는 패키지가 .NET Standard 2.1 및 .NET Core 3.1을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-118">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="003aa-119">새 동작</span><span class="sxs-lookup"><span data-stu-id="003aa-119">New behavior</span></span>

<span data-ttu-id="003aa-120">ASP.NET Core 5.0에서는 패키지가 .NET 5.0을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-120">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="003aa-121">변경 이유</span><span class="sxs-lookup"><span data-stu-id="003aa-121">Reason for change</span></span>

<span data-ttu-id="003aa-122">.NET 대상 프레임워크 요구 사항에 맞게 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-122">The change was made to better align with .NET target framework requirements.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="003aa-123">권장 조치</span><span class="sxs-lookup"><span data-stu-id="003aa-123">Recommended action</span></span>

<span data-ttu-id="003aa-124">Blazor 3.2 WebAssembly 프로젝트는 패키지 참조를 5.x.x로 업데이트하는 과정의 일환으로 .NET 5.0을 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-124">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="003aa-125">해당 패키지 중 하나를 참조하는 라이브러리는 요구 사항에 따라 .NET 5.0을 대상으로 하거나 다중 대상을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="003aa-125">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

#### <a name="category"></a><span data-ttu-id="003aa-126">범주</span><span class="sxs-lookup"><span data-stu-id="003aa-126">Category</span></span>

<span data-ttu-id="003aa-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="003aa-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="003aa-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="003aa-128">Affected APIs</span></span>

<span data-ttu-id="003aa-129">없음</span><span class="sxs-lookup"><span data-stu-id="003aa-129">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
