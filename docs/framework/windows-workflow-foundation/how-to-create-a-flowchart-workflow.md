---
title: '방법: 순서도 워크플로 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 10483c747e0f86816db6f03dd8df17472f31f15c
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063763"
---
# <a name="how-to-create-a-flowchart-workflow"></a>방법: 순서도 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다. 이 항목에서는 같은 모두 기본 제공 활동을 사용 하는 워크플로 만드는 방법을 단계별로 합니다 <xref:System.Activities.Statements.Flowchart> 활동 및 사용자 지정 활동을 이전 [방법: 활동 만들기](how-to-create-an-activity.md) 항목입니다. 이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다. 이 항목을 완료 하려면 먼저 마쳐야 [방법: 활동 만들기](how-to-create-an-activity.md)합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](https://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.  
  
### <a name="to-create-the-workflow"></a>워크플로를 만들려면  
  
1. 마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에서 **솔루션 탐색기** 선택한 **추가**하십시오 **새 항목**합니다.  
  
2. 에 **설치 됨**를 **공통 항목** 노드를 선택 **워크플로**합니다. 선택 **활동** 에서 합니다 **워크플로** 목록입니다.  
  
3. 형식 `FlowchartNumberGuessWorkflow` 에 **이름** 상자 하 고 클릭 **추가**합니다.  
  
4. 끌어서를 **순서도** 활동에서는 **순서도** 부분을 **도구 상자** 놓습니다를 **여기에 작업 놓기** 에 레이블는 워크플로 디자인 화면입니다.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>워크플로 변수와 인수를 만들려면  
  
1. 두 번 클릭 **FlowchartNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 이미 표시 되지 않으면 워크플로 디자이너에서 표시 합니다.  
  
2. 클릭 **인수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창입니다.  
  
3. 클릭 **인수를 만드는**합니다.  
  
4. 형식 `MaxNumber` 에 **이름** 상자에서 **에서** 에서 합니다 **방향** 드롭 다운 목록에서 **Int32** 합니다 에서**인수 형식** 드롭 다운 목록 및 다음 인수를 저장 하려면 ENTER 키를 누릅니다.  
  
5. 클릭 **인수를 만드는**합니다.  
  
6. 형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수 **Out** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 합니다 **인수 형식** 드롭 다운 목록 및 다음 ENTER 키를 누릅니다.  
  
7. 클릭 **인수** 닫으려면 activity designer의 왼쪽 아래에에서는 **인수** 창입니다.  
  
8. 클릭 **변수** 표시할 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창입니다.  
  
9. 클릭 **변수를 만듭니다**합니다.  
  
    > [!TIP]
    >  없으면 **변수 만들기** 상자가 표시 됩니다을 클릭 합니다 <xref:System.Activities.Statements.Flowchart> 선택 하려면 워크플로 디자이너 화면에 활동입니다.  
  
10. 형식 `Guess` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.  
  
11. 클릭 **변수를 만듭니다**합니다.  
  
12. 형식 `Target` 에 **이름** 상자에서 **Int32** 에서 합니다 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하려면 ENTER 키를 누릅니다.  
  
13. 클릭 **변수** 닫으려면 activity designer의 왼쪽 아래에에서는 **변수** 창입니다.  
  
### <a name="to-add-the-workflow-activities"></a>워크플로 활동을 추가하려면  
  
1. 끌어서를 **할당** 활동에서는 **기본** 부분을 **도구 상자** 위로 가져갑니다를 **시작** 노드 맨 위에 있는 순서도입니다. 경우는 **할당** 를 통해 작업이 **시작** 노드 주위에 삼각형 세 개가 표시 됩니다는 **시작** 노드. 삭제 합니다 **할당** 활동 바로 아래에 있는 삼각형을 **시작** 노드. 이 두 항목을 함께 연결 하 고 지정 된 **할당** 순서도의 첫 번째 활동으로 작업 합니다.  
  
    > [!NOTE]
    >  시작 노드에 활동을 직접 연결하여 워크플로에서 해당 활동을 시작 활동으로 나타낼 수도 있습니다. 이 위해 위로 마우스를 이동 합니다 **시작** 노드를 마우스를 위로 가져갈 때 나타나는 사각형 중 하나를 클릭 합니다 **시작** 노드와 끌어서 원하는 활동 아래로 줄 연결 및 중 하나에 놓습니다 표시 되는 사각형입니다. It를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 시작 활동으로 활동을 지정할 수도 있습니다 **시작 노드로 설정**합니다.  
  
2. 형식 `Target` 에 **에** 상자 및에 다음 식을 합니다 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 합니다 **뷰** 메뉴.  
  
3. 끌어서를 **프롬프트** 활동에서는 **NumberGuessWorkflowActivities** 섹션을 **도구 상자**, 아래에 놓습니다를 **할당** 활동 이전 단계와 연결 합니다 **프롬프트** 활동을 합니다 **할당** 활동. 두 활동을 연결하는 방법에는 세 가지가 있습니다. 첫 번째 방법은 놓을 때 이들을 연결 하는 **프롬프트** 워크플로에서 활동입니다. 끌 합니다 **프롬프트** 워크플로에 활동 위로 가져간 합니다 **할당** 활동 때 표시 되는 4 개의 삼각형 중 하나에 놓습니다를 **프롬프트** 통해 작업이 합니다 **할당** 활동입니다. 두 번째 방법은 삭제 하는 것을 **프롬프트** 활동을 워크플로의 원하는 위치에 놓으면 됩니다. 그런 다음 위로 마우스를 이동 합니다 **할당** 활동과 아래에 나타나는 사각형 중 하나를 끕니다를 **프롬프트** 활동. 줄 연결 되도록 마우스를 끌고를 **할당** 활동의 사각형 중 하나에 연결 합니다 **프롬프트** 작업을 선택한 다음 마우스 단추를 놓습니다. 세 번째 방법은 끌어오는 방법 대신 한다는 점을 제외 하는 첫 번째 방법은 매우 비슷합니다는 **프롬프트** 에서 작업을 **도구 상자**, 워크플로 디자인 화면의 해당 위치에서 끌어, 합니다 위로가져간 **할당** 활동 나타나는 삼각형 중 하나에 놓습니다.  
  
4. 에 **속성 창** 에 대 한 합니다 **프롬프트** 활동을 입력 `"EnterGuess"` 따옴표를 포함 하 여를 **BookmarkName** 속성 값 상자입니다. 형식 `Guess` 에 **결과** 속성 값 상자 및에 다음 식을 입력 합니다 **텍스트** 속성 상자입니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  경우는 **속성 창** 표시를 선택 하지 않는 **속성 창** 에서 합니다 **뷰** 메뉴.  
  
5. 끌어서는 **할당** 활동에서를 **기본** 부분을 **도구 상자** 는아래에이전단계에서설명한방법중하나를사용하여연결 **프롬프트** 활동입니다.  
  
6. 형식 `Turns` 에 **하** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
7. 끌어서를 **FlowDecision** 에서 **순서도** 부분을 **도구 상자** 아래에 연결 합니다 **할당** 활동. 에 **속성 창**에 다음 식을 입력 합니다 **조건** 속성 값 상자입니다.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. 다른 끌어 **FlowDecision** 에서 활동을 **도구 상자** 첫 번째 아래에 놓습니다. 레이블이 있는 사각형을 끌어 두 활동을 연결 **False** 위쪽 **FlowDecision** 사각형 위쪽의 두 번째 작업 **FlowDecision**활동입니다.  
  
    > [!TIP]
    >  표시 되지 않으면 합니다 **True** 및 **False** 레이블의 **FlowDecision**, 위로 마우스를 이동 합니다 **FlowDecision**.  
  
9. 두 번째 **FlowDecision** 활동을 선택 합니다. 에 **속성 창**에 다음 식을 입력 합니다 **조건** 속성 값 상자입니다.  
  
    ```
    Guess < Target  
    ```  
  
10. 두 개 **WriteLine** 활동을를 **기본** 섹션을 **도구 상자** 두 아래 나란히 되도록 놓을 **FlowDecision**  활동입니다. 연결 된 **True** 아래쪽의 작업 **FlowDecision** 가장 왼쪽에 있는 작업 **WriteLine** 활동 및 **False** 작업을를 맨 오른쪽 **WriteLine** 활동입니다.  
  
11. 가장 왼쪽에 있는 클릭 **WriteLine** 활동을 선택한 후에 다음 식을 입력 합니다 **텍스트** 속성 값 상자에 **속성 창**합니다.  
  
    ```
    "Your guess is too low."  
    ```  
  
12. 연결 된 **WriteLine** 의 왼쪽에는 **프롬프트** 위에 있는 작업.  
  
13. 맨 오른쪽 클릭 **WriteLine** 활동을 선택한 후에 다음 식을 입력 합니다 **텍스트** 속성 값 상자에 **속성 창**합니다.  
  
    ```
    "Your guess is too high."  
    ```  
  
14. 연결 합니다 **WriteLine** 활동의 오른쪽에는 **프롬프트** 활동 위에 합니다.  
  
     다음 예제에서는 완료된 워크플로를 보여 줍니다.  
  
     ![완료 된 Windows Workflow Foundation 순서도 보여 주는 다이어그램입니다.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a>워크플로를 빌드하려면  
  
1. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [방법: 워크플로 실행](how-to-run-a-workflow.md)합니다. 이미 완료 하는 경우는 [방법: 워크플로 실행](how-to-run-a-workflow.md) 이 단계에서 순서도 워크플로 사용 하 여 실행 하려는 워크플로의 다른 스타일을 사용 하 여 단계를 건너 뛰 세요 합니다 [빌드 및 응용 프로그램을 실행 하려면](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 부분 [하는 방법: 워크플로 실행](how-to-run-a-workflow.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Windows Workflow Foundation 프로그래밍](programming.md)
- [워크플로 디자인](designing-workflows.md)
- [초보자를 위한 자습서](getting-started-tutorial.md)
- [방법: 활동 만들기](how-to-create-an-activity.md)
- [방법: 워크플로 실행](how-to-run-a-workflow.md)
