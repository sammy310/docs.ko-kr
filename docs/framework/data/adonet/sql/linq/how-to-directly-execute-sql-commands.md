---
description: '자세히 알아보기: 방법: SQL 명령 직접 실행'
title: '방법: SQL 명령 직접 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 9dd53b3582b6099bae51dc008debd8cb3142e386
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786032"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="5147c-103">방법: SQL 명령 직접 실행</span><span class="sxs-lookup"><span data-stu-id="5147c-103">How to: Directly Execute SQL Commands</span></span>

<span data-ttu-id="5147c-104"><xref:System.Data.Linq.DataContext> 연결에서는 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 개체를 반환하지 않는 SQL 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5147c-104">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5147c-105">예제</span><span class="sxs-lookup"><span data-stu-id="5147c-105">Example</span></span>  

 <span data-ttu-id="5147c-106">다음 예제에서는 SQL 서버에서 UnitPrice를 1.00만큼 증가시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5147c-106">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5147c-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5147c-107">See also</span></span>

- [<span data-ttu-id="5147c-108">방법: SQL 쿼리 직접 실행</span><span class="sxs-lookup"><span data-stu-id="5147c-108">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="5147c-109">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="5147c-109">Communicating with the Database</span></span>](communicating-with-the-database.md)
