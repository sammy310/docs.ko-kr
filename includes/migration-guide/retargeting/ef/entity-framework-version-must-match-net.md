---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774423"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="c59a5-101">Entity Framework 버전이 .NET Framework 버전과 일치해야 함</span><span class="sxs-lookup"><span data-stu-id="c59a5-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c59a5-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c59a5-102">Details</span></span>|<span data-ttu-id="c59a5-103">Entity Framework 버전은 .NET Framework 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="c59a5-104">.NET Framework 4.5에는 Entity Framework 5를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="c59a5-105"><xref:System.ComponentModel.DataAnnotations> 주변의 .NET Framework 4.5 프로젝트에서 EF 4.x와 관련된 몇 가지 알려진 문제점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="c59a5-106">.NET 4.5에서는 다른 어셈블리로 옮겨졌으므로 사용할 주석을 결정할 때 문제가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="c59a5-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="c59a5-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c59a5-107">Suggestion</span></span>|<span data-ttu-id="c59a5-108">.NET Framework 4.5용 Entity Framework 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="c59a5-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="c59a5-109">범위</span><span class="sxs-lookup"><span data-stu-id="c59a5-109">Scope</span></span>|<span data-ttu-id="c59a5-110">주요함</span><span class="sxs-lookup"><span data-stu-id="c59a5-110">Major</span></span>|
|<span data-ttu-id="c59a5-111">버전</span><span class="sxs-lookup"><span data-stu-id="c59a5-111">Version</span></span>|<span data-ttu-id="c59a5-112">4.5</span><span class="sxs-lookup"><span data-stu-id="c59a5-112">4.5</span></span>|
|<span data-ttu-id="c59a5-113">형식</span><span class="sxs-lookup"><span data-stu-id="c59a5-113">Type</span></span>|<span data-ttu-id="c59a5-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c59a5-114">Retargeting</span></span>|
