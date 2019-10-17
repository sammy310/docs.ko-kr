---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319550"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="c6efb-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c6efb-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="c6efb-103">엔터티 사이에 설정된 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6efb-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6efb-104">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="c6efb-105">인수</span><span class="sxs-lookup"><span data-stu-id="c6efb-105">Arguments</span></span>

<span data-ttu-id="c6efb-106">엔터티 인스턴스를 `instance-expression` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="c6efb-107">CSDL (개념 스키마 정의 언어) 파일에서 관계의 형식 이름을 `relationship-type` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="c6efb-108">@No__t_0은 \<namespace >으로 한정 됩니다. \<relationship 형식 이름 >입니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="c6efb-109">관계의 끝을 `to` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="c6efb-110">관계의 시작 부분을 `from` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="c6efb-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c6efb-111">Return Value</span></span>

<span data-ttu-id="c6efb-112">끝 End의 카디널리티가 1인 경우 반환 값은 `Ref<T>`이고,</span><span class="sxs-lookup"><span data-stu-id="c6efb-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="c6efb-113">끝 End의 카디널리티가 n인 경우 반환 값은 `Collection<Ref<T>>`입니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6efb-114">주의</span><span class="sxs-lookup"><span data-stu-id="c6efb-114">Remarks</span></span>

<span data-ttu-id="c6efb-115">관계는 EDM (엔터티 데이터 모델)의 첫 번째 클래스 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-115">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="c6efb-116">둘 이상의 엔터티 형식 간에 관계를 설정할 수 있으며 사용자는 한쪽(엔터티)에서 다른 쪽으로 관계를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="c6efb-117">`from` 및 `to` 는 관계 내의 이름 확인에 모호성이 없는 경우에 한해 조건부로 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="c6efb-118">NAVIGATE는 O 및 C 공간에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="c6efb-119">탐색 구문의 일반적인 형태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="c6efb-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="c6efb-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="c6efb-121">예를 들면,</span><span class="sxs-lookup"><span data-stu-id="c6efb-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="c6efb-122">여기서 OrderCustomer는 `relationship`이고, Customer와 Order는 각각 관계의 `to-end` (고객)와 `from-end` (주문)입니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="c6efb-123">OrderCustomer가 n:1 관계 이면 탐색 식의 결과 형식은 Ref \<Customer >입니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="c6efb-124">이 식이 좀 더 단순화된 형태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="c6efb-125">마찬가지로, 다음 폼의 쿼리에서 navigate 식은 > > < 참조 \<Order 컬렉션을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="c6efb-126">인스턴스 식은 엔터티/참조 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="c6efb-127">예제</span><span class="sxs-lookup"><span data-stu-id="c6efb-127">Example</span></span>

<span data-ttu-id="c6efb-128">다음 Entity SQL 쿼리는 NAVIGATE 연산자를 사용하여 Address 및 SalesOrderHeader 엔터티 형식 사이에 설정된 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="c6efb-129">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c6efb-130">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c6efb-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="c6efb-131">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="c6efb-132">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c6efb-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="c6efb-133">참조</span><span class="sxs-lookup"><span data-stu-id="c6efb-133">See also</span></span>

- [<span data-ttu-id="c6efb-134">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c6efb-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="c6efb-135">방법: Navigate 연산자로 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="c6efb-135">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
