---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496921"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a><span data-ttu-id="886c6-101">WPF는 마우스를 고정할 수 있는 wisptis.exe 프로세스를 생성함</span><span class="sxs-lookup"><span data-stu-id="886c6-101">WPF spawns a wisptis.exe process which can freeze the mouse</span></span>

#### <a name="details"></a><span data-ttu-id="886c6-102">설명</span><span class="sxs-lookup"><span data-stu-id="886c6-102">Details</span></span>

<span data-ttu-id="886c6-103">마우스 입력을 고정할 수 있는 <code>wisptis.exe</code>가 생성되는 문제가 4.5.2에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="886c6-103">An issue was introduced in 4.5.2 that causes <code>wisptis.exe</code> to be spawned that can freeze mouse input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="886c6-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="886c6-104">Suggestion</span></span>

<span data-ttu-id="886c6-105">이 문제에 대한 픽스는 .NET Framework 4.5.2(핫픽스 롤업 3026376)의 서비스 릴리스에서 사용하거나 .NET Framework 4.6으로 업그레이드하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="886c6-105">A fix for this issue is available in a servicing release of the .NET Framework 4.5.2 (hotfix rollup 3026376), or by upgrading to the .NET Framework 4.6</span></span>

| <span data-ttu-id="886c6-106">이름</span><span class="sxs-lookup"><span data-stu-id="886c6-106">Name</span></span>    | <span data-ttu-id="886c6-107">값</span><span class="sxs-lookup"><span data-stu-id="886c6-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="886c6-108">Scope</span><span class="sxs-lookup"><span data-stu-id="886c6-108">Scope</span></span>   |<span data-ttu-id="886c6-109">주요함</span><span class="sxs-lookup"><span data-stu-id="886c6-109">Major</span></span>|
|<span data-ttu-id="886c6-110">버전</span><span class="sxs-lookup"><span data-stu-id="886c6-110">Version</span></span>|<span data-ttu-id="886c6-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="886c6-111">4.5.2</span></span>|
|<span data-ttu-id="886c6-112">형식</span><span class="sxs-lookup"><span data-stu-id="886c6-112">Type</span></span>|<span data-ttu-id="886c6-113">런타임</span><span class="sxs-lookup"><span data-stu-id="886c6-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="886c6-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="886c6-114">Affected APIs</span></span>

<span data-ttu-id="886c6-115">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="886c6-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
