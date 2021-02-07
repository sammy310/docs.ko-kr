---
description: '자세히 알아보기: + (추가)'
title: + (추가)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: b8ec9f50b349fe971513f399b7e9984e9044cf58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697311"
---
# <a name="-add"></a><span data-ttu-id="cbda4-103">+ (추가)</span><span class="sxs-lookup"><span data-stu-id="cbda4-103">+ (Add)</span></span>

<span data-ttu-id="cbda4-104">두 숫자를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-104">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbda4-105">구문</span><span class="sxs-lookup"><span data-stu-id="cbda4-105">Syntax</span></span>  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="cbda4-106">인수</span><span class="sxs-lookup"><span data-stu-id="cbda4-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="cbda4-107">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-107">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cbda4-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="cbda4-108">Result Types</span></span>  

 <span data-ttu-id="cbda4-109">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="cbda4-110">암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbda4-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbda4-111">설명</span><span class="sxs-lookup"><span data-stu-id="cbda4-111">Remarks</span></span>  

 <span data-ttu-id="cbda4-112">EDM.String 형식의 경우 더하기는 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-112">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbda4-113">예제</span><span class="sxs-lookup"><span data-stu-id="cbda4-113">Example</span></span>  

 <span data-ttu-id="cbda4-114">다음 Entity SQL 쿼리에서는 + 산술 연산자를 사용하여 두 숫자를 더합니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-114">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="cbda4-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cbda4-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cbda4-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cbda4-117">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cbda4-118">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cbda4-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="cbda4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbda4-119">See also</span></span>

- [<span data-ttu-id="cbda4-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="cbda4-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="cbda4-121">개념적 모델 형식(CSDL)</span><span class="sxs-lookup"><span data-stu-id="cbda4-121">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
