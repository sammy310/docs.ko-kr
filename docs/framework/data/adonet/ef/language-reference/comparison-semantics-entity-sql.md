---
title: 비교 의미 체계(Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 8d7868b0166f0a18824ec25e6cdf639deec665ac
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833937"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="2428a-102">비교 의미 체계(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2428a-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="2428a-103">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="2428a-104">명시적 비교</span><span class="sxs-lookup"><span data-stu-id="2428a-104">Explicit comparison</span></span>  
 <span data-ttu-id="2428a-105">같음 연산:</span><span class="sxs-lookup"><span data-stu-id="2428a-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="2428a-106">!=</span><span class="sxs-lookup"><span data-stu-id="2428a-106">!=</span></span>  
  
 <span data-ttu-id="2428a-107">정렬 연산:</span><span class="sxs-lookup"><span data-stu-id="2428a-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="2428a-108">Null 허용 여부 연산:</span><span class="sxs-lookup"><span data-stu-id="2428a-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="2428a-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="2428a-109">IS NULL</span></span>  
  
- <span data-ttu-id="2428a-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2428a-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="2428a-111">명시적 구분</span><span class="sxs-lookup"><span data-stu-id="2428a-111">Explicit distinction</span></span>  
 <span data-ttu-id="2428a-112">같음 구분:</span><span class="sxs-lookup"><span data-stu-id="2428a-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="2428a-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="2428a-113">DISTINCT</span></span>  
  
- <span data-ttu-id="2428a-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="2428a-114">GROUP BY</span></span>  
  
 <span data-ttu-id="2428a-115">정렬 구분:</span><span class="sxs-lookup"><span data-stu-id="2428a-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="2428a-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="2428a-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="2428a-117">암시적 구분</span><span class="sxs-lookup"><span data-stu-id="2428a-117">Implicit distinction</span></span>  
 <span data-ttu-id="2428a-118">Set 작업 및 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="2428a-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="2428a-119">UNION</span><span class="sxs-lookup"><span data-stu-id="2428a-119">UNION</span></span>  
  
- <span data-ttu-id="2428a-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="2428a-120">INTERSECT</span></span>  
  
- <span data-ttu-id="2428a-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="2428a-121">EXCEPT</span></span>  
  
- <span data-ttu-id="2428a-122">SET</span><span class="sxs-lookup"><span data-stu-id="2428a-122">SET</span></span>  
  
- <span data-ttu-id="2428a-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="2428a-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="2428a-124">항목 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="2428a-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="2428a-125">IN</span><span class="sxs-lookup"><span data-stu-id="2428a-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="2428a-126">지원되는 조합</span><span class="sxs-lookup"><span data-stu-id="2428a-126">Supported Combinations</span></span>  
 <span data-ttu-id="2428a-127">다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="2428a-128">**형식**</span><span class="sxs-lookup"><span data-stu-id="2428a-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="2428a-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="2428a-129">**!=**</span></span>|<span data-ttu-id="2428a-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="2428a-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="2428a-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="2428a-131">**DISTINCT**</span></span>|<span data-ttu-id="2428a-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="2428a-132">**UNION**</span></span><br /><br /> <span data-ttu-id="2428a-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="2428a-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="2428a-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="2428a-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="2428a-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="2428a-135">**SET**</span></span><br /><br /> <span data-ttu-id="2428a-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="2428a-136">**OVERLAPS**</span></span>|<span data-ttu-id="2428a-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="2428a-137">**IN**</span></span>|<span data-ttu-id="2428a-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="2428a-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="2428a-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="2428a-139">**>   >=**</span></span>|<span data-ttu-id="2428a-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="2428a-140">**ORDER BY**</span></span>|<span data-ttu-id="2428a-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="2428a-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="2428a-142">**NULL이 아님**</span><span class="sxs-lookup"><span data-stu-id="2428a-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="2428a-143">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="2428a-143">Entity type</span></span>|<span data-ttu-id="2428a-144">참조<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="2428a-145">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="2428a-146">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="2428a-147">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="2428a-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-150">참조<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="2428a-151">복합 형식</span><span class="sxs-lookup"><span data-stu-id="2428a-151">Complex type</span></span>|<span data-ttu-id="2428a-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="2428a-159">행</span><span class="sxs-lookup"><span data-stu-id="2428a-159">Row</span></span>|<span data-ttu-id="2428a-160">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="2428a-161">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="2428a-162">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="2428a-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-165">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="2428a-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="2428a-167">기본 형식</span><span class="sxs-lookup"><span data-stu-id="2428a-167">Primitive type</span></span>|<span data-ttu-id="2428a-168">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-168">Provider-specific</span></span>|<span data-ttu-id="2428a-169">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-169">Provider-specific</span></span>|<span data-ttu-id="2428a-170">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-170">Provider-specific</span></span>|<span data-ttu-id="2428a-171">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-171">Provider-specific</span></span>|<span data-ttu-id="2428a-172">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-172">Provider-specific</span></span>|<span data-ttu-id="2428a-173">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-173">Provider-specific</span></span>|<span data-ttu-id="2428a-174">공급자별</span><span class="sxs-lookup"><span data-stu-id="2428a-174">Provider-specific</span></span>|  
|<span data-ttu-id="2428a-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="2428a-175">Multiset</span></span>|<span data-ttu-id="2428a-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="2428a-183">Ref</span><span class="sxs-lookup"><span data-stu-id="2428a-183">Ref</span></span>|<span data-ttu-id="2428a-184">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="2428a-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="2428a-186">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="2428a-187">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="2428a-188">Throw</span><span class="sxs-lookup"><span data-stu-id="2428a-188">Throw</span></span>|<span data-ttu-id="2428a-189">Throw</span><span class="sxs-lookup"><span data-stu-id="2428a-189">Throw</span></span>|<span data-ttu-id="2428a-190">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="2428a-191">연결</span><span class="sxs-lookup"><span data-stu-id="2428a-191">Association</span></span><br /><br /> <span data-ttu-id="2428a-192">type</span><span class="sxs-lookup"><span data-stu-id="2428a-192">type</span></span>|<span data-ttu-id="2428a-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-194">Throw</span><span class="sxs-lookup"><span data-stu-id="2428a-194">Throw</span></span>|<span data-ttu-id="2428a-195">Throw</span><span class="sxs-lookup"><span data-stu-id="2428a-195">Throw</span></span>|<span data-ttu-id="2428a-196">Throw</span><span class="sxs-lookup"><span data-stu-id="2428a-196">Throw</span></span>|<span data-ttu-id="2428a-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="2428a-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="2428a-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="2428a-200"><sup>1</sup> 지정 된 엔터티 형식 인스턴스의 참조는 다음 예제와 같이 암시적으로 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="2428a-201">엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="2428a-202">비교를 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="2428a-203">예를 들어, 다음 쿼리는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="2428a-204"><sup>2</sup> 복합 형식의 속성은 저장소에 전송 되기 전에 결합 되므로 비교할 수 있게 됩니다 (모든 속성을 비교할 수 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="2428a-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="2428a-205">또한 <sup>4를</sup> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2428a-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="2428a-206"><sup>3</sup> Entity Framework 런타임은 지원 되지 않는 사례를 검색 하 고 공급자/저장소에 관여 하지 않고 의미 있는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="2428a-207"><sup>4</sup> 모든 속성을 비교 하려고 한 경우</span><span class="sxs-lookup"><span data-stu-id="2428a-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="2428a-208">텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="2428a-209"><sup>5</sup> 참조의 모든 개별 요소를 비교 합니다. 여기에는 엔터티 형식의 엔터티 집합 이름 및 모든 키 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2428a-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2428a-210">참조</span><span class="sxs-lookup"><span data-stu-id="2428a-210">See also</span></span>

- [<span data-ttu-id="2428a-211">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="2428a-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
