---
title: '방법: 충돌하는 전송 검색 및 문제 해결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
ms.openlocfilehash: 606231449263f1c26596ca8606a88053c6aded8e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138127"
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="e26d2-102">방법: 충돌하는 전송 검색 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e26d2-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e26d2-103">데이터베이스를 다중 사용자 변경 내용에서 기인 하는 충돌 감지 및 해결에 대 한 많은 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26d2-103">provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="e26d2-104">자세한 내용은 [방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e26d2-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e26d2-105">예제</span><span class="sxs-lookup"><span data-stu-id="e26d2-105">Example</span></span>  
 <span data-ttu-id="e26d2-106">에서는 다음 예제는 `try` / `catch` catch를 <xref:System.Data.Linq.ChangeConflictException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="e26d2-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="e26d2-107">각 충돌의 엔터티 및 멤버 정보는 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e26d2-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e26d2-108">정보 검색을 지원하려면 `using System.Reflection` 지시문(Visual Basic의 `Imports System.Reflection`)을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e26d2-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="e26d2-109">자세한 내용은 <xref:System.Reflection>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e26d2-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e26d2-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e26d2-110">See also</span></span>

- [<span data-ttu-id="e26d2-111">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="e26d2-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="e26d2-112">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="e26d2-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
