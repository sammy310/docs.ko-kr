---
title: 선언 및 발생 이벤트 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: fe96e54e92c09cf65c312306214e4460550c685d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626455"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>연습: 선언 및 발생 이벤트 (Visual Basic)
이 연습에는 선언 하 고 라는 클래스에 이벤트를 발생 하는 방법을 보여 줍니다. `Widget`합니다. 항목을 참고할 하려는 단계를 완료 하면 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)에서 이벤트를 사용 하는 방법을 보여 주는 `Widget` 응용 프로그램에서 상태 정보를 제공 하는 개체입니다.  
  
## <a name="the-widget-class"></a>위젯 클래스  
 해야 하는 순간에 대 한 가정 된 `Widget` 클래스입니다. 프로그램 `Widget` 일종의 완료 표시기 나타내려고 할 수 있는 응용 프로그램 및 클래스에 메서드를 실행 하는 데 시간이 오래 걸릴 수 있습니다.  
  
 물론, 만들 수 있습니다는 `Widget` 개체 완료율 대화 상자를 표시 한 다음 할 수 있지만 수 이후에를 사용 하는 모든 프로젝트에서이 대화 상자는 `Widget` 클래스입니다. 사용자 인터페이스 개체 핸들을 사용 하는 응용 프로그램에 개체를 디자인 하는 좋은 원칙-경우에 개체의 전체 목적은 양식 또는 대화 상자를 관리 합니다.  
  
 목적은 `Widget` 추가 하는 것 이므로 다른 작업을 수행 하는 것을 `PercentDone` 이벤트 및 호출 하는 프로시저를 통해 `Widget`의 메서드는 처리할 이벤트 및 표시 상태를 업데이트 합니다. `PercentDone` 이벤트에서 작업을 취소 메커니즘을 제공할 수도 있습니다.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>이 항목에 대 한 코드 예제를 빌드하려면  
  
1. 새 Visual Basic Windows 응용 프로그램 프로젝트를 열고 이라는 양식을 만듭니다 `Form1`합니다.  
  
2. 두 개의 단추 및 레이블을 추가 `Form1`합니다.  
  
3. 다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.  
  
    |개체|속성|설정|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|시작 태스크|  
    |`Button2`|`Text`|취소|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. 에 **프로젝트** 메뉴 선택 **클래스 추가** 라는 클래스를 추가 하려면 `Widget.vb` 프로젝트.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>위젯 클래스에 대 한 이벤트를 선언 하려면  
  
- 사용 된 `Event` 에서 이벤트를 선언 하는 키워드는 `Widget` 클래스. 이벤트 않았을 수 있습니다 `ByVal` 하 고 `ByRef` 인수를으로 `Widget`의 `PercentDone` 이벤트를 보여 줍니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 호출 하는 개체를 받으면를 `PercentDone` 이벤트는 `Percent` 인수 완료 된 작업의 백분율을 포함 합니다. `Cancel` 인수 설정할 수 있습니다 `True` 이벤트를 발생 시킨 메서드를 취소 합니다.  
  
> [!NOTE]
>  다음 예외를 사용 하 여 프로시저의 인수를 수행 하는 것 처럼 이벤트 인수를 선언할 수 있습니다. 이벤트를 사용할 수 없습니다 `Optional` 또는 `ParamArray` 인수와 이벤트 반환 값이 없는 수행 합니다.  
  
 `PercentDone` 이벤트를 발생 합니다 `LongTask` 메서드를 `Widget` 클래스. `LongTask` 두 개의 인수: 기간 메서드 프로세스로 작업과 하기 전의 최소 시간 간격을 수행할 수 `LongTask` 일시 중지 시키려면는 `PercentDone` 이벤트입니다.  
  
#### <a name="to-raise-the-percentdone-event"></a>PercentDone 이벤트 발생  
  
1. 에 대 한 액세스를 간소화 하는 `Timer` 이 클래스에 의해 사용 되는 속성 추가 `Imports` 클래스 모듈의 선언 섹션의 맨 위에 문을 위에 `Class Widget` 문.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. `Widget` 클래스에 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 응용 프로그램 호출 하는 경우는 `LongTask` 메서드를 `Widget` 클래스에서 발생 시키는 `PercentDone` 이벤트 모든 `MinimumInterval` 시간 (초). 이 이벤트는 반환 될 때 `LongTask` 확인 하는 `Cancel` 인수 설정한 `True`합니다.  
  
 몇 가지 한계는 여기에 필요 합니다. 간단히 하기 위해는 `LongTask` 절차를 이미 아는 작업은 얼마나 걸리나요 가정 합니다. 이 경우 거의 없습니다. 작업 짝수 크기의 청크로 분할 것이 어려울 수 있으며 종종 가장 중요 한 사용자에 게는 단순히 표시 하는 상황이 이르기 전에 경과 되는 시간.  
  
 이 샘플에서 다른 문제가 발생할 수 있습니다. `Timer` 자정 직전 시작 된 경우 응용 프로그램 중지 되므로; 속성 자정 이후 경과한 시간 (초) 수를 반환 합니다. 시간 측정에 보다 신중한 접근을 고려해 야 할 다음과 같은 경계 조건 하거나 피하도록와 같은 속성을 사용 하는 `Now`합니다.  
  
 이제는 `Widget` 클래스 이벤트 발생 수를 이동할 수 있습니다 다음 연습 합니다. [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 사용 하는 방법을 보여 줍니다 `WithEvents` 사용 하 여 이벤트 처리기를 연결 하는 `PercentDone` 이벤트입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)
