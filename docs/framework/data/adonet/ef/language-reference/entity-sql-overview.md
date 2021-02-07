---
description: 자세한 내용은 Entity SQL 개요를 확인 하세요.
title: Entity SQL 개요
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: eb337ff3894b24d787d829838c9cf12c934a823c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724611"
---
# <a name="entity-sql-overview"></a><span data-ttu-id="a27c5-103">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="a27c5-103">Entity SQL Overview</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="a27c5-104">는 Entity Framework에서 개념적 모델을 쿼리 하는 데 사용할 수 있는 SQL 유사 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-104">is a SQL-like language that enables you to query conceptual models in the Entity Framework.</span></span> <span data-ttu-id="a27c5-105">개념적 모델은 데이터를 엔터티와 관계로 나타내므로 SQL을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 사용한 사용자에 게 친숙 한 형식으로 이러한 엔터티와 관계를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-105">Conceptual models represent data as entities and relationships, and [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows you to query those entities and relationships in a format that is familiar to those who have used SQL.</span></span>  

 <span data-ttu-id="a27c5-106">Entity Framework는 저장소 관련 데이터 공급자와 함께 작동 하 여 제네릭을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 저장소 관련 쿼리로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-106">The Entity Framework works with storage-specific data providers to translate generic [!INCLUDE[esql](../../../../../../includes/esql-md.md)] into storage-specific queries.</span></span> <span data-ttu-id="a27c5-107">EntityClient 공급자는 엔터티 모델에 대해 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 명령을 실행하고 스칼라 결과, 결과 집합, 개체 그래프를 포함한 다양한 데이터 형식을 반환하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-107">The EntityClient provider supplies a way to execute an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] command against an entity model and return rich types of data including scalar results, result sets, and object graphs.</span></span> <span data-ttu-id="a27c5-108"><xref:System.Data.EntityClient.EntityCommand> 개체를 생성할 때 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리 문자열을 해당 <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> 속성에 할당하여 저장 프로시저 이름 또는 쿼리 텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-108">When you construct <xref:System.Data.EntityClient.EntityCommand> objects, you can specify a stored procedure name or the text of a query by assigning an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query string to its <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a27c5-109"><xref:System.Data.EntityClient.EntityDataReader>는 EDM에 대한 <xref:System.Data.EntityClient.EntityCommand> 실행 결과를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-109">The <xref:System.Data.EntityClient.EntityDataReader> exposes the results of executing a <xref:System.Data.EntityClient.EntityCommand> against an EDM.</span></span> <span data-ttu-id="a27c5-110"><xref:System.Data.EntityClient.EntityDataReader>를 반환하는 명령을 실행하려면 <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-110">To execute the command that returns the <xref:System.Data.EntityClient.EntityDataReader>, call <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>.</span></span>  
  
 <span data-ttu-id="a27c5-111">EntityClient 공급자 외에도 Entity Framework를 사용 하 여 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 개념적 모델에 대해 쿼리를 실행 하 고 엔터티 형식의 인스턴스인 강력한 형식의 CLR 개체로 데이터를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-111">In addition to the EntityClient provider, the Entity Framework enables you to use [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to execute queries against a conceptual model and return data as strongly typed CLR objects that are instances of entity types.</span></span> <span data-ttu-id="a27c5-112">자세한 내용은 [개체 작업](../working-with-objects.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a27c5-112">For more information, see [Working with Objects](../working-with-objects.md).</span></span>  
  
 <span data-ttu-id="a27c5-113">이 단원에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에 대한 개념 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a27c5-113">This section provides conceptual information about [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a27c5-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a27c5-114">In This Section</span></span>  

 [<span data-ttu-id="a27c5-115">Entity SQL과 Transact-SQL의 차이점</span><span class="sxs-lookup"><span data-stu-id="a27c5-115">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)  
  
 [<span data-ttu-id="a27c5-116">Entity SQL 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="a27c5-116">Entity SQL Quick Reference</span></span>](entity-sql-quick-reference.md)  
  
 [<span data-ttu-id="a27c5-117">유형 시스템</span><span class="sxs-lookup"><span data-stu-id="a27c5-117">Type System</span></span>](type-system-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-118">형식 정의</span><span class="sxs-lookup"><span data-stu-id="a27c5-118">Type Definitions</span></span>](type-definitions-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-119">형식 생성</span><span class="sxs-lookup"><span data-stu-id="a27c5-119">Constructing Types</span></span>](constructing-types-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-120">쿼리 계획 캐싱</span><span class="sxs-lookup"><span data-stu-id="a27c5-120">Query Plan Caching</span></span>](query-plan-caching-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a27c5-121">Namespaces</span></span>](namespaces-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-122">식별자</span><span class="sxs-lookup"><span data-stu-id="a27c5-122">Identifiers</span></span>](identifiers-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a27c5-123">Parameters</span></span>](parameters-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-124">변수</span><span class="sxs-lookup"><span data-stu-id="a27c5-124">Variables</span></span>](variables-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-125">지원되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="a27c5-125">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-126">리터럴</span><span class="sxs-lookup"><span data-stu-id="a27c5-126">Literals</span></span>](literals-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-127">Null 리터럴 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="a27c5-127">Null Literals and Type Inference</span></span>](null-literals-and-type-inference-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-128">입력 문자 세트</span><span class="sxs-lookup"><span data-stu-id="a27c5-128">Input Character Set</span></span>](input-character-set-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-129">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="a27c5-129">Query Expressions</span></span>](query-expressions-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-130">함수</span><span class="sxs-lookup"><span data-stu-id="a27c5-130">Functions</span></span>](functions-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-131">연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a27c5-131">Operator Precedence</span></span>](operator-precedence-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-132">페이징</span><span class="sxs-lookup"><span data-stu-id="a27c5-132">Paging</span></span>](paging-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-133">비교 의미 체계</span><span class="sxs-lookup"><span data-stu-id="a27c5-133">Comparison Semantics</span></span>](comparison-semantics-entity-sql.md)  
  
 [<span data-ttu-id="a27c5-134">중첩 Entity SQL 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="a27c5-134">Composing Nested Entity SQL Queries</span></span>](composing-nested-entity-sql-queries.md)  
  
 [<span data-ttu-id="a27c5-135">nullable 구조적 형식</span><span class="sxs-lookup"><span data-stu-id="a27c5-135">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="a27c5-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a27c5-136">See also</span></span>

- [<span data-ttu-id="a27c5-137">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a27c5-137">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a27c5-138">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="a27c5-138">Entity SQL Language</span></span>](entity-sql-language.md)
- [<span data-ttu-id="a27c5-139">CSDL, SSDL 및 MSL 사양</span><span class="sxs-lookup"><span data-stu-id="a27c5-139">CSDL, SSDL, and MSL Specifications</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
