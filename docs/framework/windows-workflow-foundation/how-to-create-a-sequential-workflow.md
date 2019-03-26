---
title: '방법: 순차 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 3991c16e00f1cbb4f8c1f2c8391f89ea51c1e6f2
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463802"
---
# <a name="how-to-create-a-sequential-workflow"></a>방법: 순차 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다. 이 항목에서는 같은 모두 기본 제공 활동을 사용 하는 워크플로 만드는 방법을 단계별로 합니다 <xref:System.Activities.Statements.Sequence> 활동 및 사용자 지정 활동을 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목입니다. 이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다. 이 항목을 완료 하려면 먼저 마쳐야 [방법: 활동 만들기](how-to-create-an-activity.md)합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.  
  
## <a name="to-create-the-workflow"></a>워크플로를 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 항목**합니다.  
  
2.  에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다. 선택 **활동** 에서 합니다 **워크플로** 목록입니다.  
  
3.  형식 `SequentialNumberGuessWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.  
  
4.  끌어서를 **시퀀스** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 에 레이블는 워크플로 디자인 화면입니다.  
  
## <a name="to-create-the-workflow-variables-and-arguments"></a>워크플로 변수와 인수를 만들려면  
  
1.  두 번 클릭 **SequentialNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 이미 표시 되지 않으면 워크플로 디자이너에서 표시 합니다.  
  
2.  클릭 **인수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창입니다.  
  
3.  클릭 **인수를 만드는**합니다.  
  
4.  형식 `MaxNumber` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **Int32** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.  
  
5.  클릭 **인수를 만드는**합니다.  
  
6.  형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수 **Out** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.  
  
7.  클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.  
  
8.  클릭 **변수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창입니다.  
  
9. 클릭 **변수를 만듭니다**합니다.  
  
    > [!TIP]
    >  없으면 **변수 만들기** 상자가 표시 됩니다을 클릭 합니다 **시퀀스** 선택 하려면 워크플로 디자이너 화면에 활동입니다.  
  
10. 형식 `Guess` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.  
  
11. 클릭 **변수를 만듭니다**합니다.  
  
12. 형식 `Target` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.  
  
13. 클릭 **변수** 닫으려면 activity designer의 왼쪽 아래에에서는 **변수** 창입니다.  
  
## <a name="to-add-the-workflow-activities"></a>워크플로 활동을 추가하려면  
  
1.  끌어서를 **할당** 활동에서는 **기본** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동. 형식 `Target` 에 **에** 상자 및에 다음 식을 합니다 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.  
  
2.  끌어서를 **DoWhile** 활동에서를 **제어 흐름** 섹션의 **도구 상자** 아래에 워크플로에 놓습니다를 **할당** 작업입니다.  
  
3.  에 다음 식을 입력 합니다 **DoWhile** 활동의 **조건** 속성 값 상자입니다.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <xref:System.Activities.Statements.DoWhile> 활동은 자식 활동을 실행한 다음 해당 <xref:System.Activities.Statements.DoWhile.Condition%2A>을 확인합니다. <xref:System.Activities.Statements.DoWhile.Condition%2A>이 `True`로 확인되면 <xref:System.Activities.Statements.DoWhile>의 활동이 다시 실행됩니다. 이 예제에서는 사용자의 추측 값을 확인하여 추측이 올바를 때까지 <xref:System.Activities.Statements.DoWhile>이 계속됩니다.  
  
4.  끌어서를 **프롬프트** 활동에서는 **NumberGuessWorkflowActivities** 부분을 **도구 상자** 놓습니다를 **DoWhile** 활동 이전 단계의 합니다.  
  
5.  에 **속성 창**, 형식 `"EnterGuess"` 따옴표를 포함 하 여를 **BookmarkName** 속성 값 상자에는 **프롬프트** 활동입니다. 형식 `Guess` 에 **결과** 속성 값 상자 및에 다음 식을 입력 합니다 **텍스트** 속성 상자입니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.  
  
6.  끌어서는 **할당** 활동에서를 **기본** 부분을 **도구 상자** 놓습니다를 **DoWhile** 활동 뒤에 놓습니다를 **프롬프트** 활동입니다.  
  
    > [!NOTE]
    >  놓으면를 **할당** 작업, 워크플로 디자이너를 자동으로 추가 하는 방법을 참고를 **시퀀스** 둘 다 포함 하는 작업을 **프롬프트** 활동과 새로 추가 된 **할당** 활동입니다.  
  
7.  형식 `Turns` 에 **하** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
8.  끌어서는 **경우** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **시퀀스** 활동 뒤에 놓습니다는 새로 추가 된 **할당** 활동입니다.  
  
9. 에 다음 식을 입력 합니다 **하는 경우** 활동의 **조건** 속성 값 상자입니다.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. 다른 **경우** 활동에서는 **제어 흐름** 부분을 **도구 상자** 놓습니다를 **다음** 첫번째섹션**경우** 활동입니다.  
  
11. 에 새로 추가 된 다음 식을 입력 **하는 경우** 활동의 **조건** 속성 값 상자입니다.  
  
    ```
    Guess < Target  
    ```  
  
12. 두 개 **WriteLine** 활동에서는 **기본** 부분을 **도구 상자** 되도록 하나에 놓을 **다음** 섹션 새로 추가한 **하는 경우** 활동을 하나는 **Else** 섹션.  
  
13. 클릭는 **WriteLine** 활동에는 **다음** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.  
  
    ```text
    "Your guess is too low."  
    ```  
  
14. 클릭는 **WriteLine** 활동에는 **Else** 섹션을 선택 하 고에 다음 식을 입력 합니다 **텍스트** 속성 값 상자.  
  
    ```text
    "Your guess is too high."  
    ```  
  
     다음 예제에서는 완료 된 워크플로 보여 줍니다.  
  
     ![완료 된 순차 워크플로 보여 주는 스크린샷.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)  
  
## <a name="to-build-the-workflow"></a>워크플로를 빌드하려면  
  
1.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [방법: 워크플로 실행](how-to-run-a-workflow.md)합니다. 이미 완료 하는 경우는 [방법: 워크플로 실행](how-to-run-a-workflow.md) 이 단계에서 순차 워크플로 사용 하 여 실행 하려는 워크플로의 다른 스타일을 사용 하 여 단계를 건너 뛰 세요 합니다 [빌드 및 응용 프로그램을 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 부분 [하는 방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Windows Workflow Foundation 프로그래밍](programming.md)
- [워크플로 디자인](designing-workflows.md)
- [초보자를 위한 자습서](getting-started-tutorial.md)
- [방법: 활동 만들기](how-to-create-an-activity.md)
- [방법: 워크플로 실행](how-to-run-a-workflow.md)
