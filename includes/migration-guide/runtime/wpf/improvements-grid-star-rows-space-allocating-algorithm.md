---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622097"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="92ae6-101">그리드 별 행 공간 할당 알고리즘 개선</span><span class="sxs-lookup"><span data-stu-id="92ae6-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="92ae6-102">설명</span><span class="sxs-lookup"><span data-stu-id="92ae6-102">Details</span></span>

<span data-ttu-id="92ae6-103">.NET Framework 4.7에 도입된<xref:System.Windows.Controls.Grid>[에서 크기를 에 할당하기 위한  알고리즘의](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="92ae6-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="92ae6-104">빈 행이 포함된 <code>Height=&quot;Auto&quot;</code>가 있는 그리드와 같은 일부 경우에는 행이 잘못된 위치에 정렬되었으며 그리드 외부에 배치되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ae6-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="92ae6-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="92ae6-105">Suggestion</span></span>

<span data-ttu-id="92ae6-106">애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.8 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92ae6-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="92ae6-107">이름</span><span class="sxs-lookup"><span data-stu-id="92ae6-107">Name</span></span>    | <span data-ttu-id="92ae6-108">값</span><span class="sxs-lookup"><span data-stu-id="92ae6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="92ae6-109">Scope</span><span class="sxs-lookup"><span data-stu-id="92ae6-109">Scope</span></span>   |<span data-ttu-id="92ae6-110">주요함</span><span class="sxs-lookup"><span data-stu-id="92ae6-110">Major</span></span>|
|<span data-ttu-id="92ae6-111">버전</span><span class="sxs-lookup"><span data-stu-id="92ae6-111">Version</span></span>|<span data-ttu-id="92ae6-112">4.8</span><span class="sxs-lookup"><span data-stu-id="92ae6-112">4.8</span></span>|
|<span data-ttu-id="92ae6-113">형식</span><span class="sxs-lookup"><span data-stu-id="92ae6-113">Type</span></span>|<span data-ttu-id="92ae6-114">런타임</span><span class="sxs-lookup"><span data-stu-id="92ae6-114">Runtime</span></span>|
