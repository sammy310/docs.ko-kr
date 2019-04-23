---
title: '> (보다 큼) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: e1d13fa863eb79982d239f4e2dc298f7fcd1346f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328558"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="b7571-102">> (보다 큼) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b7571-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="b7571-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 큰지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7571-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7571-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b7571-105">인수</span><span class="sxs-lookup"><span data-stu-id="b7571-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b7571-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-106">Any valid expression.</span></span> <span data-ttu-id="b7571-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b7571-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="b7571-108">Result Types</span></span>  
 <span data-ttu-id="b7571-109">왼쪽 식의 값이 오른쪽 식의 값보다 크면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7571-110">예제</span><span class="sxs-lookup"><span data-stu-id="b7571-110">Example</span></span>  
 <span data-ttu-id="b7571-111">다음 Entity SQL 쿼리는 > 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 큰지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="b7571-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b7571-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="b7571-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b7571-114">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b7571-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b7571-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="b7571-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7571-116">See also</span></span>

- [<span data-ttu-id="b7571-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="b7571-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
