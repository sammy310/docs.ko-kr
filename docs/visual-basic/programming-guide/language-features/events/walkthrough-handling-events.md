---
title: 이벤트 처리
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345079"
---
# <a name="walkthrough-handling-events-visual-basic"></a>연습: 이벤트 처리(Visual Basic)
이벤트를 사용 하는 방법을 보여 주는 두 항목 중 두 번째 항목입니다. 첫 번째 항목인 [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)에서는 이벤트를 선언 하 고 발생 시키는 방법을 보여 줍니다. 이 단원에서는 해당 연습의 폼과 클래스를 사용 하 여 이벤트를 처리 하는 방법을 보여 줍니다.  
  
 `Widget` 클래스 예제에서는 기존의 이벤트 처리 문을 사용 합니다. Visual Basic는 이벤트를 사용 하는 다른 기술을 제공 합니다. 연습으로이 예제를 수정 하 여 `AddHandler` 및 `Handles` 문을 사용할 수 있습니다.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Widget 클래스의 PercentDone 이벤트를 처리 하려면  
  
1. `Form1`에 다음 코드를 입력 합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     `WithEvents` 키워드는 `mWidget` 변수를 사용 하 여 개체의 이벤트를 처리 하도록 지정 합니다. 개체를 만들 클래스의 이름을 제공 하 여 개체의 종류를 지정 합니다.  
  
     `WithEvents` 변수는 클래스 수준 이어야 하므로 변수 `mWidget` `Form1`에서 선언 됩니다. 이는 위치를 지정 하는 클래스의 형식에 관계 없이 적용 됩니다.  
  
     변수 `mblnCancel`은 `LongTask` 메서드를 취소 하는 데 사용 됩니다.  
  
## <a name="writing-code-to-handle-an-event"></a>이벤트를 처리 하는 코드 작성  
 `WithEvents`를 사용 하 여 변수를 선언 하는 즉시 클래스 **코드 편집기**의 왼쪽 드롭다운 목록에 변수 이름이 표시 됩니다. `mWidget`를 선택 하면 `Widget` 클래스의 이벤트가 오른쪽 드롭다운 목록에 나타납니다. 이벤트를 선택 하면 접두사 `mWidget` 및 밑줄을 사용 하 여 해당 이벤트 프로시저가 표시 됩니다. `WithEvents` 변수와 연결 된 모든 이벤트 프로시저에는 접두사로 변수 이름이 지정 됩니다.  
  
#### <a name="to-handle-an-event"></a>이벤트를 처리 하려면  
  
1. **코드 편집기**의 왼쪽 드롭다운 목록에서 `mWidget`을 선택 합니다.  
  
2. 오른쪽 드롭다운 목록에서 `PercentDone` 이벤트를 선택 합니다. **코드 편집기** 가 `mWidget_PercentDone` 이벤트 프로시저를 엽니다.  
  
    > [!NOTE]
    > **코드 편집기** 는 새 이벤트 처리기를 삽입 하는 데 유용 하지만 필수는 아닙니다. 이 연습에서는 이벤트 처리기를 코드에 직접 복사 하는 것이 더 직접적입니다.  
  
3. 다음 코드를 `mWidget_PercentDone` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     `PercentDone` 이벤트가 발생할 때마다 이벤트 프로시저는 `Label` 컨트롤에 완료율을 표시 합니다. `DoEvents` 메서드를 사용 하면 레이블을 다시 그릴 수 있으며 사용자에 게 **취소** 단추를 클릭할 수 있는 기회가 제공 됩니다.  
  
4. `Button2_Click` 이벤트 처리기에 대 한 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 `LongTask`를 실행 하는 동안 사용자가 **취소** 단추를 클릭 하면 `DoEvents` 문이 이벤트 처리를 수행할 수 있도록 `Button2_Click` 이벤트가 즉시 실행 됩니다. 클래스 수준 변수 `mblnCancel`은 `True`로 설정 되 고, `mWidget_PercentDone` 이벤트는이를 테스트 하 여 `ByRef Cancel` 인수를 `True`로 설정 합니다.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>WithEvents 변수를 개체에 연결  
 이제 `Form1` `Widget` 개체의 이벤트를 처리 하도록 설정 됩니다. 모든 위치에서 `Widget`를 찾을 수 있습니다.  
  
 디자인 타임에 `WithEvents` 변수를 선언 하면 개체가 연결 되지 않습니다. `WithEvents` 변수는 다른 개체 변수와 동일 합니다. 개체를 만들고 `WithEvents` 변수를 사용 하 여 개체에 대 한 참조를 할당 해야 합니다.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>개체를 만들고이 개체에 대 한 참조를 할당 하려면  
  
1. **코드 편집기**의 왼쪽 드롭다운 목록에서 **(Form1 이벤트)** 를 선택 합니다.  
  
2. 오른쪽 드롭다운 목록에서 `Load` 이벤트를 선택 합니다. **코드 편집기** 가 `Form1_Load` 이벤트 프로시저를 엽니다.  
  
3. `Form1_Load` 이벤트 프로시저에 대 한 다음 코드를 추가 하 여 `Widget`를 만듭니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 이 코드가 실행 되 면 Visual Basic `Widget` 개체를 만들고 해당 이벤트를 `mWidget`와 연결 된 이벤트 프로시저에 연결 합니다. 이 시점부터 `Widget` `PercentDone` 이벤트를 발생 시킬 때마다 `mWidget_PercentDone` 이벤트 프로시저가 실행 됩니다.  
  
#### <a name="to-call-the-longtask-method"></a>LongTask 메서드를 호출 하려면  
  
- 다음 코드를 `Button1_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 `LongTask` 메서드를 호출 하기 전에 완료율을 표시 하는 레이블이 초기화 되어야 하 고 메서드를 취소 하기 위한 클래스 수준 `Boolean` 플래그가 `False`로 설정 되어야 합니다.  
  
 `LongTask`는 작업 기간 12.2 초를 사용 하 여 호출 됩니다. `PercentDone` 이벤트는 1 초 마다 한 번씩 발생 합니다. 이벤트가 발생할 때마다 `mWidget_PercentDone` 이벤트 프로시저가 실행 됩니다.  
  
 `LongTask` 완료 되 면 `mblnCancel`를 테스트 하 여 `LongTask` 정상적으로 종료 되었는지 또는 `mblnCancel`가 `True`로 설정 되어 있기 때문에 중지 되었는지 확인 합니다. 완료율은 이전 경우에만 업데이트 됩니다.  
  
#### <a name="to-run-the-program"></a>프로그램을 실행하려면  
  
1. F5 키를 눌러 프로젝트를 실행 모드로 전환 합니다.  
  
2. **작업 시작** 단추를 클릭 합니다. `PercentDone` 이벤트가 발생할 때마다 레이블이 완료 된 작업의 백분율로 업데이트 됩니다.  
  
3. 작업을 중지 하려면 **취소** 단추를 클릭 합니다. 클릭 하면 **취소** 단추의 모양이 즉시 변경 되지 않습니다. `My.Application.DoEvents` 문이 이벤트를 처리할 수 있을 때까지 `Click` 이벤트는 발생 하지 않습니다.  
  
    > [!NOTE]
    > `My.Application.DoEvents` 메서드는 양식이 수행 하는 것과 정확히 같은 방식으로 이벤트를 처리 하지 않습니다. 예를 들어이 연습에서는 **취소** 단추를 두 번 클릭 해야 합니다. 폼에서 이벤트를 직접 처리할 수 있도록 하려면 다중 스레딩을 사용할 수 있습니다. 자세한 내용은 [관리 되는 스레딩](../../../../standard/threading/index.md)을 참조 하세요.
  
 F11 키를 사용 하 여 프로그램을 실행 하 고 한 번에 한 줄씩 코드를 단계별로 실행 하는 것을 확인할 수 있습니다. 실행이 `LongTask`입력 되는 방식을 명확 하 게 확인 한 다음 `PercentDone` 이벤트가 발생할 때마다 `Form1`를 잠깐 다시 입력 합니다.  
  
 `Form1`코드에서 실행이 다시 실행 되는 동안 `LongTask` 메서드가 다시 호출 되는 경우 어떻게 되나요? 이벤트가 발생할 때마다 `LongTask`가 호출 되 면 스택 오버플로가 발생할 수 있습니다.  
  
 `mWidget`에 새 `Widget`에 대 한 참조를 할당 하 여 변수 `mWidget`에서 다른 `Widget` 개체에 대 한 이벤트를 처리할 수 있습니다. 실제로 단추를 클릭할 때마다 `Button1_Click`에서 코드를 수행할 수 있습니다.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>다른 위젯의 이벤트를 처리 하려면  
  
- `mWidget.LongTask(12.2, 0.33)`를 읽는 줄 바로 앞에 있는 `Button1_Click` 프로시저에 다음 코드 줄을 추가 합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 위의 코드는 단추를 클릭할 때마다 새 `Widget`를 만듭니다. `LongTask` 메서드가 완료 되 면 `Widget`에 대 한 참조가 해제 되 고 `Widget` 제거 됩니다.  
  
 `WithEvents` 변수에는 한 번에 하나의 개체 참조만 포함 될 수 있으므로 `mWidget`에 다른 `Widget` 개체를 할당 하면 이전 `Widget` 개체의 이벤트가 더 이상 처리 되지 않습니다. `mWidget`가 이전 `Widget`에 대 한 참조를 포함 하는 유일한 개체 변수인 경우 개체가 제거 됩니다. 여러 `Widget` 개체의 이벤트를 처리 하려면 `AddHandler` 문을 사용 하 여 각 개체의 이벤트를 개별적으로 처리 합니다.  
  
> [!NOTE]
> 필요한 만큼 `WithEvents` 변수를 선언할 수 있지만 `WithEvents` 변수 배열은 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
