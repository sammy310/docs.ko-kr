---
description: '자세한 정보: DEREF (Entity SQL)'
title: DEREF(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 9d0f29123c1459c6eab21ea9cd860b5c9e77f591
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724728"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="2bce1-103">DEREF(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2bce1-103">DEREF (Entity SQL)</span></span>

<span data-ttu-id="2bce1-104">참조 값을 역참조하고 이 역참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-104">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bce1-105">구문</span><span class="sxs-lookup"><span data-stu-id="2bce1-105">Syntax</span></span>  
  
```sql  
SELECT DEREF ( o.expression ) FROM Table AS o;
```  
  
## <a name="arguments"></a><span data-ttu-id="2bce1-106">인수</span><span class="sxs-lookup"><span data-stu-id="2bce1-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="2bce1-107">컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bce1-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="2bce1-108">Return Value</span></span>  

 <span data-ttu-id="2bce1-109">참조되는 엔터티의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-109">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bce1-110">설명</span><span class="sxs-lookup"><span data-stu-id="2bce1-110">Remarks</span></span>  

 <span data-ttu-id="2bce1-111">DEREF 연산자는 참조 값을 역참조하고 이 역참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-111">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="2bce1-112">예를 들어 `r` 가 ref 형식의 참조 인 경우 \<T> `Deref(r)` 은에서 참조 하는 엔터티를 `T` 생성 하는 형식의 식입니다 `r` .</span><span class="sxs-lookup"><span data-stu-id="2bce1-112">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="2bce1-113">참조 값이 null이거나 현수 참조(참조 대상이 존재하지 않음)인 경우 DEREF 연산자의 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-113">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bce1-114">예제</span><span class="sxs-lookup"><span data-stu-id="2bce1-114">Example</span></span>  

 <span data-ttu-id="2bce1-115">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 DEREF 연산자를 사용하여 참조 값을 역참조하고 이 역참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-115">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="2bce1-116">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2bce1-117">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="2bce1-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2bce1-118">[방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-118">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="2bce1-119">다음 쿼리를 ExecutePrimitiveTypeQuery 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2bce1-119">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DEREF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="2bce1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bce1-120">See also</span></span>

- [<span data-ttu-id="2bce1-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="2bce1-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="2bce1-122">행위자</span><span class="sxs-lookup"><span data-stu-id="2bce1-122">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="2bce1-123">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="2bce1-123">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="2bce1-124">KEY</span><span class="sxs-lookup"><span data-stu-id="2bce1-124">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="2bce1-125">nullable 구조적 형식</span><span class="sxs-lookup"><span data-stu-id="2bce1-125">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
