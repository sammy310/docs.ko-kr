---
description: '자세한 정보: 방법: 변경 집합 표시'
title: '방법: ChangeSet 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
ms.openlocfilehash: e5ff7aebcc74ded1300433a3bf7b280db3a11b28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786019"
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="cdf90-103">방법: ChangeSet 표시</span><span class="sxs-lookup"><span data-stu-id="cdf90-103">How to: Display a ChangeSet</span></span>

<span data-ttu-id="cdf90-104"><xref:System.Data.Linq.DataContext>을 사용하여 <xref:System.Data.Linq.DataContext.GetChangeSet%2A>에 의해 추적된 변경 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdf90-104">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdf90-105">예제</span><span class="sxs-lookup"><span data-stu-id="cdf90-105">Example</span></span>  

 <span data-ttu-id="cdf90-106">다음 예제에서는 도시가 London인 고객을 검색하여 도시를 Paris로 변경한 다음 변경 내용을 다시 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="cdf90-106">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="cdf90-107">이 코드는 다음과 유사하게 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdf90-107">Output from this code appears similar to the following.</span></span> <span data-ttu-id="cdf90-108">맨 끝에 8개가 변경되었음을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cdf90-108">Note that the summary at the end shows that eight changes were made.</span></span>  

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
  
## <a name="see-also"></a><span data-ttu-id="cdf90-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdf90-109">See also</span></span>

- [<span data-ttu-id="cdf90-110">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="cdf90-110">Debugging Support</span></span>](debugging-support.md)
