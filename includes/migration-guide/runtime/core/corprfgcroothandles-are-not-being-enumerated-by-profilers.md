---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496756"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="d4b88-101">프로파일러에서 COR_PRF_GC_ROOT_HANDLE을 열거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b88-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="d4b88-102">설명</span><span class="sxs-lookup"><span data-stu-id="d4b88-102">Details</span></span>

<span data-ttu-id="d4b88-103">.NET Framework v4.5.1에서 프로파일링 API <code>RootReferences2()</code>가 <code>COR_PRF_GC_ROOT_HANDLE</code>를 절대 반환하지 않습니다(대신 <code>COR_PRF_GC_ROOT_OTHER</code>로 반환).</span><span class="sxs-lookup"><span data-stu-id="d4b88-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="d4b88-104">이 문제는 .NET Framework 4.6부터 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b88-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d4b88-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d4b88-105">Suggestion</span></span>

<span data-ttu-id="d4b88-106">이 문제는 .NET Framework 4.6에서 해결되었으며, 해당 버전의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b88-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="d4b88-107">이름</span><span class="sxs-lookup"><span data-stu-id="d4b88-107">Name</span></span>    | <span data-ttu-id="d4b88-108">값</span><span class="sxs-lookup"><span data-stu-id="d4b88-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d4b88-109">Scope</span><span class="sxs-lookup"><span data-stu-id="d4b88-109">Scope</span></span>   |<span data-ttu-id="d4b88-110">부</span><span class="sxs-lookup"><span data-stu-id="d4b88-110">Minor</span></span>|
|<span data-ttu-id="d4b88-111">버전</span><span class="sxs-lookup"><span data-stu-id="d4b88-111">Version</span></span>|<span data-ttu-id="d4b88-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d4b88-112">4.5.1</span></span>|
|<span data-ttu-id="d4b88-113">형식</span><span class="sxs-lookup"><span data-stu-id="d4b88-113">Type</span></span>|<span data-ttu-id="d4b88-114">런타임</span><span class="sxs-lookup"><span data-stu-id="d4b88-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d4b88-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d4b88-115">Affected APIs</span></span>

<span data-ttu-id="d4b88-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4b88-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
