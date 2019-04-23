---
title: '방법: 디자이너를 사용하여 도구 모음 단추에 대한 아이콘 정의'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 19d0b284238ed662b25627d6077c1ebe6ecc6e86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323709"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>방법: 디자이너를 사용하여 도구 모음 단추에 대한 아이콘 정의
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolBar> 단추는 사용자가 쉽게 식별할 수 있도록 내에 아이콘을 표시할 수 있습니다. 추가 이미지를 통해 얻을 수는 <xref:System.Windows.Forms.ImageList> 구성 요소와 연결할 때와 <xref:System.Windows.Forms.ToolBar> 제어 합니다.  
  
 다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.ToolBar> 컨트롤 및 <xref:System.Windows.Forms.ImageList> 구성 요소입니다. 이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>디자인 타임에 도구 모음 단추의 아이콘을 설정 하려면  
  
1. 이미지를 추가 합니다 <xref:System.Windows.Forms.ImageList> 구성 요소입니다. 자세한 내용은 [방법: 디자이너를 사용 하 여 ImageList 이미지 추가 또는 제거](how-to-add-or-remove-imagelist-images-with-the-designer.md)합니다.  
  
2. 선택 된 <xref:System.Windows.Forms.ToolBar> 양식에 컨트롤입니다.  
  
3. 에 **속성** 창에서 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 속성을는 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.  
  
4. 클릭 합니다 <xref:System.Windows.Forms.ToolBar> 컨트롤의 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 선택 하 고 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 단추를 합니다 **ToolBarButton 컬렉션 편집기**합니다.  
  
5. 사용 합니다 **추가** 단추를 추가 하는 단추는 <xref:System.Windows.Forms.ToolBar> 컨트롤입니다.  
  
6. 에 **속성** 의 오른쪽 창에 표시 되는 창을 **ToolBarButton 컬렉션 편집기**설정는 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 목록의 값 중 하나로 각 도구 모음 단추의 속성은 추가할 이미지에서 출발 하는 <xref:System.Windows.Forms.ImageList> 구성 요소입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ToolBar>
- [방법: Toolbar 단추의 메뉴 이벤트 트리거](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar 컨트롤](toolbar-control-windows-forms.md)
- [ImageList 구성 요소](imagelist-component-windows-forms.md)
