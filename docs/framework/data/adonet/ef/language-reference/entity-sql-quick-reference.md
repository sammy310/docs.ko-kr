---
title: Entity SQL 빠른 참조
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 9ccfc461d394af8804c960ebf460e7fbfb025b64
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833870"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="a800a-102">Entity SQL 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="a800a-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="a800a-103">이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="a800a-104">이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="a800a-105">리터럴</span><span class="sxs-lookup"><span data-stu-id="a800a-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="a800a-106">문자열</span><span class="sxs-lookup"><span data-stu-id="a800a-106">String</span></span>  
 <span data-ttu-id="a800a-107">유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="a800a-108">유니코드 문자열 앞에 N이 붙습니다. 예를 들어 `N'hello'`입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="a800a-109">다음은 비유니코드 문자열 리터럴의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="a800a-110">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-110">Output:</span></span>  
  
|<span data-ttu-id="a800a-111">값</span><span class="sxs-lookup"><span data-stu-id="a800a-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-112">hello</span><span class="sxs-lookup"><span data-stu-id="a800a-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="a800a-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="a800a-113">DateTime</span></span>  
 <span data-ttu-id="a800a-114">DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="a800a-115">기본값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-115">There are no default values.</span></span>  
  
 <span data-ttu-id="a800a-116">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="a800a-117">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-117">Output:</span></span>  
  
|<span data-ttu-id="a800a-118">값</span><span class="sxs-lookup"><span data-stu-id="a800a-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="a800a-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="a800a-120">Integer</span><span class="sxs-lookup"><span data-stu-id="a800a-120">Integer</span></span>  
 <span data-ttu-id="a800a-121">Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="a800a-122">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="a800a-123">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-123">Output:</span></span>  
  
|<span data-ttu-id="a800a-124">값</span><span class="sxs-lookup"><span data-stu-id="a800a-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-125">1</span><span class="sxs-lookup"><span data-stu-id="a800a-125">1</span></span>|  
|<span data-ttu-id="a800a-126">2</span><span class="sxs-lookup"><span data-stu-id="a800a-126">2</span></span>|  
|<span data-ttu-id="a800a-127">3</span><span class="sxs-lookup"><span data-stu-id="a800a-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="a800a-128">기타</span><span class="sxs-lookup"><span data-stu-id="a800a-128">Other</span></span>  
 <span data-ttu-id="a800a-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="a800a-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="a800a-131">형식 생성자</span><span class="sxs-lookup"><span data-stu-id="a800a-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="a800a-132">ROW</span><span class="sxs-lookup"><span data-stu-id="a800a-132">ROW</span></span>  
 <span data-ttu-id="a800a-133">[ROW](row-entity-sql.md) 는 다음과 같이 구조적으로 형식화 된 익명 (레코드) 값을 생성 `ROW(1 AS myNumber, ‘Name’ AS myName).`입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="a800a-134">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="a800a-135">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-135">Output:</span></span>  
  
|<span data-ttu-id="a800a-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="a800a-136">ProductID</span></span>|<span data-ttu-id="a800a-137">이름</span><span class="sxs-lookup"><span data-stu-id="a800a-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="a800a-138">1</span><span class="sxs-lookup"><span data-stu-id="a800a-138">1</span></span>|<span data-ttu-id="a800a-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a800a-139">Adjustable Race</span></span>|  
|<span data-ttu-id="a800a-140">879</span><span class="sxs-lookup"><span data-stu-id="a800a-140">879</span></span>|<span data-ttu-id="a800a-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a800a-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a800a-142">712</span><span class="sxs-lookup"><span data-stu-id="a800a-142">712</span></span>|<span data-ttu-id="a800a-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a800a-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a800a-144">...</span><span class="sxs-lookup"><span data-stu-id="a800a-144">...</span></span>|<span data-ttu-id="a800a-145">...</span><span class="sxs-lookup"><span data-stu-id="a800a-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="a800a-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="a800a-146">MULTISET</span></span>  
 <span data-ttu-id="a800a-147">[MULTISET](multiset-entity-sql.md) 는 다음과 같은 컬렉션을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="a800a-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="a800a-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="a800a-149">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="a800a-150">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-150">Output:</span></span>  
  
|<span data-ttu-id="a800a-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="a800a-151">ProductID</span></span>|<span data-ttu-id="a800a-152">이름</span><span class="sxs-lookup"><span data-stu-id="a800a-152">Name</span></span>|<span data-ttu-id="a800a-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="a800a-153">ProductNumber</span></span>|<span data-ttu-id="a800a-154">…</span><span class="sxs-lookup"><span data-stu-id="a800a-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="a800a-155">842</span><span class="sxs-lookup"><span data-stu-id="a800a-155">842</span></span>|<span data-ttu-id="a800a-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="a800a-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="a800a-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="a800a-157">PA-T100</span></span>|<span data-ttu-id="a800a-158">…</span><span class="sxs-lookup"><span data-stu-id="a800a-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="a800a-159">Object</span><span class="sxs-lookup"><span data-stu-id="a800a-159">Object</span></span>  
 <span data-ttu-id="a800a-160">[명명 된 형식 생성자](named-type-constructor-entity-sql.md) `person("abc", 12)`과 같은 사용자 정의 개체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="a800a-161">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="a800a-162">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-162">Output:</span></span>  
  
|<span data-ttu-id="a800a-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="a800a-163">SalesOrderDetailID</span></span>|<span data-ttu-id="a800a-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="a800a-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="a800a-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="a800a-165">OrderQty</span></span>|<span data-ttu-id="a800a-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="a800a-166">ProductID</span></span>|<span data-ttu-id="a800a-167">...</span><span class="sxs-lookup"><span data-stu-id="a800a-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="a800a-168">1</span><span class="sxs-lookup"><span data-stu-id="a800a-168">1</span></span>|<span data-ttu-id="a800a-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="a800a-169">4911-403C-98</span></span>|<span data-ttu-id="a800a-170">1</span><span class="sxs-lookup"><span data-stu-id="a800a-170">1</span></span>|<span data-ttu-id="a800a-171">776</span><span class="sxs-lookup"><span data-stu-id="a800a-171">776</span></span>|<span data-ttu-id="a800a-172">...</span><span class="sxs-lookup"><span data-stu-id="a800a-172">...</span></span>|  
|<span data-ttu-id="a800a-173">2</span><span class="sxs-lookup"><span data-stu-id="a800a-173">2</span></span>|<span data-ttu-id="a800a-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="a800a-174">4911-403C-98</span></span>|<span data-ttu-id="a800a-175">3</span><span class="sxs-lookup"><span data-stu-id="a800a-175">3</span></span>|<span data-ttu-id="a800a-176">777</span><span class="sxs-lookup"><span data-stu-id="a800a-176">777</span></span>|<span data-ttu-id="a800a-177">...</span><span class="sxs-lookup"><span data-stu-id="a800a-177">...</span></span>|  
|<span data-ttu-id="a800a-178">...</span><span class="sxs-lookup"><span data-stu-id="a800a-178">...</span></span>|<span data-ttu-id="a800a-179">...</span><span class="sxs-lookup"><span data-stu-id="a800a-179">...</span></span>|<span data-ttu-id="a800a-180">...</span><span class="sxs-lookup"><span data-stu-id="a800a-180">...</span></span>|<span data-ttu-id="a800a-181">...</span><span class="sxs-lookup"><span data-stu-id="a800a-181">...</span></span>|<span data-ttu-id="a800a-182">...</span><span class="sxs-lookup"><span data-stu-id="a800a-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="a800a-183">참조</span><span class="sxs-lookup"><span data-stu-id="a800a-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="a800a-184">REF</span><span class="sxs-lookup"><span data-stu-id="a800a-184">REF</span></span>  
 <span data-ttu-id="a800a-185">[REF](ref-entity-sql.md) 는 엔터티 형식 인스턴스에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="a800a-186">예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="a800a-187">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-187">Output:</span></span>  
  
|<span data-ttu-id="a800a-188">값</span><span class="sxs-lookup"><span data-stu-id="a800a-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-189">1</span><span class="sxs-lookup"><span data-stu-id="a800a-189">1</span></span>|  
|<span data-ttu-id="a800a-190">2</span><span class="sxs-lookup"><span data-stu-id="a800a-190">2</span></span>|  
|<span data-ttu-id="a800a-191">3</span><span class="sxs-lookup"><span data-stu-id="a800a-191">3</span></span>|  
|<span data-ttu-id="a800a-192">...</span><span class="sxs-lookup"><span data-stu-id="a800a-192">...</span></span>|  
  
 <span data-ttu-id="a800a-193">다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="a800a-194">속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="a800a-195">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="a800a-196">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-196">Output:</span></span>  
  
|<span data-ttu-id="a800a-197">값</span><span class="sxs-lookup"><span data-stu-id="a800a-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a800a-198">Adjustable Race</span></span>|  
|<span data-ttu-id="a800a-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a800a-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a800a-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a800a-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a800a-201">...</span><span class="sxs-lookup"><span data-stu-id="a800a-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="a800a-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="a800a-202">DEREF</span></span>  
 <span data-ttu-id="a800a-203">[DEREF](deref-entity-sql.md) 는 참조 값을 역참조 하 고이 역참조의 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="a800a-204">예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="a800a-205">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="a800a-206">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-206">Output:</span></span>  
  
|<span data-ttu-id="a800a-207">값</span><span class="sxs-lookup"><span data-stu-id="a800a-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a800a-208">Adjustable Race</span></span>|  
|<span data-ttu-id="a800a-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a800a-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a800a-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a800a-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a800a-211">...</span><span class="sxs-lookup"><span data-stu-id="a800a-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="a800a-212">CREATEREF 및 KEY</span><span class="sxs-lookup"><span data-stu-id="a800a-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="a800a-213">[CREATEREF](createref-entity-sql.md) 키를 전달 하는 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="a800a-214">[Key](key-entity-sql.md) 는 형식 참조가 있는 식의 키 부분을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="a800a-215">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="a800a-216">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-216">Output:</span></span>  
  
|<span data-ttu-id="a800a-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="a800a-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="a800a-218">980</span><span class="sxs-lookup"><span data-stu-id="a800a-218">980</span></span>|  
|<span data-ttu-id="a800a-219">365</span><span class="sxs-lookup"><span data-stu-id="a800a-219">365</span></span>|  
|<span data-ttu-id="a800a-220">771</span><span class="sxs-lookup"><span data-stu-id="a800a-220">771</span></span>|  
|<span data-ttu-id="a800a-221">...</span><span class="sxs-lookup"><span data-stu-id="a800a-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="a800a-222">함수</span><span class="sxs-lookup"><span data-stu-id="a800a-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="a800a-223">정식</span><span class="sxs-lookup"><span data-stu-id="a800a-223">Canonical</span></span>  
 <span data-ttu-id="a800a-224">[정식 함수](canonical-functions.md) 에 대 한 네임 스페이스는 `Edm.Length("string")`과 같이 Edm입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="a800a-225">정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="a800a-226">두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="a800a-227">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="a800a-228">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-228">Output:</span></span>  
  
|<span data-ttu-id="a800a-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="a800a-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="a800a-230">6</span><span class="sxs-lookup"><span data-stu-id="a800a-230">6</span></span>|  
|<span data-ttu-id="a800a-231">6</span><span class="sxs-lookup"><span data-stu-id="a800a-231">6</span></span>|  
|<span data-ttu-id="a800a-232">5</span><span class="sxs-lookup"><span data-stu-id="a800a-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="a800a-233">Microsoft 공급자 특정</span><span class="sxs-lookup"><span data-stu-id="a800a-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="a800a-234">[Microsoft 공급자별 함수](../sqlclient-for-ef-functions.md) 는 `SqlServer` 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="a800a-235">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="a800a-236">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-236">Output:</span></span>  
  
|<span data-ttu-id="a800a-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="a800a-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="a800a-238">27</span><span class="sxs-lookup"><span data-stu-id="a800a-238">27</span></span>|  
|<span data-ttu-id="a800a-239">27</span><span class="sxs-lookup"><span data-stu-id="a800a-239">27</span></span>|  
|<span data-ttu-id="a800a-240">26</span><span class="sxs-lookup"><span data-stu-id="a800a-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="a800a-241">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a800a-241">Namespaces</span></span>  
 <span data-ttu-id="a800a-242">를 [사용 하 여](using-entity-sql.md) 쿼리 식에 사용 되는 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="a800a-243">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="a800a-244">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-244">Output:</span></span>  
  
|<span data-ttu-id="a800a-245">값</span><span class="sxs-lookup"><span data-stu-id="a800a-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-246">aa</span><span class="sxs-lookup"><span data-stu-id="a800a-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="a800a-247">페이징</span><span class="sxs-lookup"><span data-stu-id="a800a-247">Paging</span></span>  
 <span data-ttu-id="a800a-248">[SKIP](skip-entity-sql.md) 및 [LIMIT](limit-entity-sql.md) 하위 절을 [ORDER by](order-by-entity-sql.md) 절에 선언 하 여 페이징을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="a800a-249">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="a800a-250">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-250">Output:</span></span>  
  
|<span data-ttu-id="a800a-251">id</span><span class="sxs-lookup"><span data-stu-id="a800a-251">ID</span></span>|<span data-ttu-id="a800a-252">이름</span><span class="sxs-lookup"><span data-stu-id="a800a-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="a800a-253">10</span><span class="sxs-lookup"><span data-stu-id="a800a-253">10</span></span>|<span data-ttu-id="a800a-254">Adina</span><span class="sxs-lookup"><span data-stu-id="a800a-254">Adina</span></span>|  
|<span data-ttu-id="a800a-255">11</span><span class="sxs-lookup"><span data-stu-id="a800a-255">11</span></span>|<span data-ttu-id="a800a-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="a800a-256">Agcaoili</span></span>|  
|<span data-ttu-id="a800a-257">12</span><span class="sxs-lookup"><span data-stu-id="a800a-257">12</span></span>|<span data-ttu-id="a800a-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="a800a-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="a800a-259">그룹화</span><span class="sxs-lookup"><span data-stu-id="a800a-259">Grouping</span></span>  
 <span data-ttu-id="a800a-260">[그룹화 방법](group-by-entity-sql.md) 쿼리 ([SELECT](select-entity-sql.md)) 식에서 반환 되는 개체가 배치 될 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="a800a-261">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="a800a-262">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-262">Output:</span></span>  
  
|<span data-ttu-id="a800a-263">name</span><span class="sxs-lookup"><span data-stu-id="a800a-263">name</span></span>|  
|----------|  
|<span data-ttu-id="a800a-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a800a-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a800a-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a800a-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a800a-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="a800a-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="a800a-267">...</span><span class="sxs-lookup"><span data-stu-id="a800a-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="a800a-268">탐색</span><span class="sxs-lookup"><span data-stu-id="a800a-268">Navigation</span></span>  
 <span data-ttu-id="a800a-269">관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="a800a-270">[NAVIGATE](navigate-entity-sql.md) 는 \<namespace >으로 한정 된 관계 유형을 사용 합니다. \<relationship 유형 이름 >.</span><span class="sxs-lookup"><span data-stu-id="a800a-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="a800a-271">Navigate는 to end의 카디널리티가 1 인 경우 Ref @ no__t-0T > 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="a800a-272">끝 end의 카디널리티가 n 인 경우 < Ref @ no__t-0T > > 컬렉션이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="a800a-273">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="a800a-274">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-274">Output:</span></span>  
  
|<span data-ttu-id="a800a-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="a800a-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="a800a-276">1</span><span class="sxs-lookup"><span data-stu-id="a800a-276">1</span></span>|  
|<span data-ttu-id="a800a-277">2</span><span class="sxs-lookup"><span data-stu-id="a800a-277">2</span></span>|  
|<span data-ttu-id="a800a-278">3</span><span class="sxs-lookup"><span data-stu-id="a800a-278">3</span></span>|  
|<span data-ttu-id="a800a-279">...</span><span class="sxs-lookup"><span data-stu-id="a800a-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="a800a-280">SELECT VALUE 및 SELECT</span><span class="sxs-lookup"><span data-stu-id="a800a-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="a800a-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="a800a-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a800a-282">에서는 암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="a800a-283">SELECT VALUE 절에는 하나의 항목만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="a800a-284">이러한 절을 사용 하면 SELECT 절의 항목 주위에 행 래퍼가 생성 되지 않고 원하는 모양의 컬렉션이 생성 될 수 있습니다. 예를 들어 `SELECT VALUE a`입니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="a800a-285">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="a800a-286">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-286">Output:</span></span>  
  
|<span data-ttu-id="a800a-287">이름</span><span class="sxs-lookup"><span data-stu-id="a800a-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="a800a-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a800a-288">Adjustable Race</span></span>|  
|<span data-ttu-id="a800a-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a800a-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="a800a-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a800a-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="a800a-291">...</span><span class="sxs-lookup"><span data-stu-id="a800a-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="a800a-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="a800a-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="a800a-293">에서는 임의의 행을 만드는 행 생성자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="a800a-294">SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="a800a-295">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-295">Example:</span></span>  
  
 <span data-ttu-id="a800a-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="a800a-297">이름</span><span class="sxs-lookup"><span data-stu-id="a800a-297">Name</span></span>|<span data-ttu-id="a800a-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="a800a-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="a800a-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="a800a-299">Adjustable Race</span></span>|<span data-ttu-id="a800a-300">1</span><span class="sxs-lookup"><span data-stu-id="a800a-300">1</span></span>|  
|<span data-ttu-id="a800a-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="a800a-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="a800a-302">879</span><span class="sxs-lookup"><span data-stu-id="a800a-302">879</span></span>|  
|<span data-ttu-id="a800a-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="a800a-303">AWC Logo Cap</span></span>|<span data-ttu-id="a800a-304">712</span><span class="sxs-lookup"><span data-stu-id="a800a-304">712</span></span>|  
|<span data-ttu-id="a800a-305">...</span><span class="sxs-lookup"><span data-stu-id="a800a-305">...</span></span>|<span data-ttu-id="a800a-306">...</span><span class="sxs-lookup"><span data-stu-id="a800a-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="a800a-307">CASE 식</span><span class="sxs-lookup"><span data-stu-id="a800a-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="a800a-308">[Case 식은](case-entity-sql.md) 부울 식 집합을 계산 하 여 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a800a-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="a800a-309">예:</span><span class="sxs-lookup"><span data-stu-id="a800a-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="a800a-310">출력:</span><span class="sxs-lookup"><span data-stu-id="a800a-310">Output:</span></span>  
  
|<span data-ttu-id="a800a-311">값</span><span class="sxs-lookup"><span data-stu-id="a800a-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="a800a-312">true</span><span class="sxs-lookup"><span data-stu-id="a800a-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a800a-313">참조</span><span class="sxs-lookup"><span data-stu-id="a800a-313">See also</span></span>

- [<span data-ttu-id="a800a-314">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a800a-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a800a-315">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="a800a-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
