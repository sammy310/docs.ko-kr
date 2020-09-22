---
title: DLL 호출 규칙이 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 0481bd5e4dfe7a24dff454d0754b519509fa967f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875735"
---
# <a name="bad-dll-calling-convention"></a>DLL 호출 규칙이 잘못되었습니다.

DLL (동적 연결 라이브러리)로 전달 되는 인수는 루틴에서 예상한 것과 정확히 일치 해야 합니다. 호출 규칙은 인수의 개수, 형식 및 순서를 처리 합니다. 프로그램에서 잘못 된 형식이 나 인수 개수가 전달 되는 DLL의 루틴을 호출 하 고 있을 수 있습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 모든 인수 형식이 호출 하는 루틴의 선언에 지정 된 것과 일치 하는지 확인 합니다.  
  
2. 호출 하는 루틴의 선언에 표시 된 것과 동일한 수의 인수를 전달 하 고 있는지 확인 합니다.  
  
3. DLL 루틴에 값으로 인수가 필요한 경우 `ByVal` 루틴 선언에서 해당 인수에 대해가 지정 되어 있는지 확인 합니다.  
  
## <a name="see-also"></a>참조

- [오류 형식](../../programming-guide/language-features/error-types.md)
- [Call 문](../statements/call-statement.md)
- [Declare 문](../statements/declare-statement.md)
