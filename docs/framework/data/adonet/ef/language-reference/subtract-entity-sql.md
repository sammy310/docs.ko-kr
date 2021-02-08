---
description: 자세한 정보:-(빼기) (Entity SQL)
title: '- 빼는 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: cba23d998ad6beaf545118c69d806de46a1f6db0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791831"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="76ffa-103">- (빼기)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="76ffa-103">- (Subtract) (Entity SQL)</span></span>

<span data-ttu-id="76ffa-104">두 숫자의 차이 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-104">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ffa-105">구문</span><span class="sxs-lookup"><span data-stu-id="76ffa-105">Syntax</span></span>  
  
```sql  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="76ffa-106">인수</span><span class="sxs-lookup"><span data-stu-id="76ffa-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="76ffa-107">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-107">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="76ffa-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="76ffa-108">Result Types</span></span>  

 <span data-ttu-id="76ffa-109">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="76ffa-110">암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76ffa-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76ffa-111">예제</span><span class="sxs-lookup"><span data-stu-id="76ffa-111">Example</span></span>  

 <span data-ttu-id="76ffa-112">다음 Entity SQL 쿼리에서는 - 산술 연산자를 사용하여 두 숫자를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-112">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="76ffa-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="76ffa-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="76ffa-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="76ffa-115">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="76ffa-116">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="76ffa-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SUBTRACT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="76ffa-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76ffa-117">See also</span></span>

- [<span data-ttu-id="76ffa-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="76ffa-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
