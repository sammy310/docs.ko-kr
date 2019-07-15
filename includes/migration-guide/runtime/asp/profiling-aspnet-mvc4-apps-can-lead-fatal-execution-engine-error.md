---
ms.openlocfilehash: 107b34c7bd26e1396e8a6638d6929c15de92b8e4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803268"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="b9774-101">ASP.Net MVC4 앱을 프로파일링하면 심각한 실행 엔진 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9774-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b9774-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b9774-102">Details</span></span>|<span data-ttu-id="b9774-103">NGEN /Profile 어셈블리를 사용하는 프로파일러는 프로파일링된 ASP.NET MVC4 애플리케이션을 시작할 때 '심각한 실행 엔진 예외'로 크래시가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9774-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="b9774-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b9774-104">Suggestion</span></span>|<span data-ttu-id="b9774-105">이 문제는 .NET Framework 4.5.2에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9774-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="b9774-106">또는 프로파일러는 이벤트 마스크에 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code>를 지정하여 이 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9774-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="b9774-107">범위</span><span class="sxs-lookup"><span data-stu-id="b9774-107">Scope</span></span>|<span data-ttu-id="b9774-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b9774-108">Edge</span></span>|
|<span data-ttu-id="b9774-109">버전</span><span class="sxs-lookup"><span data-stu-id="b9774-109">Version</span></span>|<span data-ttu-id="b9774-110">4.5</span><span class="sxs-lookup"><span data-stu-id="b9774-110">4.5</span></span>|
|<span data-ttu-id="b9774-111">형식</span><span class="sxs-lookup"><span data-stu-id="b9774-111">Type</span></span>|<span data-ttu-id="b9774-112">런타임</span><span class="sxs-lookup"><span data-stu-id="b9774-112">Runtime</span></span>|

