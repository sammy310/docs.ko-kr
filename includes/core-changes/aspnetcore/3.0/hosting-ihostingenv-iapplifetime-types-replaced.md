---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394336"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a><span data-ttu-id="0e016-101">호스팅: IHostingEnvironment 및 IApplicationLifetime 형식이 사용되지 않는 것으로 표시되고 대체됨</span><span class="sxs-lookup"><span data-stu-id="0e016-101">Hosting: IHostingEnvironment and IApplicationLifetime types marked obsolete and replaced</span></span>

<span data-ttu-id="0e016-102">기존 `IHostingEnvironment` 및 `IApplicationLifetime` 형식을 대체하기 위해 새로운 형식이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-102">New types have been introduced to replace existing `IHostingEnvironment` and `IApplicationLifetime` types.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0e016-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0e016-103">Version introduced</span></span>

<span data-ttu-id="0e016-104">3.0</span><span class="sxs-lookup"><span data-stu-id="0e016-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0e016-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="0e016-105">Old behavior</span></span>

<span data-ttu-id="0e016-106">`Microsoft.Extensions.Hosting` 및 `Microsoft.AspNetCore.Hosting`과는 다른 두 가지(`IHostingEnvironment` 및 `IApplicationLifetime`) 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-106">There were two different `IHostingEnvironment` and `IApplicationLifetime` types from `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0e016-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="0e016-107">New behavior</span></span>

<span data-ttu-id="0e016-108">이전 형식은 사용되지 않음으로 표시되었으며 새 형식으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-108">The old types have been marked as obsolete and replaced with new types.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0e016-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0e016-109">Reason for change</span></span>

<span data-ttu-id="0e016-110">ASP.NET Core 2.1에 `Microsoft.Extensions.Hosting`이 도입되었을 때 `IHostingEnvironment` 및 `IApplicationLifetime`과 같은 일부 형식이 `Microsoft.AspNetCore.Hosting`에서 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-110">When `Microsoft.Extensions.Hosting` was introduced in ASP.NET Core 2.1, some types like `IHostingEnvironment` and `IApplicationLifetime` were copied from `Microsoft.AspNetCore.Hosting`.</span></span> <span data-ttu-id="0e016-111">일부 ASP.NET Core 3.0 변경으로 인해 앱에 `Microsoft.Extensions.Hosting` 및 `Microsoft.AspNetCore.Hosting` 네임스페이스가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-111">Some ASP.NET Core 3.0 changes cause apps to include both the `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting` namespaces.</span></span> <span data-ttu-id="0e016-112">이러한 중복 형식을 사용하면 네임스페이스가 모두 참조될 때 "모호한 참조" 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-112">Any use of those duplicate types causes an "ambiguous reference" compiler error when both namespaces are referenced.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0e016-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0e016-113">Recommended action</span></span>

<span data-ttu-id="0e016-114">이전 형식의 사용을 다음과 같이 새로 도입된 형식으로 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-114">Replaced any usages of the old types with the newly introduced types as below:</span></span>

<span data-ttu-id="0e016-115">**사용되지 않는 형식(경고):**</span><span class="sxs-lookup"><span data-stu-id="0e016-115">**Obsolete types (warning):**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

<span data-ttu-id="0e016-116">**새 형식:**</span><span class="sxs-lookup"><span data-stu-id="0e016-116">**New types:**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

<span data-ttu-id="0e016-117">새 `IHostEnvironment` `IsDevelopment` 및 `IsProduction` 확장 메서드는 `Microsoft.Extensions.Hosting` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-117">The new `IHostEnvironment` `IsDevelopment` and `IsProduction` extension methods are in the `Microsoft.Extensions.Hosting` namespace.</span></span> <span data-ttu-id="0e016-118">해당 네임스페이스를 프로젝트에 추가해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e016-118">That namespace may need to be added to your project.</span></span>

#### <a name="category"></a><span data-ttu-id="0e016-119">범주</span><span class="sxs-lookup"><span data-stu-id="0e016-119">Category</span></span>

<span data-ttu-id="0e016-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0e016-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0e016-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0e016-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
