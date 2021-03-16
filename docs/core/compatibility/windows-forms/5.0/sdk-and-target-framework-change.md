---
title: '호환성이 손상되는 변경: WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함'
description: Windows Forms 및 Windows Presentation Framework 앱이 .NET Core WinForms 및 WPF SDK 대신 .NET SDK를 사용하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/18/2020
ms.openlocfilehash: 408233f6f8801fb3d4e53beab28c26a777a4a3e1
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256207"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="38db6-103">WinForms 및 WPF 앱이 Microsoft.NET.Sdk를 사용함</span><span class="sxs-lookup"><span data-stu-id="38db6-103">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="38db6-104">Windows Forms 앱과 WPF(Windows Presentation Framework) 앱은 이제 .NET Core WinForms 및 WPF SDK(`Microsoft.NET.Sdk.WindowsDesktop`) 대신 .NET SDK(`Microsoft.NET.Sdk`)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-104">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

## <a name="change-description"></a><span data-ttu-id="38db6-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="38db6-105">Change description</span></span>

<span data-ttu-id="38db6-106">이전 .NET Core 버전에서는 WinForms 앱과 WPF 앱이 별도의 [프로젝트 SDK](../../../project-sdk/overview.md)(`Microsoft.NET.Sdk.WindowsDesktop`)를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-106">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="38db6-107">.NET 5부터 WinForms 및 WPF SDK는 .NET SDK(`Microsoft.NET.Sdk`)와 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-107">Starting in .NET 5, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="38db6-108">또한 .NET 5에서 새 [TFM(대상 프레임워크 모니커)](../../../../standard/frameworks.md)이 `netcoreapp` 및 `netstandard`를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-108">In addition, new [target framework monikers (TFM)](../../../../standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="38db6-109">다음 예제에서는 .NET 5 이상으로 대상을 변경할 때 WPF 프로젝트 파일에서 변경할 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-109">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5 or later.</span></span>

<span data-ttu-id="38db6-110">이전 .NET Core 버전:</span><span class="sxs-lookup"><span data-stu-id="38db6-110">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="38db6-111">.NET 5 이상 버전:</span><span class="sxs-lookup"><span data-stu-id="38db6-111">In .NET 5 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a><span data-ttu-id="38db6-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="38db6-112">Version introduced</span></span>

<span data-ttu-id="38db6-113">.NET SDK 5.0.100</span><span class="sxs-lookup"><span data-stu-id="38db6-113">.NET SDK 5.0.100</span></span>

## <a name="recommended-action"></a><span data-ttu-id="38db6-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="38db6-114">Recommended action</span></span>

<span data-ttu-id="38db6-115">WPF 또는 Windows Forms 프로젝트 파일에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-115">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="38db6-116">`Sdk` 특성을 `Microsoft.NET.Sdk`로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-116">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="38db6-117">`TargetFramework` 속성을 `net5.0-windows`로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-117">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="38db6-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="38db6-118">Affected APIs</span></span>

<span data-ttu-id="38db6-119">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38db6-119">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
