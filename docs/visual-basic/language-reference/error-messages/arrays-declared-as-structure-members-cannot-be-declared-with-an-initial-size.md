---
title: 구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 58889809b3d8d0823784279c421a141dc8056984
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841968"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.
구조의 배열 초기 크기를 사용 하 여 선언 됩니다. 구조체 요소를 초기화할 수 없습니다 및 배열 크기를 선언 하는 것은 한 가지 형태의 초기화 합니다.  
  
 **오류 ID:** BC31043  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  동적 (초기 크기)으로 구조에서 배열을 정의 합니다.  
  
2.  사용 하 여 동적 배열 차원을 변경할 수 배열의 특정 크기에 필요한 경우는 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md) 코드를 실행 하는 경우. 다음은 이에 대한 예입니다.  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고자료

- [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [방법: 구조 선언](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
