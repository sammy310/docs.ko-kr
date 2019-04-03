---
title: '방법: 및 변수 (Visual Basic) 외부로 데이터 이동'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818541"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>방법: 및 변수 (Visual Basic) 외부로 데이터 이동
대입문의 왼쪽에 변수 이름을 입력 하 여 변수에 값을 저장 합니다.  
  
## <a name="putting-data-in-a-variable"></a>변수에 데이터를 배치합니다.  
  
#### <a name="to-store-a-value-in-a-variable"></a>변수에 값을 저장 하려면  
  
-   대입문의 왼쪽에 변수 이름을 사용 합니다.  
  
     변수의 값을 설정 하는 다음 예제에서는 `alpha`합니다.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     대입문의 오른쪽에 생성 된 값을 변수에 저장 됩니다.  
  
## <a name="getting-data-from-a-variable"></a>변수에서 데이터 가져오기  
 식에서 변수 이름을 포함 하 여 변수의 값을 검색 합니다.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>변수에서 값을 검색 하려면  
  
-   식에서 변수 이름을 사용 합니다. 변수를 사용할 수 있습니다 어디에서 사용할 수 있습니다 상수 또는 리터럴, 제외 하 고 상수 값을 정의 하는 식입니다.  
  
     또는  
  
-   등호 다음 변수 이름을 사용 하 여 (`=`) 대입문에 로그인 합니다.  
  
     다음 예에서는 변수 값을 읽고 `startValue` 다음 변수의 값을 사용 하 여 `counter` 식에 있습니다.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     변수의 값은 상수 및 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다 처럼 식에 참여 합니다.  
  
## <a name="see-also"></a>참고자료

- [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
