---
description: '자세한 정보: 방법: LINQ to SQL 명령 표시'
title: '방법: LINQ to SQL 명령 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: 480e7c1cbcceb09f0d727d03569d6277e0dd754b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785993"
---
# <a name="how-to-display-linq-to-sql-commands"></a><span data-ttu-id="0d0b1-103">방법: LINQ to SQL 명령 표시</span><span class="sxs-lookup"><span data-stu-id="0d0b1-103">How to: Display LINQ to SQL Commands</span></span>

<span data-ttu-id="0d0b1-104"><xref:System.Data.Linq.DataContext.GetCommand%2A>를 사용하여 SQL 명령 및 기타 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0b1-104">Use <xref:System.Data.Linq.DataContext.GetCommand%2A> to display SQL commands and other information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d0b1-105">예제</span><span class="sxs-lookup"><span data-stu-id="0d0b1-105">Example</span></span>  

 <span data-ttu-id="0d0b1-106">다음 예제에서는 콘솔 창에 쿼리로부터의 출력, 생성된 SQL 명령, 명령 형식 및 연결 형식이 차례로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d0b1-106">In the following example, the console window displays the output from the query, followed by the SQL commands that are generated, the type of commands, and the type of connection.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 <span data-ttu-id="0d0b1-107">다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d0b1-107">Output appears as follows:</span></span>  
  
```console  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```console  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d0b1-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d0b1-108">See also</span></span>

- [<span data-ttu-id="0d0b1-109">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="0d0b1-109">Debugging Support</span></span>](debugging-support.md)
