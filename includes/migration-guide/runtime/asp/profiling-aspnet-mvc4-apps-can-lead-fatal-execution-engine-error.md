---
ms.openlocfilehash: c679cb2603d39f580203d9373d76481e904e6c1d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497097"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="70ca4-101">ASP.Net MVC4 앱을 프로파일링하면 심각한 실행 엔진 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ca4-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="70ca4-102">설명</span><span class="sxs-lookup"><span data-stu-id="70ca4-102">Details</span></span>

<span data-ttu-id="70ca4-103">NGEN /Profile 어셈블리를 사용하는 프로파일러는 프로파일링된 ASP.NET MVC4 애플리케이션을 시작할 때 '심각한 실행 엔진 예외'로 크래시가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ca4-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="70ca4-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="70ca4-104">Suggestion</span></span>

<span data-ttu-id="70ca4-105">이 문제는 .NET Framework 4.5.2에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70ca4-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="70ca4-106">또는 프로파일러는 이벤트 마스크에 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code>를 지정하여 이 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ca4-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="70ca4-107">이름</span><span class="sxs-lookup"><span data-stu-id="70ca4-107">Name</span></span>    | <span data-ttu-id="70ca4-108">값</span><span class="sxs-lookup"><span data-stu-id="70ca4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="70ca4-109">Scope</span><span class="sxs-lookup"><span data-stu-id="70ca4-109">Scope</span></span>   |<span data-ttu-id="70ca4-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="70ca4-110">Edge</span></span>|
|<span data-ttu-id="70ca4-111">버전</span><span class="sxs-lookup"><span data-stu-id="70ca4-111">Version</span></span>|<span data-ttu-id="70ca4-112">4.5</span><span class="sxs-lookup"><span data-stu-id="70ca4-112">4.5</span></span>|
|<span data-ttu-id="70ca4-113">형식</span><span class="sxs-lookup"><span data-stu-id="70ca4-113">Type</span></span>|<span data-ttu-id="70ca4-114">런타임</span><span class="sxs-lookup"><span data-stu-id="70ca4-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="70ca4-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="70ca4-115">Affected APIs</span></span>

<span data-ttu-id="70ca4-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ca4-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
