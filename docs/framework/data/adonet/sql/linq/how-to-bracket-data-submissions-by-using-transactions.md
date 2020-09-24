---
title: '방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161362"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="0d24b-102">방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="0d24b-102">How to: Bracket Data Submissions by Using Transactions</span></span>

<span data-ttu-id="0d24b-103"><xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d24b-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="0d24b-104">자세한 내용은 [트랜잭션 지원](transaction-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d24b-104">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d24b-105">예제</span><span class="sxs-lookup"><span data-stu-id="0d24b-105">Example</span></span>  

 <span data-ttu-id="0d24b-106">다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="0d24b-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="0d24b-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d24b-107">See also</span></span>

- [<span data-ttu-id="0d24b-108">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="0d24b-108">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="0d24b-109">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="0d24b-109">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="0d24b-110">트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="0d24b-110">Transaction Support</span></span>](transaction-support.md)
