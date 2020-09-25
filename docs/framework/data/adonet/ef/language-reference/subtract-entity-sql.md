---
title: '- 빼는 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 17841f336ed186dcbc50b84254048546b15297e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181039"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="d7b12-102">- (빼기)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7b12-102">- (Subtract) (Entity SQL)</span></span>

<span data-ttu-id="d7b12-103">두 숫자의 차이 값을 구합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b12-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7b12-104">Syntax</span></span>  
  
```sql  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7b12-105">인수</span><span class="sxs-lookup"><span data-stu-id="d7b12-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="d7b12-106">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d7b12-107">결과 형식</span><span class="sxs-lookup"><span data-stu-id="d7b12-107">Result Types</span></span>  

 <span data-ttu-id="d7b12-108">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d7b12-109">암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7b12-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7b12-110">예제</span><span class="sxs-lookup"><span data-stu-id="d7b12-110">Example</span></span>  

 <span data-ttu-id="d7b12-111">다음 Entity SQL 쿼리에서는 - 산술 연산자를 사용하여 두 숫자를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="d7b12-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d7b12-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="d7b12-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d7b12-114">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d7b12-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b12-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SUBTRACT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="d7b12-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7b12-116">See also</span></span>

- [<span data-ttu-id="d7b12-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="d7b12-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
