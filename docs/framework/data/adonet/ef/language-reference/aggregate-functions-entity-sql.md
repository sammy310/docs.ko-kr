---
title: 집계 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: acfd3149-f519-4c6e-8fe1-b21d243a0e58
ms.openlocfilehash: 308670f04b9a04b1fff77ece08deb39c8c4081d1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198082"
---
# <a name="aggregate-functions-entity-sql"></a><span data-ttu-id="6bf56-102">집계 함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6bf56-102">Aggregate Functions (Entity SQL)</span></span>

<span data-ttu-id="6bf56-103">집계는 컬렉션을 그룹 작업의 일부분인 스칼라로 압축하는 언어 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-103">An aggregate is a language construct that condenses a collection into a scalar as a part of a group operation.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6bf56-104">집계의 형식은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-104">aggregates come in two forms:</span></span>  
  
- [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6bf56-105">식의 어디에서 나 사용할 수 있는 컬렉션 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-105">collection functions that may be used anywhere in an expression.</span></span> <span data-ttu-id="6bf56-106">이 함수는 프로젝션의 집계 함수를 사용하며 컬렉션에 대한 해당 동작을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-106">This includes using aggregate functions in projections and predicates that act on collections.</span></span> <span data-ttu-id="6bf56-107">컬렉션 함수는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 집계를 지정하는 데 주로 사용되는 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-107">Collection functions are the preferred mode of specifying aggregates in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
- <span data-ttu-id="6bf56-108">GROUP BY 절을 포함하는 쿼리 식의 그룹 집계.</span><span class="sxs-lookup"><span data-stu-id="6bf56-108">Group aggregates in query expressions that have a GROUP BY clause.</span></span> <span data-ttu-id="6bf56-109">Transact-sql에서와 같이 그룹 집계는 DISTINCT 및 ALL을 집계 입력에 대 한 한정자로 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-109">As in Transact-SQL, group aggregates accept DISTINCT and ALL as modifiers to the aggregate input.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="6bf56-110">는 먼저 식을 컬렉션 함수로 해석 하려고 하며 식이 SELECT 식의 컨텍스트에 있는 경우이를 그룹 집계로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-110">first tries to interpret an expression as a collection function and if the expression is in the context of a SELECT expression it interprets it as a group aggregate.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6bf56-111">[Grouppartition](grouppartition-entity-sql.md)이라는 특수 집계 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-111">defines a special aggregate operator called [GROUPPARTITION](grouppartition-entity-sql.md).</span></span> <span data-ttu-id="6bf56-112">이 연산자를 사용하면 그룹화된 입력 집합에 대한 참조를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-112">This operator enables you to get a reference to the grouped input set.</span></span> <span data-ttu-id="6bf56-113">이를 통해 보다 고급 기능의 그룹화 쿼리를 사용할 수 있습니다. 이 경우 GROUP BY 절의 결과는 그룹 집계 또는 컬렉션 함수 이외의 장소에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-113">This allows more advanced grouping queries, where the results of the GROUP BY clause can be used in places other than group aggregate or collection functions.</span></span>  
  
## <a name="collection-functions"></a><span data-ttu-id="6bf56-114">컬렉션 함수</span><span class="sxs-lookup"><span data-stu-id="6bf56-114">Collection Functions</span></span>  

 <span data-ttu-id="6bf56-115">컬렉션 함수는 컬렉션에 대해 작업을 수행하고 스칼라 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-115">Collection functions operate on collections and return a scalar value.</span></span> <span data-ttu-id="6bf56-116">예를 들어, `orders`가 모든 `orders`의 컬렉션인 경우 다음 식을 사용하여 가장 빠른 운송 날짜를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-116">For example, if `orders` is a collection of all `orders`, you can calculate the earliest ship date with the following expression:</span></span>  
  
 `min(select value o.ShipDate from LOB.Orders as o)`  
  
## <a name="group-aggregates"></a><span data-ttu-id="6bf56-117">그룹 집계</span><span class="sxs-lookup"><span data-stu-id="6bf56-117">Group Aggregates</span></span>  

 <span data-ttu-id="6bf56-118">그룹 집계는 GROUP BY 절에 정의된 대로 그룹 결과에 대해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-118">Group aggregates are calculated over a group result as defined by the GROUP BY clause.</span></span> <span data-ttu-id="6bf56-119">GROUP BY 절은 데이터를 그룹으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-119">The GROUP BY clause partitions data  into groups.</span></span> <span data-ttu-id="6bf56-120">결과의 각 그룹별로 집계 함수가 적용되고 각 그룹의 요소를 집계 계산에 대한 입력으로 사용하여 개별 집계가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-120">For each group in the result, the aggregate function is applied and a separate aggregate is calculated by using the elements in each group as inputs to the aggregate calculation.</span></span> <span data-ttu-id="6bf56-121">SELECT 식에 GROUP BY 절이 사용되는 경우에는 그룹화 식 이름, 집계 또는 상수 식만 프로젝션, HAVING 또는 ORDER BY 절에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-121">When a GROUP BY clause is used in a SELECT expression, only grouping expression names, aggregates, or constant expressions may be present in the projection, HAVING, or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="6bf56-122">다음 예제에서는 각 제품에 대해 주문된 평균 수량을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-122">The following example calculates the average quantity ordered for each product.</span></span>  
  
 `select p, avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `group by ol.Product as p`  
  
 <span data-ttu-id="6bf56-123">SELECT 식에서 GROUP BY 절을 명시적으로 사용하지 않고 그룹 집계를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-123">It is possible to have a group aggregate without an explicit GROUP BY clause in the SELECT expression.</span></span> <span data-ttu-id="6bf56-124">모든 요소가 단일 그룹으로 간주되며, 이는 상수를 기준으로 그룹화를 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-124">All elements will be treated as a single group, equivalent to the case of specifying a grouping based on a constant.</span></span>  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol`  
  
 `select avg(ol.Quantity) from LOB.OrderLines as ol group by 1`  
  
 <span data-ttu-id="6bf56-125">GROUP BY 절에서 사용되는 식은 WHERE 절 식에 표시되는 동일한 이름 확인 범위를 사용하여 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bf56-125">Expressions used in the GROUP BY clause are evaluated by using the same name-resolution scope that would be visible to the WHERE clause expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf56-126">참조</span><span class="sxs-lookup"><span data-stu-id="6bf56-126">See also</span></span>

- [<span data-ttu-id="6bf56-127">함수</span><span class="sxs-lookup"><span data-stu-id="6bf56-127">Functions</span></span>](functions-entity-sql.md)
