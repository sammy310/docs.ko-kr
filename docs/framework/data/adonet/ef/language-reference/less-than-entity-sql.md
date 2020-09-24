---
title: < (보다 작음) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 389c50a697c90dadb075369fe696f7382caf3cff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161921"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="4983f-102">\<(보다 작음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4983f-102">\< (Less Than) (Entity SQL)</span></span>

<span data-ttu-id="4983f-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4983f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4983f-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4983f-105">인수</span><span class="sxs-lookup"><span data-stu-id="4983f-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="4983f-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-106">Any valid expression.</span></span> <span data-ttu-id="4983f-107">두 식은 모두 암시적으로 변환 가능한 데이터 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4983f-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="4983f-108">Result Types</span></span>  

 <span data-ttu-id="4983f-109">왼쪽 식의 값이 오른쪽 식의 값보다 작으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4983f-110">예제</span><span class="sxs-lookup"><span data-stu-id="4983f-110">Example</span></span>  

 <span data-ttu-id="4983f-111">다음 Entity SQL 쿼리는 < 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="4983f-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4983f-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4983f-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4983f-114">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4983f-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4983f-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="4983f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4983f-116">See also</span></span>

- [<span data-ttu-id="4983f-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="4983f-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
