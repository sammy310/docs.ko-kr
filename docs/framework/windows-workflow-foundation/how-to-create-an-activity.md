---
title: '방법: 작업 만들기'
description: 이 문서에서는 워크플로 파운데이션에서 두 활동을 만드는 방법을 보여 줍니다. 하나는 코드를 사용 하 여 논리를 구현 하 고 다른 활동을 사용 하 여 정의 하는 것입니다.
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: c7610d8612eb944afa9c23e1bf2abceeb3a6d38b
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190769"
---
# <a name="how-to-create-an-activity"></a>방법: 작업 만들기

활동은 [!INCLUDE[wf1](../../../includes/wf1-md.md)]에서 동작의 핵심 단위입니다. 활동의 실행 논리는 관리 코드에서 구현하거나 다른 활동을 사용하여 구현할 수 있습니다. 이 항목에서는 두 개의 활동을 만드는 방법을 보여 줍니다. 첫 번째 활동은 코드를 사용하여 실행 논리를 구현하는 간단한 활동입니다. 두 번째 활동의 구현은 다른 활동을 사용하여 정의됩니다. 이러한 활동은 자습서의 다음 단계에서 사용됩니다.

## <a name="create-the-activity-library-project"></a>활동 라이브러리 프로젝트 만들기

1. Visual Studio를 열고   >  **파일** 메뉴에서 새 **프로젝트** 를 선택 합니다.

2. **새 프로젝트** 대화 상자의 **설치 됨** 범주 아래에서 **Visual c #**  >  **워크플로** (또는 **Visual Basic**  >  **워크플로**)를 선택 합니다.

    > [!NOTE]
    > **워크플로** 템플릿 범주가 표시 되지 않으면 Visual Studio의 **Windows Workflow Foundation** 구성 요소를 설치 해야 할 수 있습니다. **새 프로젝트** 대화 상자의 왼쪽에 있는 **Visual Studio 설치 관리자 열기** 링크를 선택 합니다. Visual Studio 설치 관리자에서 **개별 구성 요소** 탭을 선택 합니다. 그런 다음 **개발 활동** 범주 아래에서 **Windows Workflow Foundation** 구성 요소를 선택 합니다. **수정** 을 선택 하 여 구성 요소를 설치 합니다.

3. **활동 라이브러리** 프로젝트 템플릿을 선택 합니다. **이름** 상자에 `NumberGuessWorkflowActivities`를 입력한 다음 **확인** 을 클릭합니다.

4. **솔루션 탐색기** 에서 **Activity1.xaml** 을 마우스 오른쪽 단추로 클릭하고 **삭제** 를 선택합니다. **확인** 을 클릭하여 확인합니다.

## <a name="create-the-readint-activity"></a>ReadInt 활동 만들기

1. **프로젝트** 메뉴에서 **새 항목 추가** 를 선택 합니다.

2. 설치 된   >  **공통 항목** 노드에서 **워크플로** 를 선택 합니다. **워크플로** 목록에서 **코드 작업** 을 선택 합니다.

3. **이름** 상자에 `ReadInt`를 입력한 다음 **추가** 를 클릭합니다.

4. 기존 `ReadInt` 정의를 다음 정의로 바꿉니다.

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > `ReadInt` 활동은 코드 활동 템플릿의 기본값인 <xref:System.Activities.NativeActivity%601> 대신 <xref:System.Activities.CodeActivity>에서 파생됩니다. 활동이 <xref:System.Activities.CodeActivity%601> 인수를 통해 노출되는 단일 결과를 제공하는 경우 <xref:System.Activities.Activity%601.Result%2A>를 사용할 수 있지만 <xref:System.Activities.CodeActivity%601>는 책갈피 사용을 지원하지 않으므로 <xref:System.Activities.NativeActivity%601>가 사용됩니다.

## <a name="create-the-prompt-activity"></a>프롬프트 활동 만들기

1. **Ctrl** + **Shift** + **B** 를 눌러 프로젝트를 빌드합니다. 프로젝트를 빌드하면 이 프로젝트의 `ReadInt` 활동을 사용하여 이 단계의 사용자 지정 활동을 빌드할 수 있습니다.

2. **프로젝트** 메뉴에서 **새 항목 추가** 를 선택 합니다.

3. 설치 된   >  **공통 항목** 노드에서 **워크플로** 를 선택 합니다. **워크플로** 목록에서 **작업** 을 선택합니다.

4. **이름** 상자에 `Prompt`를 입력한 다음 **추가** 를 클릭합니다.

5. **솔루션 탐색기** 의 xaml을 두 번 클릭 하 여 디자이너에 표시 합니다 (아직 표시 되지 않은 경우) **.**

6. 활동 디자이너의 왼쪽 아래에 있는 **인수** 를 클릭하여 **인수** 창을 표시합니다.

7. **인수 만들기** 를 클릭합니다.

8. `BookmarkName` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **문자열** 을 선택 하 고 **enter** 키를 눌러 인수를 저장 합니다.

9. **인수 만들기** 를 클릭합니다.

10. `Result`새로 추가 된 인수 아래에 있는 **이름** 상자에를 입력 `BookmarkName` 하 고 **방향** 드롭다운 목록에서 **바깥쪽** 을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32** 를 선택 하 고 **enter** 키를 누릅니다.

11. **인수 만들기** 를 클릭합니다.

12. `Text` **이름** 상자에를 입력 하 고 **방향** 드롭다운 목록 **에서 시작을** 선택한 다음 **인수 형식** 드롭다운 목록에서 **문자열** 을 선택 하 고 **enter** 키를 눌러 인수를 저장 합니다.

     이 세 가지 인수는 다음 단계에서 <xref:System.Activities.Statements.WriteLine> 활동에 추가되는 `ReadInt` 및 `Prompt` 활동의 해당 인수에 바인딩됩니다.

13. 활동 디자이너의 왼쪽 아래에 있는 **인수** 를 클릭하여 **인수** 창을 닫습니다.

14. **도구 상자** 의 **제어 흐름** 섹션에서 **Sequence** 활동을 끌어 **Prompt** 활동 디자이너의 여기에 **작업 놓기** 레이블에 놓습니다.

    > [!TIP]
    > **도구 상자** 창이 표시되지 않으면 **보기** 메뉴에서 **도구 상자** 를 선택합니다.

15. **도구 상자** 의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 **Sequence** 활동의 여기에 **작업 놓기** 레이블에 놓습니다.

16.     `Text` **속성** 창에서 **c # 식 입력** 또는 **VB 식 입력** 상자에 입력 하 여 WriteLine 활동의 text 인수를 Prompt 활동의 text 인수에 바인딩한 다음 **tab** 키를 두 번 누릅니다. 그러면 IntelliSense 목록 멤버 창이 사라지고 속성에서 선택 항목을 이동하여 속성 값이 저장됩니다. 이 속성은 `Text` 활동 자체에서 **c # 식 입력** 또는 **VB 식 입력** 상자를 입력 하 여 설정할 수도 있습니다.

    > [!TIP]
    > **속성 창이** 표시 되지 않으면 **보기** 메뉴에서 **속성 창** 을 선택 합니다.

17. **도구 상자** 의 **NumberGuessWorkflowActivities** 섹션에서 **Readint** 활동을 끌어 **Sequence** 활동에 놓으면 **WriteLine** 활동을 따릅니다.

18. 속성 창에서 BookmarkName 인수 오른쪽의 VB 식 입력 상자에를 입력 하 여 **Readint** 활동의 **BookmarkName** 인수를 **Prompt** 활동의 **BookmarkName** 인수에 바인딩한 `BookmarkName` 다음  **tab** 키를 두 번 눌러 IntelliSense 목록 멤버 창을 닫고 속성을 저장 합니다. 

19.    속성 창에서 Result 인수 오른쪽의 VB 식 입력 상자에를 입력 하 여 **Readint** 활동의 result 인수를 Prompt 활동의 result 인수에 바인딩한 `Result` 다음  **tab** 키를 두 번 누릅니다. 

20. **Ctrl** + **Shift** + **B** 를 눌러 솔루션을 빌드합니다.

## <a name="next-steps"></a>다음 단계

이러한 활동을 사용 하 여 워크플로를 만드는 방법에 대 한 지침은 자습서의 다음 단계인 [방법: 워크플로 만들기](how-to-create-a-workflow.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [사용자 지정 활동 디자인 및 구현](designing-and-implementing-custom-activities.md)
- [초보자를 위한 자습서](getting-started-tutorial.md)
- [방법: 워크플로 만들기](how-to-create-a-workflow.md)
- [사용자 지정 활동 디자이너에서 ExpressionTextBox 사용](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
