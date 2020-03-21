---
title: Entity SQL 빠른 참조
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150352"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="bac6e-102">Entity SQL 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="bac6e-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="bac6e-103">이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="bac6e-104">이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="bac6e-105">리터럴</span><span class="sxs-lookup"><span data-stu-id="bac6e-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="bac6e-106">String</span><span class="sxs-lookup"><span data-stu-id="bac6e-106">String</span></span>  
 <span data-ttu-id="bac6e-107">유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="bac6e-108">유니코드 문자열은 N으로 준비됩니다. 예를 들어, `N'hello'`.</span><span class="sxs-lookup"><span data-stu-id="bac6e-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="bac6e-109">다음은 비유니코드 문자열 리터럴의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="bac6e-110">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-110">Output:</span></span>  
  
|<span data-ttu-id="bac6e-111">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-112">hello</span><span class="sxs-lookup"><span data-stu-id="bac6e-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="bac6e-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="bac6e-113">DateTime</span></span>  
 <span data-ttu-id="bac6e-114">DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="bac6e-115">기본값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-115">There are no default values.</span></span>  
  
 <span data-ttu-id="bac6e-116">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-116">Example:</span></span>  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="bac6e-117">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-117">Output:</span></span>  
  
|<span data-ttu-id="bac6e-118">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="bac6e-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="bac6e-120">정수</span><span class="sxs-lookup"><span data-stu-id="bac6e-120">Integer</span></span>  
 <span data-ttu-id="bac6e-121">Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="bac6e-122">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-122">Example:</span></span>  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="bac6e-123">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-123">Output:</span></span>  
  
|<span data-ttu-id="bac6e-124">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-125">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-125">1</span></span>|  
|<span data-ttu-id="bac6e-126">2</span><span class="sxs-lookup"><span data-stu-id="bac6e-126">2</span></span>|  
|<span data-ttu-id="bac6e-127">3</span><span class="sxs-lookup"><span data-stu-id="bac6e-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="bac6e-128">기타</span><span class="sxs-lookup"><span data-stu-id="bac6e-128">Other</span></span>  
 <span data-ttu-id="bac6e-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="bac6e-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="bac6e-131">형식 생성자</span><span class="sxs-lookup"><span data-stu-id="bac6e-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="bac6e-132">ROW</span><span class="sxs-lookup"><span data-stu-id="bac6e-132">ROW</span></span>  
 <span data-ttu-id="bac6e-133">[ROW는](row-entity-sql.md) 다음과 같이 구조적으로 구조적으로 형식이 되는 익명(레코드) 값을 구성합니다.`ROW(1 AS myNumber, ‘Name’ AS myName).`</span><span class="sxs-lookup"><span data-stu-id="bac6e-133">[ROW](row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in: `ROW(1 AS myNumber, ‘Name’ AS myName).`</span></span>  
  
 <span data-ttu-id="bac6e-134">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-134">Example:</span></span>  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 <span data-ttu-id="bac6e-135">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-135">Output:</span></span>  
  
|<span data-ttu-id="bac6e-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="bac6e-136">ProductID</span></span>|<span data-ttu-id="bac6e-137">속성</span><span class="sxs-lookup"><span data-stu-id="bac6e-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="bac6e-138">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-138">1</span></span>|<span data-ttu-id="bac6e-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="bac6e-139">Adjustable Race</span></span>|  
|<span data-ttu-id="bac6e-140">879</span><span class="sxs-lookup"><span data-stu-id="bac6e-140">879</span></span>|<span data-ttu-id="bac6e-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="bac6e-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="bac6e-142">712</span><span class="sxs-lookup"><span data-stu-id="bac6e-142">712</span></span>|<span data-ttu-id="bac6e-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="bac6e-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="bac6e-144">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-144">...</span></span>|<span data-ttu-id="bac6e-145">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="bac6e-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="bac6e-146">MULTISET</span></span>  
 <span data-ttu-id="bac6e-147">[MULTISET은](multiset-entity-sql.md) 다음과 같은 컬렉션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-147">[MULTISET](multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 <span data-ttu-id="bac6e-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span><span class="sxs-lookup"><span data-stu-id="bac6e-148">`MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`</span></span>  
  
 <span data-ttu-id="bac6e-149">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-149">Example:</span></span>  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="bac6e-150">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-150">Output:</span></span>  
  
|<span data-ttu-id="bac6e-151">ProductID</span><span class="sxs-lookup"><span data-stu-id="bac6e-151">ProductID</span></span>|<span data-ttu-id="bac6e-152">속성</span><span class="sxs-lookup"><span data-stu-id="bac6e-152">Name</span></span>|<span data-ttu-id="bac6e-153">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="bac6e-153">ProductNumber</span></span>|<span data-ttu-id="bac6e-154">…</span><span class="sxs-lookup"><span data-stu-id="bac6e-154">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="bac6e-155">842</span><span class="sxs-lookup"><span data-stu-id="bac6e-155">842</span></span>|<span data-ttu-id="bac6e-156">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="bac6e-156">Touring-Panniers, Large</span></span>|<span data-ttu-id="bac6e-157">PA-T100</span><span class="sxs-lookup"><span data-stu-id="bac6e-157">PA-T100</span></span>|<span data-ttu-id="bac6e-158">…</span><span class="sxs-lookup"><span data-stu-id="bac6e-158">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="bac6e-159">Object</span><span class="sxs-lookup"><span data-stu-id="bac6e-159">Object</span></span>  
 <span data-ttu-id="bac6e-160">[명명된 유형 생성자 생성자(예:](named-type-constructor-entity-sql.md) `person("abc", 12)`사용자 정의 개체)</span><span class="sxs-lookup"><span data-stu-id="bac6e-160">[Named Type Constructor](named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="bac6e-161">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-161">Example:</span></span>  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 <span data-ttu-id="bac6e-162">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-162">Output:</span></span>  
  
|<span data-ttu-id="bac6e-163">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="bac6e-163">SalesOrderDetailID</span></span>|<span data-ttu-id="bac6e-164">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="bac6e-164">CarrierTrackingNumber</span></span>|<span data-ttu-id="bac6e-165">OrderQty</span><span class="sxs-lookup"><span data-stu-id="bac6e-165">OrderQty</span></span>|<span data-ttu-id="bac6e-166">ProductID</span><span class="sxs-lookup"><span data-stu-id="bac6e-166">ProductID</span></span>|<span data-ttu-id="bac6e-167">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-167">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="bac6e-168">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-168">1</span></span>|<span data-ttu-id="bac6e-169">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="bac6e-169">4911-403C-98</span></span>|<span data-ttu-id="bac6e-170">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-170">1</span></span>|<span data-ttu-id="bac6e-171">776</span><span class="sxs-lookup"><span data-stu-id="bac6e-171">776</span></span>|<span data-ttu-id="bac6e-172">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-172">...</span></span>|  
|<span data-ttu-id="bac6e-173">2</span><span class="sxs-lookup"><span data-stu-id="bac6e-173">2</span></span>|<span data-ttu-id="bac6e-174">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="bac6e-174">4911-403C-98</span></span>|<span data-ttu-id="bac6e-175">3</span><span class="sxs-lookup"><span data-stu-id="bac6e-175">3</span></span>|<span data-ttu-id="bac6e-176">777</span><span class="sxs-lookup"><span data-stu-id="bac6e-176">777</span></span>|<span data-ttu-id="bac6e-177">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-177">...</span></span>|  
|<span data-ttu-id="bac6e-178">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-178">...</span></span>|<span data-ttu-id="bac6e-179">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-179">...</span></span>|<span data-ttu-id="bac6e-180">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-180">...</span></span>|<span data-ttu-id="bac6e-181">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-181">...</span></span>|<span data-ttu-id="bac6e-182">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-182">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="bac6e-183">참조</span><span class="sxs-lookup"><span data-stu-id="bac6e-183">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="bac6e-184">REF</span><span class="sxs-lookup"><span data-stu-id="bac6e-184">REF</span></span>  
 <span data-ttu-id="bac6e-185">[REF는](ref-entity-sql.md) 엔터티 유형 인스턴스에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-185">[REF](ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="bac6e-186">예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-186">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="bac6e-187">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-187">Output:</span></span>  
  
|<span data-ttu-id="bac6e-188">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-188">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-189">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-189">1</span></span>|  
|<span data-ttu-id="bac6e-190">2</span><span class="sxs-lookup"><span data-stu-id="bac6e-190">2</span></span>|  
|<span data-ttu-id="bac6e-191">3</span><span class="sxs-lookup"><span data-stu-id="bac6e-191">3</span></span>|  
|<span data-ttu-id="bac6e-192">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-192">...</span></span>|  
  
 <span data-ttu-id="bac6e-193">다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-193">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="bac6e-194">속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-194">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="bac6e-195">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-195">Example:</span></span>  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="bac6e-196">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-196">Output:</span></span>  
  
|<span data-ttu-id="bac6e-197">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-197">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-198">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="bac6e-198">Adjustable Race</span></span>|  
|<span data-ttu-id="bac6e-199">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="bac6e-199">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="bac6e-200">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="bac6e-200">AWC Logo Cap</span></span>|  
|<span data-ttu-id="bac6e-201">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-201">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="bac6e-202">DEREF</span><span class="sxs-lookup"><span data-stu-id="bac6e-202">DEREF</span></span>  
 <span data-ttu-id="bac6e-203">[DEREF는](deref-entity-sql.md) 참조 값을 참조하고 해당 참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-203">[DEREF](deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="bac6e-204">예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-204">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="bac6e-205">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-205">Example:</span></span>  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="bac6e-206">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-206">Output:</span></span>  
  
|<span data-ttu-id="bac6e-207">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-207">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-208">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="bac6e-208">Adjustable Race</span></span>|  
|<span data-ttu-id="bac6e-209">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="bac6e-209">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="bac6e-210">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="bac6e-210">AWC Logo Cap</span></span>|  
|<span data-ttu-id="bac6e-211">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-211">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="bac6e-212">CREATEREF 및 KEY</span><span class="sxs-lookup"><span data-stu-id="bac6e-212">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="bac6e-213">[CREATEREF는](createref-entity-sql.md) 키를 전달하는 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-213">[CREATEREF](createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="bac6e-214">[KEY는](key-entity-sql.md) 형식 참조를 통해 식의 키 부분을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-214">[KEY](key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="bac6e-215">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-215">Example:</span></span>  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="bac6e-216">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-216">Output:</span></span>  
  
|<span data-ttu-id="bac6e-217">ProductID</span><span class="sxs-lookup"><span data-stu-id="bac6e-217">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="bac6e-218">980</span><span class="sxs-lookup"><span data-stu-id="bac6e-218">980</span></span>|  
|<span data-ttu-id="bac6e-219">365</span><span class="sxs-lookup"><span data-stu-id="bac6e-219">365</span></span>|  
|<span data-ttu-id="bac6e-220">771</span><span class="sxs-lookup"><span data-stu-id="bac6e-220">771</span></span>|  
|<span data-ttu-id="bac6e-221">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-221">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="bac6e-222">Functions</span><span class="sxs-lookup"><span data-stu-id="bac6e-222">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="bac6e-223">Canonical</span><span class="sxs-lookup"><span data-stu-id="bac6e-223">Canonical</span></span>  
 <span data-ttu-id="bac6e-224">[표준 함수의](canonical-functions.md) 네임스페이스는 `Edm.Length("string")`에서와 같이 Edm입니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-224">The namespace for [canonical functions](canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="bac6e-225">정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-225">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="bac6e-226">두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-226">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="bac6e-227">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-227">Example:</span></span>  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="bac6e-228">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-228">Output:</span></span>  
  
|<span data-ttu-id="bac6e-229">NameLen</span><span class="sxs-lookup"><span data-stu-id="bac6e-229">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="bac6e-230">6</span><span class="sxs-lookup"><span data-stu-id="bac6e-230">6</span></span>|  
|<span data-ttu-id="bac6e-231">6</span><span class="sxs-lookup"><span data-stu-id="bac6e-231">6</span></span>|  
|<span data-ttu-id="bac6e-232">5</span><span class="sxs-lookup"><span data-stu-id="bac6e-232">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="bac6e-233">Microsoft 공급자 특정</span><span class="sxs-lookup"><span data-stu-id="bac6e-233">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="bac6e-234">[Microsoft 공급자별 함수는](../sqlclient-for-ef-functions.md) 네임스페이스에 `SqlServer` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-234">[Microsoft provider-specific functions](../sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="bac6e-235">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-235">Example:</span></span>  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="bac6e-236">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-236">Output:</span></span>  
  
|<span data-ttu-id="bac6e-237">EmailLen</span><span class="sxs-lookup"><span data-stu-id="bac6e-237">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="bac6e-238">27</span><span class="sxs-lookup"><span data-stu-id="bac6e-238">27</span></span>|  
|<span data-ttu-id="bac6e-239">27</span><span class="sxs-lookup"><span data-stu-id="bac6e-239">27</span></span>|  
|<span data-ttu-id="bac6e-240">26</span><span class="sxs-lookup"><span data-stu-id="bac6e-240">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="bac6e-241">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bac6e-241">Namespaces</span></span>  
 <span data-ttu-id="bac6e-242">[using는](using-entity-sql.md) 쿼리 식에 사용되는 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-242">[USING](using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="bac6e-243">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-243">Example:</span></span>  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="bac6e-244">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-244">Output:</span></span>  
  
|<span data-ttu-id="bac6e-245">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-245">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-246">aa</span><span class="sxs-lookup"><span data-stu-id="bac6e-246">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="bac6e-247">Paging</span><span class="sxs-lookup"><span data-stu-id="bac6e-247">Paging</span></span>  
 <span data-ttu-id="bac6e-248">페이징은 [ORDER BY](order-by-entity-sql.md) 절에 [SKIP](skip-entity-sql.md) 및 [LIMIT](limit-entity-sql.md) 하위 절을 선언하여 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-248">Paging can be expressed by declaring a [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses to the [ORDER BY](order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="bac6e-249">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-249">Example:</span></span>  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="bac6e-250">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-250">Output:</span></span>  
  
|<span data-ttu-id="bac6e-251">ID</span><span class="sxs-lookup"><span data-stu-id="bac6e-251">ID</span></span>|<span data-ttu-id="bac6e-252">속성</span><span class="sxs-lookup"><span data-stu-id="bac6e-252">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="bac6e-253">10</span><span class="sxs-lookup"><span data-stu-id="bac6e-253">10</span></span>|<span data-ttu-id="bac6e-254">Adina</span><span class="sxs-lookup"><span data-stu-id="bac6e-254">Adina</span></span>|  
|<span data-ttu-id="bac6e-255">11</span><span class="sxs-lookup"><span data-stu-id="bac6e-255">11</span></span>|<span data-ttu-id="bac6e-256">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="bac6e-256">Agcaoili</span></span>|  
|<span data-ttu-id="bac6e-257">12</span><span class="sxs-lookup"><span data-stu-id="bac6e-257">12</span></span>|<span data-ttu-id="bac6e-258">Aguilar</span><span class="sxs-lookup"><span data-stu-id="bac6e-258">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="bac6e-259">Grouping(그룹화)</span><span class="sxs-lookup"><span data-stu-id="bac6e-259">Grouping</span></span>  
 <span data-ttu-id="bac6e-260">[GROUPING BY는](group-by-entity-sql.md) [쿼리(SELECT)](select-entity-sql.md)식에 의해 반환되는 개체를 배치할 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-260">[GROUPING BY](group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="bac6e-261">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-261">Example:</span></span>  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="bac6e-262">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-262">Output:</span></span>  
  
|<span data-ttu-id="bac6e-263">name</span><span class="sxs-lookup"><span data-stu-id="bac6e-263">name</span></span>|  
|----------|  
|<span data-ttu-id="bac6e-264">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="bac6e-264">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="bac6e-265">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="bac6e-265">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="bac6e-266">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="bac6e-266">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="bac6e-267">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-267">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="bac6e-268">탐색</span><span class="sxs-lookup"><span data-stu-id="bac6e-268">Navigation</span></span>  
 <span data-ttu-id="bac6e-269">관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-269">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="bac6e-270">[NAVIGATE는](navigate-entity-sql.md) 네임스페이스 \<> 정규화된 관계 유형을 취합니다. \<관계 유형 이름>.</span><span class="sxs-lookup"><span data-stu-id="bac6e-270">[NAVIGATE](navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="bac6e-271">행간 끝의 카디널리티가 1이면 탐색은 참조\<T> 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-271">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="bac6e-272">끝까지의 카디널리티가 n이면 참조\<T>><컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-272">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="bac6e-273">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-273">Example:</span></span>  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="bac6e-274">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-274">Output:</span></span>  
  
|<span data-ttu-id="bac6e-275">AddressID</span><span class="sxs-lookup"><span data-stu-id="bac6e-275">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="bac6e-276">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-276">1</span></span>|  
|<span data-ttu-id="bac6e-277">2</span><span class="sxs-lookup"><span data-stu-id="bac6e-277">2</span></span>|  
|<span data-ttu-id="bac6e-278">3</span><span class="sxs-lookup"><span data-stu-id="bac6e-278">3</span></span>|  
|<span data-ttu-id="bac6e-279">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-279">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="bac6e-280">SELECT VALUE 및 SELECT</span><span class="sxs-lookup"><span data-stu-id="bac6e-280">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="bac6e-281">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="bac6e-281">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="bac6e-282">에서는 암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-282">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="bac6e-283">SELECT VALUE 절 하나에는 항목 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-283">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="bac6e-284">이러한 절을 사용하면 SELECT 절의 항목 주위에 행 래퍼가 생성되지 않으며 원하는 셰이프 컬렉션(예: `SELECT VALUE a`)을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-284">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="bac6e-285">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-285">Example:</span></span>  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 <span data-ttu-id="bac6e-286">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-286">Output:</span></span>  
  
|<span data-ttu-id="bac6e-287">속성</span><span class="sxs-lookup"><span data-stu-id="bac6e-287">Name</span></span>|  
|----------|  
|<span data-ttu-id="bac6e-288">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="bac6e-288">Adjustable Race</span></span>|  
|<span data-ttu-id="bac6e-289">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="bac6e-289">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="bac6e-290">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="bac6e-290">AWC Logo Cap</span></span>|  
|<span data-ttu-id="bac6e-291">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-291">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="bac6e-292">SELECT</span><span class="sxs-lookup"><span data-stu-id="bac6e-292">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="bac6e-293">에서는 임의의 행을 만드는 행 생성자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-293">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="bac6e-294">SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-294">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="bac6e-295">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-295">Example:</span></span>  
  
 <span data-ttu-id="bac6e-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-296">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="bac6e-297">속성</span><span class="sxs-lookup"><span data-stu-id="bac6e-297">Name</span></span>|<span data-ttu-id="bac6e-298">ProductID</span><span class="sxs-lookup"><span data-stu-id="bac6e-298">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="bac6e-299">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="bac6e-299">Adjustable Race</span></span>|<span data-ttu-id="bac6e-300">1</span><span class="sxs-lookup"><span data-stu-id="bac6e-300">1</span></span>|  
|<span data-ttu-id="bac6e-301">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="bac6e-301">All-Purpose Bike Stand</span></span>|<span data-ttu-id="bac6e-302">879</span><span class="sxs-lookup"><span data-stu-id="bac6e-302">879</span></span>|  
|<span data-ttu-id="bac6e-303">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="bac6e-303">AWC Logo Cap</span></span>|<span data-ttu-id="bac6e-304">712</span><span class="sxs-lookup"><span data-stu-id="bac6e-304">712</span></span>|  
|<span data-ttu-id="bac6e-305">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-305">...</span></span>|<span data-ttu-id="bac6e-306">...</span><span class="sxs-lookup"><span data-stu-id="bac6e-306">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="bac6e-307">CASE 식</span><span class="sxs-lookup"><span data-stu-id="bac6e-307">CASE EXPRESSION</span></span>  
 <span data-ttu-id="bac6e-308">[CASE 식은](case-entity-sql.md) 부울 식 집합을 평가하여 결과를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bac6e-308">The [case expression](case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="bac6e-309">예제:</span><span class="sxs-lookup"><span data-stu-id="bac6e-309">Example:</span></span>  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="bac6e-310">출력:</span><span class="sxs-lookup"><span data-stu-id="bac6e-310">Output:</span></span>  
  
|<span data-ttu-id="bac6e-311">값</span><span class="sxs-lookup"><span data-stu-id="bac6e-311">Value</span></span>|  
|-----------|  
|<span data-ttu-id="bac6e-312">TRUE</span><span class="sxs-lookup"><span data-stu-id="bac6e-312">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bac6e-313">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bac6e-313">See also</span></span>

- [<span data-ttu-id="bac6e-314">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="bac6e-314">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="bac6e-315">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="bac6e-315">Entity SQL Overview</span></span>](entity-sql-overview.md)
