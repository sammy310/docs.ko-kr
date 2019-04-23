---
title: 인터페이스 (Visual Basic) 만들기 및 구현
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322032"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>연습: 인터페이스 (Visual Basic) 만들기 및 구현

인터페이스는 속성, 메서드 및 이벤트의 특징을 설명 하지만 구조체 또는 클래스까지 구현 세부 정보입니다.  
  
 이 연습에는 선언 및 인터페이스를 구현 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>인터페이스를 정의 하려면
  
1. 새 Visual Basic Windows 애플리케이션 프로젝트를 엽니다.  
  
2. 새 모듈을 클릭 하 여 프로젝트에 추가할 **모듈 추가** 에 **프로젝트** 메뉴.  
  
3. 새 모듈의 이름을 `Module1.vb` 누릅니다 **추가**합니다. 새 모듈의 코드가 표시 됩니다.  
  
4. 라는 인터페이스를 정의 `TestInterface` 내에서 `Module1` 입력 하 여 `Interface TestInterface` 간에 `Module` 및 `End Module` 문 및 ENTER 키를 누릅니다. 합니다 **코드 편집기** 들여쓰기를 `Interface` 키워드 추가 `End Interface` 코드 블록을 형성 하는 문입니다.  
  
5. 속성, 메서드 및 인터페이스에 대 한 이벤트 사이 다음 코드를 배치 하 여 정의 된 `Interface` 및 `End Interface` 문:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>구현

 인터페이스 멤버를 선언 하는 데 구문이 클래스 멤버를 선언 하는 데 사용 되는 구문에서 다른 지를 확인할 수 있습니다. 이러한 차이 인터페이스 구현 코드를 포함할 수 없습니다 사실을 반영 합니다.  
  
### <a name="to-implement-the-interface"></a>인터페이스를 구현 하려면
  
1. 라는 클래스를 추가 `ImplementationClass` 다음 문을 추가 하 여 `Module1`뒤를 `End Interface` 문의 하기 전에 `End Module` 문 및 enter 키를 눌러:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 일치 하는 제공 `End Class` ENTER 키를 누르면 문입니다.  
  
2. 다음을 추가 합니다 `Implements` 문을 `ImplementationClass`를 구현 하는 인터페이스 클래스의 이름을 합니다.  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     클래스 또는 구조체의 맨 위에 있는 다른 항목과 별도로 나열 하는 경우는 `Implements` 문을 클래스 또는 구조체는 인터페이스를 구현 함을 나타냅니다.  
  
     통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 구현에 필요한 클래스 멤버 `TestInterface` 경우 ENTER 키를 누릅니다 하 고 다음 단계를 건너뛸 수 있습니다.  
  
3. 인터페이스의 모든 멤버를 구현 해야 통합된 개발 환경 내에서 작동 하지 않는 경우 `MyInterface`합니다. 다음 코드를 추가 `ImplementationClass` 구현 `Event1`를 `Method1`, 및 `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     `Implements` 문을 인터페이스 및 인터페이스 구현 되는 멤버 이름을 지정 합니다.  
  
4. 정의 완료 `Prop1` 속성 값을 저장 하는 클래스에는 개인 필드를 추가 하 여:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     값을 반환 합니다 `pval` 속성에서 접근자를 가져옵니다.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     값을 설정할 `pval` 속성에 set 접근자입니다.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. 정의 완료 `Method1` 다음 코드를 추가 하 여 합니다.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>인터페이스의 구현을 테스트 하려면
  
1. 프로젝트의 시작 폼을 마우스 오른쪽 단추로 클릭 합니다 **솔루션 탐색기**, 클릭 **코드 보기**합니다. 편집기 시작 폼에 대 한 클래스를 표시합니다. 기본적으로 시작 폼 이라고 `Form1`합니다.  
  
2. 다음을 추가 합니다 `testInstance` 필드는 `Form1` 클래스:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     선언 하 여 `testInstance` 으로 `WithEvents`, `Form1` 클래스는 해당 이벤트를 처리할 수 있습니다.  
  
3. 다음 이벤트 처리기를 추가 합니다 `Form1` 클래스에 의해 발생 하는 이벤트를 처리할 `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. 라는 이름의 서브루틴을 추가 `Test` 에 `Form1` 클래스 구현 클래스를 테스트 하려면:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     `Test` 프로시저를 구현 하는 클래스의 인스턴스를 만듭니다 `MyInterface`, 해당 인스턴스를 할당 합니다 `testInstance` 필드 속성을 설정 하 고 인터페이스를 통해 메서드를 실행 합니다.  
  
5. 호출 하는 코드를 추가 합니다 `Test` 프로시저를 `Form1 Load` 시작 폼의 프로시저:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. 실행 된 `Test` f5 키를 눌러 프로시저입니다. 메시지 "Prop1 설정한 9" 표시 됩니다. 클릭 한 후, 메시지 "Method1에 대 한 X 매개 변수는 5입니다"가 표시 됩니다. 확인을 클릭 하 고 "이벤트 처리기는 이벤트를 포착 하는 데 사용" 메시지가 표시 됩니다.  
  
## <a name="see-also"></a>참고자료

- [Implements 문](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [인터페이스](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface 문](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)
