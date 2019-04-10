---
title: + (추가)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: 8ecbb7a8b38625f248dbfb5974bb8c64eb482ca2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328272"
---
# <a name="-add"></a><span data-ttu-id="f7ef4-102">+ (추가)</span><span class="sxs-lookup"><span data-stu-id="f7ef4-102">+ (Add)</span></span>
<span data-ttu-id="f7ef4-103">두 숫자를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ef4-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7ef4-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f7ef4-105">인수</span><span class="sxs-lookup"><span data-stu-id="f7ef4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f7ef4-106">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="f7ef4-107">결과 형식</span><span class="sxs-lookup"><span data-stu-id="f7ef4-107">Result Types</span></span>  
 <span data-ttu-id="f7ef4-108">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="f7ef4-109">암시적 형식 승격에 대 한 자세한 내용은 참조 하세요. [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7ef4-110">설명</span><span class="sxs-lookup"><span data-stu-id="f7ef4-110">Remarks</span></span>  
 <span data-ttu-id="f7ef4-111">EDM.String 형식의 경우 더하기는 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ef4-112">예제</span><span class="sxs-lookup"><span data-stu-id="f7ef4-112">Example</span></span>  
 <span data-ttu-id="f7ef4-113">다음 Entity SQL 쿼리에서는 + 산술 연산자를 사용하여 두 숫자를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="f7ef4-114">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f7ef4-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f7ef4-116">절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f7ef4-117">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ef4-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="f7ef4-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7ef4-118">See also</span></span>

- [<span data-ttu-id="f7ef4-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="f7ef4-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="f7ef4-120">개념적 모델 형식(CSDL)</span><span class="sxs-lookup"><span data-stu-id="f7ef4-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
