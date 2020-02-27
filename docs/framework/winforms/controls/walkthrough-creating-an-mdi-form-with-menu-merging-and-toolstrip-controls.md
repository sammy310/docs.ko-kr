---
title: '연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628789"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기

<xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 애플리케이션을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다. MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.

이 연습에서는 MDI 폼을 사용 하 여 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 사용 하는 방법을 보여 줍니다. 폼은 자식 메뉴와 메뉴 병합도 지원합니다. 이 연습에서는 다음 작업을 보여 줍니다.

- Windows Forms 프로젝트 만들기

- 폼에 대 한 주 메뉴 만들기 메뉴의 실제 이름은 다를 수 있습니다.

- **도구 상자**에 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 추가

- 자식 폼 만들기

- <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 z 순서로 정렬 합니다.

작업이 완료 되 면 메뉴 병합 및 이동 가능한 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 지 원하는 MDI 폼을 갖게 됩니다.

이 항목의 코드를 단일 목록으로 복사 하려면 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조 하세요.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료 하려면 Visual Studio가 필요 합니다.

## <a name="create-the-project"></a>프로젝트 만들기

1. Visual Studio에서 **system.windows.forms.toolstrip.mdiform** (**File** > **New** > **project** >  **C# Visual** 또는 **Visual Basic** > **클래식 Desktop** > **응용 프로그램**) 라는 Windows 응용 프로그램 프로젝트를 만듭니다.

2. Windows Forms 디자이너에서 폼을 선택 합니다.

3. 속성 창에서 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>의 값을 `true`로 설정 합니다.

## <a name="create-the-main-menu"></a>주 메뉴 만들기

부모 MDI 폼에는 주 메뉴가 포함 됩니다. 주 메뉴에는 **창**이라는 하나의 메뉴 항목이 있습니다. **창** 메뉴 항목을 사용 하 여 자식 폼을 만들 수 있습니다. 자식 폼의 메뉴 항목이 주 메뉴에 병합 됩니다.

1. **도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어옵니다.

2. <xref:System.Windows.Forms.MenuStrip> 컨트롤에 <xref:System.Windows.Forms.ToolStripMenuItem>을 추가 하 고 이름을 **창**에 추가 합니다.

3. <xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.

4. 속성 창에서 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성의 값을 `ToolStripMenuItem1`로 설정 합니다.

5. **창** 메뉴 항목에 하위 항목을 추가한 다음 하위 항목의 이름을 **New**로 지정한 다음

6. 속성 창에서 **이벤트**를 클릭 합니다.

7. <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 두 번 클릭 합니다.

     Windows Forms 디자이너 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트에 대 한 이벤트 처리기를 생성 합니다.

8. 다음 코드를 이벤트 처리기에 삽입 합니다.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>도구 상자에 ToolStripPanel 컨트롤 추가

MDI 폼에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용 하는 경우 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 있어야 합니다. <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자** 에 추가 하 여 WINDOWS FORMS 디자이너에서 MDI 폼을 빌드해야 합니다.

1. **도구 상자**를 연 다음 **모든 Windows Forms** 탭을 클릭 하 여 사용할 수 있는 Windows Forms 컨트롤을 표시 합니다.

2. 마우스 오른쪽 단추를 클릭 하 여 바로 가기 메뉴를 열고 **항목 선택**을 선택 합니다.

3. **도구 상자 항목 선택** 대화 상자에서 **ToolStripPanel**를 찾을 때까지 **이름** 열을 아래로 스크롤합니다.

4. **ToolStripPanel**확인란을 선택 하 고 **확인**을 클릭 합니다.

     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 **도구 상자**에 나타납니다.

## <a name="create-a-child-form"></a>자식 폼 만들기

이 절차에서는 자체 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 포함 하는 별도의 자식 폼 클래스를 정의 합니다. 이 폼에 대 한 메뉴 항목은 부모 폼의 메뉴 항목과 병합 됩니다.

1. `ChildForm` 라는 새 폼을 프로젝트에 추가 합니다.

     자세한 내용은 [방법: 프로젝트에 Windows Forms 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))를 참조 하세요.

2. **도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼으로 끌어옵니다.

3. <xref:System.Windows.Forms.MenuStrip> 컨트롤의 디자이너 작업 문자 모양 (![작은 검정색 화살표](./media/designer-actions-glyph.gif))을 클릭 한 다음 **항목 편집**을 선택 합니다.

4. **항목 컬렉션 편집기** 대화 상자에서 **childmenuitem** 이라는 새 <xref:System.Windows.Forms.ToolStripMenuItem>를 자식 메뉴에 추가 합니다.

     자세한 내용은 [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))를 참조 하세요.

## <a name="test-the-form"></a>양식 테스트

1. **F5** 키를 눌러 폼을 컴파일하고 실행 합니다.

2. **창** 메뉴 항목을 클릭 하 여 메뉴를 열고 **새로 만들기**를 클릭 합니다.

     새 자식 폼이 폼의 MDI 클라이언트 영역에 만들어집니다. 자식 폼의 메뉴가 주 메뉴와 병합 됩니다.

3. 자식 폼을 닫습니다.

     자식 폼의 메뉴가 주 메뉴에서 제거 됩니다.

4. **새로 만들기** 를 여러 번 클릭 합니다.

     자식 폼은 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성이 할당 되기 때문에 **창** 메뉴 항목에 자동으로 나열 됩니다.

## <a name="add-toolstrip-support"></a>ToolStrip 지원 추가

이 절차에서는 MDI 부모 폼에 4 개의 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 추가 합니다. 각 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 폼의 가장자리에 도킹 된 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 내에 추가 됩니다.

1. **도구 상자**에서 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 끌어옵니다.

2. <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택 하 고 **도구 상자**에서 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 두 번 클릭 합니다.

     <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 생성 됩니다.

3. <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.

4. 속성 창에서 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle.Left>로 변경 합니다.

     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤은 폼의 왼쪽에 주 메뉴 아래에 도킹 합니다. MDI 클라이언트 영역의 크기는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 맞게 조정 됩니다.

5. 1-4 단계를 반복 합니다.

     새 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 맨 위에 도킹 합니다.

     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤은 주 메뉴 아래에 도킹 되지만 첫 번째 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 오른쪽에 도킹 됩니다. 이 단계에서는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 올바른 위치 지정에서 z 순서에 대 한 중요성을 보여 줍니다.

6. 두 개 이상의 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 대해 1 ~ 4 단계를 반복 합니다.

     새 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 오른쪽 및 아래쪽에 도킹 합니다.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>ToolStripPanel 컨트롤을 Z 순서로 정렬

MDI 폼에서 도킹 된 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 위치는 z 순서에서 컨트롤의 위치에 따라 결정 됩니다. 문서 개요 창에서 컨트롤의 z 순서를 쉽게 정렬할 수 있습니다.

1. **보기** 메뉴에서 **다른 창**을 클릭 한 다음 **문서 개요**를 클릭 합니다.

     이전 절차에서 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 정렬 하는 것은 표준이 아닙니다. 이는 z 순서가 올바르지 않기 때문입니다. 문서 개요 창을 사용 하 여 컨트롤의 z 순서를 변경할 수 있습니다.

2. 문서 개요 창에서 **ToolStripPanel4**를 선택 합니다.

3. 목록 맨 아래에 **ToolStripPanel4** 가 표시 될 때까지 아래쪽 화살표 단추를 반복 해 서 클릭 합니다.

     **ToolStripPanel4** 컨트롤은 폼의 아래쪽에 다른 컨트롤 아래에 도킹 됩니다.

4. **ToolStripPanel2**를 선택 합니다.

5. 아래쪽 화살표 단추를 한 번 클릭 하 여 목록에서 세 번째 컨트롤을 배치 합니다.

     **ToolStripPanel2** 컨트롤은 폼의 맨 위, 주 메뉴 및 기타 컨트롤의 위쪽에 도킹 됩니다.

6. **문서 개요** 창에서 다양 한 컨트롤을 선택 하 고 z 순서에서 다른 위치로 이동 합니다. 도킹 된 컨트롤의 배치에 대 한 z 순서의 효과를 확인 합니다. **편집** 메뉴에서 CTRL + Z 또는 **undo** 를 사용 하 여 변경 내용을 취소 합니다.

## <a name="checkpoint---test-your-form"></a>검사점-양식 테스트

1. **F5** 키를 눌러 폼을 컴파일하고 실행 합니다.

2. <xref:System.Windows.Forms.ToolStrip> 컨트롤의 그립을 클릭 하 고 컨트롤을 폼의 다른 위치로 끕니다.

     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 간에 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 끌어 놓을 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 연습에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합을 사용 하 여 MDI 부모 폼을 만들었습니다. 다양 한 용도로 <xref:System.Windows.Forms.ToolStrip> 컨트롤 패밀리를 사용할 수 있습니다.

- <xref:System.Windows.Forms.ContextMenuStrip>를 사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만듭니다. 자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)를 참조 하세요.

- 자동으로 채워진 표준 메뉴가 있는 폼을 만들었습니다. 자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](walkthrough-providing-standard-menu-items-to-a-form.md)을 참조 하세요.

- <xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양을 제공 합니다. 자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [방법: MDI 상위 폼 만들기](../advanced/how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 폼 만들기](../advanced/how-to-create-mdi-child-forms.md)
- [방법: MDI 드롭다운 메뉴에 MenuStrip 삽입](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [ToolStrip 컨트롤](toolstrip-control-windows-forms.md)
