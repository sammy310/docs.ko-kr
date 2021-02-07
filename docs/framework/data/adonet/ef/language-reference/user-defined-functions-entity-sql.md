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
# <a name="user-defined-functions-entity-sql"></a>사용자 정의 함수(Entity SQL)

Entity SQL에서는 쿼리에서 사용자 정의 함수를 호출할 수 있습니다. 이러한 함수는 쿼리 ( [방법: User-Defined 함수 호출](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)))를 사용 하 여 인라인으로 정의 하거나 개념적 모델의 일부로 정의할 수 있습니다. [방법: 개념적 모델의 사용자 지정 함수 정의를](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))참조 하세요. 개념적 모델 함수는 개념적 모델에 있는 [Function](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) 요소의 [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) 요소에서 Entity SQL 명령으로 정의 됩니다.  
  
 Entity SQL을 통해 쿼리 명령 자체에서 함수를 정의할 수 있습니다. [함수](function-entity-sql.md) 연산자는 인라인 함수를 정의 합니다. 함수 시그니처가 고유하면 단일 명령에서 여러 함수를 정의할 수 있으며, 이러한 함수는 이름이 같을 수 있습니다. 자세한 내용은 [Function Overload Resolution](function-overload-resolution-entity-sql.md)을 참조하세요.  
  
## <a name="see-also"></a>참조

- [함수](functions-entity-sql.md)
