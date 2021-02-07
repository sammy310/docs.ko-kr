---
description: 다음에 대 한 자세한 정보:/(나누기) (Entity SQL)
title: '- 나누면 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 4ac487c636c460401eeb147dc7ce1a8d8ba7f7ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724637"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="bcfcb-103">/ (나누기) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bcfcb-103">/ (Divide) (Entity SQL)</span></span>

<span data-ttu-id="bcfcb-104">한 숫자를 다른 숫자로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-104">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfcb-105">구문</span><span class="sxs-lookup"><span data-stu-id="bcfcb-105">Syntax</span></span>  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="bcfcb-106">인수</span><span class="sxs-lookup"><span data-stu-id="bcfcb-106">Arguments</span></span>  

 `dividend`  
 <span data-ttu-id="bcfcb-107">나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-107">The numeric expression to divide.</span></span> <span data-ttu-id="bcfcb-108">`dividend` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-108">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="bcfcb-109">피제수를 나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-109">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="bcfcb-110">`divisor` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-110">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="bcfcb-111">결과 형식</span><span class="sxs-lookup"><span data-stu-id="bcfcb-111">Result Types</span></span>  

 <span data-ttu-id="bcfcb-112">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-112">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="bcfcb-113">암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-113">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcfcb-114">예제</span><span class="sxs-lookup"><span data-stu-id="bcfcb-114">Example</span></span>  

 <span data-ttu-id="bcfcb-115">다음 Entity SQL 쿼리에서는/산술 연산자를 사용 하 여 한 숫자를 다른 숫자로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-115">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="bcfcb-116">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bcfcb-117">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bcfcb-118">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bcfcb-119">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bcfcb-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="bcfcb-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcfcb-120">See also</span></span>

- [<span data-ttu-id="bcfcb-121">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="bcfcb-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
