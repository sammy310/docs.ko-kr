---
title: 배열 범위는 형식 지정자에 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f20ed883005641082eb89e2effa5221594910ffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935358"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>배열 범위는 형식 지정자에 사용할 수 없습니다.
배열 크기는 데이터 형식 지정자의 일부로 선언할 수 없습니다.  
  
 **오류 ID:** BC30638  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 이름 바로 뒤에 변수 형식, 배열 크기를 배치 하는 대신 다음 예와에서 같이 배열 크기를 지정 합니다.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- 배열을 정의 하 고 다음 예와에서 같이 원하는 수의 요소를 초기화 합니다.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>참고자료

- [배열(C++)](../../../visual-basic/programming-guide/language-features/arrays/index.md)
