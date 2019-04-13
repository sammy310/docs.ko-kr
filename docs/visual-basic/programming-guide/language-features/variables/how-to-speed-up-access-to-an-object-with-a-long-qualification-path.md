---
title: '방법: 정규화 경로가 긴 (Visual Basic)를 사용 하 여 개체에 대 한 액세스 속도'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 94c838a69aab9fcae9dc0c79b6038ee90e2369e7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299139"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>방법: 정규화 경로가 긴 (Visual Basic)를 사용 하 여 개체에 대 한 액세스 속도
여러 메서드 및 속성을 정규화 된 경로 필요로 하는 개체에 자주 액세스 하지는 정규화 된 경로 반복 하 여 코드 속도 수 있습니다.  
  
 두 가지 방법으로 정규화 된 경로 반복을 방지할 수 있습니다. 개체를 변수에 할당할 수 있습니다 또는 사용할 수는 `With`... `End With` 블록입니다.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>변수에 할당 하 여 과도 하 게 정규화 된 개체에 대 한 액세스 속도  
  
1. 자주 액세스 하는 개체 유형의 변수를 선언 합니다. 선언의 초기화 부분에는 정규화 된 경로 지정 합니다.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2. 개체의 멤버에 액세스 하는 변수를 사용 합니다.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>With를 사용 하 여 액세스를 과도 하 게 정규화 된 개체를 가속화 하는 중... End 블록  
  
1. 정규화 된 경로에 배치 된 `With` 문.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2. 내에서 개체의 멤버에 액세스 합니다 `With` 차단 하기 전에 `End With` 문.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>참고자료

- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [With...End With 문](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
