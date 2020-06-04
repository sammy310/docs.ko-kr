---
title: 개체 변수
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410337"
---
# <a name="object-variables-in-visual-basic"></a>Visual Basic의 개체 변수

변수는 직접 값을 저장 하는 것 외에도 개체를 참조할 수 있습니다. 변수에 값을 할당 하는 것과 같은 이유로 개체를 변수에 할당 합니다.

- 변수 이름은 개체 자체에 액세스 하는 데 필요한 메서드 및 속성의 전체 경로 보다 짧고 쉽게 기억할 수 있습니다.

- 개체를 참조 하는 변수를 사용 하는 것은 필요한 메서드나 속성을 통해 개체 자체에 반복 해 서 액세스 하는 것 보다 효율적입니다.

- 코드를 실행 하는 동안 다른 개체를 참조 하도록 변수를 변경할 수 있습니다.

## <a name="making-code-shorter"></a>코드 더 짧게 만들기

개체 변수를 사용 하 여 입력 해야 하는 코드를 줄일 수 있습니다. 다음 예제에서는 메서드 및 속성의 전체 경로를 사용 하 여 개체에 액세스 <xref:System.Windows.Forms.Control> 합니다.

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

컨트롤에 개체 변수를 사용 하는 경우이 코드를 줄이고 실행 속도를 높일 수 있습니다. 할당 하려는 특정 클래스 (이 경우)를 사용 하 여 개체 변수를 선언 해야 합니다 `Control` . 개체를 변수에 할당 한 후에는 개체를 참조 하는 개체를 처리 하는 것과 동일 하 게 처리할 수 있습니다. 개체의 속성을 설정 또는 검색 하거나 해당 메서드 중 하나를 사용할 수 있습니다. 다음 예제에서는 개체 변수를 사용 하 여 앞의 예제에서 코드를 단순화 합니다.

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a>참고 항목

- [변수 선언](variable-declaration.md)
- [방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [개체 변수 선언](object-variable-declaration.md)
- [개체 변수 할당](object-variable-assignment.md)
- [개체 변수 값](object-variable-values.md)
