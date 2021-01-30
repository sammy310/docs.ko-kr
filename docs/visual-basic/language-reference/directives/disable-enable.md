---
title: 지시문 사용 및 사용 안 함
ms.date: 01/28/2021
helpviewer_keywords:
- directives, enable
- directives, disable
- disable directive
ms.openlocfilehash: 3104b25c903465f3a650304f477b25a74591c8ba
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217239"
---
# <a name="disable-and-enable-directives-visual-basic"></a>#Disable 및 #Enable 지시문 (Visual Basic)

`#Disable`및 `#Enable` 지시문은 Visual Basic 소스 코드 컴파일러 지시문입니다. 이러한 코드는 코드 영역에 대 한 특정 경고를 사용 하지 않도록 설정 하 고 다시 활성화 하는 데 사용 됩니다.

```vb
' Suppress warning about no awaits in this method.
#Disable Warning BC42356
    Async Function TestAsync() As Task
        Console.WriteLine("testing")
    End Function
#Enable Warning BC42356
```

쉼표로 구분 된 경고 코드 목록을 사용 하지 않도록 설정 하 고 사용 하도록 설정할 수도 있습니다.

## <a name="see-also"></a>참조

- [Visual Basic 언어 참조](../index.md)
- [코드 분석 경고를 표시 하지 않는 방법](../../../fundamentals/code-analysis/suppress-warnings.md)
