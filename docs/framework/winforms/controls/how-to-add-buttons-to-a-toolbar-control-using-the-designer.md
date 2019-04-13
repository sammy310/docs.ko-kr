---
title: '방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 509aa0b03dbbb370384fb83e0d8e5471fc2cb819
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306198"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 중요 한 부분을 <xref:System.Windows.Forms.ToolBar> 컨트롤은 단추를 추가 합니다. 또는 메뉴 명령에 쉽게 액세스할 수 있도록 사용할 수 있습니다 이러한 메뉴 구조에 사용할 수 없는 사용자에 게 명령을 노출할 응용 프로그램의 사용자 인터페이스의 다른 영역에 배치할 수 있습니다 또는.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ToolBar> 제어 합니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-add-buttons-at-design-time"></a>디자인 타임에 단추를 추가 하려면  
  
1. <xref:System.Windows.Forms.ToolBar> 컨트롤을 선택합니다.  
  
2. 에 **속성** 창 클릭 합니다 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 선택 하 고 클릭 합니다 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png " vbEllipsesButton")) 버튼을 클릭 하 여 **ToolBarButton 컬렉션 편집기**합니다.  
  
3. 사용 하 여는 **추가** 및 **제거** 단추를 추가 하거나 제거 하는 단추는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.  
  
4. 개별 단추 속성을 구성 합니다 **속성** 편집기의 오른쪽 창에 표시 되는 창입니다. 다음 표에서 고려해 야 할 몇 가지 중요 한 속성을 보여 줍니다.  
  
    |속성|설명|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|드롭다운 도구 모음 단추에 표시할 메뉴를 설정 합니다. 도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>합니다. 이 속성의 인스턴스를 사용 하는 <xref:System.Windows.Forms.ContextMenu> 클래스를 참조 합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|토글 스타일 도구 모음 단추가 부분적으로 눌리는 지 여부를 설정 합니다. 도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|토글 스타일 도구 모음 단추가 현재 눌러진된 상태에 있는지 여부를 설정 합니다. 도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> 또는 <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|도구 모음 단추의 스타일을 설정합니다. 에 있는 값 중 하나 여야 합니다 <xref:System.Windows.Forms.ToolBarButtonStyle> 열거형입니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|단추에서 표시 되는 텍스트 문자열입니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|단추의 도구 설명으로 표시 되는 텍스트입니다.|  
  
5. 클릭 **확인** 지정한 패널을 만들고 대화 상자를 닫습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolBar>
- [방법: 도구 모음 단추에 대한 아이콘 정의](how-to-define-an-icon-for-a-toolbar-button.md)
- [방법: Toolbar 단추에 대한 메뉴 이벤트 트리거](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar 컨트롤 개요](toolbar-control-overview-windows-forms.md)
- [ToolBar 컨트롤](toolbar-control-windows-forms.md)
