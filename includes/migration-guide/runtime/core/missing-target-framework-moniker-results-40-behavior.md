---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497605"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="af847-101">누락된 대상 프레임워크 모니커로 인해 4.0 동작 발생</span><span class="sxs-lookup"><span data-stu-id="af847-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="af847-102">설명</span><span class="sxs-lookup"><span data-stu-id="af847-102">Details</span></span>

<span data-ttu-id="af847-103">어셈블리 수준에 적용된 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>이 없는 애플리케이션은 .NET Framework 4.0의 의미 체계(쿼크)를 사용하여 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="af847-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="af847-104">높은 품질을 보장하려면 모든 바이너리가 빌드될 때 사용된 .NET Framework의 버전을 나타내는 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>로 명시적으로 특성을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af847-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="af847-105">프로젝트 파일에서 대상 프레임워크 모니커를 사용하면 MSBuild가 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>를 자동으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="af847-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="af847-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="af847-106">Suggestion</span></span>

<span data-ttu-id="af847-107">어셈블리에 직접 특성을 추가하거나 [프로젝트 파일 또는 Visual Studio의 프로젝트 속성 GUI를 통해](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/) 대상 프레임워크를 지정하여 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af847-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="af847-108">이름</span><span class="sxs-lookup"><span data-stu-id="af847-108">Name</span></span>    | <span data-ttu-id="af847-109">값</span><span class="sxs-lookup"><span data-stu-id="af847-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="af847-110">Scope</span><span class="sxs-lookup"><span data-stu-id="af847-110">Scope</span></span>   |<span data-ttu-id="af847-111">주요함</span><span class="sxs-lookup"><span data-stu-id="af847-111">Major</span></span>|
|<span data-ttu-id="af847-112">버전</span><span class="sxs-lookup"><span data-stu-id="af847-112">Version</span></span>|<span data-ttu-id="af847-113">4.5</span><span class="sxs-lookup"><span data-stu-id="af847-113">4.5</span></span>|
|<span data-ttu-id="af847-114">형식</span><span class="sxs-lookup"><span data-stu-id="af847-114">Type</span></span>|<span data-ttu-id="af847-115">런타임</span><span class="sxs-lookup"><span data-stu-id="af847-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="af847-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="af847-116">Affected APIs</span></span>

<span data-ttu-id="af847-117">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af847-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
