---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344300"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="767f1-101">Razor: 런타임 컴파일이 패키지로 이동됨</span><span class="sxs-lookup"><span data-stu-id="767f1-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="767f1-102">Razor 뷰 및 Razor Pages의 런타임 컴파일을 지원하기 위해 별도의 패키지로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="767f1-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="767f1-103">Version introduced</span></span>

<span data-ttu-id="767f1-104">3.0</span><span class="sxs-lookup"><span data-stu-id="767f1-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="767f1-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="767f1-105">Old behavior</span></span>

<span data-ttu-id="767f1-106">추가 패키지 없이 런타임 컴파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="767f1-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="767f1-107">New behavior</span></span>

<span data-ttu-id="767f1-108">이 기능은 [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) 패키지로 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="767f1-109">런타임 컴파일을 지원하기 위해 이전에 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`에서 다음 API를 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="767f1-110">이제 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`를 통해 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="767f1-111">`RazorViewEngineOptions.FileProviders`는 이제 `MvcRazorRuntimeCompilationOptions.FileProviders`입니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="767f1-112">`RazorViewEngineOptions.AdditionalCompilationReferences`는 이제 `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`입니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="767f1-113">또한 `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="767f1-114">파일 변경 시 재컴파일은 `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지를 참조하여 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="767f1-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="767f1-115">Reason for change</span></span>

<span data-ttu-id="767f1-116">이 변경은 Roslyn에서 ASP.NET Core 공유 프레임워크 종속성을 제거하기 위해 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="767f1-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="767f1-117">Recommended action</span></span>

<span data-ttu-id="767f1-118">Razor 파일의 런타임 컴파일 또는 재컴파일이 필요한 앱은 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="767f1-119">`Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` 패키지에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="767f1-120">`AddRazorRuntimeCompilation`에 대한 호출을 포함하도록 프로젝트의 `Startup.ConfigureServices` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="767f1-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="767f1-121">예:</span><span class="sxs-lookup"><span data-stu-id="767f1-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="767f1-122">범주</span><span class="sxs-lookup"><span data-stu-id="767f1-122">Category</span></span>

<span data-ttu-id="767f1-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="767f1-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="767f1-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="767f1-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
