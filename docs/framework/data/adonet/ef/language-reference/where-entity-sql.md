---
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: b551d15d7de2cf07afc7455b7fd0a0faf6436ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319178"
---
# <a name="where-entity-sql"></a><span data-ttu-id="de508-102">WHERE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="de508-102">WHERE (Entity SQL)</span></span>
<span data-ttu-id="de508-103">WHERE 절은 [FROM](from-entity-sql.md) 절 바로 뒤에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de508-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de508-104">구문</span><span class="sxs-lookup"><span data-stu-id="de508-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="de508-105">인수</span><span class="sxs-lookup"><span data-stu-id="de508-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="de508-106">Boolean 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="de508-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de508-107">주의</span><span class="sxs-lookup"><span data-stu-id="de508-107">Remarks</span></span>  
 <span data-ttu-id="de508-108">WHERE 절에는 Transact-sql에 대해 설명한 것과 동일한 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de508-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="de508-109">WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="de508-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="de508-110">식 `e`에는 부운 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de508-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="de508-111">WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de508-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="de508-112">FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de508-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de508-113">참조</span><span class="sxs-lookup"><span data-stu-id="de508-113">See also</span></span>

- [<span data-ttu-id="de508-114">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="de508-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="de508-115">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="de508-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
