---
title: 변수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 88ee41bc08711cf84b8b2e273c9ac0f4267d1d34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149819"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="213c9-102">변수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="213c9-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="213c9-103">변수</span><span class="sxs-lookup"><span data-stu-id="213c9-103">Variable</span></span>  
 <span data-ttu-id="213c9-104">변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="213c9-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="213c9-105">변수 참조는 식별자 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에 정의된 대로 유효한 [식별자여야](identifiers-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="213c9-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="213c9-106">다음 예제에서는 식에서 변수 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="213c9-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="213c9-107">FROM 절의 `c`는 변수 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="213c9-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="213c9-108">SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="213c9-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="213c9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="213c9-109">See also</span></span>

- [<span data-ttu-id="213c9-110">식별자</span><span class="sxs-lookup"><span data-stu-id="213c9-110">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="213c9-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="213c9-111">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="213c9-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="213c9-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
