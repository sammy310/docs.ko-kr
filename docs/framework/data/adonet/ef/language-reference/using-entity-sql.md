---
description: '자세한 정보: 사용 (Entity SQL)'
title: USING(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 084ab56f25041377dd6a0a35dd743122f482eeba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795055"
---
# <a name="using-entity-sql"></a><span data-ttu-id="d7269-103">USING(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d7269-103">USING (Entity SQL)</span></span>

<span data-ttu-id="d7269-104">쿼리 식에 사용되는 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7269-104">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7269-105">구문</span><span class="sxs-lookup"><span data-stu-id="d7269-105">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7269-106">인수</span><span class="sxs-lookup"><span data-stu-id="d7269-106">Arguments</span></span>  

 `alias`  
 <span data-ttu-id="d7269-107">네임스페이스를 정규화하는 데 사용할 짧은 별칭을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7269-107">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="d7269-108">유효한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d7269-108">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7269-109">예제</span><span class="sxs-lookup"><span data-stu-id="d7269-109">Example</span></span>  

 <span data-ttu-id="d7269-110">다음 Entity SQL 쿼리에서는 USING 연산자를 사용하여 쿼리 식에 사용되는 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7269-110">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="d7269-111">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="d7269-111">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d7269-112">[방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7269-112">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="d7269-113">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d7269-113">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7269-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7269-114">See also</span></span>

- [<span data-ttu-id="d7269-115">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d7269-115">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="d7269-116">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="d7269-116">Entity SQL Reference</span></span>](entity-sql-reference.md)
