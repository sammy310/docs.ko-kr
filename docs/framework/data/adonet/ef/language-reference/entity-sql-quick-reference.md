---
title: Entity SQL 빠른 참조
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207073"
---
# <a name="entity-sql-quick-reference"></a><span data-ttu-id="d3ca2-102">Entity SQL 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="d3ca2-102">Entity SQL Quick Reference</span></span>
<span data-ttu-id="d3ca2-103">이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-103">This topic provides a quick reference to [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries.</span></span> <span data-ttu-id="d3ca2-104">이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-104">The queries in this topic are based on the AdventureWorks Sales model.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="d3ca2-105">리터럴</span><span class="sxs-lookup"><span data-stu-id="d3ca2-105">Literals</span></span>  
  
### <a name="string"></a><span data-ttu-id="d3ca2-106">문자열</span><span class="sxs-lookup"><span data-stu-id="d3ca2-106">String</span></span>  
 <span data-ttu-id="d3ca2-107">유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-107">There are Unicode and non-Unicode character string literals.</span></span> <span data-ttu-id="d3ca2-108">유니코드 문자열은 명사를 사용 하 여 앞에 있습니다. 예를 들어 `N'hello'`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-108">Unicode strings are prepended with N. For example, `N'hello'`.</span></span>  
  
 <span data-ttu-id="d3ca2-109">다음은 비유니코드 문자열 리터럴의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-109">The following is an example of a Non-Unicode string literal:</span></span>  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 <span data-ttu-id="d3ca2-110">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-110">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-111">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-111">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-112">hello</span><span class="sxs-lookup"><span data-stu-id="d3ca2-112">hello</span></span>|  
  
### <a name="datetime"></a><span data-ttu-id="d3ca2-113">DateTime</span><span class="sxs-lookup"><span data-stu-id="d3ca2-113">DateTime</span></span>  
 <span data-ttu-id="d3ca2-114">DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-114">In DateTime literals, both date and time parts are mandatory.</span></span> <span data-ttu-id="d3ca2-115">기본값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-115">There are no default values.</span></span>  
  
 <span data-ttu-id="d3ca2-116">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-116">Example:</span></span>  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 <span data-ttu-id="d3ca2-117">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-117">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-118">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-118">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-119">12/25/2006 1:01:00 AM</span><span class="sxs-lookup"><span data-stu-id="d3ca2-119">12/25/2006 1:01:00 AM</span></span>|  
  
### <a name="integer"></a><span data-ttu-id="d3ca2-120">정수</span><span class="sxs-lookup"><span data-stu-id="d3ca2-120">Integer</span></span>  
 <span data-ttu-id="d3ca2-121">Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-121">Integer literals can be of type Int32 (123), UInt32 (123U), Int64 (123L), and UInt64 (123UL).</span></span>  
  
 <span data-ttu-id="d3ca2-122">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-122">Example:</span></span>  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 <span data-ttu-id="d3ca2-123">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-123">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-124">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-124">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-125">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-125">1</span></span>|  
|<span data-ttu-id="d3ca2-126">2</span><span class="sxs-lookup"><span data-stu-id="d3ca2-126">2</span></span>|  
|<span data-ttu-id="d3ca2-127">3</span><span class="sxs-lookup"><span data-stu-id="d3ca2-127">3</span></span>|  
  
### <a name="other"></a><span data-ttu-id="d3ca2-128">기타</span><span class="sxs-lookup"><span data-stu-id="d3ca2-128">Other</span></span>  
 <span data-ttu-id="d3ca2-129">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-129">Other literals supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are Guid, Binary, Float/Double, Decimal, and `null`.</span></span> <span data-ttu-id="d3ca2-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-130">Null literals in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] are considered to be compatible with every other type in the conceptual model.</span></span>  
  
## <a name="type-constructors"></a><span data-ttu-id="d3ca2-131">형식 생성자</span><span class="sxs-lookup"><span data-stu-id="d3ca2-131">Type Constructors</span></span>  
  
### <a name="row"></a><span data-ttu-id="d3ca2-132">ROW</span><span class="sxs-lookup"><span data-stu-id="d3ca2-132">ROW</span></span>  
 <span data-ttu-id="d3ca2-133">[행](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) 에서처럼, 구조적으로 형식화 된 익명 레코드 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-133">[ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) constructs an anonymous, structurally-typed (record) value as in:</span></span> `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 <span data-ttu-id="d3ca2-134">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-134">Example:</span></span>  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 <span data-ttu-id="d3ca2-135">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-135">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-136">ProductID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-136">ProductID</span></span>|<span data-ttu-id="d3ca2-137">이름</span><span class="sxs-lookup"><span data-stu-id="d3ca2-137">Name</span></span>|  
|---------------|----------|  
|<span data-ttu-id="d3ca2-138">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-138">1</span></span>|<span data-ttu-id="d3ca2-139">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d3ca2-139">Adjustable Race</span></span>|  
|<span data-ttu-id="d3ca2-140">879</span><span class="sxs-lookup"><span data-stu-id="d3ca2-140">879</span></span>|<span data-ttu-id="d3ca2-141">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d3ca2-141">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d3ca2-142">712</span><span class="sxs-lookup"><span data-stu-id="d3ca2-142">712</span></span>|<span data-ttu-id="d3ca2-143">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d3ca2-143">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d3ca2-144">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-144">...</span></span>|<span data-ttu-id="d3ca2-145">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-145">...</span></span>|  
  
### <a name="multiset"></a><span data-ttu-id="d3ca2-146">MULTISET</span><span class="sxs-lookup"><span data-stu-id="d3ca2-146">MULTISET</span></span>  
 <span data-ttu-id="d3ca2-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) 와 같은 컬렉션을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-147">[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) constructs collections, such as:</span></span>  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 <span data-ttu-id="d3ca2-148">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-148">Example:</span></span>  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 <span data-ttu-id="d3ca2-149">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-149">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-150">ProductID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-150">ProductID</span></span>|<span data-ttu-id="d3ca2-151">이름</span><span class="sxs-lookup"><span data-stu-id="d3ca2-151">Name</span></span>|<span data-ttu-id="d3ca2-152">ProductNumber</span><span class="sxs-lookup"><span data-stu-id="d3ca2-152">ProductNumber</span></span>|<span data-ttu-id="d3ca2-153">…</span><span class="sxs-lookup"><span data-stu-id="d3ca2-153">…</span></span>|  
|---------------|----------|-------------------|-------|  
|<span data-ttu-id="d3ca2-154">842</span><span class="sxs-lookup"><span data-stu-id="d3ca2-154">842</span></span>|<span data-ttu-id="d3ca2-155">Touring-Panniers, Large</span><span class="sxs-lookup"><span data-stu-id="d3ca2-155">Touring-Panniers, Large</span></span>|<span data-ttu-id="d3ca2-156">PA-T100</span><span class="sxs-lookup"><span data-stu-id="d3ca2-156">PA-T100</span></span>|<span data-ttu-id="d3ca2-157">…</span><span class="sxs-lookup"><span data-stu-id="d3ca2-157">…</span></span>|  
  
### <a name="object"></a><span data-ttu-id="d3ca2-158">개체</span><span class="sxs-lookup"><span data-stu-id="d3ca2-158">Object</span></span>  
 <span data-ttu-id="d3ca2-159">[형식 생성자 라는](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) 와 같은 명명 된 사용자 정의 개체를 생성 `person("abc", 12)`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-159">[Named Type Constructor](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) constructs (named) user-defined objects, such as `person("abc", 12)`.</span></span>  
  
 <span data-ttu-id="d3ca2-160">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-160">Example:</span></span>  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 <span data-ttu-id="d3ca2-161">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-161">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-162">SalesOrderDetailID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-162">SalesOrderDetailID</span></span>|<span data-ttu-id="d3ca2-163">CarrierTrackingNumber</span><span class="sxs-lookup"><span data-stu-id="d3ca2-163">CarrierTrackingNumber</span></span>|<span data-ttu-id="d3ca2-164">OrderQty</span><span class="sxs-lookup"><span data-stu-id="d3ca2-164">OrderQty</span></span>|<span data-ttu-id="d3ca2-165">ProductID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-165">ProductID</span></span>|<span data-ttu-id="d3ca2-166">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-166">...</span></span>|  
|------------------------|---------------------------|--------------|---------------|---------|  
|<span data-ttu-id="d3ca2-167">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-167">1</span></span>|<span data-ttu-id="d3ca2-168">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="d3ca2-168">4911-403C-98</span></span>|<span data-ttu-id="d3ca2-169">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-169">1</span></span>|<span data-ttu-id="d3ca2-170">776</span><span class="sxs-lookup"><span data-stu-id="d3ca2-170">776</span></span>|<span data-ttu-id="d3ca2-171">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-171">...</span></span>|  
|<span data-ttu-id="d3ca2-172">2</span><span class="sxs-lookup"><span data-stu-id="d3ca2-172">2</span></span>|<span data-ttu-id="d3ca2-173">4911-403C-98</span><span class="sxs-lookup"><span data-stu-id="d3ca2-173">4911-403C-98</span></span>|<span data-ttu-id="d3ca2-174">3</span><span class="sxs-lookup"><span data-stu-id="d3ca2-174">3</span></span>|<span data-ttu-id="d3ca2-175">777</span><span class="sxs-lookup"><span data-stu-id="d3ca2-175">777</span></span>|<span data-ttu-id="d3ca2-176">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-176">...</span></span>|  
|<span data-ttu-id="d3ca2-177">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-177">...</span></span>|<span data-ttu-id="d3ca2-178">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-178">...</span></span>|<span data-ttu-id="d3ca2-179">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-179">...</span></span>|<span data-ttu-id="d3ca2-180">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-180">...</span></span>|<span data-ttu-id="d3ca2-181">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-181">...</span></span>|  
  
## <a name="references"></a><span data-ttu-id="d3ca2-182">참조</span><span class="sxs-lookup"><span data-stu-id="d3ca2-182">References</span></span>  
  
### <a name="ref"></a><span data-ttu-id="d3ca2-183">REF</span><span class="sxs-lookup"><span data-stu-id="d3ca2-183">REF</span></span>  
 <span data-ttu-id="d3ca2-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) 엔터티 형식 인스턴스에 대 한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-184">[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) creates a reference to an entity type instance.</span></span> <span data-ttu-id="d3ca2-185">예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-185">For example, the following query returns references to each Order entity in the Orders entity set:</span></span>  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 <span data-ttu-id="d3ca2-186">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-186">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-187">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-187">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-188">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-188">1</span></span>|  
|<span data-ttu-id="d3ca2-189">2</span><span class="sxs-lookup"><span data-stu-id="d3ca2-189">2</span></span>|  
|<span data-ttu-id="d3ca2-190">3</span><span class="sxs-lookup"><span data-stu-id="d3ca2-190">3</span></span>|  
|<span data-ttu-id="d3ca2-191">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-191">...</span></span>|  
  
 <span data-ttu-id="d3ca2-192">다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-192">The following example uses the property extraction operator (.) to access a property of an entity.</span></span> <span data-ttu-id="d3ca2-193">속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-193">When the property extraction operator is used, the reference is automatically dereferenced.</span></span>  
  
 <span data-ttu-id="d3ca2-194">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-194">Example:</span></span>  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d3ca2-195">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-195">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-196">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-196">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-197">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d3ca2-197">Adjustable Race</span></span>|  
|<span data-ttu-id="d3ca2-198">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d3ca2-198">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d3ca2-199">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d3ca2-199">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d3ca2-200">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-200">...</span></span>|  
  
### <a name="deref"></a><span data-ttu-id="d3ca2-201">DEREF</span><span class="sxs-lookup"><span data-stu-id="d3ca2-201">DEREF</span></span>  
 <span data-ttu-id="d3ca2-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) 역참조 참조 값과의 결과 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-202">[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="d3ca2-203">예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-203">For example, the following query produces the Order entities for each Order in the Orders entity set: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`..</span></span>  
  
 <span data-ttu-id="d3ca2-204">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-204">Example:</span></span>  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d3ca2-205">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-205">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-206">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-206">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-207">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d3ca2-207">Adjustable Race</span></span>|  
|<span data-ttu-id="d3ca2-208">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d3ca2-208">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d3ca2-209">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d3ca2-209">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d3ca2-210">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-210">...</span></span>|  
  
### <a name="createref-and-key"></a><span data-ttu-id="d3ca2-211">CREATEREF 및 KEY</span><span class="sxs-lookup"><span data-stu-id="d3ca2-211">CREATEREF AND KEY</span></span>  
 <span data-ttu-id="d3ca2-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) 키를 전달 하는 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-212">[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) creates a reference passing a key.</span></span> <span data-ttu-id="d3ca2-213">[키](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) 형식 참조가 있는 식의 키 부분을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-213">[KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extracts the key portion of an expression with type reference.</span></span>  
  
 <span data-ttu-id="d3ca2-214">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-214">Example:</span></span>  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d3ca2-215">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-215">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-216">ProductID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-216">ProductID</span></span>|  
|---------------|  
|<span data-ttu-id="d3ca2-217">980</span><span class="sxs-lookup"><span data-stu-id="d3ca2-217">980</span></span>|  
|<span data-ttu-id="d3ca2-218">365</span><span class="sxs-lookup"><span data-stu-id="d3ca2-218">365</span></span>|  
|<span data-ttu-id="d3ca2-219">771</span><span class="sxs-lookup"><span data-stu-id="d3ca2-219">771</span></span>|  
|<span data-ttu-id="d3ca2-220">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-220">...</span></span>|  
  
## <a name="functions"></a><span data-ttu-id="d3ca2-221">함수</span><span class="sxs-lookup"><span data-stu-id="d3ca2-221">Functions</span></span>  
  
### <a name="canonical"></a><span data-ttu-id="d3ca2-222">정식</span><span class="sxs-lookup"><span data-stu-id="d3ca2-222">Canonical</span></span>  
 <span data-ttu-id="d3ca2-223">에 대 한 네임 스페이스 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) Edm은 `Edm.Length("string")`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-223">The namespace for [canonical functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) is Edm, as in `Edm.Length("string")`.</span></span> <span data-ttu-id="d3ca2-224">정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-224">You do not have to specify the namespace unless another namespace is imported that contains a function with the same name as a canonical function.</span></span> <span data-ttu-id="d3ca2-225">두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-225">If two namespaces have the same function, the user should specific the full name.</span></span>  
  
 <span data-ttu-id="d3ca2-226">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-226">Example:</span></span>  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="d3ca2-227">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-227">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-228">NameLen</span><span class="sxs-lookup"><span data-stu-id="d3ca2-228">NameLen</span></span>|  
|-------------|  
|<span data-ttu-id="d3ca2-229">6</span><span class="sxs-lookup"><span data-stu-id="d3ca2-229">6</span></span>|  
|<span data-ttu-id="d3ca2-230">6</span><span class="sxs-lookup"><span data-stu-id="d3ca2-230">6</span></span>|  
|<span data-ttu-id="d3ca2-231">5</span><span class="sxs-lookup"><span data-stu-id="d3ca2-231">5</span></span>|  
  
### <a name="microsoft-provider-specific"></a><span data-ttu-id="d3ca2-232">Microsoft 공급자 특정</span><span class="sxs-lookup"><span data-stu-id="d3ca2-232">Microsoft Provider-Specific</span></span>  
 <span data-ttu-id="d3ca2-233">[Microsoft 공급자 특정 함수](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) 에 `SqlServer` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-233">[Microsoft provider-specific functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) are in the `SqlServer` namespace.</span></span>  
  
 <span data-ttu-id="d3ca2-234">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-234">Example:</span></span>  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 <span data-ttu-id="d3ca2-235">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-235">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-236">EmailLen</span><span class="sxs-lookup"><span data-stu-id="d3ca2-236">EmailLen</span></span>|  
|--------------|  
|<span data-ttu-id="d3ca2-237">27</span><span class="sxs-lookup"><span data-stu-id="d3ca2-237">27</span></span>|  
|<span data-ttu-id="d3ca2-238">27</span><span class="sxs-lookup"><span data-stu-id="d3ca2-238">27</span></span>|  
|<span data-ttu-id="d3ca2-239">26</span><span class="sxs-lookup"><span data-stu-id="d3ca2-239">26</span></span>|  
  
## <a name="namespaces"></a><span data-ttu-id="d3ca2-240">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d3ca2-240">Namespaces</span></span>  
 <span data-ttu-id="d3ca2-241">[사용 하 여](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) 쿼리 식에 사용 되는 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-241">[USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) specifies namespaces used in a query expression.</span></span>  
  
 <span data-ttu-id="d3ca2-242">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-242">Example:</span></span>  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 <span data-ttu-id="d3ca2-243">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-243">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-244">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-244">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-245">aa</span><span class="sxs-lookup"><span data-stu-id="d3ca2-245">aa</span></span>|  
  
## <a name="paging"></a><span data-ttu-id="d3ca2-246">페이징</span><span class="sxs-lookup"><span data-stu-id="d3ca2-246">Paging</span></span>  
 <span data-ttu-id="d3ca2-247">페이징 선언 하 여 표현 될 수 있습니다는 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) 및 [제한](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) 하위 절을 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 절.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-247">Paging can be expressed by declaring a [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) and [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) sub-clauses to the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clause.</span></span>  
  
 <span data-ttu-id="d3ca2-248">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-248">Example:</span></span>  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 <span data-ttu-id="d3ca2-249">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-249">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-250">ID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-250">ID</span></span>|<span data-ttu-id="d3ca2-251">이름</span><span class="sxs-lookup"><span data-stu-id="d3ca2-251">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="d3ca2-252">10</span><span class="sxs-lookup"><span data-stu-id="d3ca2-252">10</span></span>|<span data-ttu-id="d3ca2-253">Adina</span><span class="sxs-lookup"><span data-stu-id="d3ca2-253">Adina</span></span>|  
|<span data-ttu-id="d3ca2-254">11</span><span class="sxs-lookup"><span data-stu-id="d3ca2-254">11</span></span>|<span data-ttu-id="d3ca2-255">Agcaoili</span><span class="sxs-lookup"><span data-stu-id="d3ca2-255">Agcaoili</span></span>|  
|<span data-ttu-id="d3ca2-256">12</span><span class="sxs-lookup"><span data-stu-id="d3ca2-256">12</span></span>|<span data-ttu-id="d3ca2-257">Aguilar</span><span class="sxs-lookup"><span data-stu-id="d3ca2-257">Aguilar</span></span>|  
  
## <a name="grouping"></a><span data-ttu-id="d3ca2-258">그룹화</span><span class="sxs-lookup"><span data-stu-id="d3ca2-258">Grouping</span></span>  
 <span data-ttu-id="d3ca2-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) 쿼리에서 반환 된 개체 그룹을 지정 합니다 ([선택](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) 식 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-259">[GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) specifies groups into which objects returned by a query ([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expression are to be placed.</span></span>  
  
 <span data-ttu-id="d3ca2-260">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-260">Example:</span></span>  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 <span data-ttu-id="d3ca2-261">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-261">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-262">name</span><span class="sxs-lookup"><span data-stu-id="d3ca2-262">name</span></span>|  
|----------|  
|<span data-ttu-id="d3ca2-263">LL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="d3ca2-263">LL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="d3ca2-264">ML Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="d3ca2-264">ML Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="d3ca2-265">HL Mountain Seat Assembly</span><span class="sxs-lookup"><span data-stu-id="d3ca2-265">HL Mountain Seat Assembly</span></span>|  
|<span data-ttu-id="d3ca2-266">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-266">...</span></span>|  
  
## <a name="navigation"></a><span data-ttu-id="d3ca2-267">탐색</span><span class="sxs-lookup"><span data-stu-id="d3ca2-267">Navigation</span></span>  
 <span data-ttu-id="d3ca2-268">관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-268">The relationship navigation operator allows you to navigate over the relationship from one entity (from end) to another (to end).</span></span> <span data-ttu-id="d3ca2-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) 수행으로 정규화 된 관계 유형을 \<네임 스페이스 >.\< 관계 유형 이름 >.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-269">[NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) takes the relationship type qualified as \<namespace>.\<relationship type name>.</span></span> <span data-ttu-id="d3ca2-270">이동 Ref 반환\<T > 경우의 카디널리티를 종료 하는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-270">Navigate returns Ref\<T> if the cardinality of the to end is 1.</span></span> <span data-ttu-id="d3ca2-271">하는 경우의 카디널리티를 종료 하려면 n, 컬렉션은 < Ref\<T >> 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-271">If the cardinality of the to end is n, the Collection<Ref\<T>> will be returned.</span></span>  
  
 <span data-ttu-id="d3ca2-272">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-272">Example:</span></span>  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 <span data-ttu-id="d3ca2-273">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-273">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-274">AddressID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-274">AddressID</span></span>|  
|---------------|  
|<span data-ttu-id="d3ca2-275">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-275">1</span></span>|  
|<span data-ttu-id="d3ca2-276">2</span><span class="sxs-lookup"><span data-stu-id="d3ca2-276">2</span></span>|  
|<span data-ttu-id="d3ca2-277">3</span><span class="sxs-lookup"><span data-stu-id="d3ca2-277">3</span></span>|  
|<span data-ttu-id="d3ca2-278">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-278">...</span></span>|  
  
## <a name="select-value-and-select"></a><span data-ttu-id="d3ca2-279">SELECT VALUE 및 SELECT</span><span class="sxs-lookup"><span data-stu-id="d3ca2-279">SELECT VALUE AND SELECT</span></span>  
  
### <a name="select-value"></a><span data-ttu-id="d3ca2-280">SELECT VALUE</span><span class="sxs-lookup"><span data-stu-id="d3ca2-280">SELECT VALUE</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="d3ca2-281">암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-281">provides the SELECT VALUE clause to skip the implicit row construction.</span></span> <span data-ttu-id="d3ca2-282">SELECT VALUE 절에 하나의 항목만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-282">Only one item can be specified in a SELECT VALUE clause.</span></span> <span data-ttu-id="d3ca2-283">이러한 절은 사용 되는 SELECT 절의 항목 주위에 없는 행 래퍼가 생성 하 고 원하는 모양의 컬렉션이 만들어질 수 있습니다 예를 들어: `SELECT VALUE a`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-283">When such a clause is used, no row wrapper is constructed around the items in the SELECT clause, and a collection of the desired shape can be produced, for example: `SELECT VALUE a`.</span></span>  
  
 <span data-ttu-id="d3ca2-284">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-284">Example:</span></span>  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 <span data-ttu-id="d3ca2-285">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-285">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-286">이름</span><span class="sxs-lookup"><span data-stu-id="d3ca2-286">Name</span></span>|  
|----------|  
|<span data-ttu-id="d3ca2-287">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d3ca2-287">Adjustable Race</span></span>|  
|<span data-ttu-id="d3ca2-288">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d3ca2-288">All-Purpose Bike Stand</span></span>|  
|<span data-ttu-id="d3ca2-289">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d3ca2-289">AWC Logo Cap</span></span>|  
|<span data-ttu-id="d3ca2-290">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-290">...</span></span>|  
  
### <a name="select"></a><span data-ttu-id="d3ca2-291">선택</span><span class="sxs-lookup"><span data-stu-id="d3ca2-291">SELECT</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="d3ca2-292">또한 임의의 행을 만드는 행 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-292">also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="d3ca2-293">SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-293">SELECT takes one or more elements in the projection and results in a data record with fields, for example: `SELECT a, b, c`.</span></span>  
  
 <span data-ttu-id="d3ca2-294">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-294">Example:</span></span>  
  
 <span data-ttu-id="d3ca2-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-295">SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:</span></span>  
  
|<span data-ttu-id="d3ca2-296">이름</span><span class="sxs-lookup"><span data-stu-id="d3ca2-296">Name</span></span>|<span data-ttu-id="d3ca2-297">ProductID</span><span class="sxs-lookup"><span data-stu-id="d3ca2-297">ProductID</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d3ca2-298">Adjustable Race</span><span class="sxs-lookup"><span data-stu-id="d3ca2-298">Adjustable Race</span></span>|<span data-ttu-id="d3ca2-299">1</span><span class="sxs-lookup"><span data-stu-id="d3ca2-299">1</span></span>|  
|<span data-ttu-id="d3ca2-300">All-Purpose Bike Stand</span><span class="sxs-lookup"><span data-stu-id="d3ca2-300">All-Purpose Bike Stand</span></span>|<span data-ttu-id="d3ca2-301">879</span><span class="sxs-lookup"><span data-stu-id="d3ca2-301">879</span></span>|  
|<span data-ttu-id="d3ca2-302">AWC Logo Cap</span><span class="sxs-lookup"><span data-stu-id="d3ca2-302">AWC Logo Cap</span></span>|<span data-ttu-id="d3ca2-303">712</span><span class="sxs-lookup"><span data-stu-id="d3ca2-303">712</span></span>|  
|<span data-ttu-id="d3ca2-304">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-304">...</span></span>|<span data-ttu-id="d3ca2-305">...</span><span class="sxs-lookup"><span data-stu-id="d3ca2-305">...</span></span>|  
  
## <a name="case-expression"></a><span data-ttu-id="d3ca2-306">CASE 식</span><span class="sxs-lookup"><span data-stu-id="d3ca2-306">CASE EXPRESSION</span></span>  
 <span data-ttu-id="d3ca2-307">합니다 [사례 식을](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) 결과 결정 하는 부울 식 집합을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ca2-307">The [case expression](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evaluates a set of Boolean expressions to determine the result.</span></span>  
  
 <span data-ttu-id="d3ca2-308">예제:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-308">Example:</span></span>  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 <span data-ttu-id="d3ca2-309">출력:</span><span class="sxs-lookup"><span data-stu-id="d3ca2-309">Output:</span></span>  
  
|<span data-ttu-id="d3ca2-310">값</span><span class="sxs-lookup"><span data-stu-id="d3ca2-310">Value</span></span>|  
|-----------|  
|<span data-ttu-id="d3ca2-311">TRUE</span><span class="sxs-lookup"><span data-stu-id="d3ca2-311">TRUE</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3ca2-312">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3ca2-312">See also</span></span>

- [<span data-ttu-id="d3ca2-313">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="d3ca2-313">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="d3ca2-314">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="d3ca2-314">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
