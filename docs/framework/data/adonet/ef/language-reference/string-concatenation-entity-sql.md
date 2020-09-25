---
title: + (문자열 연결) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
ms.openlocfilehash: 92591448a3707ba11ad2462161050e48e0398728
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173629"
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="a77d4-102">+ (문자열 연결)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a77d4-102">+ (String Concatenation) (Entity SQL)</span></span>

<span data-ttu-id="a77d4-103">두 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a77d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="a77d4-104">Syntax</span></span>  
  
```sql  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a77d4-105">인수</span><span class="sxs-lookup"><span data-stu-id="a77d4-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="a77d4-106">EDM.String 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="a77d4-107">두 식이 모두 동일한 데이터 형식으로 되어 있거나 식 하나가 암시적으로 다른 식의 데이터 형식으로 변환될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a77d4-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="a77d4-108">Result Types</span></span>  

 <span data-ttu-id="a77d4-109">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="a77d4-110">암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a77d4-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a77d4-111">예제</span><span class="sxs-lookup"><span data-stu-id="a77d4-111">Example</span></span>  

 <span data-ttu-id="a77d4-112">다음 Entity SQL 쿼리에서는 + 연산자를 사용하여 두 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="a77d4-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a77d4-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="a77d4-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a77d4-115">[방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="a77d4-116">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d4-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CONCAT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="a77d4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a77d4-117">See also</span></span>

- [<span data-ttu-id="a77d4-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a77d4-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a77d4-119">개념적 모델 형식(CSDL)</span><span class="sxs-lookup"><span data-stu-id="a77d4-119">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
