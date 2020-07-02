---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622128"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="85703-101">ASP.Net MVC4 앱을 프로파일링하면 심각한 실행 엔진 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85703-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="85703-102">설명</span><span class="sxs-lookup"><span data-stu-id="85703-102">Details</span></span>

<span data-ttu-id="85703-103">NGEN /Profile 어셈블리를 사용하는 프로파일러는 프로파일링된 ASP.NET MVC4 애플리케이션을 시작할 때 '심각한 실행 엔진 예외'로 크래시가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85703-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85703-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="85703-104">Suggestion</span></span>

<span data-ttu-id="85703-105">이 문제는 .NET Framework 4.5.2에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85703-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="85703-106">또는 프로파일러는 이벤트 마스크에 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code>를 지정하여 이 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85703-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="85703-107">이름</span><span class="sxs-lookup"><span data-stu-id="85703-107">Name</span></span>    | <span data-ttu-id="85703-108">값</span><span class="sxs-lookup"><span data-stu-id="85703-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85703-109">Scope</span><span class="sxs-lookup"><span data-stu-id="85703-109">Scope</span></span>   |<span data-ttu-id="85703-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="85703-110">Edge</span></span>|
|<span data-ttu-id="85703-111">버전</span><span class="sxs-lookup"><span data-stu-id="85703-111">Version</span></span>|<span data-ttu-id="85703-112">4.5</span><span class="sxs-lookup"><span data-stu-id="85703-112">4.5</span></span>|
|<span data-ttu-id="85703-113">형식</span><span class="sxs-lookup"><span data-stu-id="85703-113">Type</span></span>|<span data-ttu-id="85703-114">런타임</span><span class="sxs-lookup"><span data-stu-id="85703-114">Runtime</span></span>|
