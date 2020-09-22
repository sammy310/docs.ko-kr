---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867930"
---
# <a name="narrowing-visual-basic"></a>Narrowing(Visual Basic)

변환 연산자 ( `CType` )가 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 값 중 일부를 보유할 수 없는 형식으로 변환 함을 나타냅니다.  
  
## <a name="converting-with-the-narrowing-keyword"></a>축소 키워드를 사용 하 여 변환  

 변환 프로시저는 `Public Shared` 와 함께를 지정 해야 합니다 `Narrowing` .  
  
 축소 변환은 런타임에 항상 성공 하지 않으며 데이터 손실이 발생 하거나 실패할 수 있습니다. 예를 들어,에 대 한 `Long` `Integer` `String` `Date` 기본 형식과 파생 형식에 대 한 기본 형식이 있습니다. 기본 형식에 파생 형식의 멤버가 모두 포함 되어 있지 않아 파생 형식의 인스턴스가 아닌 경우 마지막 변환은 축소입니다.  
  
 `Option Strict`가 이면 `On` 소비 하는 코드에서 `CType` 모든 축소 변환에를 사용 해야 합니다.  
  
 `Narrowing`키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Operator Statement](../statements/operator-statement.md)  
  
## <a name="see-also"></a>참조

- [Operator Statement](../statements/operator-statement.md)
- [Widening](widening.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [방법: 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [CType Function](../functions/ctype-function.md)
- [Option Strict 문](../statements/option-strict-statement.md)
