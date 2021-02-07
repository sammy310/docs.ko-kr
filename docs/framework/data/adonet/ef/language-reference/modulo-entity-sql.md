---
description: '자세한 정보: (모듈로) (Entity SQL)'
title: '% (모듈로)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 8ac9bf2fa9dbee843215dcfeed13fefc7bd54796
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696635"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="49e9e-103">% (모듈로)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="49e9e-103">(Modulo) (Entity SQL)</span></span>

<span data-ttu-id="49e9e-104">한 식을 다른 식으로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-104">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e9e-105">구문</span><span class="sxs-lookup"><span data-stu-id="49e9e-105">Syntax</span></span>  
  
```sql  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="49e9e-106">인수</span><span class="sxs-lookup"><span data-stu-id="49e9e-106">Arguments</span></span>  

 `dividend`  
 <span data-ttu-id="49e9e-107">나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-107">The numeric expression to divide.</span></span> <span data-ttu-id="49e9e-108">`dividend` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-108">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="49e9e-109">피제수를 나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-109">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="49e9e-110">`divisor` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-110">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="49e9e-111">결과 형식</span><span class="sxs-lookup"><span data-stu-id="49e9e-111">Result Types</span></span>  

 <span data-ttu-id="49e9e-112">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="49e9e-112">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="49e9e-113">예제</span><span class="sxs-lookup"><span data-stu-id="49e9e-113">Example</span></span>  

 <span data-ttu-id="49e9e-114">다음 Entity SQL 쿼리에서는 % 산술 연산자를 사용하여 한 식을 다른 식으로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-114">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="49e9e-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="49e9e-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="49e9e-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="49e9e-117">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="49e9e-118">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="49e9e-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#MODULO](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="49e9e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49e9e-119">See also</span></span>

- [<span data-ttu-id="49e9e-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="49e9e-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
