---
title: Sub 또는 Function이 정의되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 9eb13d943f9f1cffc984847f7339111e06f5aa6b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373929"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub 또는 Function이 정의되지 않았습니다(Visual Basic).
`Sub`또는를 `Function` 호출 하기 위해 정의 해야 합니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
- 프로시저 이름의 철자가 틀린 경우  
  
- **참조** 대화 상자에서 해당 프로젝트에 대 한 참조를 명시적으로 추가 하지 않고 다른 프로젝트에서 프로시저를 호출 하려고 합니다.  
  
- 호출 하는 프로시저에 표시 되지 않는 프로시저 지정  
  
- 지정 된 라이브러리 또는 코드 리소스에 없는 Windows DLL (동적 연결 라이브러리) 루틴 또는 Macintosh 코드 리소스 루틴을 선언 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 프로시저 이름의 철자가 정확한 지 확인 합니다.  
  
2. **참조** 대화 상자에서 호출 하려는 프로시저를 포함 하는 프로젝트의 이름을 찾습니다. 표시 되지 않으면 **찾아보기** 단추를 클릭 하 여 검색 합니다. 프로젝트 이름 왼쪽의 확인란을 선택 하 고 **확인**을 클릭 합니다.  
  
3. 루틴의 이름을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목

- [오류 유형](../../programming-guide/language-features/error-types.md)
- [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
- [Sub 문](../statements/sub-statement.md)
- [Function 문](../statements/function-statement.md)
