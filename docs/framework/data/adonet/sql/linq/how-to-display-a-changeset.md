---
title: '방법: ChangeSet 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: 92acee0d36634ea09c245418fcc7a8b97d208aa6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228635"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="4a459-102">방법: ChangeSet 표시</span><span class="sxs-lookup"><span data-stu-id="4a459-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="4a459-103"><xref:System.Data.Linq.DataContext>을 사용하여 <xref:System.Data.Linq.DataContext.GetChangeSet%2A>에 의해 추적된 변경 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a459-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a459-104">예제</span><span class="sxs-lookup"><span data-stu-id="4a459-104">Example</span></span>  
 <span data-ttu-id="4a459-105">다음 예제에서는 도시가 London인 고객을 검색하여 도시를 Paris로 변경한 다음 변경 내용을 다시 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4a459-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="4a459-106">이 코드는 다음과 유사하게 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a459-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="4a459-107">맨 끝에 8개가 변경되었음을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a459-107">Note that the summary at the end shows that eight changes were made.</span></span>  

 ```console
CustomerID: AROUT
   Original value: London
   Updated value: Paris
CustomerID: BSBEV
   Original value: London
   Updated value: Paris
CustomerID: CONSH
   Original value: London
   Updated value: Paris
CustomerID: EASTC
   Original value: London
   Updated value: Paris
CustomerID: NORTS
    Original value: London
    Updated value: Paris
CustomerID: PARIS
    Original value: London
    Updated value: Paris
CustomerID: SEVES
    Original value: London
    Updated value: Paris
CustomerID: SPECD
    Original value: London
    Updated value: Paris
Total changes: {Added: 0, Removed: 0, Modified: 8}
```
  
## <a name="see-also"></a><span data-ttu-id="4a459-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a459-108">See also</span></span>

- [<span data-ttu-id="4a459-109">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="4a459-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
