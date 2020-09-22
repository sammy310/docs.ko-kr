---
title: 이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 9bdc12e3dc57b440ed9f304201b8ec401db37871
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874073"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.

이전 함수 실행 시간이 초과 되었으므로 함수 실행을 사용할 수 없습니다. 함수 실행을 다시 사용 하도록 설정 하려면 다시 한 단계씩 실행 하거나 디버깅을 다시 시작 합니다.  
  
 Visual Studio 디버거에서 식이 프로시저 호출을 지정 하지만 다른 계산 시간이 초과 되었습니다.  
  
 프로시저 호출 시간이 초과 될 경우 무한 루프 또는 *무한 루프*를 포함할 수 있습니다. 자세한 내용은 다음 [을 참조 하세요. 다음 문](../statements/for-next-statement.md).  
  
 무한 루프의 특수 한 경우는 *재귀*입니다. 자세한 내용은 [재귀 프로시저](../../programming-guide/language-features/procedures/recursive-procedures.md)를 참조 하세요.  
  
 **오류 ID:** BC30957  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 가능 하면 이전 함수 평가가 무엇이 었는 지와 그 원인을 확인 하십시오. 그렇지 않으면이 오류가 다시 발생할 수 있습니다.  
  
2. 디버거를 다시 한 단계씩 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.  
  
## <a name="see-also"></a>참조

- [Visual Studio의 디버깅](/visualstudio/debugger/debugger-feature-tour)
- [디버거로 코드 탐색](/visualstudio/debugger/navigating-through-code-with-the-debugger)
