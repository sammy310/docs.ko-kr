---
description: '자세한 정보: User-Defined 함수 (Entity SQL)'
title: 사용자 정의 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: b5ebff087da08530e13f301e58509ba2d90c3605
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673208"
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="344a4-103">사용자 정의 함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="344a4-103">User-Defined Functions (Entity SQL)</span></span>

<span data-ttu-id="344a4-104">Entity SQL에서는 쿼리에서 사용자 정의 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344a4-104">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="344a4-105">이러한 함수는 쿼리 ( [방법: User-Defined 함수 호출](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)))를 사용 하 여 인라인으로 정의 하거나 개념적 모델의 일부로 정의할 수 있습니다. [방법: 개념적 모델의 사용자 지정 함수 정의를](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="344a4-105">You can define these functions inline with the query (see [How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span></span> <span data-ttu-id="344a4-106">개념적 모델 함수는 개념적 모델에 있는 [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) 요소의 [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) 요소에서 Entity SQL 명령으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="344a4-106">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) element of a [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="344a4-107">Entity SQL을 통해 쿼리 명령 자체에서 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344a4-107">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="344a4-108">[함수](function-entity-sql.md) 연산자는 인라인 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="344a4-108">The [FUNCTION](function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="344a4-109">함수 시그니처가 고유하면 단일 명령에서 여러 함수를 정의할 수 있으며, 이러한 함수는 이름이 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344a4-109">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="344a4-110">자세한 내용은 [Function Overload Resolution](function-overload-resolution-entity-sql.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="344a4-110">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344a4-111">참조</span><span class="sxs-lookup"><span data-stu-id="344a4-111">See also</span></span>

- [<span data-ttu-id="344a4-112">함수</span><span class="sxs-lookup"><span data-stu-id="344a4-112">Functions</span></span>](functions-entity-sql.md)
