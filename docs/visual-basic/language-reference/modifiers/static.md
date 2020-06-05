---
title: 정적
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 3b323d5fb1c4f1357b9f476213793c69d29b7208
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402696"
---
# <a name="static-visual-basic"></a>Static(Visual Basic)
선언 된 지역 변수를 하나 이상 유지 하 고 선언 된 프로시저가 종료 된 후에 최신 값을 유지 하도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 프로시저의 지역 변수는 프로시저가 중지 되는 즉시 존재 하지 않게 됩니다. 정적 변수는 계속 존재 하며 최신 값을 유지 합니다. 다음에 코드가 프로시저를 호출 하면 변수가 다시 초기화 되지 않고 사용자가 할당 한 최신 값을 유지 합니다. 정적 변수는 정의 된 클래스 또는 모듈의 수명 동안 계속 존재 합니다.  
  
## <a name="rules"></a>규칙  
  
- **선언 컨텍스트.** `Static`로컬 변수에만 사용할 수 있습니다. 즉, 변수에 대 한 선언 컨텍스트는 프로시저 `Static` 또는 프로시저의 블록 이어야 하며 소스 파일, 네임 스페이스, 클래스, 구조체 또는 모듈 일 수 없습니다.  
  
     `Static`구조 프로시저 내에서는를 사용할 수 없습니다.  
  
- 지역 변수의 데이터 형식은 `Static` 유추할 수 없습니다. 자세한 내용은 [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.  
  
- **결합된 한정자.** `Static` `ReadOnly` `Shadows` 동일한 선언에서, 또는를 함께 지정할 수 없습니다 `Shared` .  
  
## <a name="behavior"></a>동작  
 프로시저에서 정적 변수를 선언 하는 경우 `Shared` 전체 응용 프로그램에 대해 정적 변수의 복사본을 하나만 사용할 수 있습니다. 클래스 `Shared` 의 인스턴스를 가리키는 변수가 아니라 클래스 이름을 사용 하 여 프로시저를 호출 합니다.  
  
 프로시저가 아닌 프로시저에서 정적 변수를 선언 하는 경우 `Shared` 클래스의 각 인스턴스에 대해 변수의 복사본을 하나만 사용할 수 있습니다. 클래스의 특정 인스턴스를 가리키는 변수를 사용 하 여 비공유 프로시저를 호출 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Static`의 사용법을 보여줍니다.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 `Static`변수는 `totalSales` 한 번만 0으로 초기화 됩니다. 를 입력할 때마다 `updateSales` 에서 `totalSales` 가장 최근의 값을 계산 합니다.  
  
 `Static`이 컨텍스트에서는 한정자를 사용할 수 있습니다.  
  
 [Dim 문](../statements/dim-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [Overloads](shadows.md)
- [공유](shared.md)
- [Visual Basic의 수명](../../programming-guide/language-features/declared-elements/lifetime.md)
- [변수 선언](../../programming-guide/language-features/variables/variable-declaration.md)
- [구조체](../../programming-guide/language-features/data-types/structures.md)
- [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)
- [개체 및 클래스](../../programming-guide/language-features/objects-and-classes/index.md)
