---
title: '방법: 개체의 현재 인스턴스 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 43bfd54592fb1d26cbf7f268b7e098e01e3745d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410427"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>방법: 개체의 현재 인스턴스 참조(Visual Basic)
개체의 *현재 인스턴스* 는 코드가 현재 실행 중인 인스턴스입니다.  
  
 키워드를 사용 하 여 `Me` 현재 인스턴스를 참조 합니다.  
  
### <a name="to-refer-to-the-current-instance"></a>현재 인스턴스를 참조 하려면  
  
- `Me`일반적으로 개체 변수 이름을 사용 하는 키워드를 사용 합니다.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     `Me`는 개체 변수 처럼 동작 하지만이를 선언 하거나 할당할 수는 없습니다. `Me`항상 현재 인스턴스를 참조 합니다.  
  
## <a name="see-also"></a>참고 항목

- [개체 변수](object-variables.md)
- [개체 변수 할당](object-variable-assignment.md)
- [Me, My, MyBase 및 MyClass](../../program-structure/me-my-mybase-and-myclass.md)
