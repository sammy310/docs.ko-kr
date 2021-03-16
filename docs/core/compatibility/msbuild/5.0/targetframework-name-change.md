---
title: '호환성이 손상되는 변경: netcoreapp에서 net으로 TargetFramework 변경'
description: MSBuild TargetFramework 속성의 값이 netcoreapp3.1에서 net5.0으로 변경된 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/17/2020
ms.openlocfilehash: 88bfe7602c83f61b56f11c4e0336702571369e3c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256493"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="01c62-103">netcoreapp에서 net으로 TargetFramework 변경</span><span class="sxs-lookup"><span data-stu-id="01c62-103">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="01c62-104">MSBuild `TargetFramework` 속성 값이 `netcoreapp3.1`에서 `net5.0`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-104">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="01c62-105">이로 인해 `TargetFramework`의 값을 구문 분석하는 데 필요한 코드가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-105">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="01c62-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="01c62-106">Version introduced</span></span>

<span data-ttu-id="01c62-107">5.0</span><span class="sxs-lookup"><span data-stu-id="01c62-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="01c62-108">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="01c62-108">Change description</span></span>

<span data-ttu-id="01c62-109">.NET Core 1.0 - 3.1에서 MSBuild `TargetFramework` 속성 값은 `netcoreapp`으로 시작합니다(예: .NET Core 3.1을 대상으로 하는 앱의 경우 `netcoreapp3.1`).</span><span class="sxs-lookup"><span data-stu-id="01c62-109">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="01c62-110">.NET 5부터 해당 값은 `net`으로만 시작하도록 단순화됩니다(예: .NET 5.0의 경우 `net5.0`).</span><span class="sxs-lookup"><span data-stu-id="01c62-110">Starting in .NET 5, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="01c62-111">자세한 내용은 [.NET Standard의 미래 ](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) 및 [.NET 5의 대상 프레임워크 이름](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01c62-111">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="01c62-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="01c62-112">Reason for change</span></span>

- <span data-ttu-id="01c62-113">`TargetFramework` 값을 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-113">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="01c62-114">프로젝트가 `TargetFramework` 특성에 `TargetPlatform`을 포함할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-114">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="01c62-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="01c62-115">Recommended action</span></span>

<span data-ttu-id="01c62-116">`TargetFramework`의 값을 구문 분석하는 논리가 있는 경우 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-116">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="01c62-117">예를 들어 다음 MSBuild 조건은 `TargetFramework` 값에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-117">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="01c62-118">이 요구 사항에 대해 대상 프레임워크 식별자를 비교하기 위해 코드를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01c62-118">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a><span data-ttu-id="01c62-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="01c62-119">Affected APIs</span></span>

<span data-ttu-id="01c62-120">N/A</span><span class="sxs-lookup"><span data-stu-id="01c62-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
