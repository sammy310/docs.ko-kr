---
ms.openlocfilehash: d75dc2caa3a002b9d34ac74f2c5c5e192281c0df
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281308"
---
### <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="39d9b-101">기본 ActivityIdFormat이 W3C임</span><span class="sxs-lookup"><span data-stu-id="39d9b-101">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="39d9b-102">활동의 기본 식별자 형식(<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>)이 이제 <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-102">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="39d9b-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="39d9b-103">Change description</span></span>

<span data-ttu-id="39d9b-104">W3C 활동 ID 형식은 .NET Core 3.0에서 계층 구조 ID 형식의 대안으로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-104">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="39d9b-105">그러나 호환성을 유지하기 위해 W3C 형식은 .NET 5.0까지 기본값으로 지정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-105">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="39d9b-106">[W3C 형식이 비준되고](https://www.w3.org/TR/trace-context/) 여러 언어 구현에서 활발하게 추진되어 .NET 5.0에서 기본값이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-106">The default was changed in .NET 5.0 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="39d9b-107">앱이 .NET 5.0 이상이 아닌 플랫폼을 대상으로 하는 경우 <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>이 기본 형식인 이전 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-107">If your app targets a platform other than .NET 5.0 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="39d9b-108">이 기본값은 net45 이상, netstandard1.1 이상, netcoreapp(1.x, 2.x, 3.x) 플랫폼에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-108">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="39d9b-109">.NET 5.0 이상에서는 <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>이 <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-109">In .NET 5.0 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="39d9b-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="39d9b-110">Version introduced</span></span>

<span data-ttu-id="39d9b-111">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="39d9b-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="39d9b-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="39d9b-112">Recommended action</span></span>

<span data-ttu-id="39d9b-113">애플리케이션이 분산 추적에 사용되는 식별자와 관련이 없는 경우 아무 동작도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-113">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="39d9b-114">ASP.NET Core 및 <xref:System.Net.Http.HttpClient>와 같은 라이브러리는 <xref:System.Diagnostics.ActivityIdFormat>의 두 버전을 모두 사용하거나 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-114">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="39d9b-115">기존 시스템과의 상호 운용성이 필요하거나 현재 시스템이 식별자 형식을 사용하는 경우 <xref:System.Diagnostics.Activity.DefaultIdFormat>을 <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>으로 설정하여 이전 동작을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-115">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="39d9b-116">또는 다음 세 가지 방법 중 하나로 AppContext 스위치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-116">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="39d9b-117">프로젝트 파일에서</span><span class="sxs-lookup"><span data-stu-id="39d9b-117">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="39d9b-118">*runtimeconfig.json* 파일에서</span><span class="sxs-lookup"><span data-stu-id="39d9b-118">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="39d9b-119">환경 변수를 통해</span><span class="sxs-lookup"><span data-stu-id="39d9b-119">Through an environment variable.</span></span>

  <span data-ttu-id="39d9b-120">`DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL`을 `true` 또는 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39d9b-120">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

#### <a name="category"></a><span data-ttu-id="39d9b-121">범주</span><span class="sxs-lookup"><span data-stu-id="39d9b-121">Category</span></span>

<span data-ttu-id="39d9b-122">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="39d9b-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="39d9b-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="39d9b-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
