---
title: '방법: 상태 시스템 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 654621ab7dd74c26a7fddbd985559a713c0e9df3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294810"
---
# <a name="how-to-create-a-state-machine-workflow"></a>방법: 상태 시스템 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다. 이 항목에서는 같은 모두 기본 제공 활동을 사용 하는 워크플로 만드는 방법을 단계별로 합니다 <xref:System.Activities.Statements.StateMachine> 활동 및 사용자 지정 활동을 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목입니다. 이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다. 이 항목을 완료 하려면 먼저 마쳐야 [방법: 활동 만들기](how-to-create-an-activity.md)합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.  
  
### <a name="to-create-the-workflow"></a>워크플로를 만들려면  
  
1. 마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 항목**합니다.  
  
2. 에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다. 선택 **활동** 에서 합니다 **워크플로** 목록입니다.  
  
3. 형식 `StateMachineNumberGuessWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.  
  
4. 끌어서를 **StateMachine** 활동에서는 **상태 시스템** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 에 레이블 워크플로 디자인 화면입니다.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>워크플로 변수와 인수를 만들려면  
  
1. 두 번 클릭 **StateMachineNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 이미 표시 되지 않으면 워크플로 디자이너에서 표시 합니다.  
  
2. 클릭 **인수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창입니다.  
  
3. 클릭 **인수를 만드는**합니다.  
  
4. 형식 `MaxNumber` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **Int32** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.  
  
5. 클릭 **인수를 만드는**합니다.  
  
6. 형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수 **Out** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.  
  
7. 클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.  
  
8. 클릭 **변수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창입니다.  
  
9. 클릭 **변수를 만듭니다**합니다.  
  
    > [!TIP]
    >  없으면 **변수 만들기** 상자가 표시 됩니다을 클릭 합니다 <xref:System.Activities.Statements.StateMachine> 선택 하려면 워크플로 디자이너 화면에 활동입니다.  
  
10. 형식 `Guess` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.  
  
11. 클릭 **변수를 만듭니다**합니다.  
  
12. 형식 `Target` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.  
  
13. 클릭 **변수** 닫으려면 activity designer의 왼쪽 아래에에서는 **변수** 창입니다.  
  
### <a name="to-add-the-workflow-activities"></a>워크플로 활동을 추가하려면  
  
1. 클릭 **State1** 하 여 선택 합니다. 에 **속성 창**를 변경 합니다 **DisplayName** 를 `Initialize Target`.  
  
    > [!TIP]
    >  경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.  
  
2. 이름을 새로 바꾼 두 번 클릭 **Initialize Target** 확장 하는 데 워크플로 디자이너의 상태입니다.  
  
3. 끌어서는 **할당** 활동에서를 **기본형** 섹션을 **도구 상자** 놓습니다를 **항목** 상태 섹션. 형식 `Target` 에 **에** 상자 및에 다음 식을 합니다 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.  
  
4. 전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.  
  
5. 끌어서를 **상태** 활동에서는 **상태 시스템** 부분을 **도구 상자** 워크플로 디자이너로 위로 가져갑니다는 **Initialize Target** 상태입니다. 주위에 삼각형 네 개가 표시 됩니다는 참고 합니다 **Initialize Target** 상태 위에 새 상태가 합니다. 바로 아래에 있는 삼각형에 새 상태를 삭제 합니다 **Initialize Target** 상태입니다. 이 새 상태가 워크플로에 배치 및의 전환이 만들어집니다 합니다 **Initialize Target** 새 상태로 상태입니다.  
  
6. 클릭 **State1** 선택, 변경 합니다 **DisplayName** 에 `Enter Guess`를 차례로 확장 하는 데 워크플로 디자이너의 상태를 두 번 클릭 합니다.  
  
7. 끌어서를 **WriteLine** 활동에서를 **기본형** 섹션을 **도구 상자** 놓습니다를 **항목** 상태 섹션.  
  
8. 에 다음 식을 입력 합니다 **텍스트** 의 속성 상자를 **WriteLine**합니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. 끌어서를 **할당** 활동에서는 **기본** 부분을 **도구 상자** 끌어다 놓으십시오를 **종료** 상태 섹션.  
  
10. 형식 `Turns` 에 **하** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
11. 전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.  
  
12. 끌어서를 **FinalState** 활동에서를 **상태 시스템** 섹션을 **도구 상자**, 위로 가져갑니다를 **Enter Guess** 상태를 놓습니다 오른쪽에 나타나는 삼각형에는 **Enter Guess** 상태 간의 전환을 만들어지도록 **Enter Guess** 하 고 **FinalState**합니다.  
  
13. 전환의 기본 이름은 **T2**합니다. 선택 하 고 설정 워크플로 디자이너에서 전환을 클릭 해당 **DisplayName** 하 **Guess Correct**합니다. 그런 다음을 선택 합니다 **FinalState**, 두 상태 중 어느 쪽도 겹치지 않고 표시할 전체 전환 이름 위한 공간을 확보 되도록 오른쪽에 놓습니다. 이렇게 하면 자습서의 나머지 단계를 보다 쉽게 진행할 수 있습니다.  
  
14. 이름을 새로 바꾼 두 번 클릭 **Guess Correct** 확장 하는 데 워크플로 디자이너에서 전환 합니다.  
  
15. 끌어서를 **ReadInt** 활동에서는 **NumberGuessWorkflowActivities** 부분을 **도구 상자** 놓습니다를 **트리거** 섹션 전환 합니다.  
  
16. 에 **속성 창** 에 대 한 합니다 **ReadInt** 활동을 입력 `"EnterGuess"` 따옴표를 포함 하 여를 **BookmarkName** 속성 값 상자 및 형식 `Guess`에 **결과** 속성 값 상자  
  
17. 에 다음 식을 입력 합니다 **Guess Correct** 전환 **조건** 속성 값 상자입니다.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. 전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.  
  
    > [!NOTE]
    >  트리거 이벤트를 받고 <xref:System.Activities.Statements.Transition.Condition%2A>이 `True`인 경우 전환이 발생합니다. 이 전환의 경우 사용자의 `Guess` 임의로 생성 된 일치 `Target`, 컨트롤을 전달 하는 다음을 **FinalState** 되 고 워크플로가 완료 합니다.  
  
19. 추측이 올바른지 여부에 따라 워크플로의 전환 해야 하는 **FinalState** 또는 다시 합니다 **Enter Guess** 다른 시도 대 한 상태입니다. 두 전환 모두 사용자의 추측을 통해 받을 때까지 기다리는 동일한 트리거를 공유 합니다 **ReadInt** 활동입니다. 이를 공유 전환이라고 합니다. 공유 전환을 만들려면의 시작을 나타내는 원을 클릭 합니다 **Guess Correct** 전환 하 고 원하는 상태로 끕니다. 이 경우에 전환은 자체 전환, 따라서의 시작점을 끌어 합니다 **Guess Correct** 전환 하 고 맨 아래에 다시 놓습니다 합니다 **Enter Guess** 상태입니다. 전환을 만든 후 워크플로 디자이너에서 선택 하 고 설정 해당 **DisplayName** 속성을 **Guess Incorrect**합니다.  
  
    > [!NOTE]
    >  공유 전환을 만들 수도 있습니다에서 전환 디자이너 내에서 클릭 하 여 **공유 트리거 전환 추가** 아래쪽의 전환 디자이너, 한 다음 원하는 대상 상태를 선택 하 여  **연결에 사용할 상태** 드롭 다운 합니다.  
  
    > [!NOTE]
    >  전환의 <xref:System.Activities.Statements.Transition.Condition%2A>이 `false`가 되거나 모든 공유 트리거 전환 조건이 `false`가 되는 경우에는 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예약됩니다. 이 자습서에서는 조건이 구성된 방식(추측이 올바른지 또는 잘못되었는지에 따라 특정 동작이 지정됨) 때문에 이러한 상황이 발생할 수 없습니다.  
  
20. 두 번 클릭 합니다 **Guess Incorrect** 확장 하는 데 워크플로 디자이너에서 전환 합니다. 합니다 **트리거** 동일 하 게 이미 설정 되어 **ReadInt** 활동에서 사용 하는 **Guess Correct** 전환 합니다.  
  
21. 에 다음 식을 입력 합니다 **조건을** 속성 값 상자입니다.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. 끌어서는 **경우** 활동에서를 **제어 흐름** 섹션을 **도구 상자** 놓습니다를 **작업** 전환의 섹션입니다.  
  
23. 에 다음 식을 입력 합니다 **하는 경우** 활동의 **조건** 속성 값 상자입니다.  
  
    ```
    Guess < Target  
    ```  
  
24. 두 개 **WriteLine** 활동에서는 **기본** 부분을 **도구 상자** 되도록 하나에 놓을 **다음** 섹션 합니다 **하는 경우** 활동을 하나는 **Else** 섹션입니다.  
  
25. 클릭는 **WriteLine** 활동에는 **다음** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.  
  
    ```
    "Your guess is too low."  
    ```  
  
26. 클릭는 **WriteLine** 활동에는 **Else** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.  
  
    ```
    "Your guess is too high."  
    ```  
  
27. 전체 반환 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 있는 이동 경로 표시 합니다.  
  
     다음 예제에서는 완료된 워크플로를 보여 줍니다.  
  
     ![완료 된 상태 시스템 워크플로](./media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>워크플로를 빌드하려면  
  
1. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [방법: 워크플로 실행](how-to-run-a-workflow.md)합니다. 이미 완료 하는 경우는 [방법: 워크플로 실행](how-to-run-a-workflow.md) 이 단계에서 상태 시스템 워크플로 사용 하 여 실행 하려는 워크플로의 다른 스타일을 사용 하 여 단계를 건너 뛰 세요 합니다 [빌드 및 응용 프로그램을 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 부분 [하는 방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Windows Workflow Foundation 프로그래밍](programming.md)
- [워크플로 디자인](designing-workflows.md)
- [초보자를 위한 자습서](getting-started-tutorial.md)
- [방법: 작업 만들기](how-to-create-an-activity.md)
- [방법: 워크플로 실행](how-to-run-a-workflow.md)
