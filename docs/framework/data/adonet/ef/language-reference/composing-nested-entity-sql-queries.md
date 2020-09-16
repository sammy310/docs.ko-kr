---
title: 중첩 Entity SQL 쿼리 작성
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: b28c46ba9a89ffffe8cd95ad55eb502eb8ea48a6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541098"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="0cdf0-102">중첩 Entity SQL 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="0cdf0-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="0cdf0-103">은 다양한 기능을 가진 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-103">is a rich functional language.</span></span> <span data-ttu-id="0cdf0-104">의 빌딩 블록은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="0cdf0-105">기존 SQL과 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 은 테이블 형식 결과 집합으로 제한 되지 않습니다 .는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 리터럴, 매개 변수 또는 중첩 된 식을 포함할 수 있는 복잡 한 식을 작성할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="0cdf0-106">식의 값은 매개 변수화할 수 있으며 다른 식으로 구성될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="0cdf0-107">중첩된 식</span><span class="sxs-lookup"><span data-stu-id="0cdf0-107">Nested Expressions</span></span>  
 <span data-ttu-id="0cdf0-108">중첩된 식은 자신이 반환한 형식의 값이 허용되는 임의의 위치에 놓일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="0cdf0-109">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0cdf0-109">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="0cdf0-110">중첩 쿼리는 프로젝션 절에 위치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="0cdf0-111">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="0cdf0-111">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="0cdf0-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 중첩 쿼리는 반드시 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="0cdf0-113">다음 예제에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [방법: 두 쿼리의 합집합 순서를 정렬](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="0cdf0-114">프로젝션의 중첩 쿼리</span><span class="sxs-lookup"><span data-stu-id="0cdf0-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="0cdf0-115">프로젝션 절의 중첩 쿼리는 서버의 Cartesian 제품 쿼리로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="0cdf0-116">SQL Server를 포함 한 일부 백엔드 서버에서는 TempDB 테이블이 매우 커질 수 있으므로 서버 성능에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-116">In some backend servers, including SQL Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="0cdf0-117">다음은 이러한 쿼리의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-117">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="0cdf0-118">중첩 쿼리 순서</span><span class="sxs-lookup"><span data-stu-id="0cdf0-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="0cdf0-119">Entity Framework에서 중첩된 식은 쿼리 내 임의의 위치에 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="0cdf0-120">Entity SQL을 사용하면 보다 유연성 있게 쿼리를 작성할 수 있으므로 중첩 쿼리의 순서가 포함된 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="0cdf0-121">하지만 중첩 쿼리의 순서는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdf0-121">However, the order of a nested query is not preserved.</span></span>  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a><span data-ttu-id="0cdf0-122">참조</span><span class="sxs-lookup"><span data-stu-id="0cdf0-122">See also</span></span>

- [<span data-ttu-id="0cdf0-123">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="0cdf0-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
