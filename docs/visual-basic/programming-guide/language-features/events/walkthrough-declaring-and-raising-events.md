---
title: 이벤트 선언 및 발생
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345094"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>연습: 이벤트 선언 및 발생(Visual Basic)
이 연습에서는 `Widget`라는 클래스에 대 한 이벤트를 선언 하 고 발생 시키는 방법을 보여 줍니다. 단계를 완료 한 후에는 `Widget` 개체의 이벤트를 사용 하 여 응용 프로그램에서 상태 정보를 제공 하는 방법을 보여 주는 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)항목을 읽어 볼 수 있습니다.  
  
## <a name="the-widget-class"></a>Widget 클래스  
 `Widget` 클래스가 있는 순간을 가정 합니다. `Widget` 클래스에는 실행 하는 데 시간이 오래 걸릴 수 있는 메서드가 있으며 응용 프로그램에서 일종의 완성 표시기를 배치할 수 있도록 하려고 합니다.  
  
 물론 `Widget` 개체에 완료율 대화 상자를 표시할 수 있지만 `Widget` 클래스를 사용 하는 모든 프로젝트에서 해당 대화 상자를 사용할 수 있습니다. 개체를 사용 하는 응용 프로그램은 폼 이나 대화 상자를 관리 하는 것이 아니라 개체를 사용 하는 응용 프로그램에서 사용자 인터페이스를 처리 하도록 하는 것이 좋습니다.  
  
 `Widget`의 목적은 다른 작업을 수행 하는 것 이므로 `PercentDone` 이벤트를 추가 하 고 `Widget`의 메서드를 호출 하는 프로시저가 해당 이벤트를 처리 하 고 상태 업데이트를 표시 하는 것이 좋습니다. 또한 `PercentDone` 이벤트는 작업을 취소 하는 메커니즘을 제공할 수 있습니다.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>이 항목에 대 한 코드 예제를 빌드하려면  
  
1. 새 Visual Basic Windows 응용 프로그램 프로젝트를 열고 `Form1`라는 양식을 만듭니다.  
  
2. `Form1`에 두 개의 단추와 레이블을 추가 합니다.  
  
3. 다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.  
  
    |개체|속성|설정|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|시작 태스크|  
    |`Button2`|`Text`|취소|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. **프로젝트** 메뉴에서 **클래스 추가** 를 선택 하 여 `Widget.vb` 라는 클래스를 프로젝트에 추가 합니다.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Widget 클래스의 이벤트를 선언 하려면  
  
- `Event` 키워드를 사용 하 여 `Widget` 클래스에서 이벤트를 선언 합니다. 이벤트는 `Widget`의 `PercentDone` 이벤트에서 보여 주는 것 처럼 `ByVal` 및 `ByRef` 인수를 가질 수 있습니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 호출 하는 개체가 `PercentDone` 이벤트를 수신 하는 경우 `Percent` 인수에는 완료 된 작업의 백분율이 포함 됩니다. 이벤트를 발생 시킨 메서드를 취소 하려면 `True`로 `Cancel` 인수를 설정할 수 있습니다.  
  
> [!NOTE]
> 프로시저의 인수를 사용 하는 것과 같은 방법으로 이벤트 인수를 선언할 수 있습니다. 단, 이벤트는 `Optional` 또는 `ParamArray` 인수를 가질 수 없고 이벤트에 반환 값이 없습니다.  
  
 `PercentDone` 이벤트는 `Widget` 클래스의 `LongTask` 메서드에 의해 발생 합니다. `LongTask`는 두 개의 인수를 사용 합니다. 메서드가 작업을 수행 하는 시간을 lie 하 고 `LongTask` 하기 전의 최소 시간 간격을 사용 하 여 `PercentDone` 이벤트를 발생 시킵니다.  
  
#### <a name="to-raise-the-percentdone-event"></a>PercentDone 이벤트를 발생 시키려면  
  
1. 이 클래스에서 사용 하는 `Timer` 속성에 대 한 액세스를 간소화 하려면 `Class Widget` 문 위의 클래스 모듈의 선언 섹션 맨 위에 `Imports` 문을 추가 합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. `Widget` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 응용 프로그램이 `LongTask` 메서드를 호출 하면 `Widget` 클래스는 `MinimumInterval` 초 마다 `PercentDone` 이벤트를 발생 시킵니다. 이벤트가 반환 될 때 `LongTask`는 `Cancel` 인수가 `True`로 설정 되었는지 확인 합니다.  
  
 여기에 몇 가지 법적 사항이 필요 합니다. 간단 하 게 하기 위해 `LongTask` 절차에서는 작업에 걸리는 시간을 미리 알고 있다고 가정 합니다. 거의 그렇지 않습니다. 작업을 짝수의 청크로 분할 하는 것은 어려울 수 있으며, 대부분의 경우 사용자에 게 가장 중요 한 것은 문제가 발생 했음을 표시 하기 전에 경과 하는 시간입니다.  
  
 이 샘플에서 다른 결함을 발견 했을 수 있습니다. `Timer` 속성은 자정 이후 경과 된 시간 (초)을 반환 합니다. 따라서 응용 프로그램은 자정 직전에 시작 되는 경우 중지 됩니다. 보다 신중 하 게 시간을 측정 하는 방법은이를 고려 하거나 `Now`같은 속성을 사용 하 여 모두 사용 하지 않도록 하는 것과 같은 경계 조건을 사용 하는 것입니다.  
  
 이제 `Widget` 클래스가 이벤트를 발생 시킬 수 있으므로 다음 연습으로 이동할 수 있습니다. [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 에서는 `WithEvents` 사용 하 여 이벤트 처리기를 `PercentDone` 이벤트와 연결 하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
