---
description: '자세한 정보: 스택 공간 부족 (Visual Basic)'
title: 스택 공간이 부족합니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: a32ca0d2becade33177596501b7eabde4251e0a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795491"
---
# <a name="out-of-stack-space-visual-basic"></a>스택 공간이 부족합니다(Visual Basic).

스택은 실행 중인 프로그램의 요구에 따라 동적으로 증가 하 고 축소 되는 메모리의 작업 영역입니다. 제한을 초과 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 프로시저가 너무 많이 중첩 되지 않았는지 확인 합니다.  
  
2. 재귀 프로시저가 올바르게 종료 되는지 확인 합니다.  
  
3. 지역 변수를 사용할 수 있는 것 보다 더 많은 지역 변수 공간이 필요한 경우 모듈 수준에서 일부 변수를 선언 해 보세요. 또한, 또는 키워드 앞에를 사용 하 여 프로시저의 모든 변수를 정적으로 선언할 수 있습니다 `Property` `Sub` `Function` `Static` . 또는 문을 사용 하 여 `Static` 프로시저 내에서 개별 정적 변수를 선언할 수 있습니다.  
  
4. 고정 길이 문자열이 가변 길이 문자열 보다 많은 스택 공간을 사용 하므로 고정 길이 문자열 중 일부를 가변 길이 문자열로 다시 정의 합니다. 스택 공간이 필요 없는 모듈 수준에서 문자열을 정의할 수도 있습니다.  
  
5. `DoEvents`대화 상자를 사용 하 여 `Calls` 스택에서 활성화 된 프로시저를 확인 하 여 중첩 된 함수 호출 수를 확인 합니다.  
  
6. 스택에서 이미 이벤트 프로시저를 호출 하는 이벤트를 트리거하여 "이벤트 cascade"를 발생 시 키 지 않도록 해야 합니다. 이벤트 캐스케이딩은 종결 되지 않은 재귀 프로시저 호출과 유사 하지만, 코드에서 명시적으로 호출 하는 것이 아니라 Visual Basic에 의해 호출이 수행 되기 때문에 명확 하지 않습니다. `Calls`대화 상자를 사용 하 여 스택에서 활성화 된 프로시저를 볼 수 있습니다.  
  
## <a name="see-also"></a>참조

- [메모리 창](/visualstudio/debugger/memory-windows)
