---
title: ID 캐시에서 개체 검색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
ms.openlocfilehash: 702d88f844f00b86e64404bd100fd6b3d34971c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211233"
---
# <a name="retrieving-objects-from-the-identity-cache"></a><span data-ttu-id="2b6c2-102">ID 캐시에서 개체 검색</span><span class="sxs-lookup"><span data-stu-id="2b6c2-102">Retrieving Objects from the Identity Cache</span></span>
<span data-ttu-id="2b6c2-103">이 항목은 <xref:System.Data.Linq.DataContext>에서 관리하는 ID 캐시에서 개체를 반환하는 LINQ to SQL 쿼리의 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-103">This topic describes the types of LINQ to SQL queries that return an object from the identity cache that is managed by the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="2b6c2-104">LINQ to SQL에서 <xref:System.Data.Linq.DataContext>가 개체를 관리하는 방법 중 하나는 쿼리가 실행될 때 ID 캐시에 개체 ID를 로깅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-104">In LINQ to SQL, one of the ways in which the <xref:System.Data.Linq.DataContext> manages objects is by logging object identities in an identity cache as queries are executed.</span></span> <span data-ttu-id="2b6c2-105">일부 경우 LINQ to SQL은 데이터베이스에서 쿼리를 실행하기 전에 ID 캐시에서 개체를 검색하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-105">In some cases, LINQ to SQL will attempt to retrieve an object from the identity cache before executing a query in the database.</span></span>  
  
 <span data-ttu-id="2b6c2-106">일반적으로 LINQ to SQL 쿼리의 경우 ID 캐시에서 개체를 반환하려면 쿼리가 개체의 기본 키를 기반으로 해야 하며 단일 개체를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-106">In general, for a LINQ to SQL query to return an object from the identity cache, the query must be based on the primary key of an object and must return a single object.</span></span> <span data-ttu-id="2b6c2-107">특히 쿼리는 아래에 나와 있는 일반적인 형태 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-107">In particular, the query must be in one of the general forms shown below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b6c2-108">미리 컴파일된 쿼리는 ID 캐시에서 개체를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-108">Pre-compiled queries will not return objects from the identity cache.</span></span> <span data-ttu-id="2b6c2-109">미리 컴파일된 쿼리에 대 한 자세한 내용은 참조 하세요. <xref:System.Data.Linq.CompiledQuery> 고 [방법: 저장 및 쿼리를 다시 사용](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-109">For more information about pre-compiled queries, see <xref:System.Data.Linq.CompiledQuery> and [How to: Store and Reuse Queries](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).</span></span>  
  
 <span data-ttu-id="2b6c2-110">ID 캐시에서 개체를 검색하려면 쿼리는 다음과 같은 일반적인 형태 중 하나로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-110">A query must be in one of the following general forms to retrieve an object from the identity cache:</span></span>  
  
-   <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`  
  
-   <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`  
  
 <span data-ttu-id="2b6c2-111">이러한 일반적인 형태에서 `Function1`, `Function2` 및 `predicate`는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-111">In these general forms, `Function1`, `Function2`, and `predicate` are defined as follows.</span></span>  
  
 `Function1` <span data-ttu-id="2b6c2-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-112">can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.Where%2A>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `Function2` <span data-ttu-id="2b6c2-113">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-113">can be any of the following:</span></span>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 `predicate` <span data-ttu-id="2b6c2-114">개체의 기본 키 속성을 상수 값으로 설정 되어 있는 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-114">must be an expression in which the object's primary key property is set to a constant value.</span></span> <span data-ttu-id="2b6c2-115">개체에 둘 이상의 속성에서 정의한 기본 키가 있는 경우 각 기본 키 속성은 상수 값으로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-115">If an object has a primary key defined by more than one property, each primary key property must be set to a constant value.</span></span> <span data-ttu-id="2b6c2-116">다음은 `predicate`가 사용해야 하는 형태의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-116">The following are examples of the form `predicate` must take:</span></span>  
  
-   `c => c.PK == constant_value`  
  
-   `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## <a name="example"></a><span data-ttu-id="2b6c2-117">예제</span><span class="sxs-lookup"><span data-stu-id="2b6c2-117">Example</span></span>  
 <span data-ttu-id="2b6c2-118">다음 코드는 ID 캐시에서 개체를 검색하는 LINQ to SQL 쿼리의 형식에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b6c2-118">The following code provides examples of the types of LINQ to SQL queries that retrieve an object from the identity cache.</span></span>  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2b6c2-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b6c2-119">See also</span></span>

- [<span data-ttu-id="2b6c2-120">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="2b6c2-120">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="2b6c2-121">개체 ID</span><span class="sxs-lookup"><span data-stu-id="2b6c2-121">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
- [<span data-ttu-id="2b6c2-122">배경 정보</span><span class="sxs-lookup"><span data-stu-id="2b6c2-122">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="2b6c2-123">개체 ID</span><span class="sxs-lookup"><span data-stu-id="2b6c2-123">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)
