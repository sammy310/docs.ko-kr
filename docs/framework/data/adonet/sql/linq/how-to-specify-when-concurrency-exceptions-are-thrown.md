---
description: '자세한 정보: 방법: 동시성 예외가 Throw 되는 시기 지정'
title: '방법: 동시성 예외가 throw되는 시기 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: d445cabfd2498f3599d874c2b7983a86c2c36c7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785876"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="e08aa-103">방법: 동시성 예외가 throw되는 시기 지정</span><span class="sxs-lookup"><span data-stu-id="e08aa-103">How to: Specify When Concurrency Exceptions are Thrown</span></span>

<span data-ttu-id="e08aa-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Data.Linq.ChangeConflictException> 예외는 낙관적 동시성 충돌 때문에 개체가 업데이트되지 않는 경우 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e08aa-104">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="e08aa-105">자세한 내용은 [낙관적 동시성: 개요](optimistic-concurrency-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e08aa-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="e08aa-106">변경 내용을 데이터베이스에 전송하기 전에 동시성 예외가 throw되는 시점을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08aa-106">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
- <span data-ttu-id="e08aa-107">첫 번째 실패 시 예외를 Throw합니다(<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="e08aa-107">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
- <span data-ttu-id="e08aa-108">모든 업데이트 시도를 완료하고 모든 실패를 누적하여 예외에 누적된 실패를 보고합니다(<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="e08aa-108">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="e08aa-109">Throw되면 <xref:System.Data.Linq.ChangeConflictException> 예외에서 <xref:System.Data.Linq.ChangeConflictCollection> 컬렉션에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e08aa-109">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="e08aa-110">이 컬렉션에서는 <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> 컬렉션에 대한 액세스를 포함하여 실패한 단일 업데이트 시도에 매핑된 각 충돌에 대한 자세한 내용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e08aa-110">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="e08aa-111">각 멤버 충돌은 동시성 확인에 실패한 업데이트의 단일 멤버에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e08aa-111">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e08aa-112">예제</span><span class="sxs-lookup"><span data-stu-id="e08aa-112">Example</span></span>  

 <span data-ttu-id="e08aa-113">다음 코드에서는 두 값의 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e08aa-113">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e08aa-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e08aa-114">See also</span></span>

- [<span data-ttu-id="e08aa-115">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="e08aa-115">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
- [<span data-ttu-id="e08aa-116">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="e08aa-116">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
