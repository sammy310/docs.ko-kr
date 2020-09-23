---
title: '방법: 배열 변수 초기화'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 1add054a6cb6468f4581f92ca3a258c5b0cdc77d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058861"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>방법: Visual Basic에서 배열 변수 초기화

배열 리터럴을 절에 포함 하 `New` 고 배열의 초기 값을 지정 하 여 배열 변수를 초기화 합니다. 형식을 지정 하거나 배열 리터럴의 값에서 유추 되도록 허용할 수 있습니다. 형식을 유추 하는 방법에 대 한 자세한 내용은 [배열의](index.md)"초기 값으로 배열 채우기"를 참조 하십시오.  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>배열 리터럴을 사용 하 여 배열 변수를 초기화 하려면  
  
- `New`절에서 또는 배열 값을 할당 하는 경우 요소 값을 중괄호 () 안에 제공 `{}` 합니다. 다음 예제에서는 형식의 요소가 포함 된 배열을 포함 하는 변수를 선언 하 고, 만들고, 초기화 하는 여러 가지 방법을 보여 줍니다 `Char` .  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     각 문이 실행 된 후 생성 된 배열의 길이는 3이 고 인덱스 0부터 인덱스 2 까지의 요소는 초기 값을 포함 합니다. 상한과 값을 모두 제공 하는 경우 인덱스 0부터 상한 까지의 모든 요소에 대 한 값을 포함 해야 합니다.  
  
     배열 리터럴에 요소 값을 제공 하는 경우에는 인덱스 상한을 지정할 필요가 없습니다. 상한을 지정 하지 않으면 배열 리터럴의 값 수를 기반으로 배열의 크기가 유추 됩니다.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>배열 리터럴을 사용 하 여 다차원 배열 변수를 초기화 하려면  
  
- 중괄호 내의 중괄호 () 안에 값을 중첩 `{}` 합니다. 중첩 된 배열 리터럴이 모두 동일한 형식 및 길이의 배열로 유추 되는지 확인 합니다. 다음 코드 예제에서는 다차원 배열 초기화의 몇 가지 예를 보여 줍니다.  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- 배열 범위를 명시적으로 지정 하거나, 그대로 두고, 컴파일러가 배열 리터럴의 값을 기준으로 배열 범위를 유추 하도록 할 수 있습니다. 상한 및 값을 모두 제공 하는 경우 인덱스 0부터 모든 차원의 상한 사이의 모든 요소에 대 한 값을 포함 해야 합니다. 다음 예제에서는 형식의 요소가 있는 2 차원 배열을 포함 하는 변수를 선언 하 고, 만들고, 초기화 하는 여러 가지 방법을 보여 줍니다. `Short`  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     각 문이 실행 된 후 생성 된 배열에는,,,, 및 인덱스를 포함 하는 6 개의 초기화 된 요소가 포함 `(0,0)` `(0,1)` `(0,2)` `(1,0)` `(1,1)` `(1,2)` 됩니다. 각 배열 위치에는 값이 포함 `10` 됩니다.  
  
- 다음 예제에서는 다차원 배열을 반복 합니다. Visual Basic으로 작성 된 Windows 콘솔 응용 프로그램에서 메서드 안에 코드를 붙여넣습니다 `Sub Main()` . 마지막 주석은 출력을 보여 줍니다.  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>배열 리터럴을 사용 하 여 가변 배열 변수를 초기화 하려면  
  
- 개체 값을 중괄호 () 안에 중첩 시킵니다 `{}` . 가변 배열의 경우에는 길이가 다른 배열을 지정 하는 배열 리터럴을 중첩할 수도 있지만 중첩 된 배열 리터럴이 괄호 ()로 묶여 있는지 확인 `()` 합니다. 괄호는 중첩 된 배열 리터럴을 강제로 계산 하 고 결과 배열은 가변 배열의 초기 값으로 사용 됩니다. 다음 코드 예제에서는 가변 배열 초기화의 두 가지 예를 보여 줍니다.  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- 다음 예제에서는 가변 배열을 반복 합니다. Visual Basic으로 작성 된 Windows 콘솔 응용 프로그램에서 메서드 안에 코드를 붙여넣습니다 `Sub Main()` .  코드의 마지막 주석은 출력을 보여 줍니다.  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>참조

- [배열](index.md)
- [배열 문제 해결](troubleshooting-arrays.md)
