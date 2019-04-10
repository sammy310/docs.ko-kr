---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: d4293b8e027f7f0f7eabac7ad9c8a9852ddd3a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178479"
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="caa6a-102">MULTISET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="caa6a-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="caa6a-103">값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="caa6a-104">MULTISET 생성자의 모든 값은 호환되는 `T`형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="caa6a-105">빈 multiset 생성자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa6a-106">구문</span><span class="sxs-lookup"><span data-stu-id="caa6a-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="caa6a-107">인수</span><span class="sxs-lookup"><span data-stu-id="caa6a-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="caa6a-108">유효한 모든 값 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caa6a-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="caa6a-109">Return Value</span></span>  
 <span data-ttu-id="caa6a-110">MULTISET 형식의 컬렉션인\<T >입니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caa6a-111">설명</span><span class="sxs-lookup"><span data-stu-id="caa6a-111">Remarks</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="caa6a-112">세 가지 종류의 생성자를 제공 합니다: 행 생성자, 개체 생성자, multiset 또는 컬렉션 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-112">provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="caa6a-113">자세한 내용은 [형식 생성](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="caa6a-114">multiset 생성자는 값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="caa6a-115">생성자의 모든 값은 호환되는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="caa6a-116">예를 들어, 다음 식은 정수의 multiset를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="caa6a-117">중첩 된 multiset 리터럴은 래핑 multiset에 단일 multiset 요소가 있을 때만 지원 됩니다. 예를 들어 `{{1, 2, 3}}`합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-117">Nested multiset literals are only supported when a wrapping multiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="caa6a-118">래핑 multiset에 여러 개의 multiset 요소가 있는 경우(예: `{{1, 2}, {3, 4}}`) 중첩된 multiset 리터럴이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caa6a-119">예제</span><span class="sxs-lookup"><span data-stu-id="caa6a-119">Example</span></span>  
 <span data-ttu-id="caa6a-120">다음 Entity SQL 쿼리에서는 MULTISET 연산자를 사용하여 값 목록에서 multiset 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="caa6a-121">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="caa6a-122">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="caa6a-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="caa6a-123">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="caa6a-124">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="caa6a-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="caa6a-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="caa6a-125">See also</span></span>

- [<span data-ttu-id="caa6a-126">형식 생성</span><span class="sxs-lookup"><span data-stu-id="caa6a-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="caa6a-127">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="caa6a-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
