---
description: Entity SQL 빠른 참조에 대해 자세히 알아보세요.
title: Entity SQL 빠른 참조
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: ddac48bece1f0e9df737db295d4d028529ea290f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724559"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="ae32a-103">Entity SQL 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="ae32a-103">Entity SQL Quick Reference</span></span>

<span data-ttu-id="ae32a-104">이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-104">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="ae32a-105">이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-105">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="ae32a-106">리터럴</span><span class="sxs-lookup"><span data-stu-id="ae32a-106">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="ae32a-107">String</span><span class="sxs-lookup"><span data-stu-id="ae32a-107">String</span></span>  

 <span data-ttu-id="ae32a-108">유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-108">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="ae32a-109">유니코드 문자열 앞에 N이 붙습니다. 예를 들면 `N'hello'` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-109">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="ae32a-110">다음은 비유니코드 문자열 리터럴의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-110">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="ae32a-111">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-111">Output:</span></span>  
  
|<span data-ttu-id="ae32a-112">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-112">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-113">hello</span><span class="sxs-lookup"><span data-stu-id="ae32a-113">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="ae32a-114">DateTime</span><span class="sxs-lookup"><span data-stu-id="ae32a-114">DateTime</span></span>  

 <span data-ttu-id="ae32a-115">DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-115">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="ae32a-116">기본값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-116">There are no default values.</span></span>  
  
 <span data-ttu-id="ae32a-117">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-117">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="ae32a-118">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-118">Output:</span></span>  
  
|<span data-ttu-id="ae32a-119">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-119">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-120">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="ae32a-120">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="ae32a-121">정수</span><span class="sxs-lookup"><span data-stu-id="ae32a-121">Integer</span></span>  

 <span data-ttu-id="ae32a-122">Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-122">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="ae32a-123">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-123">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="ae32a-124">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-124">Output:</span></span>  
  
|<span data-ttu-id="ae32a-125">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-125">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-126">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-126">1</span></span>|  
|<span data-ttu-id="ae32a-127">2</span><span class="sxs-lookup"><span data-stu-id="ae32a-127">2</span></span>|  
|<span data-ttu-id="ae32a-128">3</span><span class="sxs-lookup"><span data-stu-id="ae32a-128">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="ae32a-129">기타</span><span class="sxs-lookup"><span data-stu-id="ae32a-129">Other</span></span>  

 <span data-ttu-id="ae32a-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-130">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="ae32a-131">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-131">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="ae32a-132">형식 생성자</span><span class="sxs-lookup"><span data-stu-id="ae32a-132">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="ae32a-133">ROW</span><span class="sxs-lookup"><span data-stu-id="ae32a-133">ROW</span></span>  

 <span data-ttu-id="ae32a-134">[ROW](row-entity-sql.md) 는 다음과 같이 구조적으로 형식화 된 익명의 값을 생성 합니다. `ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="ae32a-134">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="ae32a-135">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-135">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="ae32a-136">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-136">Output:</span></span>  
  
|<span data-ttu-id="ae32a-137">ProductID</span><span class="sxs-lookup"><span data-stu-id="ae32a-137">ProductID</span></span>|<span data-ttu-id="ae32a-138">Name</span><span class="sxs-lookup"><span data-stu-id="ae32a-138">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="ae32a-139">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-139">1</span></span>|<span data-ttu-id="ae32a-140">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="ae32a-140">Adjustable Race</span></span>|  
|<span data-ttu-id="ae32a-141">879</span><span class="sxs-lookup"><span data-stu-id="ae32a-141">879</span></span>|<span data-ttu-id="ae32a-142">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="ae32a-142">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="ae32a-143">712</span><span class="sxs-lookup"><span data-stu-id="ae32a-143">712</span></span>|<span data-ttu-id="ae32a-144">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="ae32a-144">AWC Logo Cap</span></span>|  
|<span data-ttu-id="ae32a-145">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-145">...</span></span>|<span data-ttu-id="ae32a-146">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-146">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="ae32a-147">MULTISET</span><span class="sxs-lookup"><span data-stu-id="ae32a-147">MULTISET</span></span>  

 <span data-ttu-id="ae32a-148">[MULTISET](multiset-entity-sql.md) 는 다음과 같은 컬렉션을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-148">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="ae32a-149">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="ae32a-149">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="ae32a-150">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-150">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="ae32a-151">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-151">Output:</span></span>  
  
|<span data-ttu-id="ae32a-152">ProductID</span><span class="sxs-lookup"><span data-stu-id="ae32a-152">ProductID</span></span>|<span data-ttu-id="ae32a-153">Name</span><span class="sxs-lookup"><span data-stu-id="ae32a-153">Name</span></span>|<span data-ttu-id="ae32a-154">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="ae32a-154">ProductNumber</span></span>|<span data-ttu-id="ae32a-155">…</span><span class="sxs-lookup"><span data-stu-id="ae32a-155">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="ae32a-156">842</span><span class="sxs-lookup"><span data-stu-id="ae32a-156">842</span></span>|<span data-ttu-id="ae32a-157">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="ae32a-157">Touring-Panniers, Large</span></span>|<span data-ttu-id="ae32a-158">PA-T100</span><span class="sxs-lookup"><span data-stu-id="ae32a-158">PA-T100</span></span>|<span data-ttu-id="ae32a-159">…</span><span class="sxs-lookup"><span data-stu-id="ae32a-159">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="ae32a-160">Object</span><span class="sxs-lookup"><span data-stu-id="ae32a-160">Object</span></span>  

 <span data-ttu-id="ae32a-161">[명명 된 형식 생성자](named-type-constructor-entity-sql.md) 는와 같은 사용자 정의 개체를 생성 `person("abc", 12)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-161">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="ae32a-162">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-162">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="ae32a-163">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-163">Output:</span></span>  
  
|<span data-ttu-id="ae32a-164">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="ae32a-164">SalesOrderDetailID</span></span>|<span data-ttu-id="ae32a-165">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="ae32a-165">CarrierTrackingNumber</span></span>|<span data-ttu-id="ae32a-166">OrderQty</span><span class="sxs-lookup"><span data-stu-id="ae32a-166">OrderQty</span></span>|<span data-ttu-id="ae32a-167">ProductID</span><span class="sxs-lookup"><span data-stu-id="ae32a-167">ProductID</span></span>|<span data-ttu-id="ae32a-168">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-168">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="ae32a-169">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-169">1</span></span>|<span data-ttu-id="ae32a-170">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="ae32a-170">4911-403C-98</span></span>|<span data-ttu-id="ae32a-171">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-171">1</span></span>|<span data-ttu-id="ae32a-172">776</span><span class="sxs-lookup"><span data-stu-id="ae32a-172">776</span></span>|<span data-ttu-id="ae32a-173">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-173">...</span></span>|  
|<span data-ttu-id="ae32a-174">2</span><span class="sxs-lookup"><span data-stu-id="ae32a-174">2</span></span>|<span data-ttu-id="ae32a-175">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="ae32a-175">4911-403C-98</span></span>|<span data-ttu-id="ae32a-176">3</span><span class="sxs-lookup"><span data-stu-id="ae32a-176">3</span></span>|<span data-ttu-id="ae32a-177">777</span><span class="sxs-lookup"><span data-stu-id="ae32a-177">777</span></span>|<span data-ttu-id="ae32a-178">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-178">...</span></span>|  
|<span data-ttu-id="ae32a-179">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-179">...</span></span>|<span data-ttu-id="ae32a-180">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-180">...</span></span>|<span data-ttu-id="ae32a-181">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-181">...</span></span>|<span data-ttu-id="ae32a-182">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-182">...</span></span>|<span data-ttu-id="ae32a-183">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-183">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="ae32a-184">참조</span><span class="sxs-lookup"><span data-stu-id="ae32a-184">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ae32a-185">REF</span><span class="sxs-lookup"><span data-stu-id="ae32a-185">REF</span></span>  

 <span data-ttu-id="ae32a-186">[REF](ref-entity-sql.md) 는 엔터티 형식 인스턴스에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-186">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="ae32a-187">예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-187">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="ae32a-188">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-188">Output:</span></span>  
  
|<span data-ttu-id="ae32a-189">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-189">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-190">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-190">1</span></span>|  
|<span data-ttu-id="ae32a-191">2</span><span class="sxs-lookup"><span data-stu-id="ae32a-191">2</span></span>|  
|<span data-ttu-id="ae32a-192">3</span><span class="sxs-lookup"><span data-stu-id="ae32a-192">3</span></span>|  
|<span data-ttu-id="ae32a-193">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-193">...</span></span>|  
  
 <span data-ttu-id="ae32a-194">다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-194">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="ae32a-195">속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-195">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="ae32a-196">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-196">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="ae32a-197">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-197">Output:</span></span>  
  
|<span data-ttu-id="ae32a-198">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-198">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-199">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="ae32a-199">Adjustable Race</span></span>|  
|<span data-ttu-id="ae32a-200">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="ae32a-200">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="ae32a-201">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="ae32a-201">AWC Logo Cap</span></span>|  
|<span data-ttu-id="ae32a-202">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-202">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="ae32a-203">DEREF</span><span class="sxs-lookup"><span data-stu-id="ae32a-203">DEREF</span></span>  

 <span data-ttu-id="ae32a-204">[DEREF](deref-entity-sql.md) 는 참조 값을 역참조 하 고이 역참조의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-204">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="ae32a-205">예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-205">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="ae32a-206">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-206">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="ae32a-207">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-207">Output:</span></span>  
  
|<span data-ttu-id="ae32a-208">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-208">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-209">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="ae32a-209">Adjustable Race</span></span>|  
|<span data-ttu-id="ae32a-210">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="ae32a-210">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="ae32a-211">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="ae32a-211">AWC Logo Cap</span></span>|  
|<span data-ttu-id="ae32a-212">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-212">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="ae32a-213">CREATEREF 및 KEY</span><span class="sxs-lookup"><span data-stu-id="ae32a-213">CREATEREF AND KEY</span></span>  

 <span data-ttu-id="ae32a-214">[CREATEREF](createref-entity-sql.md) 키를 전달 하는 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-214">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="ae32a-215">[Key](key-entity-sql.md) 는 형식 참조가 있는 식의 키 부분을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-215">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="ae32a-216">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-216">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="ae32a-217">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-217">Output:</span></span>  
  
|<span data-ttu-id="ae32a-218">ProductID</span><span class="sxs-lookup"><span data-stu-id="ae32a-218">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="ae32a-219">980</span><span class="sxs-lookup"><span data-stu-id="ae32a-219">980</span></span>|  
|<span data-ttu-id="ae32a-220">365</span><span class="sxs-lookup"><span data-stu-id="ae32a-220">365</span></span>|  
|<span data-ttu-id="ae32a-221">771</span><span class="sxs-lookup"><span data-stu-id="ae32a-221">771</span></span>|  
|<span data-ttu-id="ae32a-222">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-222">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="ae32a-223">Functions</span><span class="sxs-lookup"><span data-stu-id="ae32a-223">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="ae32a-224">Canonical</span><span class="sxs-lookup"><span data-stu-id="ae32a-224">Canonical</span></span>  

 <span data-ttu-id="ae32a-225">[정식 함수](canonical-functions.md) 에 대 한 네임 스페이스는와 같이 Edm입니다 `Edm.Length("string")` .</span><span class="sxs-lookup"><span data-stu-id="ae32a-225">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="ae32a-226">정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-226">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="ae32a-227">두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-227">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="ae32a-228">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-228">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="ae32a-229">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-229">Output:</span></span>  
  
|<span data-ttu-id="ae32a-230">NameLen</span><span class="sxs-lookup"><span data-stu-id="ae32a-230">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="ae32a-231">6</span><span class="sxs-lookup"><span data-stu-id="ae32a-231">6</span></span>|  
|<span data-ttu-id="ae32a-232">6</span><span class="sxs-lookup"><span data-stu-id="ae32a-232">6</span></span>|  
|<span data-ttu-id="ae32a-233">5</span><span class="sxs-lookup"><span data-stu-id="ae32a-233">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="ae32a-234">Microsoft 공급자 특정</span><span class="sxs-lookup"><span data-stu-id="ae32a-234">Microsoft Provider-Specific</span></span>  

 <span data-ttu-id="ae32a-235">[Microsoft 공급자별 함수](../sqlclient-for-ef-functions.md) 는 네임 스페이스에 있습니다 `SqlServer` .</span><span class="sxs-lookup"><span data-stu-id="ae32a-235">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="ae32a-236">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-236">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="ae32a-237">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-237">Output:</span></span>  
  
|<span data-ttu-id="ae32a-238">EmailLen</span><span class="sxs-lookup"><span data-stu-id="ae32a-238">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="ae32a-239">27</span><span class="sxs-lookup"><span data-stu-id="ae32a-239">27</span></span>|  
|<span data-ttu-id="ae32a-240">27</span><span class="sxs-lookup"><span data-stu-id="ae32a-240">27</span></span>|  
|<span data-ttu-id="ae32a-241">26</span><span class="sxs-lookup"><span data-stu-id="ae32a-241">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="ae32a-242">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ae32a-242">Namespaces</span></span>  

 <span data-ttu-id="ae32a-243">를 [사용 하 여](using-entity-sql.md) 쿼리 식에 사용 되는 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-243">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="ae32a-244">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-244">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="ae32a-245">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-245">Output:</span></span>  
  
|<span data-ttu-id="ae32a-246">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-246">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-247">aa</span><span class="sxs-lookup"><span data-stu-id="ae32a-247">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="ae32a-248">페이징</span><span class="sxs-lookup"><span data-stu-id="ae32a-248">Paging</span></span>  

 <span data-ttu-id="ae32a-249">[SKIP](skip-entity-sql.md) 및 [LIMIT](limit-entity-sql.md) 하위 절을 [ORDER by](order-by-entity-sql.md) 절에 선언 하 여 페이징을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-249">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="ae32a-250">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-250">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="ae32a-251">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-251">Output:</span></span>  
  
|<span data-ttu-id="ae32a-252">ID</span><span class="sxs-lookup"><span data-stu-id="ae32a-252">ID</span></span>|<span data-ttu-id="ae32a-253">속성</span><span class="sxs-lookup"><span data-stu-id="ae32a-253">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="ae32a-254">10</span><span class="sxs-lookup"><span data-stu-id="ae32a-254">10</span></span>|<span data-ttu-id="ae32a-255">Adina</span><span class="sxs-lookup"><span data-stu-id="ae32a-255">Adina</span></span>|  
|<span data-ttu-id="ae32a-256">11</span><span class="sxs-lookup"><span data-stu-id="ae32a-256">11</span></span>|<span data-ttu-id="ae32a-257">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="ae32a-257">Agcaoili</span></span>|  
|<span data-ttu-id="ae32a-258">12</span><span class="sxs-lookup"><span data-stu-id="ae32a-258">12</span></span>|<span data-ttu-id="ae32a-259">Aguilar</span><span class="sxs-lookup"><span data-stu-id="ae32a-259">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="ae32a-260">그룹화</span><span class="sxs-lookup"><span data-stu-id="ae32a-260">Grouping</span></span>  

 <span data-ttu-id="ae32a-261">[그룹화 방법](group-by-entity-sql.md) 쿼리 ([SELECT](select-entity-sql.md)) 식에서 반환 되는 개체가 배치 될 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-261">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="ae32a-262">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-262">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="ae32a-263">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-263">Output:</span></span>  
  
|<span data-ttu-id="ae32a-264">name</span><span class="sxs-lookup"><span data-stu-id="ae32a-264">name</span></span>|  
|----------|  
|<span data-ttu-id="ae32a-265">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="ae32a-265">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="ae32a-266">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="ae32a-266">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="ae32a-267">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="ae32a-267">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="ae32a-268">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-268">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="ae32a-269">탐색</span><span class="sxs-lookup"><span data-stu-id="ae32a-269">Navigation</span></span>  

 <span data-ttu-id="ae32a-270">관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-270">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="ae32a-271">[탐색](navigate-entity-sql.md) 은 .로 한정 된 관계 유형을 사용 합니다. \<namespace> \<relationship type name></span><span class="sxs-lookup"><span data-stu-id="ae32a-271">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="ae32a-272">\<T>To end의 카디널리티가 1 인 경우 Navigate는 Ref를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-272">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="ae32a-273">끝 end의 카디널리티가 n 인 경우<Ref \<T>> 컬렉션이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-273">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="ae32a-274">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-274">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="ae32a-275">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-275">Output:</span></span>  
  
|<span data-ttu-id="ae32a-276">AddressID</span><span class="sxs-lookup"><span data-stu-id="ae32a-276">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="ae32a-277">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-277">1</span></span>|  
|<span data-ttu-id="ae32a-278">2</span><span class="sxs-lookup"><span data-stu-id="ae32a-278">2</span></span>|  
|<span data-ttu-id="ae32a-279">3</span><span class="sxs-lookup"><span data-stu-id="ae32a-279">3</span></span>|  
|<span data-ttu-id="ae32a-280">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-280">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="ae32a-281">SELECT VALUE 및 SELECT</span><span class="sxs-lookup"><span data-stu-id="ae32a-281">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="ae32a-282">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="ae32a-282">SELECT VALUE</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="ae32a-283">에서는 암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-283">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="ae32a-284">SELECT VALUE 절 하나에는 항목 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-284">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="ae32a-285">이러한 절을 사용 하면 SELECT 절의 항목 주위에 행 래퍼가 생성 되지 않으며,와 같이 원하는 모양의 컬렉션이 생성 될 수 `SELECT VALUE a` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-285">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="ae32a-286">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-286">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="ae32a-287">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-287">Output:</span></span>  
  
|<span data-ttu-id="ae32a-288">Name</span><span class="sxs-lookup"><span data-stu-id="ae32a-288">Name</span></span>|  
|----------|  
|<span data-ttu-id="ae32a-289">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="ae32a-289">Adjustable Race</span></span>|  
|<span data-ttu-id="ae32a-290">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="ae32a-290">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="ae32a-291">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="ae32a-291">AWC Logo Cap</span></span>|  
|<span data-ttu-id="ae32a-292">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-292">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="ae32a-293">SELECT</span><span class="sxs-lookup"><span data-stu-id="ae32a-293">SELECT</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="ae32a-294">에서는 임의의 행을 만드는 행 생성자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-294">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="ae32a-295">SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-295">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="ae32a-296">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-296">Example:</span></span>  
  
 <span data-ttu-id="ae32a-297">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-297">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="ae32a-298">Name</span><span class="sxs-lookup"><span data-stu-id="ae32a-298">Name</span></span>|<span data-ttu-id="ae32a-299">ProductID</span><span class="sxs-lookup"><span data-stu-id="ae32a-299">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="ae32a-300">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="ae32a-300">Adjustable Race</span></span>|<span data-ttu-id="ae32a-301">1</span><span class="sxs-lookup"><span data-stu-id="ae32a-301">1</span></span>|  
|<span data-ttu-id="ae32a-302">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="ae32a-302">All-Purpose Bike Stand</span></span>|<span data-ttu-id="ae32a-303">879</span><span class="sxs-lookup"><span data-stu-id="ae32a-303">879</span></span>|  
|<span data-ttu-id="ae32a-304">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="ae32a-304">AWC Logo Cap</span></span>|<span data-ttu-id="ae32a-305">712</span><span class="sxs-lookup"><span data-stu-id="ae32a-305">712</span></span>|  
|<span data-ttu-id="ae32a-306">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-306">...</span></span>|<span data-ttu-id="ae32a-307">...</span><span class="sxs-lookup"><span data-stu-id="ae32a-307">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="ae32a-308">CASE 식</span><span class="sxs-lookup"><span data-stu-id="ae32a-308">CASE EXPRESSION</span></span>  

 <span data-ttu-id="ae32a-309">[Case 식은](case-entity-sql.md) 부울 식 집합을 계산 하 여 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae32a-309">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="ae32a-310">예제:</span><span class="sxs-lookup"><span data-stu-id="ae32a-310">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="ae32a-311">출력:</span><span class="sxs-lookup"><span data-stu-id="ae32a-311">Output:</span></span>  
  
|<span data-ttu-id="ae32a-312">값</span><span class="sxs-lookup"><span data-stu-id="ae32a-312">Value</span></span>|  
|-----------|  
|<span data-ttu-id="ae32a-313">TRUE</span><span class="sxs-lookup"><span data-stu-id="ae32a-313">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae32a-314">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae32a-314">See also</span></span>

- [<span data-ttu-id="ae32a-315">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="ae32a-315">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="ae32a-316">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="ae32a-316">Entity SQL Overview</span></span>](entity-sql-overview.md)
