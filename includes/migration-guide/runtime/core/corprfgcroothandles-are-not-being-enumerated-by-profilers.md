---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858571"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="d7a1a-101">프로파일러에서 COR_PRF_GC_ROOT_HANDLE을 열거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a1a-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d7a1a-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d7a1a-102">Details</span></span>|<span data-ttu-id="d7a1a-103">.NET Framework v4.5.1에서 프로파일링 API <code>RootReferences2()</code>가 <code>COR_PRF_GC_ROOT_HANDLE</code>를 절대 반환하지 않습니다(대신 <code>COR_PRF_GC_ROOT_OTHER</code>로 반환).</span><span class="sxs-lookup"><span data-stu-id="d7a1a-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="d7a1a-104">이 문제는 .NET Framework 4.6부터 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a1a-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="d7a1a-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d7a1a-105">Suggestion</span></span>|<span data-ttu-id="d7a1a-106">이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a1a-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="d7a1a-107">범위</span><span class="sxs-lookup"><span data-stu-id="d7a1a-107">Scope</span></span>|<span data-ttu-id="d7a1a-108">사소함</span><span class="sxs-lookup"><span data-stu-id="d7a1a-108">Minor</span></span>|
|<span data-ttu-id="d7a1a-109">Version</span><span class="sxs-lookup"><span data-stu-id="d7a1a-109">Version</span></span>|<span data-ttu-id="d7a1a-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d7a1a-110">4.5.1</span></span>|
|<span data-ttu-id="d7a1a-111">형식</span><span class="sxs-lookup"><span data-stu-id="d7a1a-111">Type</span></span>|<span data-ttu-id="d7a1a-112">런타임</span><span class="sxs-lookup"><span data-stu-id="d7a1a-112">Runtime</span></span>|
