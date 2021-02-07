---
description: '자세히 알아보기: NAVIGATE (Entity SQL)'
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 7fa39a988429fe0a658b01078d2369ad4767f4a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696505"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="e057a-103">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e057a-103">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="e057a-104">엔터티 사이에 설정된 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-104">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="e057a-105">구문</span><span class="sxs-lookup"><span data-stu-id="e057a-105">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="e057a-106">인수</span><span class="sxs-lookup"><span data-stu-id="e057a-106">Arguments</span></span>

<span data-ttu-id="e057a-107">`instance-expression` 엔터티의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-107">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="e057a-108">`relationship-type` CSDL (개념 스키마 정의 언어) 파일에서 관계의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-108">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="e057a-109">는 `relationship-type` .로 한정 \<namespace> 됩니다 \<relationship type name> .</span><span class="sxs-lookup"><span data-stu-id="e057a-109">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="e057a-110">`to` 관계의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-110">`to` The end of the relationship.</span></span>

<span data-ttu-id="e057a-111">`from` 관계의 시작 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-111">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="e057a-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="e057a-112">Return Value</span></span>

<span data-ttu-id="e057a-113">끝 End의 카디널리티가 1인 경우 반환 값은 `Ref<T>`이고,</span><span class="sxs-lookup"><span data-stu-id="e057a-113">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="e057a-114">끝 End의 카디널리티가 n인 경우 반환 값은 `Collection<Ref<T>>`입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-114">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e057a-115">설명</span><span class="sxs-lookup"><span data-stu-id="e057a-115">Remarks</span></span>

<span data-ttu-id="e057a-116">관계는 EDM (엔터티 데이터 모델)의 첫 번째 클래스 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-116">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="e057a-117">둘 이상의 엔터티 형식 간에 관계를 설정할 수 있으며 사용자는 한쪽(엔터티)에서 다른 쪽으로 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-117">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="e057a-118">`from` 및 `to` 는 관계 내의 이름 확인에 모호성이 없는 경우에 한해 조건부로 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-118">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="e057a-119">NAVIGATE는 O 및 C 공간에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-119">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="e057a-120">탐색 구문의 일반적인 형태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-120">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="e057a-121">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="e057a-121">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="e057a-122">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="e057a-122">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="e057a-123">여기서 OrderCustomer는 `relationship`이고, Customer와 Order는 각각 관계의 `to-end` (고객)와 `from-end` (주문)입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-123">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="e057a-124">OrderCustomer가 n:1 관계 이면 탐색 식의 결과 형식은 Ref \<Customer> 입니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-124">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="e057a-125">이 식이 좀 더 단순화된 형태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-125">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="e057a-126">마찬가지로, 다음 형식의 쿼리에서 navigate 식은 Ref><컬렉션을 생성 \<Order> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-126">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="e057a-127">인스턴스 식은 엔터티/참조 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-127">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="e057a-128">예제</span><span class="sxs-lookup"><span data-stu-id="e057a-128">Example</span></span>

<span data-ttu-id="e057a-129">다음 Entity SQL 쿼리는 NAVIGATE 연산자를 사용하여 Address 및 SalesOrderHeader 엔터티 형식 사이에 설정된 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-129">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="e057a-130">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e057a-131">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e057a-131">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="e057a-132">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-132">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="e057a-133">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e057a-133">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="e057a-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e057a-134">See also</span></span>

- [<span data-ttu-id="e057a-135">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e057a-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e057a-136">방법: Navigate 연산자로 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="e057a-136">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
