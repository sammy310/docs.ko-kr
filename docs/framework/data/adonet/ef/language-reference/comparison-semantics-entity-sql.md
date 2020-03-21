---
title: 비교 의미 체계(Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 57d81d4b581df76a4382ad5e1d72fe8250b10d43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150456"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="8a30f-102">비교 의미 체계(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8a30f-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="8a30f-103">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="8a30f-104">명시적 비교</span><span class="sxs-lookup"><span data-stu-id="8a30f-104">Explicit comparison</span></span>  
 <span data-ttu-id="8a30f-105">같음 연산:</span><span class="sxs-lookup"><span data-stu-id="8a30f-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="8a30f-106">!=</span><span class="sxs-lookup"><span data-stu-id="8a30f-106">!=</span></span>  
  
 <span data-ttu-id="8a30f-107">정렬 연산:</span><span class="sxs-lookup"><span data-stu-id="8a30f-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="8a30f-108">Null 허용 여부 연산:</span><span class="sxs-lookup"><span data-stu-id="8a30f-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="8a30f-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="8a30f-109">IS NULL</span></span>  
  
- <span data-ttu-id="8a30f-110">NULL이 아님</span><span class="sxs-lookup"><span data-stu-id="8a30f-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="8a30f-111">명시적 구분</span><span class="sxs-lookup"><span data-stu-id="8a30f-111">Explicit distinction</span></span>  
 <span data-ttu-id="8a30f-112">같음 구분:</span><span class="sxs-lookup"><span data-stu-id="8a30f-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="8a30f-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="8a30f-113">DISTINCT</span></span>  
  
- <span data-ttu-id="8a30f-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="8a30f-114">GROUP BY</span></span>  
  
 <span data-ttu-id="8a30f-115">정렬 구분:</span><span class="sxs-lookup"><span data-stu-id="8a30f-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="8a30f-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="8a30f-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="8a30f-117">암시적 구분</span><span class="sxs-lookup"><span data-stu-id="8a30f-117">Implicit distinction</span></span>  
 <span data-ttu-id="8a30f-118">Set 작업 및 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="8a30f-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="8a30f-119">UNION</span><span class="sxs-lookup"><span data-stu-id="8a30f-119">UNION</span></span>  
  
- <span data-ttu-id="8a30f-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="8a30f-120">INTERSECT</span></span>  
  
- <span data-ttu-id="8a30f-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="8a30f-121">EXCEPT</span></span>  
  
- <span data-ttu-id="8a30f-122">SET</span><span class="sxs-lookup"><span data-stu-id="8a30f-122">SET</span></span>  
  
- <span data-ttu-id="8a30f-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="8a30f-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="8a30f-124">항목 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="8a30f-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="8a30f-125">IN</span><span class="sxs-lookup"><span data-stu-id="8a30f-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="8a30f-126">지원되는 조합</span><span class="sxs-lookup"><span data-stu-id="8a30f-126">Supported Combinations</span></span>  
 <span data-ttu-id="8a30f-127">다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="8a30f-128">**유형**</span><span class="sxs-lookup"><span data-stu-id="8a30f-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="8a30f-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="8a30f-129">**!=**</span></span>|<span data-ttu-id="8a30f-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="8a30f-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="8a30f-131">**별개**</span><span class="sxs-lookup"><span data-stu-id="8a30f-131">**DISTINCT**</span></span>|<span data-ttu-id="8a30f-132">**연합**</span><span class="sxs-lookup"><span data-stu-id="8a30f-132">**UNION**</span></span><br /><br /> <span data-ttu-id="8a30f-133">**교차**</span><span class="sxs-lookup"><span data-stu-id="8a30f-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="8a30f-134">**제외한**</span><span class="sxs-lookup"><span data-stu-id="8a30f-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="8a30f-135">**설정**</span><span class="sxs-lookup"><span data-stu-id="8a30f-135">**SET**</span></span><br /><br /> <span data-ttu-id="8a30f-136">**겹치는**</span><span class="sxs-lookup"><span data-stu-id="8a30f-136">**OVERLAPS**</span></span>|<span data-ttu-id="8a30f-137">**에서**</span><span class="sxs-lookup"><span data-stu-id="8a30f-137">**IN**</span></span>|<span data-ttu-id="8a30f-138">**< <=**</span><span class="sxs-lookup"><span data-stu-id="8a30f-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="8a30f-139">**> >=**</span><span class="sxs-lookup"><span data-stu-id="8a30f-139">**>   >=**</span></span>|<span data-ttu-id="8a30f-140">**주문별**</span><span class="sxs-lookup"><span data-stu-id="8a30f-140">**ORDER BY**</span></span>|<span data-ttu-id="8a30f-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="8a30f-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="8a30f-142">**NULL이 아닙니다.**</span><span class="sxs-lookup"><span data-stu-id="8a30f-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="8a30f-143">엔터티 유형</span><span class="sxs-lookup"><span data-stu-id="8a30f-143">Entity type</span></span>|<span data-ttu-id="8a30f-144">참조<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="8a30f-145">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="8a30f-146">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="8a30f-147">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="8a30f-148"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-149"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-150">참조<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="8a30f-151">복합 형식</span><span class="sxs-lookup"><span data-stu-id="8a30f-151">Complex type</span></span>|<span data-ttu-id="8a30f-152"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-153"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-154"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-155"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-156"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-157"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-158"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="8a30f-159">행</span><span class="sxs-lookup"><span data-stu-id="8a30f-159">Row</span></span>|<span data-ttu-id="8a30f-160">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="8a30f-161">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="8a30f-162">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="8a30f-163"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-164"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-165">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="8a30f-166"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="8a30f-167">기본 형식</span><span class="sxs-lookup"><span data-stu-id="8a30f-167">Primitive type</span></span>|<span data-ttu-id="8a30f-168">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-168">Provider-specific</span></span>|<span data-ttu-id="8a30f-169">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-169">Provider-specific</span></span>|<span data-ttu-id="8a30f-170">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-170">Provider-specific</span></span>|<span data-ttu-id="8a30f-171">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-171">Provider-specific</span></span>|<span data-ttu-id="8a30f-172">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-172">Provider-specific</span></span>|<span data-ttu-id="8a30f-173">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-173">Provider-specific</span></span>|<span data-ttu-id="8a30f-174">공급자별</span><span class="sxs-lookup"><span data-stu-id="8a30f-174">Provider-specific</span></span>|  
|<span data-ttu-id="8a30f-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="8a30f-175">Multiset</span></span>|<span data-ttu-id="8a30f-176"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-177"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-178"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-179"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-180"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-181"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-182"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="8a30f-183">Ref</span><span class="sxs-lookup"><span data-stu-id="8a30f-183">Ref</span></span>|<span data-ttu-id="8a30f-184">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="8a30f-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="8a30f-186">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="8a30f-187">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="8a30f-188">Throw</span><span class="sxs-lookup"><span data-stu-id="8a30f-188">Throw</span></span>|<span data-ttu-id="8a30f-189">Throw</span><span class="sxs-lookup"><span data-stu-id="8a30f-189">Throw</span></span>|<span data-ttu-id="8a30f-190">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="8a30f-191">연결</span><span class="sxs-lookup"><span data-stu-id="8a30f-191">Association</span></span><br /><br /> <span data-ttu-id="8a30f-192">type</span><span class="sxs-lookup"><span data-stu-id="8a30f-192">type</span></span>|<span data-ttu-id="8a30f-193"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-194">Throw</span><span class="sxs-lookup"><span data-stu-id="8a30f-194">Throw</span></span>|<span data-ttu-id="8a30f-195">Throw</span><span class="sxs-lookup"><span data-stu-id="8a30f-195">Throw</span></span>|<span data-ttu-id="8a30f-196">Throw</span><span class="sxs-lookup"><span data-stu-id="8a30f-196">Throw</span></span>|<span data-ttu-id="8a30f-197"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-198"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="8a30f-199"><sup>던져 3</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="8a30f-200"><sup>1개</sup> 다음 예제와 같이 지정된 엔터티 형식 인스턴스의 참조는 암시적으로 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="8a30f-201">엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="8a30f-202">비교를 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="8a30f-203">예를 들어, 다음 쿼리는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-203">For example, the following query will throw an exception:</span></span>  
  
```sql  
SELECT p1, p2
FROM AdventureWorksEntities.Product AS p1
     JOIN AdventureWorksEntities.Product AS p2
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="8a30f-204"><sup>2개</sup> 복잡한 형식의 속성은 저장소로 전송되기 전에 병합되므로 모든 속성이 비교되는 한 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="8a30f-205">또한 <sup>4를 참조하십시오.</sup></span><span class="sxs-lookup"><span data-stu-id="8a30f-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="8a30f-206"><sup>3개</sup> Entity Framework 런타임은 지원되지 않는 사례를 검색하고 공급자/저장소를 참여하지 않고 의미 있는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="8a30f-207"><sup>4개</sup> 모든 속성을 비교하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="8a30f-208">텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a30f-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="8a30f-209"><sup>5개</sup> 참조의 모든 개별 요소를 비교합니다(엔터티 집합 이름과 엔터티 형식의 모든 키 속성포함).</span><span class="sxs-lookup"><span data-stu-id="8a30f-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a30f-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a30f-210">See also</span></span>

- [<span data-ttu-id="8a30f-211">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="8a30f-211">Entity SQL Overview</span></span>](entity-sql-overview.md)
