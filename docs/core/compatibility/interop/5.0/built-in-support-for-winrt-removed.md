---
title: '호환성이 손상되는 변경: WinRT의 기본 제공 지원이 .NET에서 제거됨'
description: WinRT의 기본 제공 지원이 .NET에서 제거되는 .NET 5의 interop 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/13/2020
ms.openlocfilehash: 986b810b74c7e7d7514ec2b734bfab45e29b87fa
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256688"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="73b68-103">WinRT의 기본 제공 지원이 .NET에서 제거됨</span><span class="sxs-lookup"><span data-stu-id="73b68-103">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="73b68-104">.NET에서 [WinRT(Windows 런타임)](/uwp/winrt-cref/winrt-type-system) API 사용을 위한 기본 제공 지원이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-104">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="73b68-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="73b68-105">Version introduced</span></span>

<span data-ttu-id="73b68-106">5.0</span><span class="sxs-lookup"><span data-stu-id="73b68-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="73b68-107">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="73b68-107">Change description</span></span>

<span data-ttu-id="73b68-108">이전에는 CoreCLR이 [WinMD(Windows 메타데이터) 파일](/uwp/winrt-cref/winmd-files)을 사용하여 WinRT 형식을 활성화하고 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-108">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="73b68-109">.NET 5부터 CoreCLR은 더 이상 WinMD 파일을 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-109">Starting in .NET 5, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="73b68-110">지원되지 않는 어셈블리를 참조하려고 하면 <xref:System.IO.FileNotFoundException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-110">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="73b68-111">WinRT 클래스를 활성화하는 경우 <xref:System.PlatformNotSupportedException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-111">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="73b68-112">이 호환성이 손상되는 변경은 다음과 같은 이유로 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-112">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="73b68-113">WinRT를 .NET 런타임과 별도로 개발하고 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-113">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="73b68-114">iOS, Android 등의 다른 운영 체제용으로 제공되는 interop 시스템과의 대칭을 이룰 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-114">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="73b68-115">C# 기능, IL(중간 언어) 연결 및 AOT(Ahead-Of-Time) 컴파일과 같은 다른 .NET 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-115">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="73b68-116">.NET 런타임 코드베이스를 간소화하기 위해서입니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-116">To simplify the .NET runtime codebase.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="73b68-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="73b68-117">Recommended action</span></span>

- <span data-ttu-id="73b68-118">[Microsoft.Windows.SDK.Contracts 패키지](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts)에 대한 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-118">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span></span>  <span data-ttu-id="73b68-119">대신 프로젝트의 `TargetFramework` 속성을 통해 액세스하려는 Windows API의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-119">Instead, specify the version of the Windows APIs that you want to access via the `TargetFramework` property of the project.</span></span>  <span data-ttu-id="73b68-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-120">For example:</span></span>

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- <span data-ttu-id="73b68-121">[C#/WinRT](/windows/uwp/csharp-winrt/) 도구 체인을 사용하여 .NET 5 이상 버전용 WinRT API 및 형식을 생성하거나 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="73b68-121">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types for .NET 5 and later versions.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="73b68-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="73b68-122">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
