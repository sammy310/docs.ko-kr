---
description: '다음에 대 한 자세한 정보: ANYELEMENT (Entity SQL)'
title: ANYELEMENT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 3330c1b0bed69084bc83c5a689762ff529539d54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697155"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="340d0-103">ANYELEMENT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="340d0-103">ANYELEMENT (Entity SQL)</span></span>

<span data-ttu-id="340d0-104">다중값 컬렉션에서 요소를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-104">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340d0-105">구문</span><span class="sxs-lookup"><span data-stu-id="340d0-105">Syntax</span></span>  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="340d0-106">인수</span><span class="sxs-lookup"><span data-stu-id="340d0-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="340d0-107">요소를 추출할 컬렉션을 반환하는 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-107">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="340d0-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="340d0-108">Return Value</span></span>  

 <span data-ttu-id="340d0-109">컬렉션의 단일 요소 또는 임의 요소(컬렉션에 여러 요소가 있는 경우)를 반환하거나 컬렉션이 비어 있는 경우 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-109">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="340d0-110">`collection`가 형식의 컬렉션인 경우 `Collection<T>` `ANYELEMENT(collection)` 는 형식의 인스턴스를 생성 하는 유효한 식입니다 `T` .</span><span class="sxs-lookup"><span data-stu-id="340d0-110">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="340d0-111">설명</span><span class="sxs-lookup"><span data-stu-id="340d0-111">Remarks</span></span>  

 <span data-ttu-id="340d0-112">ANYELEMENT는 다중값 컬렉션에서 임의의 요소를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-112">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="340d0-113">예를 들어, 다음 예제에서는 `Customers`집합에서 singleton 요소를 추출하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-113">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="340d0-114">예제</span><span class="sxs-lookup"><span data-stu-id="340d0-114">Example</span></span>  

 <span data-ttu-id="340d0-115">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 ANYELEMENT 연산자를 사용하여 다중값 컬렉션에서 요소를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-115">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="340d0-116">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="340d0-117">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="340d0-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="340d0-118">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="340d0-119">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="340d0-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="340d0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="340d0-120">See also</span></span>

- [<span data-ttu-id="340d0-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="340d0-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="340d0-122">nullable 구조적 형식</span><span class="sxs-lookup"><span data-stu-id="340d0-122">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
