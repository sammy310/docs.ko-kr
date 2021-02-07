---
description: '자세히 알아보기: 방법: 엔터티 충돌 정보 검색'
title: '방법: 엔터티 충돌 정보 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: dde11a431ae977595b9845444e48705a4552fb23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767754"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="80ad8-103">방법: 엔터티 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="80ad8-103">How to: Retrieve Entity Conflict Information</span></span>

<span data-ttu-id="80ad8-104"><xref:System.Data.Linq.ObjectChangeConflict> 클래스의 개체를 사용하여 <xref:System.Data.Linq.ChangeConflictException> 예외로 인해 발생한 충돌에 대한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80ad8-104">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="80ad8-105">자세한 내용은 [낙관적 동시성: 개요](optimistic-concurrency-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80ad8-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80ad8-106">예제</span><span class="sxs-lookup"><span data-stu-id="80ad8-106">Example</span></span>  

 <span data-ttu-id="80ad8-107">다음 예제에서는 누적된 충돌 목록을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="80ad8-107">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="80ad8-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80ad8-108">See also</span></span>

- [<span data-ttu-id="80ad8-109">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="80ad8-109">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
