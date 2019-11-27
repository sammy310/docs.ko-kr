---
title: 정적
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350756"
---
# <a name="static-visual-basic"></a>Static(Visual Basic)
선언 된 지역 변수를 하나 이상 유지 하 고 선언 된 프로시저가 종료 된 후에 최신 값을 유지 하도록 지정 합니다.  
  
## <a name="remarks"></a>주의  
 일반적으로 프로시저의 지역 변수는 프로시저가 중지 되는 즉시 존재 하지 않게 됩니다. 정적 변수는 계속 존재 하며 최신 값을 유지 합니다. 다음에 코드가 프로시저를 호출 하면 변수가 다시 초기화 되지 않고 사용자가 할당 한 최신 값을 유지 합니다. 정적 변수는 정의 된 클래스 또는 모듈의 수명 동안 계속 존재 합니다.  
  
## <a name="rules"></a>규칙  
  
- **선언 컨텍스트입니다.** `Static`는 지역 변수에만 사용할 수 있습니다. 즉, `Static` 변수에 대 한 선언 컨텍스트는 프로시저 또는 프로시저의 블록 이어야 하며 소스 파일, 네임 스페이스, 클래스, 구조체 또는 모듈 일 수 없습니다.  
  
     구조 프로시저 내에서는 `Static`를 사용할 수 없습니다.  
  
- `Static` 지역 변수의 데이터 형식은 유추할 수 없습니다. 자세한 내용은 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.  
  
- **결합 된 한정자입니다.** 동일한 선언에서 `ReadOnly`, `Shadows`또는 `Shared`와 함께 `Static`를 지정할 수 없습니다.  
  
## <a name="behavior"></a>동작  
 `Shared` 프로시저에서 정적 변수를 선언 하는 경우 전체 응용 프로그램에 대해 정적 변수의 복사본을 하나만 사용할 수 있습니다. 클래스의 인스턴스를 가리키는 변수가 아니라 클래스 이름을 사용 하 여 `Shared` 프로시저를 호출 합니다.  
  
 `Shared`하지 않는 프로시저에서 정적 변수를 선언 하는 경우 클래스의 각 인스턴스에 대해 변수의 복사본 하나만 사용할 수 있습니다. 클래스의 특정 인스턴스를 가리키는 변수를 사용 하 여 비공유 프로시저를 호출 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Static`의 사용법을 보여줍니다.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 `Static` 변수 `totalSales` 0으로 한 번만 초기화 됩니다. `updateSales`를 입력할 때마다 `totalSales`에 대해 계산 된 최신 값이 계속 됩니다.  
  
 이 컨텍스트에서는 `Static` 한정자를 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>참고 항목

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [공유](../../../visual-basic/language-reference/modifiers/shared.md)
- [Visual Basic 수명](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
