---
description: '자세한 정보: MULTISET (Entity SQL)'
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: f963638d018299e1cae7435f6dd3b7eaf855b4eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696596"
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="b2ffb-103">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b2ffb-103">MULTISET (Entity SQL)</span></span>

<span data-ttu-id="b2ffb-104">값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-104">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="b2ffb-105">MULTISET 생성자의 모든 값은 호환되는 `T`형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-105">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="b2ffb-106">빈 multiset 생성자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-106">Empty multiset constructors are not allowed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2ffb-107">구문</span><span class="sxs-lookup"><span data-stu-id="b2ffb-107">Syntax</span></span>

```sql
MULTISET ( expression [{, expression }] )
-- or
{ expression [{, expression }] }
```

## <a name="arguments"></a><span data-ttu-id="b2ffb-108">인수</span><span class="sxs-lookup"><span data-stu-id="b2ffb-108">Arguments</span></span>

`expression`  
 <span data-ttu-id="b2ffb-109">유효한 모든 값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-109">Any valid list of values.</span></span>

## <a name="return-value"></a><span data-ttu-id="b2ffb-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="b2ffb-110">Return Value</span></span>

<span data-ttu-id="b2ffb-111">MULTISET 유형의 컬렉션입니다 \<T> .</span><span class="sxs-lookup"><span data-stu-id="b2ffb-111">A collection of type MULTISET\<T>.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2ffb-112">설명</span><span class="sxs-lookup"><span data-stu-id="b2ffb-112">Remarks</span></span>

<!-- markdownlint-disable DOCSMD001 -->

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="b2ffb-113">에서는 행 생성자, 개체 생성자, multiset 또는 컬렉션 생성자라는 세 가지 종류의 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-113">provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="b2ffb-114">자세한 내용은 [형식 구성](constructing-types-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-114">For more information, see [Constructing Types](constructing-types-entity-sql.md).</span></span>

<span data-ttu-id="b2ffb-115">multiset 생성자는 값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-115">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="b2ffb-116">생성자의 모든 값은 호환되는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-116">All the values in the constructor must be of a compatible type.</span></span>

<span data-ttu-id="b2ffb-117">예를 들어, 다음 식은 정수의 multiset를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-117">For example, the following expression creates a multiset of integers.</span></span>

`MULTISET(1, 2, 3)`

`{1, 2, 3}`

> [!NOTE]
> <span data-ttu-id="b2ffb-118">중첩 multiset 리터럴은 래핑 multiset에 단일 multiset 요소가 있는 경우에만 지원 됩니다. 예를 들면 `{{1, 2, 3}}` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-118">Nested multiset literals are only supported when a wrapping multiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="b2ffb-119">래핑 multiset에 여러 개의 multiset 요소가 있는 경우(예: `{{1, 2}, {3, 4}}`) 중첩된 multiset 리터럴이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-119">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>

## <a name="example"></a><span data-ttu-id="b2ffb-120">예제</span><span class="sxs-lookup"><span data-stu-id="b2ffb-120">Example</span></span>

<span data-ttu-id="b2ffb-121">다음 Entity SQL 쿼리에서는 MULTISET 연산자를 사용하여 값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-121">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="b2ffb-122">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b2ffb-123">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-123">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="b2ffb-124">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="b2ffb-125">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ffb-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

[!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]

## <a name="see-also"></a><span data-ttu-id="b2ffb-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2ffb-126">See also</span></span>

- [<span data-ttu-id="b2ffb-127">형식 생성</span><span class="sxs-lookup"><span data-stu-id="b2ffb-127">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="b2ffb-128">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="b2ffb-128">Entity SQL Reference</span></span>](entity-sql-reference.md)
