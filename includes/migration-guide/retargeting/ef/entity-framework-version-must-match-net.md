---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617194"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="debc8-101">Entity Framework 버전이 .NET Framework 버전과 일치해야 함</span><span class="sxs-lookup"><span data-stu-id="debc8-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="debc8-102">설명</span><span class="sxs-lookup"><span data-stu-id="debc8-102">Details</span></span>

<span data-ttu-id="debc8-103">EF(Entity Framework) 버전은 .NET Framework 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="debc8-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="debc8-104">.NET Framework 4.5에는 Entity Framework 5를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="debc8-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="debc8-105"><xref:System.ComponentModel.DataAnnotations> 주변의 .NET Framework 4.5 프로젝트에서 EF 4.x와 관련된 몇 가지 알려진 문제점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="debc8-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="debc8-106">.NET Framework 4.5에서는 이 네임스페이스가 다른 어셈블리로 옮겨졌으므로 사용할 주석을 결정할 때 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="debc8-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="debc8-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="debc8-107">Suggestion</span></span>

<span data-ttu-id="debc8-108">.NET Framework 4.5용 Entity Framework 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="debc8-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="debc8-109">이름</span><span class="sxs-lookup"><span data-stu-id="debc8-109">Name</span></span>    | <span data-ttu-id="debc8-110">값</span><span class="sxs-lookup"><span data-stu-id="debc8-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="debc8-111">Scope</span><span class="sxs-lookup"><span data-stu-id="debc8-111">Scope</span></span>   | <span data-ttu-id="debc8-112">주요함</span><span class="sxs-lookup"><span data-stu-id="debc8-112">Major</span></span>       |
| <span data-ttu-id="debc8-113">버전</span><span class="sxs-lookup"><span data-stu-id="debc8-113">Version</span></span> | <span data-ttu-id="debc8-114">4.5</span><span class="sxs-lookup"><span data-stu-id="debc8-114">4.5</span></span>         |
| <span data-ttu-id="debc8-115">형식</span><span class="sxs-lookup"><span data-stu-id="debc8-115">Type</span></span>    | <span data-ttu-id="debc8-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="debc8-116">Retargeting</span></span> |
