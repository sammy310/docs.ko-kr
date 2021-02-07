---
description: '자세한 정보: 방법: 행 집합 반환'
title: '방법: 행 집합 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b799ce82542e6929f42485508b3a2c36cc42ee60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723389"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="51391-103">방법: 행 집합 반환</span><span class="sxs-lookup"><span data-stu-id="51391-103">How to: Return Rowsets</span></span>

<span data-ttu-id="51391-104">이 예제에서는 데이터베이스의 행 집합을 반환하고 입력 매개 변수를 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="51391-104">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="51391-105">행 집합을 반환 하는 저장 프로시저를 실행 하는 경우 저장 프로시저의 반환을 저장 하는 *result* 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="51391-105">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="51391-106">자세한 내용은 [LINQ to SQL 소스 코드 분석](analyzing-linq-to-sql-source-code.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51391-106">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="51391-107">예제</span><span class="sxs-lookup"><span data-stu-id="51391-107">Example</span></span>  

 <span data-ttu-id="51391-108">다음 예제에서는 고객의 행을 반환하고 입력 매개 변수를 사용하여 고객의 도시가 "London"인 행만을 반환하는 저장 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51391-108">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="51391-109">예제에서는 열거 가능한 `CustomersByCityResult` 클래스로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="51391-109">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```sql  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="51391-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51391-110">See also</span></span>

- [<span data-ttu-id="51391-111">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="51391-111">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="51391-112">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="51391-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
