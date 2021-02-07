---
description: '방법에 대 한 자세한 정보: 방법: 트랜잭션을 사용 하 여 데이터 전송'
title: '방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: a1bbebfcdb4b65e83c4ac6dc9b87b06f33f2cb41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739029"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="5dbf3-103">방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="5dbf3-103">How to: Bracket Data Submissions by Using Transactions</span></span>

<span data-ttu-id="5dbf3-104"><xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5dbf3-104">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="5dbf3-105">자세한 내용은 [트랜잭션 지원](transaction-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5dbf3-105">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dbf3-106">예제</span><span class="sxs-lookup"><span data-stu-id="5dbf3-106">Example</span></span>  

 <span data-ttu-id="5dbf3-107">다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="5dbf3-107">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5dbf3-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5dbf3-108">See also</span></span>

- [<span data-ttu-id="5dbf3-109">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="5dbf3-109">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="5dbf3-110">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="5dbf3-110">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="5dbf3-111">트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="5dbf3-111">Transaction Support</span></span>](transaction-support.md)
