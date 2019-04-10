---
title: Entity SQL 언어
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 09ec1a5518ec0847b54394449f32b3068c811577
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140935"
---
# <a name="entity-sql-language"></a><span data-ttu-id="6a2e8-102">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="6a2e8-102">Entity SQL Language</span></span>
<span data-ttu-id="6a2e8-103">Entity SQL은 SQL과 유사한 저장소 독립적 쿼리 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="6a2e8-104">Entity SQL을 사용하면 엔터티 데이터를 개체 또는 테이블 형식으로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="6a2e8-105">Entity SQL은 다음의 경우에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="6a2e8-106">쿼리를 동적으로 런타임에 생성해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="6a2e8-107">이 경우에는 런타임에 Entity SQL 쿼리 문자열을 생성하는 대신 <xref:System.Data.Objects.ObjectQuery%601>의 쿼리 작성기 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="6a2e8-108">쿼리를 모델 정의의 일부로 정의할 경우.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="6a2e8-109">Entity SQL만 데이터 모델에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="6a2e8-110">자세한 내용은 참조 하세요. [QueryView 요소 (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="6a2e8-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="6a2e8-111">EntityClient에서 <xref:System.Data.EntityClient.EntityDataReader>를 사용하여 읽기 전용 엔터티 데이터를 행 집합으로 반환할 경우.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="6a2e8-112">자세한 내용은 [Entity Framework 용 EntityClient 공급자](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="6a2e8-113">SQL 기반 쿼리 언어의 전문가에게는 Entity SQL이 가장 편할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="6a2e8-114">EntityClient 공급자와 함께 Entity SQL 사용</span><span class="sxs-lookup"><span data-stu-id="6a2e8-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="6a2e8-115">EntityClient 공급자와 함께 Entity SQL을 사용하려는 경우 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="6a2e8-116">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="6a2e8-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="6a2e8-117">방법: EntityConnection 연결 문자열 빌드</span><span class="sxs-lookup"><span data-stu-id="6a2e8-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="6a2e8-118">방법: PrimitiveType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="6a2e8-119">방법: StructuralType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="6a2e8-120">방법: RefType 결과를 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="6a2e8-121">방법: 복합 형식을 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="6a2e8-122">방법: 중첩 컬렉션을 반환하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="6a2e8-123">방법: EntityCommand를 사용하여 매개 변수가 있는 Entity SQL 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="6a2e8-124">방법: EntityCommand를 사용하여 매개 변수 있는 저장 프로시저 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="6a2e8-125">방법: 다형성 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="6a2e8-126">방법: 탐색 연산자로 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="6a2e8-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="6a2e8-127">개체 쿼리와 함께 Entity SQL 사용</span><span class="sxs-lookup"><span data-stu-id="6a2e8-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="6a2e8-128">개체 쿼리와 함께 Entity SQL을 사용하려는 경우 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a2e8-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="6a2e8-129">방법: 엔터티 형식 개체를 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-130">방법: 매개 변수가 있는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-130">How to: Execute a Parameterized Query</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-131">방법: 탐색 속성을 사용하여 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="6a2e8-131">How to: Navigate Relationships Using Navigation Properties</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-132">방법: 사용자 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="6a2e8-132">How to: Call a User-Defined Function</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-133">방법: 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="6a2e8-133">How to: Filter Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-134">방법: 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="6a2e8-134">How to: Sort Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-135">방법: 데이터 그룹화</span><span class="sxs-lookup"><span data-stu-id="6a2e8-135">How to: Group Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-136">방법: 집계 데이터</span><span class="sxs-lookup"><span data-stu-id="6a2e8-136">How to: Aggregate Data</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-137">방법: 익명 형식 개체를 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-138">방법: 기본 형식의 컬렉션을 반환 하는 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="6a2e8-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-139">방법: EntityCollection의 쿼리 관련 개체</span><span class="sxs-lookup"><span data-stu-id="6a2e8-139">How to: Query Related Objects in an EntityCollection</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-140">방법: 두 개의 쿼리의 공용 구조체 정렬</span><span class="sxs-lookup"><span data-stu-id="6a2e8-140">How to: Order the Union of Two Queries</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [<span data-ttu-id="6a2e8-141">방법: 쿼리 결과 페이징</span><span class="sxs-lookup"><span data-stu-id="6a2e8-141">How to: Page Through Query Results</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a><span data-ttu-id="6a2e8-142">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6a2e8-142">In This Section</span></span>  
 [<span data-ttu-id="6a2e8-143">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="6a2e8-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="6a2e8-144">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="6a2e8-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="6a2e8-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a2e8-145">See also</span></span>

- [<span data-ttu-id="6a2e8-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6a2e8-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="6a2e8-147">언어 참조</span><span class="sxs-lookup"><span data-stu-id="6a2e8-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
