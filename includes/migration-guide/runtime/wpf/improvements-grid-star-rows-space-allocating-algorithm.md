---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237607"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="f86c7-101">그리드 별 행 공간 할당 알고리즘 개선</span><span class="sxs-lookup"><span data-stu-id="f86c7-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f86c7-102">설명</span><span class="sxs-lookup"><span data-stu-id="f86c7-102">Details</span></span>|<span data-ttu-id="f86c7-103">.NET Framework 4.7에 도입된<xref:System.Windows.Controls.Grid>[에서 크기를 에 할당하기 위한  알고리즘의](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f86c7-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="f86c7-104">빈 행이 포함된 <code>Height=&quot;Auto&quot;</code>가 있는 그리드와 같은 일부 경우에는 행이 잘못된 위치에 정렬되었으며 그리드 외부에 배치되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f86c7-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="f86c7-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f86c7-105">Suggestion</span></span>|<span data-ttu-id="f86c7-106">애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.8 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f86c7-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="f86c7-107">Scope</span><span class="sxs-lookup"><span data-stu-id="f86c7-107">Scope</span></span>|<span data-ttu-id="f86c7-108">주요함</span><span class="sxs-lookup"><span data-stu-id="f86c7-108">Major</span></span>|
|<span data-ttu-id="f86c7-109">버전</span><span class="sxs-lookup"><span data-stu-id="f86c7-109">Version</span></span>|<span data-ttu-id="f86c7-110">4.8</span><span class="sxs-lookup"><span data-stu-id="f86c7-110">4.8</span></span>|
|<span data-ttu-id="f86c7-111">형식</span><span class="sxs-lookup"><span data-stu-id="f86c7-111">Type</span></span>|<span data-ttu-id="f86c7-112">런타임</span><span class="sxs-lookup"><span data-stu-id="f86c7-112">Runtime</span></span>|
