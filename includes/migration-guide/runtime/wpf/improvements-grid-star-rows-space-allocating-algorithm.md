---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497756"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="1aaea-101">그리드 별 행 공간 할당 알고리즘 개선</span><span class="sxs-lookup"><span data-stu-id="1aaea-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="1aaea-102">설명</span><span class="sxs-lookup"><span data-stu-id="1aaea-102">Details</span></span>

<span data-ttu-id="1aaea-103">.NET Framework 4.7에 도입된<xref:System.Windows.Controls.Grid>[에서 크기를 에 할당하기 위한  알고리즘의](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1aaea-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="1aaea-104">빈 행이 포함된 <code>Height=&quot;Auto&quot;</code>가 있는 그리드와 같은 일부 경우에는 행이 잘못된 위치에 정렬되었으며 그리드 외부에 배치되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aaea-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1aaea-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="1aaea-105">Suggestion</span></span>

<span data-ttu-id="1aaea-106">애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.8 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aaea-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="1aaea-107">이름</span><span class="sxs-lookup"><span data-stu-id="1aaea-107">Name</span></span>    | <span data-ttu-id="1aaea-108">값</span><span class="sxs-lookup"><span data-stu-id="1aaea-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1aaea-109">Scope</span><span class="sxs-lookup"><span data-stu-id="1aaea-109">Scope</span></span>   |<span data-ttu-id="1aaea-110">주요함</span><span class="sxs-lookup"><span data-stu-id="1aaea-110">Major</span></span>|
|<span data-ttu-id="1aaea-111">버전</span><span class="sxs-lookup"><span data-stu-id="1aaea-111">Version</span></span>|<span data-ttu-id="1aaea-112">4.8</span><span class="sxs-lookup"><span data-stu-id="1aaea-112">4.8</span></span>|
|<span data-ttu-id="1aaea-113">형식</span><span class="sxs-lookup"><span data-stu-id="1aaea-113">Type</span></span>|<span data-ttu-id="1aaea-114">런타임</span><span class="sxs-lookup"><span data-stu-id="1aaea-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1aaea-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1aaea-115">Affected APIs</span></span>

<span data-ttu-id="1aaea-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1aaea-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
