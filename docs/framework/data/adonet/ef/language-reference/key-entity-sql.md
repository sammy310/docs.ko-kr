---
description: '자세한 정보: 키 (Entity SQL)'
title: KEY(Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 83901a378c3bcc92436df734a04cb7fdf639ecb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748299"
---
# <a name="key-entity-sql"></a><span data-ttu-id="7b79a-103">KEY(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7b79a-103">KEY (Entity SQL)</span></span>

<span data-ttu-id="7b79a-104">참조 또는 엔터티 식의 키를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-104">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b79a-105">구문</span><span class="sxs-lookup"><span data-stu-id="7b79a-105">Syntax</span></span>  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="7b79a-106">설명</span><span class="sxs-lookup"><span data-stu-id="7b79a-106">Remarks</span></span>  

 <span data-ttu-id="7b79a-107">엔터티 키에는 지정한 엔터티 또는 엔터티 참조의 올바른 순서대로 키 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-107">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="7b79a-108">여러 엔터티 집합이 같은 형식을 기반으로 할 수 있으므로 동일한 키가 각 엔터티 집합에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-108">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="7b79a-109">고유한 참조를 만들려면 `REF`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-109">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="7b79a-110">KEY 연산자의 반환 형식은 엔터티의 각 키에 해당하는 필드가 같은 순서대로 포함된 행 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-110">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="7b79a-111">다음 예제에서 Key 연산자는 BadOrder 엔터티에 대한 참조를 전달하고 해당 참조의 키 부분을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-111">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="7b79a-112">이 경우 `Id` 속성에 해당하는 필드 한 개만 포함된 레코드 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-112">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="7b79a-113">예제</span><span class="sxs-lookup"><span data-stu-id="7b79a-113">Example</span></span>  

 <span data-ttu-id="7b79a-114">다음 Entity SQL 쿼리에서는 KEY 연산자를 사용하여 형식 참조가 있는 식의 키 부분을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-114">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="7b79a-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7b79a-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7b79a-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7b79a-117">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7b79a-118">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7b79a-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a><span data-ttu-id="7b79a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b79a-119">See also</span></span>

- [<span data-ttu-id="7b79a-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7b79a-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="7b79a-121">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="7b79a-121">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="7b79a-122">행위자</span><span class="sxs-lookup"><span data-stu-id="7b79a-122">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="7b79a-123">DEREF</span><span class="sxs-lookup"><span data-stu-id="7b79a-123">DEREF</span></span>](deref-entity-sql.md)
