---
title: '> (보다 큼) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: f2d3a0ed81cf75b7e567dbd07e119629ea47ac69
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833768"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="cda3b-102">> (보다 큼) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cda3b-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="cda3b-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 큰지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="cda3b-104">Syntax</span></span>  
  
```sql  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="cda3b-105">인수</span><span class="sxs-lookup"><span data-stu-id="cda3b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="cda3b-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-106">Any valid expression.</span></span> <span data-ttu-id="cda3b-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cda3b-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="cda3b-108">Result Types</span></span>  
 <span data-ttu-id="cda3b-109">왼쪽 식의 값이 오른쪽 식의 값보다 크면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda3b-110">예제</span><span class="sxs-lookup"><span data-stu-id="cda3b-110">Example</span></span>  
 <span data-ttu-id="cda3b-111">다음 Entity SQL 쿼리는 > 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 큰지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="cda3b-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cda3b-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="cda3b-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cda3b-114">@No__t-0How to: StructuralType 결과 @ no__t-0을 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cda3b-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="cda3b-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GREATER](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="cda3b-116">참조</span><span class="sxs-lookup"><span data-stu-id="cda3b-116">See also</span></span>

- [<span data-ttu-id="cda3b-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="cda3b-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
