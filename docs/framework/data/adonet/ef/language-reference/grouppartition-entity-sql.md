---
title: GROUPPARTITION(Entity SQL)
ms.date: 03/30/2017
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
ms.openlocfilehash: 19df566c254a3f3202eb3554ab43ee0d7c944181
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833759"
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="78cb2-102">GROUPPARTITION(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="78cb2-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="78cb2-103">집계가 관련된 현재 그룹 파티션에서 예측된 인수 값의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="78cb2-104">`GroupPartition` 집계는 그룹 기반 집계이며 컬렉션 기반 형식을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78cb2-105">구문</span><span class="sxs-lookup"><span data-stu-id="78cb2-105">Syntax</span></span>  
  
```sql  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="78cb2-106">인수</span><span class="sxs-lookup"><span data-stu-id="78cb2-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="78cb2-107">임의의 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식입니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78cb2-108">설명</span><span class="sxs-lookup"><span data-stu-id="78cb2-108">Remarks</span></span>  
 <span data-ttu-id="78cb2-109">다음 쿼리는 제품 목록 및 각 제품당 주문 라인 수량 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="78cb2-110">다음 두 쿼리는 구문적으로 서로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-110">The following two queries are semantically equal:</span></span>  
  
```sql  
SELECT p, Sum(GroupPartition(ol.Quantity)) FROM LOB.OrderLines AS ol
  GROUP BY ol.Product AS p
SELET p, Sum(ol.Quantity) FROM LOB.OrderLines AS ol
  group by ol.Product as p  
```  
  
 <span data-ttu-id="78cb2-111">`GROUPPARTITION` 연산자는 사용자 정의 집계 연산자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
<span data-ttu-id="78cb2-112">`GROUPPARTITION` 은 그룹화된 입력 집합에 대한 참조를 포함하는 특수 집계 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="78cb2-113">이러한 참조는 범위 내에 GROUP BY가 있는 쿼리의 아무 곳에서나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="78cb2-114">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-114">For example:</span></span>
  
```sql  
SELECT p, GroupPartition(ol.Quantity) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="78cb2-115">일반 `GROUP BY`을 사용 하는 경우 그룹화 결과는 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-115">With a regular `GROUP BY`, the results of the grouping are hidden.</span></span> <span data-ttu-id="78cb2-116">결과는 집계 함수에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="78cb2-117">그룹화 결과를 보려면 하위 쿼리를 사용하여 그룹화 및 입력 집합 결과를 상호 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="78cb2-118">다음 두 쿼리는 동일한 의미를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-118">The following two queries are equivalent:</span></span>  
  
```sql  
SELET p, (SELECT q FROM GroupPartition(ol.Quantity) AS q) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
SELECT p, (SELECT ol.Quantity AS q FROM LOB.OrderLines AS ol2 WHERE ol2.Product = p) FROM LOB.OrderLines AS ol GROUP BY ol.Product AS p
```  
  
 <span data-ttu-id="78cb2-119">예제와 나와 있듯이 GROUPPARTITION 집계 연산자를 사용하면 그룹화 이후 입력 집합에 대한 참조를 보다 쉽게 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="78cb2-120">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 매개 변수를 사용하는 경우 GROUPPARTITION 연산자는 연산자 입력에서 `expression` 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="78cb2-121">예를 들어, 그룹 파티션에 대한 다음의 모든 입력 식은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```sql  
SELECT groupkey, GroupPartition(b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(1) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition(a + b) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey
SELECT groupkey, GroupPartition({a + b}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition({42}) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
SELECT groupkey, GroupPartition(b > a) FROM {1,2,3} AS a INNER JOIN {4,5,6} AS b ON true GROUP BY a AS groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="78cb2-122">예제</span><span class="sxs-lookup"><span data-stu-id="78cb2-122">Example</span></span>  
 <span data-ttu-id="78cb2-123">다음 예제에서는 GROUPPARTITION 절을 GROUP BY 절과 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="78cb2-124">GROUP BY 절은 `SalesOrderHeader` 엔터티를 해당 `Contact`별로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="78cb2-125">그리고 나서 GROUPPARTITION 절은 각 그룹에 대한 `TotalDue` 속성을 예상하여 10진수 컬렉션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="78cb2-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#Collection_GroupPartition](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#collection_grouppartition)]
