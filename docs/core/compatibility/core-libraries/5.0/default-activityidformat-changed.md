---
title: '호환성이 손상되는 변경: 기본 ActivityIdFormat이 W3C임'
description: 기본 ActivityIdFormat이 W3C인 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: f15c2d61443117cfbcb2be7de9561fecbff9a1d9
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257507"
---
# <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="4ce80-103">기본 ActivityIdFormat이 W3C임</span><span class="sxs-lookup"><span data-stu-id="4ce80-103">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="4ce80-104">활동의 기본 식별자 형식(<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>)이 이제 <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-104">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="change-description"></a><span data-ttu-id="4ce80-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="4ce80-105">Change description</span></span>

<span data-ttu-id="4ce80-106">W3C 활동 ID 형식은 .NET Core 3.0에서 계층 구조 ID 형식의 대안으로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-106">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="4ce80-107">그러나 호환성을 유지하기 위해 W3C 형식은 .NET 5.0까지 기본값으로 지정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-107">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="4ce80-108">[W3C 형식이 비준되고](https://www.w3.org/TR/trace-context/) 여러 언어 구현에서 활발하게 추진되어 .NET 5에서 기본값이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-108">The default was changed in .NET 5 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="4ce80-109">앱이 .NET 5 이상이 아닌 플랫폼을 대상으로 하는 경우 <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>이 기본 형식인 이전 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-109">If your app targets a platform other than .NET 5 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="4ce80-110">이 기본값은 net45 이상, netstandard1.1 이상, netcoreapp(1.x, 2.x, 3.x) 플랫폼에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-110">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="4ce80-111">.NET 5 이상에서는 <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>이 <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-111">In .NET 5 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4ce80-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="4ce80-112">Version introduced</span></span>

<span data-ttu-id="4ce80-113">5.0</span><span class="sxs-lookup"><span data-stu-id="4ce80-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4ce80-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="4ce80-114">Recommended action</span></span>

<span data-ttu-id="4ce80-115">애플리케이션이 분산 추적에 사용되는 식별자와 관련이 없는 경우 아무 동작도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-115">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="4ce80-116">ASP.NET Core 및 <xref:System.Net.Http.HttpClient>와 같은 라이브러리는 <xref:System.Diagnostics.ActivityIdFormat>의 두 버전을 모두 사용하거나 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-116">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="4ce80-117">기존 시스템과의 상호 운용성이 필요하거나 현재 시스템이 식별자 형식을 사용하는 경우 <xref:System.Diagnostics.Activity.DefaultIdFormat>을 <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>으로 설정하여 이전 동작을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-117">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4ce80-118">또는 다음 세 가지 방법 중 하나로 AppContext 스위치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-118">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="4ce80-119">프로젝트 파일에서</span><span class="sxs-lookup"><span data-stu-id="4ce80-119">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="4ce80-120">*runtimeconfig.json* 파일에서</span><span class="sxs-lookup"><span data-stu-id="4ce80-120">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="4ce80-121">환경 변수를 통해</span><span class="sxs-lookup"><span data-stu-id="4ce80-121">Through an environment variable.</span></span>

  <span data-ttu-id="4ce80-122">`DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL`을 `true` 또는 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ce80-122">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4ce80-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4ce80-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
