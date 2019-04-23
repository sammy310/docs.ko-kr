---
title: 오류 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831568"
---
# <a name="error-types-visual-basic"></a>오류 형식(Visual Basic)
Visual basic의 경우 오류 (라고도 *예외*) 세 가지 범주 중 하나에 속합니다: 구문 오류, 런타임 오류 및 논리 오류입니다.  
  
## <a name="syntax-errors"></a>구문 오류  
 *구문 오류* 는 코드를 작성 하는 동안 발생 하 합니다. Visual Basic에서 입력할 때 코드를 확인 합니다 **코드 편집기** 창 고 철자 부적절 하 게 언어 요소를 사용 하 여 등의 실수 한 경우 경고 합니다. 구문 오류는 오류의 가장 일반적인 형식입니다. 해결할 수 있습니다 이러한 쉽게 코딩 환경에서 발생 하는 즉시.  
  
> [!NOTE]
>  `Option Explicit` 문의 구문 오류를 방지 하는 한 가지 방법은 됩니다. 한다는 미리 응용 프로그램에서 사용할 모든 변수를 선언할 수 있습니다. 따라서 코드에서 해당 변수를 사용 하면 인쇄 오류 즉시 발생 및 해결할 수 있습니다.  
  
## <a name="run-time-errors"></a>런타임 오류  
 *런타임 오류* 는 컴파일 및 코드를 실행 한 후에 표시 되는 것입니다. 이러한 구문 오류가 없는지 되었지만 실행 되지 것입니다는 올바른 것으로 나타날 수 있는 코드를 포함 합니다. 예를 들어 파일을 여는 코드 줄을 올바르게 작성할 수 있습니다. 하지만 응용 프로그램이 수행할 수 없으면 파일 손상 된 경우는 `Open` 함수 및 해당 실행을 중지 합니다. 잘못 된 코드를 재작성 로컬 폴더를 컴파일하여 다시 실행 하 여 대부분의 런타임 오류를 해결할 수 있습니다.  
  
## <a name="logic-errors"></a>논리 오류  
 *논리 오류* 는 나타나는 응용 프로그램을 사용에서 합니다. 이들은 사용자 작업에 대 한 응답에서 대부분의 종종 원치 않거나 예기치 않은 결과입니다. 예를 들어, 키를 잘못 입력된 또는 기타 외부 요인 않이 예상된 매개 변수 내에서 작업을 중지 하려면 응용 프로그램 또는 완전히 합니다. 논리 오류는 일반적으로 아니므로 항상 지우기 시작 위치를 해결 하려면 가장 어려운 형식입니다.  
  
## <a name="see-also"></a>참고자료

- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [디버거 기본 사항](/visualstudio/debugger/debugger-basics)
