---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 14e0b026f4fc3b0bf202ea643a28d6f1a7df2b7c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867647"
---
# <a name="widening-visual-basic"></a>Widening(Visual Basic)

변환 연산자 ( `CType` )가 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 모든 값을 보유할 수 있는 형식으로 변환 함을 나타냅니다.  
  
## <a name="converting-with-the-widening-keyword"></a>확대/축소 키워드를 사용 하 여 변환  

 변환 프로시저는 `Public Shared` 와 함께를 지정 해야 합니다 `Widening` .  
  
 확대 변환은 런타임에 항상 성공 하며 데이터 손실이 발생 하지 않습니다. 예를 들어, `Single` `Double` 파생 된 `Char` `String` 형식을 기본 형식으로 변환할 수 있습니다. 이 마지막 변환은 파생 된 형식에 기본 형식의 모든 멤버가 포함 되어 있으므로 기본 형식의 인스턴스입니다.  
  
 를 사용 하는 코드는 `CType` 가 인 경우에도 확대 변환에를 사용할 필요가 없습니다. `Option Strict` `On`  
  
 `Widening`키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 확대 및 축소 변환 연산자의 정의 예제 [는 방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [Operator Statement](../statements/operator-statement.md)
- [Narrowing](narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [방법: 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict 문](../statements/option-strict-statement.md)
- [방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
