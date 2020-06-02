---
title: '방법: 테이블 반환 사용자 정의 함수 사용'
description: 다음 예를 사용 하 여 단일 행 집합을 반환 하는 테이블 반환 함수를 만드는 방법을 배울 수 있습니다. 이러한 테이블 반환 함수는 테이블과 동일 하 게 사용 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 44866367393e321d7dd2db965e2fad8a2e6b63e9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286328"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="01266-104">방법: 테이블 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="01266-104">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="01266-105">테이블 반환 함수에서는 여러 결과 모양을 반환할 수 있는 저장 프로시저와 달리 단일 행 집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="01266-105">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="01266-106">테이블 반환 함수의 반환 형식은 `Table`이기 때문에 테이블을 사용할 수 있는 SQL의 위치인 어디에나 테이블 반환 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01266-106">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="01266-107">또한 테이블 반환 함수를 테이블로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01266-107">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01266-108">예제</span><span class="sxs-lookup"><span data-stu-id="01266-108">Example</span></span>  
 <span data-ttu-id="01266-109">다음 SQL 함수는 `TABLE`을 반환한다는 것을 명시적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01266-109">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="01266-110">따라서 반환된 행 집합 구조는 암시적으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="01266-110">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="01266-111">에서는 함수를 다음과 같이 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="01266-111">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="01266-112">예제</span><span class="sxs-lookup"><span data-stu-id="01266-112">Example</span></span>  
 <span data-ttu-id="01266-113">다음 SQL 코드에서는 함수에서 반환하는 테이블에 조인하거나 테이블 반환 함수를 원하는 다른 테이블로 처리할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01266-113">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="01266-114">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리는 다음과 같이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="01266-114">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="01266-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01266-115">See also</span></span>

- [<span data-ttu-id="01266-116">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="01266-116">User-Defined Functions</span></span>](user-defined-functions.md)
