---
description: '자세한 정보: ISNULL (Entity SQL)'
title: ISNULL(Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 1dbaf964facf089ab6714ebd58baf8b040288cff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748494"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="37b1f-103">ISNULL(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="37b1f-103">ISNULL (Entity SQL)</span></span>

<span data-ttu-id="37b1f-104">쿼리 식이 null인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-104">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b1f-105">구문</span><span class="sxs-lookup"><span data-stu-id="37b1f-105">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="37b1f-106">인수</span><span class="sxs-lookup"><span data-stu-id="37b1f-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="37b1f-107">모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-107">Any valid query expression.</span></span> <span data-ttu-id="37b1f-108">컬렉션이거나, 컬렉션 멤버를 포함하거나, 컬렉션 형식 속성을 가진 레코드 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-108">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="37b1f-109">NOT</span><span class="sxs-lookup"><span data-stu-id="37b1f-109">NOT</span></span>  
 <span data-ttu-id="37b1f-110">IS NULL의 EDM 부울 결과를 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-110">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37b1f-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="37b1f-111">Return Value</span></span>  

 <span data-ttu-id="37b1f-112">`true`이 null을 반환하면 `expression`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-112">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b1f-113">설명</span><span class="sxs-lookup"><span data-stu-id="37b1f-113">Remarks</span></span>  

 <span data-ttu-id="37b1f-114">외부 조인의 요소가 null인지 여부를 확인하려면 `IS NULL`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-114">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="37b1f-115">멤버에 실제 값이 있는지 여부를 확인하려면 `IS NULL`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-115">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="37b1f-116">다음 표에서는 일부 패턴에 대한 `IS NULL`의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-116">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="37b1f-117">공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-117">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="37b1f-118">무늬</span><span class="sxs-lookup"><span data-stu-id="37b1f-118">Pattern</span></span>|<span data-ttu-id="37b1f-119">동작</span><span class="sxs-lookup"><span data-stu-id="37b1f-119">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="37b1f-120">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-120">null IS NULL</span></span>|<span data-ttu-id="37b1f-121">`true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-121">Returns `true`.</span></span>|  
|<span data-ttu-id="37b1f-122">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-122">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="37b1f-123">`true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-123">Returns `true`.</span></span>|  
|<span data-ttu-id="37b1f-124">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-124">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="37b1f-125">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-125">Throws an error.</span></span>|  
|<span data-ttu-id="37b1f-126">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-126">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="37b1f-127">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-127">Throws an error.</span></span>|  
|<span data-ttu-id="37b1f-128">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-128">EntityType IS NULL</span></span>|<span data-ttu-id="37b1f-129">`true` 또는 `false`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-129">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="37b1f-130">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-130">ComplexType IS NULL</span></span>|<span data-ttu-id="37b1f-131">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-131">Throws an error.</span></span>|  
|<span data-ttu-id="37b1f-132">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="37b1f-132">RowType IS NULL</span></span>|<span data-ttu-id="37b1f-133">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-133">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37b1f-134">예제</span><span class="sxs-lookup"><span data-stu-id="37b1f-134">Example</span></span>  

 <span data-ttu-id="37b1f-135">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 IS NOT NULL 연산자를 사용하여 쿼리 식이 null이 아닌지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-135">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="37b1f-136">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-136">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="37b1f-137">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="37b1f-137">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="37b1f-138">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-138">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="37b1f-139">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="37b1f-139">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="37b1f-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37b1f-140">See also</span></span>

- [<span data-ttu-id="37b1f-141">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="37b1f-141">Entity SQL Reference</span></span>](entity-sql-reference.md)
