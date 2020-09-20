---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656346"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="94143-101">WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함</span><span class="sxs-lookup"><span data-stu-id="94143-101">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="94143-102">Windows Forms 앱과 WPF(Windows Presentation Framework) 앱은 이제 .NET Core WinForms 및 WPF SDK(`Microsoft.NET.Sdk.WindowsDesktop`) 대신 .NET SDK(`Microsoft.NET.Sdk`)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94143-102">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

#### <a name="change-description"></a><span data-ttu-id="94143-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="94143-103">Change description</span></span>

<span data-ttu-id="94143-104">이전 .NET Core 버전에서는 WinForms 앱과 WPF 앱이 별도의 [프로젝트 SDK](../../../../docs/core/project-sdk/overview.md)(`Microsoft.NET.Sdk.WindowsDesktop`)를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="94143-104">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="94143-105">.NET 5.0부터 WinForms 및 WPF SDK는 .NET SDK(`Microsoft.NET.Sdk`)와 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94143-105">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="94143-106">또한 .NET 5에서 새 [TFM(대상 프레임워크 모니커)](../../../../docs/standard/frameworks.md)이 `netcoreapp` 및 `netstandard`를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="94143-106">In addition, new [target framework monikers (TFM)](../../../../docs/standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="94143-107">다음 예제에서는 .NET 5.0 이상으로 대상을 변경할 때 WPF 프로젝트 파일에 수행해야 하는 변경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94143-107">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="94143-108">이전 .NET Core 버전:</span><span class="sxs-lookup"><span data-stu-id="94143-108">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="94143-109">.NET 5.0 이상 버전:</span><span class="sxs-lookup"><span data-stu-id="94143-109">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a><span data-ttu-id="94143-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="94143-110">Version introduced</span></span>

<span data-ttu-id="94143-111">.NET 5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="94143-111">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="94143-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="94143-112">Recommended action</span></span>

<span data-ttu-id="94143-113">WPF 또는 Windows Forms 프로젝트 파일에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="94143-113">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="94143-114">`Sdk` 특성을 `Microsoft.NET.Sdk`로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="94143-114">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="94143-115">`TargetFramework` 속성을 `net5.0-windows`로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="94143-115">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

#### <a name="category"></a><span data-ttu-id="94143-116">범주</span><span class="sxs-lookup"><span data-stu-id="94143-116">Category</span></span>

- <span data-ttu-id="94143-117">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94143-117">Windows Forms</span></span>
- <span data-ttu-id="94143-118">WPF(Windows Presentation Framework)</span><span class="sxs-lookup"><span data-stu-id="94143-118">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="94143-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="94143-119">Affected APIs</span></span>

<span data-ttu-id="94143-120">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94143-120">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
