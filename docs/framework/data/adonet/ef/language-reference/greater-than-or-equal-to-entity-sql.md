---
title: '>= (크거나 같음) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 9e1d7e92097713ebdaf15523a5f99f98ed8be0b3
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833739"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="4e4c3-102">> = (크거나 같음) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4e4c3-102">>= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="4e4c3-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e4c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e4c3-104">Syntax</span></span>  
  
```sql  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e4c3-105">인수</span><span class="sxs-lookup"><span data-stu-id="4e4c3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="4e4c3-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-106">Any valid expression.</span></span> <span data-ttu-id="4e4c3-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4e4c3-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="4e4c3-108">Result Types</span></span>  
 <span data-ttu-id="4e4c3-109">왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e4c3-110">예제</span><span class="sxs-lookup"><span data-stu-id="4e4c3-110">Example</span></span>  
 <span data-ttu-id="4e4c3-111">다음 Entity SQL 쿼리는 >= 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="4e4c3-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4e4c3-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4e4c3-114">[방법: StructuralType 결과를 반환하는 쿼리 실행](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4e4c3-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4e4c3-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="4e4c3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e4c3-116">See also</span></span>

- [<span data-ttu-id="4e4c3-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="4e4c3-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
