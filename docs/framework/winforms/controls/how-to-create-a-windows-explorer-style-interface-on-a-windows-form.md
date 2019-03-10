---
title: '방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 444d85265822b5dd4b3a5fd5f4329ec6cc1427f5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705014"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기
Windows 탐색기는 쉽게 사용할 수 있으므로 응용 프로그램에 대 한 공통 사용자 인터페이스 좋습니다.  
  
 Windows 탐색기가 기본적으로 <xref:System.Windows.Forms.TreeView> 컨트롤 및 <xref:System.Windows.Forms.ListView> 별도 패널에서 컨트롤입니다. 패널을 분할 하 여 조정할 수 있습니다. 이 컨트롤 배열을 표시 하 고 정보를 검색에 대 한 매우 효율적입니다.  
  
 다음 단계는 Windows 탐색기와 유사한 폼에서에서 컨트롤을 정렬 하는 방법을 보여 줍니다. Windows 탐색기 응용 프로그램의 파일 검색 기능을 추가 하는 방법을 표시 되지 않습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Windows 탐색기 스타일 Windows 폼을 만들려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트** > **Visual C#** 나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).  
  
2.  **도구 상자**:  
  
    1.  끌어서를 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼으로 합니다.  
  
    2.  끌어서를 <xref:System.Windows.Forms.TreeView> 컨트롤을 **SplitterPanel1** (의 패널을 합니다 <xref:System.Windows.Forms.SplitContainer> 표시 하는 컨트롤 **Panel1**).  
  
    3.  끌어서를 <xref:System.Windows.Forms.ListView> 컨트롤을 **SplitterPanel2** (의 패널 합니다 <xref:System.Windows.Forms.SplitContainer> 표시 컨트롤 **Panel2**).  
  
3.  CTRL 키를 차례로 클릭 하 여 모든 3 가지 컨트롤을 선택 합니다. 선택 하는 경우는 <xref:System.Windows.Forms.SplitContainer> 컨트롤, 패널 대신 분할 막대를 클릭 합니다.  
  
    > [!NOTE]
    >  사용 하지 않는 합니다 **모두 선택** 명령을 합니다 **편집** 메뉴. 이렇게 하면 다음 단계에 필요한 속성에 표시 되지 것입니다 합니다 **속성** 창입니다.  
  
4.  **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
5.  F5 키를 눌러 애플리케이션을 실행합니다.  
  
     Windows 탐색기와 비슷한 두 부분으로 구성 사용자 인터페이스를 표시 합니다.  
  
    > [!NOTE]
    >  분할자를 끌면 패널 자체 조정 합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.SplitContainer>
- [방법: Windows Forms로 다중 창 사용자 인터페이스 만들기](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [방법: 크기 조정 및 분할 창에서 위치 지정 동작 정의](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [방법: 가로로 창 분합니다](how-to-split-a-window-horizontally.md)
- [SplitContainer 컨트롤](splitcontainer-control-windows-forms.md)
