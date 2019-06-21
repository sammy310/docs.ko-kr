---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 6ce88cecf210d8b3cf541fe7e870e19a59e344ec
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307328"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="18660-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="18660-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="18660-103">엔터티 사이에 설정된 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="18660-104">구문</span><span class="sxs-lookup"><span data-stu-id="18660-104">Syntax</span></span>

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="18660-105">인수</span><span class="sxs-lookup"><span data-stu-id="18660-105">Arguments</span></span>

<span data-ttu-id="18660-106">`instance-expression` 엔터티의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="18660-107">`relationship-type` 개념 스키마 정의 언어 (CSDL) 파일에서 관계의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="18660-108">합니다 `relationship-type` 으로 한정 됩니다 \<네임 스페이스 >.\< 관계 유형 이름 >.</span><span class="sxs-lookup"><span data-stu-id="18660-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="18660-109">`to` 관계의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="18660-110">`from` 관계의 시작 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="18660-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="18660-111">Return Value</span></span>

<span data-ttu-id="18660-112">끝 End의 카디널리티가 1인 경우 반환 값은 `Ref<T>`이고,</span><span class="sxs-lookup"><span data-stu-id="18660-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="18660-113">끝 End의 카디널리티가 n인 경우 반환 값은 `Collection<Ref<T>>`입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="18660-114">설명</span><span class="sxs-lookup"><span data-stu-id="18660-114">Remarks</span></span>

<span data-ttu-id="18660-115">관계는 엔터티 데이터 모델 (EDM)에서 고급 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-115">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="18660-116">둘 이상의 엔터티 형식 간에 관계를 설정할 수 있으며 사용자는 한쪽(엔터티)에서 다른 쪽으로 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18660-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="18660-117">`from` 및 `to` 는 관계 내의 이름 확인에 모호성이 없는 경우에 한해 조건부로 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="18660-118">NAVIGATE는 O 및 C 공간에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="18660-119">탐색 구문의 일반적인 형태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18660-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="18660-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="18660-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="18660-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="18660-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="18660-122">여기서 OrderCustomer는 `relationship`이고, Customer와 Order는 각각 관계의 `to-end` (고객)와 `from-end` (주문)입니다.</span><span class="sxs-lookup"><span data-stu-id="18660-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="18660-123">OrderCustomer가 n:1 관계 라면 탐색 식의 결과 형식은 Ref 경우\<고객 >.</span><span class="sxs-lookup"><span data-stu-id="18660-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="18660-124">이 식이 좀 더 단순화된 형태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="18660-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="18660-125">마찬가지로, 다음 형태의 쿼리에서 탐색 식은 산출 컬렉션 < Ref\<순서 >> 합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="18660-126">인스턴스 식은 엔터티/참조 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="18660-127">예제</span><span class="sxs-lookup"><span data-stu-id="18660-127">Example</span></span>

<span data-ttu-id="18660-128">다음 Entity SQL 쿼리는 NAVIGATE 연산자를 사용하여 Address 및 SalesOrderHeader 엔터티 형식 사이에 설정된 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="18660-129">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="18660-130">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="18660-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="18660-131">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="18660-132">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="18660-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a><span data-ttu-id="18660-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="18660-133">See also</span></span>

- [<span data-ttu-id="18660-134">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="18660-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="18660-135">방법: 이동 사용 하 여 관계 탐색 연산자</span><span class="sxs-lookup"><span data-stu-id="18660-135">How to: Navigate Relationships with Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
