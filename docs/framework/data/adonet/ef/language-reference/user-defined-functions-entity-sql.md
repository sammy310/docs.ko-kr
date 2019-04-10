---
title: 사용자 정의 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 4922e7fada676a6c26042236ccdb6315d6d455ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104626"
---
# <a name="user-defined-functions-entity-sql"></a>사용자 정의 함수(Entity SQL)
Entity SQL에서는 쿼리에서 사용자 정의 함수를 호출할 수 있습니다. 이러한 함수를 쿼리에서 인라인으로 정의할 수 있습니다 (참조 [방법: 사용자 정의 함수 호출](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) 또는 개념적 모델의 일부로 (참조 [방법: 개념적 모델의 사용자 지정 함수 정의](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))). Entity SQL 명령으로 정의 된 개념적 모델 함수는 [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) 의 요소를 [함수](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) 개념적 모델의 요소입니다.  
  
 Entity SQL을 통해 쿼리 명령 자체에서 함수를 정의할 수 있습니다. 합니다 [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) 연산자는 인라인 함수를 정의 합니다. 함수 시그니처가 고유하면 단일 명령에서 여러 함수를 정의할 수 있으며, 이러한 함수는 이름이 같을 수 있습니다. 자세한 내용은 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
