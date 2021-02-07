---
description: '자세히 알아보기: 방법: 멤버 충돌 정보 검색'
title: '방법: 멤버 충돌 정보 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 2a33aba1a113bdfd66bdc341bfc9ae59406f2c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723402"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="2d3b6-103">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="2d3b6-103">How to: Retrieve Member Conflict Information</span></span>

<span data-ttu-id="2d3b6-104"><xref:System.Data.Linq.MemberChangeConflict> 클래스를 사용하여 충돌의 각 멤버에 대한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-104">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="2d3b6-105">이와 동일한 컨텍스트에서 멤버의 충돌에 대한 사용자 지정 처리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-105">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="2d3b6-106">자세한 내용은 [낙관적 동시성: 개요](optimistic-concurrency-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-106">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d3b6-107">예제</span><span class="sxs-lookup"><span data-stu-id="2d3b6-107">Example</span></span>  

 <span data-ttu-id="2d3b6-108">다음 코드에서는 <xref:System.Data.Linq.ObjectChangeConflict> 개체를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-108">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="2d3b6-109">그런 다음 각 개체에 대해 <xref:System.Data.Linq.MemberChangeConflict> 개체를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-109">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d3b6-110"><xref:System.Reflection> 정보를 제공하려면 <xref:System.Data.Linq.MemberChangeConflict.Member%2A>을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2d3b6-110">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2d3b6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d3b6-111">See also</span></span>

- [<span data-ttu-id="2d3b6-112">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="2d3b6-112">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
