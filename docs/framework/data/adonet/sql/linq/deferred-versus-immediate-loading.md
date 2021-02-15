---
description: '자세한 정보: 지연 및 즉시 로드 비교'
title: 지연된 로드 및 즉시 로드 비교
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d7247f-a3b7-460b-b342-5c1a2365aa1a
ms.openlocfilehash: 8c2237bd726ca79c7c168040e2a701f51ec3d238
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464757"
---
# <a name="deferred-versus-immediate-loading"></a><span data-ttu-id="c97aa-103">지연된 로드 및 즉시 로드 비교</span><span class="sxs-lookup"><span data-stu-id="c97aa-103">Deferred versus Immediate Loading</span></span>

<span data-ttu-id="c97aa-104">개체를 쿼리하면 실제로 요청한 개체만 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-104">When you query for an object, you actually retrieve only the object you requested.</span></span> <span data-ttu-id="c97aa-105">*관련* 개체는 동시에 자동으로 인출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-105">The *related* objects are not automatically fetched at the same time.</span></span> <span data-ttu-id="c97aa-106">자세한 내용은 [관계 간 쿼리](querying-across-relationships.md)를 참조 하세요. 관련 개체에 액세스 하려고 시도 하면 해당 개체가 검색 하는 요청을 생성 하기 때문에 관련 개체가 아직 로드 되지 않은 것을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-106">(For more information, see [Querying Across Relationships](querying-across-relationships.md).) You cannot see the fact that the related objects are not already loaded, because an attempt to access them produces a request that retrieves them.</span></span>  
  
 <span data-ttu-id="c97aa-107">예를 들어 특정 주문 집합을 쿼리 한 다음 가끔 특정 고객에 게 전자 메일 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-107">For example, you might want to query for a particular set of orders and then only occasionally send an email notification to particular customers.</span></span> <span data-ttu-id="c97aa-108">처음부터 매 주문마다 모든 고객 데이터를 검색할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-108">You would not necessarily need initially to retrieve all customer data with every order.</span></span> <span data-ttu-id="c97aa-109">지연된 로드를 사용하여 반드시 검색해야 할 때까지 추가 정보의 검색을 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-109">You can use deferred loading to defer retrieval of extra information until you absolutely have to.</span></span> <span data-ttu-id="c97aa-110">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c97aa-110">Consider the following example:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#1)]
 [!code-vb[DLinqQueryConcepts#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c97aa-111">반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-111">The opposite might also be true.</span></span> <span data-ttu-id="c97aa-112">고객과 주문 데이터를 동시에 확인해야 하는 애플리케이션이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="c97aa-112">You might have an application that has to view customer and order data at the same time.</span></span> <span data-ttu-id="c97aa-113">두 데이터 집합이 모두 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-113">You know you need both sets of data.</span></span> <span data-ttu-id="c97aa-114">결과를 얻으면 바로 애플리케이션에 각 고객에 대한 주문 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-114">You know your application needs order information for each customer as soon as you get the results.</span></span> <span data-ttu-id="c97aa-115">각 고객의 주문에 대한 쿼리를 개별적으로 전송하는 것은 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-115">You would not want to submit individual queries for orders for every customer.</span></span> <span data-ttu-id="c97aa-116">이 경우에는 고객과 주문 데이터를 함께 검색하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-116">What you really want is to retrieve the order data together with the customers.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#2)]
 [!code-vb[DLinqQueryConcepts#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#2)]  
  
 <span data-ttu-id="c97aa-117">또한 외적 쿼리를 생성하고 모든 관련 데이터를 하나의 큰 프로젝션으로 검색하여 쿼리에서 고객과 주문을 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-117">You can also join customers and orders in a query by forming the cross-product and retrieving all the relative bits of data as one large projection.</span></span> <span data-ttu-id="c97aa-118">그러나 이 결과는 엔터티가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-118">But these results are not entities.</span></span> <span data-ttu-id="c97aa-119">자세한 내용은 [LINQ to SQL 개체 모델](the-linq-to-sql-object-model.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c97aa-119">(For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md)).</span></span> <span data-ttu-id="c97aa-120">엔터티는 ID를 포함하며 사용자가 수정할 수 있는 개체이지만 이 결과는 변경할 수도 유지할 수도 없는 프로젝션입니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-120">Entities are objects that have identity and that you can modify, whereas these results would be projections that cannot be changed and persisted.</span></span> <span data-ttu-id="c97aa-121">더욱 심각한 문제는 결합된 조인 출력에서 각 주문에 대해 각 고객이 반복되므로 많은 중복 데이터가 검색된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-121">Even worse, you would be retrieving lots of redundant data as each customer repeats for each order in the flattened join output.</span></span>  
  
 <span data-ttu-id="c97aa-122">실제로 필요한 것은 관련 개체 집합을 동시에 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-122">What you really need is a way to retrieve a set of related objects at the same time.</span></span> <span data-ttu-id="c97aa-123">집합은 그래프의 구분된 섹션이므로 실제로 사용할 데이터보다 많거나 적게 검색하지는 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-123">The set is a delineated section of a graph so that you would never be retrieving more or less than was necessary for your intended use.</span></span> <span data-ttu-id="c97aa-124">이를 위해 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델 영역을 즉시 로드하기 위해 <xref:System.Data.Linq.DataLoadOptions>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-124">For this purpose, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides <xref:System.Data.Linq.DataLoadOptions> for immediate loading of a region of your object model.</span></span> <span data-ttu-id="c97aa-125">메서드에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-125">Methods include:</span></span>  
  
- <span data-ttu-id="c97aa-126"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 메서드 - 주 대상과 관련된 데이터를 즉시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-126">The  <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method, to immediately load data related to the main target.</span></span>  
  
- <span data-ttu-id="c97aa-127"><xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 메서드 - 특정 관계에 대해 검색한 개체를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="c97aa-127">The <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method, to filter objects retrieved for a particular relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97aa-128">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c97aa-128">See also</span></span>

- [<span data-ttu-id="c97aa-129">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="c97aa-129">Query Concepts</span></span>](query-concepts.md)
