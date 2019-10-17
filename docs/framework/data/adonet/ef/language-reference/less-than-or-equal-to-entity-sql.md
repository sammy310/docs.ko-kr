---
title: < = (작거나 같음) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: b3c8fef47b06b9fdd0a1619a9e56d3d916d9dd2d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319643"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="dc61f-102">\<=(보다 작거나 같음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dc61f-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="dc61f-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작거나 같은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc61f-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc61f-104">Syntax</span></span>  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="dc61f-105">인수</span><span class="sxs-lookup"><span data-stu-id="dc61f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="dc61f-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-106">Any valid expression.</span></span> <span data-ttu-id="dc61f-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="dc61f-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="dc61f-108">Result Types</span></span>  
 <span data-ttu-id="dc61f-109">왼쪽 식의 값이 오른쪽 식의 값보다 작거나 같으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc61f-110">예제</span><span class="sxs-lookup"><span data-stu-id="dc61f-110">Example</span></span>  
 <span data-ttu-id="dc61f-111">다음 Entity SQL 쿼리는 <= 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작거나 같은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="dc61f-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dc61f-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="dc61f-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dc61f-114">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="dc61f-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="dc61f-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="dc61f-116">참조</span><span class="sxs-lookup"><span data-stu-id="dc61f-116">See also</span></span>

- [<span data-ttu-id="dc61f-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="dc61f-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
