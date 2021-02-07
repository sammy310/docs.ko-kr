---
description: '자세히 알아보기: WHERE (Entity SQL)'
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: e094a93927f6ac77aef772654f1d8d4fcf999cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712872"
---
# <a name="where-entity-sql"></a><span data-ttu-id="6834a-103">WHERE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6834a-103">WHERE (Entity SQL)</span></span>

<span data-ttu-id="6834a-104">WHERE 절은 [FROM](from-entity-sql.md) 절 바로 뒤에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-104">The WHERE clause is applied directly after the [FROM](from-entity-sql.md) clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6834a-105">구문</span><span class="sxs-lookup"><span data-stu-id="6834a-105">Syntax</span></span>  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6834a-106">인수</span><span class="sxs-lookup"><span data-stu-id="6834a-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="6834a-107">Boolean 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-107">A Boolean type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6834a-108">설명</span><span class="sxs-lookup"><span data-stu-id="6834a-108">Remarks</span></span>  

 <span data-ttu-id="6834a-109">WHERE 절에는 Transact-sql에 대해 설명한 것과 동일한 의미 체계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-109">The WHERE clause has the same semantics as described for Transact-SQL.</span></span> <span data-ttu-id="6834a-110">WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-110">It restricts the objects produced by the query expression by limiting the elements of the source collections to those that pass the condition.</span></span>  
  
```sql  
select c from cs as c where e  
```  
  
 <span data-ttu-id="6834a-111">식 `e`에는 부운 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-111">The expression `e` must have the type Boolean.</span></span>  
  
 <span data-ttu-id="6834a-112">WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-112">The WHERE clause is applied directly after the FROM clause and before any grouping, ordering, or projection takes place.</span></span> <span data-ttu-id="6834a-113">FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6834a-113">All element names defined in the FROM clause are visible to the expression of the WHERE clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6834a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6834a-114">See also</span></span>

- [<span data-ttu-id="6834a-115">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="6834a-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="6834a-116">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="6834a-116">Query Expressions</span></span>](query-expressions-entity-sql.md)
