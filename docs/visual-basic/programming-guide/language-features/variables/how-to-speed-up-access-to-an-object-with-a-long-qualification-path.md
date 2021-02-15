---
description: '자세한 정보: 방법: 긴 정규화 경로를 사용 하 여 개체에 대 한 액세스 속도 향상 (Visual Basic)'
title: '방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 8e0b5dc2ab6c23d57a4e9d905cfd711a79843185
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100467045"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)

여러 메서드 및 속성의 정규화 경로를 필요로 하는 개체에 자주 액세스 하는 경우 한정 경로를 반복 하지 않고 코드 속도를 높일 수 있습니다.

두 가지 방법으로 한정 경로를 반복 하지 않을 수 있습니다. 개체를 변수에 할당 하거나 ... 블록에서 사용할 수 있습니다. `With` `End With`

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>변수에 할당 하 여 높은 정규화 된 개체에 대 한 액세스 속도를 높이려면

1. 자주 액세스 하는 개체의 형식에 대 한 변수를 선언 합니다. 선언의 초기화 부분에서 한정 경로를 지정 합니다.

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. 변수를 사용 하 여 개체의 멤버에 액세스 합니다.

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>을 사용 하 여 높은 정규화 된 개체에 대 한 액세스 속도를 높이려면 ... 블록으로 끝

1. 문에 한정 경로를 넣습니다 `With` .

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. 문 앞의 블록 내에서 개체의 멤버에 액세스 합니다 `With` `End With` .

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a>추가 정보

- [개체 변수](object-variables.md)
- [With...End With 문](../../../language-reference/statements/with-end-with-statement.md)
