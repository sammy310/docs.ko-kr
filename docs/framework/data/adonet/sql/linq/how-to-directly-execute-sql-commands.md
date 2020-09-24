---
title: '방법: SQL 명령 직접 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 6c72e683c37968ce18717b70ef6d647ca287bd20
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147647"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="b26b1-102">방법: SQL 명령 직접 실행</span><span class="sxs-lookup"><span data-stu-id="b26b1-102">How to: Directly Execute SQL Commands</span></span>

<span data-ttu-id="b26b1-103"><xref:System.Data.Linq.DataContext> 연결에서는 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 개체를 반환하지 않는 SQL 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b26b1-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b26b1-104">예제</span><span class="sxs-lookup"><span data-stu-id="b26b1-104">Example</span></span>  

 <span data-ttu-id="b26b1-105">다음 예제에서는 SQL 서버에서 UnitPrice를 1.00만큼 증가시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b26b1-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b26b1-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b26b1-106">See also</span></span>

- [<span data-ttu-id="b26b1-107">방법: SQL 쿼리 직접 실행</span><span class="sxs-lookup"><span data-stu-id="b26b1-107">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="b26b1-108">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="b26b1-108">Communicating with the Database</span></span>](communicating-with-the-database.md)
