---
title: < (보다 작음) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: fb3f4a1c6bc0df6af3c27836f7b53b2701776366
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319689"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="2c75d-102">\<(보다 작음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2c75d-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="2c75d-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c75d-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c75d-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2c75d-105">인수</span><span class="sxs-lookup"><span data-stu-id="2c75d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2c75d-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-106">Any valid expression.</span></span> <span data-ttu-id="2c75d-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2c75d-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="2c75d-108">Result Types</span></span>  
 <span data-ttu-id="2c75d-109">왼쪽 식의 값이 오른쪽 식의 값보다 작으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c75d-110">예제</span><span class="sxs-lookup"><span data-stu-id="2c75d-110">Example</span></span>  
 <span data-ttu-id="2c75d-111">다음 Entity SQL 쿼리는 < 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="2c75d-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2c75d-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="2c75d-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2c75d-114">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2c75d-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2c75d-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="2c75d-116">참조</span><span class="sxs-lookup"><span data-stu-id="2c75d-116">See also</span></span>

- [<span data-ttu-id="2c75d-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="2c75d-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
