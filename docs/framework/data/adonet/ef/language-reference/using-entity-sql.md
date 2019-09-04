---
title: USING(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 9495e5daf88326c5a682172d835c3349fe79e571
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248756"
---
# <a name="using-entity-sql"></a><span data-ttu-id="e27c6-102">USING(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e27c6-102">USING (Entity SQL)</span></span>
<span data-ttu-id="e27c6-103">쿼리 식에 사용되는 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e27c6-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e27c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e27c6-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="e27c6-105">인수</span><span class="sxs-lookup"><span data-stu-id="e27c6-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="e27c6-106">네임스페이스를 정규화하는 데 사용할 짧은 별칭을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e27c6-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="e27c6-107">유효한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e27c6-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e27c6-108">예제</span><span class="sxs-lookup"><span data-stu-id="e27c6-108">Example</span></span>  
 <span data-ttu-id="e27c6-109">다음 Entity SQL 쿼리에서는 USING 연산자를 사용하여 쿼리 식에 사용되는 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e27c6-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="e27c6-110">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e27c6-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e27c6-111">[방법: PrimitiveType 결과](../how-to-execute-a-query-that-returns-primitivetype-results.md)를 반환 하는 쿼리를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e27c6-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="e27c6-112">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e27c6-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e27c6-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e27c6-113">See also</span></span>

- [<span data-ttu-id="e27c6-114">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e27c6-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="e27c6-115">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e27c6-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
