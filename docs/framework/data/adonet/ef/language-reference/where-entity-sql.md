---
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 1907b8786622d3c8019c75916f997c830cc07cfb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180961"
---
# <a name="where-entity-sql"></a><span data-ttu-id="1f52c-102">WHERE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1f52c-102">WHERE (Entity SQL)</span></span>

<span data-ttu-id="1f52c-103">WHERE 절은 [FROM](from-entity-sql.md) 절 바로 뒤에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-103">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f52c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f52c-104">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1f52c-105">인수</span><span class="sxs-lookup"><span data-stu-id="1f52c-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="1f52c-106">Boolean 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-106">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f52c-107">설명</span><span class="sxs-lookup"><span data-stu-id="1f52c-107">Remarks</span></span>  

 <span data-ttu-id="1f52c-108">WHERE 절에는 Transact-sql에 대해 설명한 것과 동일한 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-108">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="1f52c-109">WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-109">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="1f52c-110">식 `e`에는 부운 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-110">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="1f52c-111">WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-111">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="1f52c-112">FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f52c-112">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f52c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f52c-113">See also</span></span>

- [<span data-ttu-id="1f52c-114">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="1f52c-114">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="1f52c-115">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="1f52c-115">Query Expressions</span></span>](query-expressions-entity-sql.md)
