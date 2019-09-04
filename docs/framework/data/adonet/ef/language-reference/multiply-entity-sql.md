---
title: '* 곱하기 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 19fb73d327f91303de938a5f49866339413b9698
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250056"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="8a0d7-102">\* (곱하기) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8a0d7-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="8a0d7-103">두 식을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a0d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a0d7-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8a0d7-105">인수</span><span class="sxs-lookup"><span data-stu-id="8a0d7-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8a0d7-106">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8a0d7-107">결과 형식</span><span class="sxs-lookup"><span data-stu-id="8a0d7-107">Result Types</span></span>  
 <span data-ttu-id="8a0d7-108">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="8a0d7-109">암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a0d7-110">예제</span><span class="sxs-lookup"><span data-stu-id="8a0d7-110">Example</span></span>  
 <span data-ttu-id="8a0d7-111">다음 Entity SQL 쿼리에서는 \* 산술 연산자를 사용하여 두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="8a0d7-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8a0d7-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8a0d7-114">[방법: StructuralType 결과](../how-to-execute-a-query-that-returns-structuraltype-results.md)를 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8a0d7-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="8a0d7-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="8a0d7-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a0d7-116">See also</span></span>

- [<span data-ttu-id="8a0d7-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="8a0d7-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
