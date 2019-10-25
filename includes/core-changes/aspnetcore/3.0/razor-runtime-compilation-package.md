---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394147"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="1d15d-101">Razor: 런타임 컴파일이 패키지로 이동됨</span><span class="sxs-lookup"><span data-stu-id="1d15d-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="1d15d-102">Razor 뷰 및 Razor Pages의 런타임 컴파일을 지원하기 위해 별도의 패키지로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1d15d-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1d15d-103">Version introduced</span></span>

<span data-ttu-id="1d15d-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1d15d-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1d15d-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="1d15d-105">Old behavior</span></span>

<span data-ttu-id="1d15d-106">추가 패키지 없이 런타임 컴파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1d15d-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="1d15d-107">New behavior</span></span>

<span data-ttu-id="1d15d-108">기능이 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="1d15d-109">런타임 컴파일을 지원하기 위해 이전에 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`에서 다음 API를 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="1d15d-110">이제 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`를 통해 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="1d15d-111">또한 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="1d15d-112">파일 변경 시 재컴파일은 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지를 참조하여 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1d15d-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="1d15d-113">Reason for change</span></span>

<span data-ttu-id="1d15d-114">이 변경은 Roslyn에서 ASP.NET Core 공유 프레임워크 종속성을 제거하기 위해 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1d15d-115">권장 작업</span><span class="sxs-lookup"><span data-stu-id="1d15d-115">Recommended action</span></span>

<span data-ttu-id="1d15d-116">Razor 파일의 런타임 컴파일 또는 재컴파일이 필요한 앱은 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="1d15d-117">`Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="1d15d-118">`AddMvcRazorRuntimeCompilation`에 대한 호출을 포함하도록 프로젝트의 `Startup.ConfigureServices` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="1d15d-119">예를 들어 `Startup.ConfigureServices`에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d15d-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="1d15d-120">범주</span><span class="sxs-lookup"><span data-stu-id="1d15d-120">Category</span></span>

<span data-ttu-id="1d15d-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1d15d-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1d15d-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1d15d-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
