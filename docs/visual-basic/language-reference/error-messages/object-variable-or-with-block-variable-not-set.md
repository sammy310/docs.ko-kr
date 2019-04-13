---
title: Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: b2c0c47b359e218111c1629ea574303a6d663046
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297930"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
잘못 된 개체 변수는 참조 됩니다.   여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.  
  
-   변수는 형식을 지정 하지 않고 선언 되었습니다. 기본적으로 입력 변수 형식을 지정 하지 않고 선언 된 경우 `Object`합니다.  
  
     예를 들어, 사용 하 여 선언 된 변수에 `Dim x` 형식의 것 `Object;` 로 선언 된 변수 `Dim x As String` 형식일 수는 `String`합니다.  
  
    > [!TIP]
    >  합니다 `Option Strict` 문이 발생 되는 암시적 형식을 허용 하지 않는 `Object` 형식입니다. 형식을 생략 하면 컴파일 타임 오류가 발생 합니다. 참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.  
  
-   에 설정 된 개체를 참조 하려고 합니다. `Nothing`  
  
     .  
  
-   배열 변수를 제대로 선언 되지 않은의 요소에 액세스 하려고 합니다.  
  
     로 배열을 선언 하는 예를 들어 `products() As String` 배열의 요소를 참조 하려고 하면 오류를 트리거할 `products(3) = "Widget"`합니다. 배열의 요소가 없는 고 개체로 처리 됩니다.  
  
-   내의 코드에서 액세스 하려는 `With...End With` 블록 초기화 되기 전에 차단 합니다.   A `With...End With` 블록을 실행 하 여 초기화 해야 합니다 `With` 문 진입점입니다.  
  
> [!NOTE]
>  이전 버전의 Visual Basic 또는 VBA에서이 오류도을 트리거한 것을 사용 하지 않고 값을 변수에 할당 합니다 `Set` 키워드 (`x = "name"` 대신 `Set x = "name"`). `Set` 키워드 Visual Basic.net에서 더 이상 유효 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. 설정할 `Option Strict` 에 `On` 파일의 시작 부분에 다음 코드를 추가 하 여:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2. 사용 하도록 설정 하지 않으려면 `Option Strict`, 형식을 사용 하지 않고 지정 된 변수에 대 한 코드 검색 (`Dim x` 대신 `Dim x As String`) 의도 된 형식 선언에 추가 합니다.  
  
3. 에 설정 된 개체 변수에 참조 되지 있는지 `Nothing`합니다.  키워드에 대 한 코드 검색 `Nothing`, 개체 설정 되지 않도록 코드를 수정 하 고 `Nothing` 참조 한 후 될 때까지 합니다.  
  
4. 액세스 하기 전에 모든 배열 변수는 차원이 구분 해야 합니다. 배열을 처음 만들 때 차원을 할당 하거나 (`Dim x(5) As String` 대신 `Dim x() As String`)를 사용할지를 `ReDim` 처음으로 액세스 하기 전에 배열의 차수를 설정 하려면 키워드입니다.  
  
5. 있는지 확인 하 `With` 블록을 실행 하 여 초기화를 `With` 문 진입점입니다.  
  
## <a name="see-also"></a>참고자료

- [개체 변수 선언](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)
- [With...End With 문](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
