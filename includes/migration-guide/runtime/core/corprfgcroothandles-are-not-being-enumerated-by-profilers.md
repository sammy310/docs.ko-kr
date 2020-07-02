---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620209"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="cebdd-101">프로파일러에서 COR_PRF_GC_ROOT_HANDLE을 열거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cebdd-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="cebdd-102">설명</span><span class="sxs-lookup"><span data-stu-id="cebdd-102">Details</span></span>

<span data-ttu-id="cebdd-103">.NET Framework v4.5.1에서 프로파일링 API <code>RootReferences2()</code>가 <code>COR_PRF_GC_ROOT_HANDLE</code>를 절대 반환하지 않습니다(대신 <code>COR_PRF_GC_ROOT_OTHER</code>로 반환).</span><span class="sxs-lookup"><span data-stu-id="cebdd-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="cebdd-104">이 문제는 .NET Framework 4.6부터 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cebdd-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cebdd-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cebdd-105">Suggestion</span></span>

<span data-ttu-id="cebdd-106">이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cebdd-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="cebdd-107">이름</span><span class="sxs-lookup"><span data-stu-id="cebdd-107">Name</span></span>    | <span data-ttu-id="cebdd-108">값</span><span class="sxs-lookup"><span data-stu-id="cebdd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cebdd-109">Scope</span><span class="sxs-lookup"><span data-stu-id="cebdd-109">Scope</span></span>   |<span data-ttu-id="cebdd-110">부</span><span class="sxs-lookup"><span data-stu-id="cebdd-110">Minor</span></span>|
|<span data-ttu-id="cebdd-111">버전</span><span class="sxs-lookup"><span data-stu-id="cebdd-111">Version</span></span>|<span data-ttu-id="cebdd-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="cebdd-112">4.5.1</span></span>|
|<span data-ttu-id="cebdd-113">형식</span><span class="sxs-lookup"><span data-stu-id="cebdd-113">Type</span></span>|<span data-ttu-id="cebdd-114">런타임</span><span class="sxs-lookup"><span data-stu-id="cebdd-114">Runtime</span></span>|
