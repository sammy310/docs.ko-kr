---
description: '자세히 알아보기: 변수 (Entity SQL)'
title: 변수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 134fee8f61c8e87a18520e6622f6a6a5cceb0076
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795042"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="f81c8-103">변수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f81c8-103">Variables (Entity SQL)</span></span>

## <a name="variable"></a><span data-ttu-id="f81c8-104">변수</span><span class="sxs-lookup"><span data-stu-id="f81c8-104">Variable</span></span>  

 <span data-ttu-id="f81c8-105">변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c8-105">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="f81c8-106">변수 참조는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [식별자](identifiers-entity-sql.md)에 정의 된 대로 유효한 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f81c8-106">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="f81c8-107">다음 예제에서는 식에서 변수 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f81c8-107">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="f81c8-108">FROM 절의 `c`는 변수 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="f81c8-108">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="f81c8-109">SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f81c8-109">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="f81c8-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f81c8-110">See also</span></span>

- [<span data-ttu-id="f81c8-111">식별자</span><span class="sxs-lookup"><span data-stu-id="f81c8-111">Identifiers</span></span>](identifiers-entity-sql.md)
- [<span data-ttu-id="f81c8-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f81c8-112">Parameters</span></span>](parameters-entity-sql.md)
- [<span data-ttu-id="f81c8-113">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="f81c8-113">Entity SQL Overview</span></span>](entity-sql-overview.md)
