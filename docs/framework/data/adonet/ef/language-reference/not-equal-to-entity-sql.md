---
description: 자세히 알아보기:! = (같지 않음) (Entity SQL)
title: '!= (같지 않음)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: a7a96606fb1834b757253948c3a0d2cde11893dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696401"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="9c858-103">!= (같지 않음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9c858-103">!= (Not Equal To) (Entity SQL)</span></span>

<span data-ttu-id="9c858-104">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값과 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-104">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="9c858-105">!=(같지 않음) 연산자는 기능이 <> 연산자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-105">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c858-106">구문</span><span class="sxs-lookup"><span data-stu-id="9c858-106">Syntax</span></span>  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c858-107">인수</span><span class="sxs-lookup"><span data-stu-id="9c858-107">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="9c858-108">유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-108">Any valid expression.</span></span> <span data-ttu-id="9c858-109">두 식은 모두 암시적으로 변환 가능한 데이터 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-109">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9c858-110">결과 형식</span><span class="sxs-lookup"><span data-stu-id="9c858-110">Result Types</span></span>  

 <span data-ttu-id="9c858-111">왼쪽 식의 값이 오른쪽 식의 값과 다르면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-111">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c858-112">예제</span><span class="sxs-lookup"><span data-stu-id="9c858-112">Example</span></span>  

 <span data-ttu-id="9c858-113">다음 Entity SQL 쿼리는 != 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값과 다른지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-113">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="9c858-114">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9c858-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="9c858-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9c858-116">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9c858-117">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9c858-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="9c858-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c858-118">See also</span></span>

- [<span data-ttu-id="9c858-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="9c858-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
