---
title: 선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 2e3f50d08fdf78b5ca9bf9e3399b00ed0328320f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874034"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>선택적 매개 변수 형식으로 사용된 제네릭 매개 변수에는 클래스 제약 조건이 있어야 합니다.

프로시저는 참조 형식으로 제한 되지 않는 형식 매개 변수를 사용 하는 선택적 매개 변수를 사용 하 여 선언 됩니다.  
  
 항상 각 선택적 매개 변수에 대 한 기본값을 제공 해야 합니다. 매개 변수가 참조 형식이 면 선택적 값은 `Nothing` 모든 참조 형식에 유효한 값인로 지정 해야 합니다. 그러나 매개 변수가 값 형식이 면 해당 형식은 Visual Basic에 의해 미리 정의 된 기본 데이터 형식 이어야 합니다. 이는 사용자 정의 구조체와 같은 복합 값 형식에 유효한 기본값이 없기 때문입니다.  
  
 선택적 매개 변수에 대 한 형식 매개 변수를 사용 하는 경우 유효한 기본값이 없는 값 형식의 가능성을 방지 하기 위해 해당 매개 변수를 참조 형식으로 지정 해야 합니다. 즉 `Class` , 키워드를 사용 하거나 특정 클래스의 이름을 사용 하 여 형식 매개 변수를 제한 해야 합니다.  
  
 **오류 ID:** BC32124  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 참조 형식만 허용 하도록 형식 매개 변수를 제한 하거나 선택적 매개 변수에 사용 하지 않습니다.  
  
## <a name="see-also"></a>참조

- [Visual Basic의 제네릭 형식](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
- [Class 문](../statements/class-statement.md)
- [선택적 매개 변수](../../programming-guide/language-features/procedures/optional-parameters.md)
- [구조체](../../programming-guide/language-features/data-types/structures.md)
- [없는지](../nothing.md)
