---
title: 식이 값이므로 할당 대상일 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 3027be6ee4ed3664b81c661b6a086a3604573833
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826135"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>식이 값이므로 할당 대상일 수 없습니다.
문에서 식에 값을 할당 하려고 합니다. 런타임 시 쓰기 가능한 변수, 속성 또는 배열 요소에만 값을 할당할 수 있습니다. 다음 예제에서는이 오류는 발생 하는 방법을 보여 줍니다.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 비슷한 예는 속성 및 배열 요소에 적용할 수 있습니다.  
  
 **간접 액세스 합니다.** 값 형식을 통해 간접적으로 액세스는이 오류를 생성할 수도 있습니다. 다음 코드 예제 값을 설정 하려고 시도 하는 것이 좋습니다 <xref:System.Drawing.Point> 통해 간접적으로 액세스 하 여 <xref:System.Windows.Forms.Control.Location%2A>입니다.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 위 예의 마지막 문이 실패에 대 한 임시 할당만 만들어지므로 합니다 <xref:System.Drawing.Point> 반환한 구조는 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다. 구조체는 값 형식 및 문을 실행 한 후에 임시 구조 유지 되지 않습니다. 선언에 대 한 변수를 사용 하 여 문제가 해결 되 <xref:System.Windows.Forms.Control.Location%2A>에 대 한 더 영구적인 할당 만듭니다는 <xref:System.Drawing.Point> 구조입니다. 다음 예제에서는 앞의 예제 시간의 마지막 문으로 대체할 수 있는 코드를 보여 줍니다.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **오류 ID:** BC30068  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   문 값 식에 할당 하는 경우 쓰기 가능한 단일 변수, 속성 또는 배열 요소를 사용 하 여 식을 대체 합니다.  
  
-   문이 값 형식 (일반적으로 구조)를 통해 간접적으로 액세스 하는 경우 값 형식을 저장할 변수를 만듭니다.  
  
-   변수에 적절 한 구조 (또는 다른 값 형식)를 할당 합니다.  
  
-   값을 할당 하는 속성에 액세스 하려면 변수를 사용 합니다.  
  
## <a name="see-also"></a>참고자료

- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
- [프로시저 문제 해결](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
