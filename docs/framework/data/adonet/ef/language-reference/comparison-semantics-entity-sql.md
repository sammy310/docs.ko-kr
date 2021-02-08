---
description: '자세한 정보: 비교 의미 체계 (Entity SQL)'
title: 비교 의미 체계(Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: b1c832cb6f2903073b1c6be806c73823b1f4a220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786435"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="f5a2e-103">비교 의미 체계(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f5a2e-103">Comparison Semantics (Entity SQL)</span></span>

<span data-ttu-id="f5a2e-104">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-104">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="f5a2e-105">명시적 비교</span><span class="sxs-lookup"><span data-stu-id="f5a2e-105">Explicit comparison</span></span>  

 <span data-ttu-id="f5a2e-106">같음 연산:</span><span class="sxs-lookup"><span data-stu-id="f5a2e-106">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="f5a2e-107">!=</span><span class="sxs-lookup"><span data-stu-id="f5a2e-107">!=</span></span>  
  
 <span data-ttu-id="f5a2e-108">정렬 연산:</span><span class="sxs-lookup"><span data-stu-id="f5a2e-108">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="f5a2e-109">Null 허용 여부 연산:</span><span class="sxs-lookup"><span data-stu-id="f5a2e-109">Nullability operations:</span></span>  
  
- <span data-ttu-id="f5a2e-110">IS NULL</span><span class="sxs-lookup"><span data-stu-id="f5a2e-110">IS NULL</span></span>  
  
- <span data-ttu-id="f5a2e-111">NULL이 아님</span><span class="sxs-lookup"><span data-stu-id="f5a2e-111">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="f5a2e-112">명시적 구분</span><span class="sxs-lookup"><span data-stu-id="f5a2e-112">Explicit distinction</span></span>  

 <span data-ttu-id="f5a2e-113">같음 구분:</span><span class="sxs-lookup"><span data-stu-id="f5a2e-113">Equality distinction:</span></span>  
  
- <span data-ttu-id="f5a2e-114">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="f5a2e-114">DISTINCT</span></span>  
  
- <span data-ttu-id="f5a2e-115">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="f5a2e-115">GROUP BY</span></span>  
  
 <span data-ttu-id="f5a2e-116">정렬 구분:</span><span class="sxs-lookup"><span data-stu-id="f5a2e-116">Ordering distinction:</span></span>  
  
- <span data-ttu-id="f5a2e-117">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="f5a2e-117">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="f5a2e-118">암시적 구분</span><span class="sxs-lookup"><span data-stu-id="f5a2e-118">Implicit distinction</span></span>  

 <span data-ttu-id="f5a2e-119">Set 작업 및 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="f5a2e-119">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="f5a2e-120">UNION</span><span class="sxs-lookup"><span data-stu-id="f5a2e-120">UNION</span></span>  
  
- <span data-ttu-id="f5a2e-121">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="f5a2e-121">INTERSECT</span></span>  
  
- <span data-ttu-id="f5a2e-122">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="f5a2e-122">EXCEPT</span></span>  
  
- <span data-ttu-id="f5a2e-123">SET</span><span class="sxs-lookup"><span data-stu-id="f5a2e-123">SET</span></span>  
  
- <span data-ttu-id="f5a2e-124">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="f5a2e-124">OVERLAPS</span></span>  
  
 <span data-ttu-id="f5a2e-125">항목 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="f5a2e-125">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="f5a2e-126">IN</span><span class="sxs-lookup"><span data-stu-id="f5a2e-126">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="f5a2e-127">지원되는 조합</span><span class="sxs-lookup"><span data-stu-id="f5a2e-127">Supported Combinations</span></span>  

 <span data-ttu-id="f5a2e-128">다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-128">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="f5a2e-129">**유형**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-129">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="f5a2e-130">**!=**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-130">**!=**</span></span>|<span data-ttu-id="f5a2e-131">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-131">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="f5a2e-132">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-132">**DISTINCT**</span></span>|<span data-ttu-id="f5a2e-133">**UNION**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-133">**UNION**</span></span><br /><br /> <span data-ttu-id="f5a2e-134">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-134">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="f5a2e-135">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-135">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="f5a2e-136">**SET**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-136">**SET**</span></span><br /><br /> <span data-ttu-id="f5a2e-137">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-137">**OVERLAPS**</span></span>|<span data-ttu-id="f5a2e-138">**IN**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-138">**IN**</span></span>|<span data-ttu-id="f5a2e-139">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-139">**<   <=**</span></span><br /><br /> <span data-ttu-id="f5a2e-140">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-140">**>   >=**</span></span>|<span data-ttu-id="f5a2e-141">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-141">**ORDER BY**</span></span>|<span data-ttu-id="f5a2e-142">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-142">**IS NULL**</span></span><br /><br /> <span data-ttu-id="f5a2e-143">**NULL이 아님**</span><span class="sxs-lookup"><span data-stu-id="f5a2e-143">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="f5a2e-144">엔터티 유형</span><span class="sxs-lookup"><span data-stu-id="f5a2e-144">Entity type</span></span>|<span data-ttu-id="f5a2e-145">참조<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-145">Ref<sup>1</sup></span></span>|<span data-ttu-id="f5a2e-146">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="f5a2e-147">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="f5a2e-148">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-148">All properties<sup>2</sup></span></span>|<span data-ttu-id="f5a2e-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-150">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-150">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-151">참조<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-151">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="f5a2e-152">복합 형식</span><span class="sxs-lookup"><span data-stu-id="f5a2e-152">Complex type</span></span>|<span data-ttu-id="f5a2e-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-158">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-159">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-159">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f5a2e-160">행</span><span class="sxs-lookup"><span data-stu-id="f5a2e-160">Row</span></span>|<span data-ttu-id="f5a2e-161">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="f5a2e-162">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="f5a2e-163">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-163">All properties<sup>4</sup></span></span>|<span data-ttu-id="f5a2e-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-165">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-165">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-166">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-166">All properties<sup>4</sup></span></span>|<span data-ttu-id="f5a2e-167">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-167">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f5a2e-168">기본 형식</span><span class="sxs-lookup"><span data-stu-id="f5a2e-168">Primitive type</span></span>|<span data-ttu-id="f5a2e-169">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-169">Provider-specific</span></span>|<span data-ttu-id="f5a2e-170">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-170">Provider-specific</span></span>|<span data-ttu-id="f5a2e-171">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-171">Provider-specific</span></span>|<span data-ttu-id="f5a2e-172">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-172">Provider-specific</span></span>|<span data-ttu-id="f5a2e-173">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-173">Provider-specific</span></span>|<span data-ttu-id="f5a2e-174">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-174">Provider-specific</span></span>|<span data-ttu-id="f5a2e-175">공급자별</span><span class="sxs-lookup"><span data-stu-id="f5a2e-175">Provider-specific</span></span>|  
|<span data-ttu-id="f5a2e-176">Multiset</span><span class="sxs-lookup"><span data-stu-id="f5a2e-176">Multiset</span></span>|<span data-ttu-id="f5a2e-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-182">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-183">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-183">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f5a2e-184">Ref</span><span class="sxs-lookup"><span data-stu-id="f5a2e-184">Ref</span></span>|<span data-ttu-id="f5a2e-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="f5a2e-186">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="f5a2e-187">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="f5a2e-188">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-188">Yes<sup>5</sup></span></span>|<span data-ttu-id="f5a2e-189">Throw</span><span class="sxs-lookup"><span data-stu-id="f5a2e-189">Throw</span></span>|<span data-ttu-id="f5a2e-190">Throw</span><span class="sxs-lookup"><span data-stu-id="f5a2e-190">Throw</span></span>|<span data-ttu-id="f5a2e-191">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-191">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="f5a2e-192">연결</span><span class="sxs-lookup"><span data-stu-id="f5a2e-192">Association</span></span><br /><br /> <span data-ttu-id="f5a2e-193">형식</span><span class="sxs-lookup"><span data-stu-id="f5a2e-193">type</span></span>|<span data-ttu-id="f5a2e-194">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-194">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-195">Throw</span><span class="sxs-lookup"><span data-stu-id="f5a2e-195">Throw</span></span>|<span data-ttu-id="f5a2e-196">Throw</span><span class="sxs-lookup"><span data-stu-id="f5a2e-196">Throw</span></span>|<span data-ttu-id="f5a2e-197">Throw</span><span class="sxs-lookup"><span data-stu-id="f5a2e-197">Throw</span></span>|<span data-ttu-id="f5a2e-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-199">Throw<sup>3</sup></span></span>|<span data-ttu-id="f5a2e-200">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f5a2e-200">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="f5a2e-201"><sup>1</sup> 지정 된 엔터티 형식 인스턴스의 참조는 다음 예제와 같이 암시적으로 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-201"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="f5a2e-202">엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-202">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="f5a2e-203">비교를 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-203">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="f5a2e-204">예를 들어, 다음 쿼리는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-204">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="f5a2e-205"><sup>2</sup> 복합 형식의 속성은 저장소에 전송 되기 전에 결합 되므로 비교할 수 있게 됩니다 (모든 속성을 비교할 수 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="f5a2e-205"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="f5a2e-206">또한 <sup>4를</sup> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-206">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="f5a2e-207"><sup>3</sup> Entity Framework 런타임은 지원 되지 않는 사례를 검색 하 고 공급자/저장소에 관여 하지 않고 의미 있는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-207"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="f5a2e-208"><sup>4</sup> 모든 속성을 비교 하려고 한 경우</span><span class="sxs-lookup"><span data-stu-id="f5a2e-208"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="f5a2e-209">텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-209">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="f5a2e-210"><sup>5</sup> 참조의 모든 개별 요소를 비교 합니다. 여기에는 엔터티 형식의 엔터티 집합 이름 및 모든 키 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5a2e-210"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a2e-211">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5a2e-211">See also</span></span>

- [<span data-ttu-id="f5a2e-212">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="f5a2e-212">Entity SQL Overview</span></span>](entity-sql-overview.md)
