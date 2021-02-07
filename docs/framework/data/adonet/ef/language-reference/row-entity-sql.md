---
description: '자세히 알아보기: ROW (Entity SQL)'
title: ROW(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 2d0bcf3c5be8ef3b67e170af5159ae7dd8744630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739276"
---
# <a name="row-entity-sql"></a><span data-ttu-id="a65f4-103">ROW(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a65f4-103">ROW (Entity SQL)</span></span>

<span data-ttu-id="a65f4-104">값 하나 이상을 기반으로 하여 구조적으로 형식화된 익명 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-104">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65f4-105">구문</span><span class="sxs-lookup"><span data-stu-id="a65f4-105">Syntax</span></span>  
  
```sql  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="a65f4-106">인수</span><span class="sxs-lookup"><span data-stu-id="a65f4-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="a65f4-107">행 형식에서 생성되는 값을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-107">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="a65f4-108">행 형식에서 지정된 값의 별칭을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-108">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="a65f4-109">별칭이 제공되지 않은 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 별칭 생성 규칙에 따라 별칭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-109">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a65f4-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="a65f4-110">Return Value</span></span>  

 <span data-ttu-id="a65f4-111">행 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-111">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a65f4-112">설명</span><span class="sxs-lookup"><span data-stu-id="a65f4-112">Remarks</span></span>  

 <span data-ttu-id="a65f4-113">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 의 행 생성자를 사용하여 값 하나 이상을 기반으로 구조적으로 형식화된 익명 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-113">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="a65f4-114">행 생성자의 결과 형식은 필드 형식이 행 생성에 사용된 값의 형식과 동일한 행 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-114">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="a65f4-115">예를 들어, 다음 식은 형식 `Record(a int, b string, c int)`의 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-115">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```sql  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="a65f4-116">행 생성자에서 식의 별칭을 제공하지 않으면 Entity Framework에서 별칭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-116">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="a65f4-117">자세한 내용은 [식별자](identifiers-entity-sql.md) 항목의 "별칭 지정 규칙" 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a65f4-117">For more information, see the "Aliasing Rules" section of the [Identifiers](identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="a65f4-118">행 생성자에서 식에 별칭을 지정하는 데 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-118">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="a65f4-119">행 생성자의 식은 동일한 생성자 내의 다른 별칭을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-119">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="a65f4-120">동일한 행 생성자 내의 서로 다른 두 식은 별칭이 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-120">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="a65f4-121">쿼리 생성자에 대 한 자세한 내용은 [형식 구성](constructing-types-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a65f4-121">For more information about query constructors, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a65f4-122">예제</span><span class="sxs-lookup"><span data-stu-id="a65f4-122">Example</span></span>  

 <span data-ttu-id="a65f4-123">다음 Entity SQL 쿼리에서는 ROW 연산자를 사용하여 구조적으로 형식화된 익명 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-123">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="a65f4-124">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-124">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a65f4-125">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="a65f4-125">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a65f4-126">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-126">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a65f4-127">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f4-127">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ROW](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#row)]  
  
## <a name="see-also"></a><span data-ttu-id="a65f4-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a65f4-128">See also</span></span>

- [<span data-ttu-id="a65f4-129">형식 생성</span><span class="sxs-lookup"><span data-stu-id="a65f4-129">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="a65f4-130">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a65f4-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a65f4-131">형식 정의</span><span class="sxs-lookup"><span data-stu-id="a65f4-131">Type Definitions</span></span>](type-definitions-entity-sql.md)
