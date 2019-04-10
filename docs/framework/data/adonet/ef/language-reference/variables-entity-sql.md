---
title: 변수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bf6fa95e38d1eb5817fd67165b6993cbb0755fd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153584"
---
# <a name="variables-entity-sql"></a><span data-ttu-id="1f911-102">변수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1f911-102">Variables (Entity SQL)</span></span>
## <a name="variable"></a><span data-ttu-id="1f911-103">변수</span><span class="sxs-lookup"><span data-stu-id="1f911-103">Variable</span></span>  
 <span data-ttu-id="1f911-104">변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="1f911-104">A variable expression is a reference to a named expression defined in the current scope.</span></span> <span data-ttu-id="1f911-105">변수 참조는 유효 해야 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식별자에 정의 된 대로 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f911-105">A variable reference must be a valid [!INCLUDE[esql](../../../../../../includes/esql-md.md)] identifier, as defined in [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="1f911-106">다음 예제에서는 식에서 변수 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f911-106">The following example shows the use of a variable in the expression.</span></span> <span data-ttu-id="1f911-107">FROM 절의 `c`는 변수 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="1f911-107">The `c` in the FROM clause is the definition of the variable.</span></span> <span data-ttu-id="1f911-108">SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f911-108">The use of `c` in the SELECT clause represents the variable reference.</span></span>  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f911-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f911-109">See also</span></span>

- [<span data-ttu-id="1f911-110">식별자</span><span class="sxs-lookup"><span data-stu-id="1f911-110">Identifiers</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)
- [<span data-ttu-id="1f911-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f911-111">Parameters</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)
- [<span data-ttu-id="1f911-112">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="1f911-112">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
