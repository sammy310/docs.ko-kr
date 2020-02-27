---
title: '연습: 폼에 표준 메뉴 항목 제공'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628776"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>연습: 폼에 표준 메뉴 항목 제공

<xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.

이 연습에서는 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용 하 여 표준 메뉴를 만드는 방법을 보여 줍니다. 또한 사용자가 메뉴 항목을 선택 하면 폼이 응답 합니다. 이 연습에서는 다음 작업을 보여 줍니다.

- Windows Forms 프로젝트 만들기

- 표준 메뉴 만들기

- <xref:System.Windows.Forms.StatusStrip> 컨트롤 만들기

- 메뉴 항목 선택 항목을 처리 합니다.

작업이 완료 되 면 <xref:System.Windows.Forms.StatusStrip> 컨트롤에서 메뉴 항목을 선택 하 여 표시 하는 표준 메뉴가 있는 폼을 갖게 됩니다.

이 항목의 코드를 단일 목록으로 복사 하려면 [방법: 폼에 표준 메뉴 항목 제공](how-to-provide-standard-menu-items-to-a-form.md)을 참조 하세요.

## <a name="prerequisites"></a>사전 요구 사항

이 연습을 완료 하려면 Visual Studio가 필요 합니다.

## <a name="create-the-project"></a>프로젝트 만들기

1. Visual Studio에서 **standardmenuform** (**파일** > **새** > **프로젝트** >  **C# Visual** 또는 **Visual Basic** > **클래식 Desktop** > **응용 프로그램**) 이라는 Windows 응용 프로그램 프로젝트를 만듭니다.

2. Windows Forms 디자이너에서 폼을 선택 합니다.

## <a name="create-a-standard-menu"></a>표준 메뉴 만들기

Windows Forms 디자이너은 표준 메뉴 항목으로 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자동으로 채울 수 있습니다.

1. **도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어옵니다.

2. <xref:System.Windows.Forms.MenuStrip> 컨트롤의 디자이너 작업 문자 모양 (![작은 검정색 화살표](./media/designer-actions-glyph.gif))을 클릭 하 고 **표준 항목 삽입**을 선택 합니다.

     <xref:System.Windows.Forms.MenuStrip> 컨트롤이 표준 메뉴 항목으로 채워집니다.

3. **파일** 메뉴 항목을 클릭 하 여 기본 메뉴 항목 및 해당 아이콘을 표시 합니다.

## <a name="create-a-statusstrip-control"></a>StatusStrip 컨트롤 만들기

<xref:System.Windows.Forms.StatusStrip> 컨트롤을 사용 하 여 Windows Forms 응용 프로그램의 상태를 표시 합니다. 현재 예제에서 사용자가 선택한 메뉴 항목은 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 표시 됩니다.

1. **도구 상자**에서 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 폼으로 끌어옵니다.

     <xref:System.Windows.Forms.StatusStrip> 컨트롤은 폼의 아래쪽에 자동으로 도킹 됩니다.

2. <xref:System.Windows.Forms.StatusStrip> 컨트롤의 드롭다운 단추를 클릭 하 고 **Statuslabel** 을 선택 하 여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 추가 합니다.

## <a name="handle-item-selection"></a>항목 선택 처리

사용자가 메뉴 항목을 선택할 때 응답 하는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 처리 합니다.

1. 표준 메뉴 만들기 섹션에서 만든 **파일** 메뉴 항목을 클릭 합니다.

2. **속성** 창에서 **이벤트**를 클릭합니다.

3. <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 두 번 클릭 합니다.

     Windows Forms 디자이너 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트에 대 한 이벤트 처리기를 생성 합니다.

4. 다음 코드를 이벤트 처리기에 삽입 합니다.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. `UpdateStatus` 유틸리티 메서드 정의를 양식에 삽입 합니다.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>검사점-양식 테스트

1. **F5** 키를 눌러 폼을 컴파일하고 실행 합니다.

2. **파일** 메뉴 항목을 클릭 하 여 메뉴를 엽니다.

3. **파일** 메뉴에서 항목 중 하나를 클릭 하 여 선택 합니다.

     <xref:System.Windows.Forms.StatusStrip> 컨트롤은 선택한 항목을 표시 합니다.

## <a name="next-steps"></a>다음 단계

이 연습에서는 표준 메뉴가 있는 폼을 만들었습니다. 다양 한 용도로 <xref:System.Windows.Forms.ToolStrip> 컨트롤 패밀리를 사용할 수 있습니다.

- <xref:System.Windows.Forms.ContextMenuStrip>를 사용 하 여 컨트롤에 대 한 바로 가기 메뉴를 만듭니다. 자세한 내용은 [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)를 참조 하세요.

- 도킹 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용 하 여 MDI (다중 문서 인터페이스) 폼을 만듭니다. 자세한 내용은 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조 하세요.

- <xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양을 제공 합니다. 자세한 내용은 [방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](how-to-set-the-toolstrip-renderer-for-an-application.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip 컨트롤](menustrip-control-windows-forms.md)
