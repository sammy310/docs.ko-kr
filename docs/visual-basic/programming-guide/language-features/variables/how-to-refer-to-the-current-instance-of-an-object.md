---
title: '방법: 개체 (Visual Basic)의 현재 인스턴스 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 70955cd55dfb91d4111e59ae58bfe409a4470433
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663537"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>방법: 개체 (Visual Basic)의 현재 인스턴스 참조
합니다 *현재 인스턴스* 는 코드가 현재 실행 중인 개체의 합니다.  
  
 사용할는 `Me` 키워드를 현재 인스턴스를 참조 하세요.  
  
### <a name="to-refer-to-the-current-instance"></a>현재 인스턴스를 가리키도록  
  
- 사용 된 `Me` 키워드 위치는 일반적으로 사용 하는 개체 변수의 이름입니다.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     하지만 `Me` 개체 처럼 변수를 선언할 수 없거나 값을 할당할 합니다. `Me` 항상 현재 인스턴스를 의미합니다.  
  
## <a name="see-also"></a>참고자료

- [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
