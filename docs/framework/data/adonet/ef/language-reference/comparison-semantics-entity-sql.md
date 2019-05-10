---
title: 비교 의미 체계(Entity SQL)
ms.date: 03/30/2017
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
ms.openlocfilehash: 2ca91861d4830321168e96fb200c4889dc33b04b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631713"
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="53c7c-102">비교 의미 체계(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="53c7c-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="53c7c-103">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="53c7c-104">명시적 비교</span><span class="sxs-lookup"><span data-stu-id="53c7c-104">Explicit comparison</span></span>  
 <span data-ttu-id="53c7c-105">같음 연산:</span><span class="sxs-lookup"><span data-stu-id="53c7c-105">Equality operations:</span></span>  
  
- =  
  
- <span data-ttu-id="53c7c-106">!=</span><span class="sxs-lookup"><span data-stu-id="53c7c-106">!=</span></span>  
  
 <span data-ttu-id="53c7c-107">정렬 연산:</span><span class="sxs-lookup"><span data-stu-id="53c7c-107">Ordering operations:</span></span>  
  
- <  
  
- \<=  
  
- \>  
  
- \>=  
  
 <span data-ttu-id="53c7c-108">Null 허용 여부 연산:</span><span class="sxs-lookup"><span data-stu-id="53c7c-108">Nullability operations:</span></span>  
  
- <span data-ttu-id="53c7c-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="53c7c-109">IS NULL</span></span>  
  
- <span data-ttu-id="53c7c-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="53c7c-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="53c7c-111">명시적 구분</span><span class="sxs-lookup"><span data-stu-id="53c7c-111">Explicit distinction</span></span>  
 <span data-ttu-id="53c7c-112">같음 구분:</span><span class="sxs-lookup"><span data-stu-id="53c7c-112">Equality distinction:</span></span>  
  
- <span data-ttu-id="53c7c-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="53c7c-113">DISTINCT</span></span>  
  
- <span data-ttu-id="53c7c-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="53c7c-114">GROUP BY</span></span>  
  
 <span data-ttu-id="53c7c-115">정렬 구분:</span><span class="sxs-lookup"><span data-stu-id="53c7c-115">Ordering distinction:</span></span>  
  
- <span data-ttu-id="53c7c-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="53c7c-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="53c7c-117">암시적 구분</span><span class="sxs-lookup"><span data-stu-id="53c7c-117">Implicit distinction</span></span>  
 <span data-ttu-id="53c7c-118">Set 작업 및 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="53c7c-118">Set operations and predicates (equality):</span></span>  
  
- <span data-ttu-id="53c7c-119">UNION</span><span class="sxs-lookup"><span data-stu-id="53c7c-119">UNION</span></span>  
  
- <span data-ttu-id="53c7c-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="53c7c-120">INTERSECT</span></span>  
  
- <span data-ttu-id="53c7c-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="53c7c-121">EXCEPT</span></span>  
  
- <span data-ttu-id="53c7c-122">SET</span><span class="sxs-lookup"><span data-stu-id="53c7c-122">SET</span></span>  
  
- <span data-ttu-id="53c7c-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="53c7c-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="53c7c-124">항목 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="53c7c-124">Item predicates (equality):</span></span>  
  
- <span data-ttu-id="53c7c-125">IN</span><span class="sxs-lookup"><span data-stu-id="53c7c-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="53c7c-126">지원되는 조합</span><span class="sxs-lookup"><span data-stu-id="53c7c-126">Supported Combinations</span></span>  
 <span data-ttu-id="53c7c-127">다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="53c7c-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="53c7c-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="53c7c-129">**\!=**</span><span class="sxs-lookup"><span data-stu-id="53c7c-129">**!=**</span></span>|<span data-ttu-id="53c7c-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="53c7c-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="53c7c-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="53c7c-131">**DISTINCT**</span></span>|<span data-ttu-id="53c7c-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="53c7c-132">**UNION**</span></span><br /><br /> <span data-ttu-id="53c7c-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="53c7c-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="53c7c-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="53c7c-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="53c7c-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="53c7c-135">**SET**</span></span><br /><br /> <span data-ttu-id="53c7c-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="53c7c-136">**OVERLAPS**</span></span>|<span data-ttu-id="53c7c-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="53c7c-137">**IN**</span></span>|<span data-ttu-id="53c7c-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="53c7c-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="53c7c-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="53c7c-139">**>   >=**</span></span>|<span data-ttu-id="53c7c-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="53c7c-140">**ORDER BY**</span></span>|<span data-ttu-id="53c7c-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="53c7c-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="53c7c-142">**NULL이 아님**</span><span class="sxs-lookup"><span data-stu-id="53c7c-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="53c7c-143">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="53c7c-143">Entity type</span></span>|<span data-ttu-id="53c7c-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="53c7c-145">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="53c7c-146">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="53c7c-147">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="53c7c-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="53c7c-151">복합 형식</span><span class="sxs-lookup"><span data-stu-id="53c7c-151">Complex type</span></span>|<span data-ttu-id="53c7c-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="53c7c-159">행</span><span class="sxs-lookup"><span data-stu-id="53c7c-159">Row</span></span>|<span data-ttu-id="53c7c-160">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="53c7c-161">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="53c7c-162">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="53c7c-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-165">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="53c7c-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="53c7c-167">기본 형식</span><span class="sxs-lookup"><span data-stu-id="53c7c-167">Primitive type</span></span>|<span data-ttu-id="53c7c-168">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-168">Provider-specific</span></span>|<span data-ttu-id="53c7c-169">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-169">Provider-specific</span></span>|<span data-ttu-id="53c7c-170">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-170">Provider-specific</span></span>|<span data-ttu-id="53c7c-171">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-171">Provider-specific</span></span>|<span data-ttu-id="53c7c-172">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-172">Provider-specific</span></span>|<span data-ttu-id="53c7c-173">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-173">Provider-specific</span></span>|<span data-ttu-id="53c7c-174">공급자별</span><span class="sxs-lookup"><span data-stu-id="53c7c-174">Provider-specific</span></span>|  
|<span data-ttu-id="53c7c-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="53c7c-175">Multiset</span></span>|<span data-ttu-id="53c7c-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="53c7c-183">Ref</span><span class="sxs-lookup"><span data-stu-id="53c7c-183">Ref</span></span>|<span data-ttu-id="53c7c-184">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="53c7c-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="53c7c-186">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="53c7c-187">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="53c7c-188">Throw</span><span class="sxs-lookup"><span data-stu-id="53c7c-188">Throw</span></span>|<span data-ttu-id="53c7c-189">Throw</span><span class="sxs-lookup"><span data-stu-id="53c7c-189">Throw</span></span>|<span data-ttu-id="53c7c-190">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="53c7c-191">연결</span><span class="sxs-lookup"><span data-stu-id="53c7c-191">Association</span></span><br /><br /> <span data-ttu-id="53c7c-192">type</span><span class="sxs-lookup"><span data-stu-id="53c7c-192">type</span></span>|<span data-ttu-id="53c7c-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-194">Throw</span><span class="sxs-lookup"><span data-stu-id="53c7c-194">Throw</span></span>|<span data-ttu-id="53c7c-195">Throw</span><span class="sxs-lookup"><span data-stu-id="53c7c-195">Throw</span></span>|<span data-ttu-id="53c7c-196">Throw</span><span class="sxs-lookup"><span data-stu-id="53c7c-196">Throw</span></span>|<span data-ttu-id="53c7c-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="53c7c-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="53c7c-200"><sup>1</sup>지정 된 엔터티 형식 인스턴스의 참조를 암시적으로 비교 되는 다음 예와 같이:</span><span class="sxs-lookup"><span data-stu-id="53c7c-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="53c7c-201">엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="53c7c-202">비교를 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="53c7c-203">예를 들어, 다음 쿼리는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="53c7c-204"><sup>2</sup>복합 형식의 속성 (으로 해당 속성이 모두 비교 가능한) 비교할 수 있는 상태가 저장소에 전송 되기 전에 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="53c7c-205">또한 참조 <sup>4입니다.</sup></span><span class="sxs-lookup"><span data-stu-id="53c7c-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="53c7c-206"><sup>3</sup>Entity Framework 런타임에서 지원 되지 않는 경우를 검색 하 고 공급자/저장소 개입 없이도 의미 있는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="53c7c-207"><sup>4</sup>모든 속성을 비교 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="53c7c-208">텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53c7c-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="53c7c-209"><sup>5</sup>참조의 모든 개별 요소가 비교 (엔터티 집합 이름 및 엔터티 형식의 모든 키 속성 포함).</span><span class="sxs-lookup"><span data-stu-id="53c7c-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c7c-210">참고자료</span><span class="sxs-lookup"><span data-stu-id="53c7c-210">See also</span></span>

- [<span data-ttu-id="53c7c-211">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="53c7c-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
