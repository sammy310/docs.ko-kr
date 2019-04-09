---
title: '방법: 멤버 충돌 정보 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: fae1513e7a7ead98318d907b220b7510758c9ffe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115091"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="ae61f-102">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="ae61f-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="ae61f-103"><xref:System.Data.Linq.MemberChangeConflict> 클래스를 사용하여 충돌의 각 멤버에 대한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae61f-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="ae61f-104">이와 동일한 컨텍스트에서 멤버의 충돌에 대한 사용자 지정 처리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae61f-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="ae61f-105">자세한 내용은 참조 하세요. [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae61f-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae61f-106">예제</span><span class="sxs-lookup"><span data-stu-id="ae61f-106">Example</span></span>  
 <span data-ttu-id="ae61f-107">다음 코드에서는 <xref:System.Data.Linq.ObjectChangeConflict> 개체를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ae61f-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="ae61f-108">그런 다음 각 개체에 대해 <xref:System.Data.Linq.MemberChangeConflict> 개체를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ae61f-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae61f-109"><xref:System.Reflection> 정보를 제공하려면 <xref:System.Data.Linq.MemberChangeConflict.Member%2A>을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ae61f-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ae61f-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae61f-110">See also</span></span>

- [<span data-ttu-id="ae61f-111">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="ae61f-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
