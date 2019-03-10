---
title: '방법: 디자이너를 사용 하 여 Windows Forms로 다중 창 사용자 인터페이스 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 1ad446fde4ccfc9ad9c48e619321deed044f1014
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713776"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>방법: 디자이너를 사용 하 여 Windows Forms로 다중 창 사용자 인터페이스 만들기
다음 절차를 사용 하 여 Microsoft Outlook에서 사용 하는 비슷한 다중 창 사용자 인터페이스를 만듭니다는 **폴더** 목록에는 **메시지** 창 및 **미리보기** 창입니다. 이 정렬 폼에 컨트롤을 도킹을 통해 주로 수행 됩니다.  
  
 컨트롤을 고정 하면 부모 컨테이너의 가장자리 컨트롤은 고정 시킬 확인할 수 있습니다. 따라서 설정 하는 경우는 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Right>, 컨트롤의 오른쪽 가장자리 부모 컨트롤의 오른쪽 가장자리에 도킹 됩니다. 또한 컨트롤의 도킹된 가장자리 컨테이너 컨트롤과의 일치 하도록 크기가 조정 됩니다. 방법에 대 한 자세한 내용은 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 참조 하십시오 [방법: Windows Forms에서 컨트롤을 도킹](how-to-dock-controls-on-windows-forms.md)합니다.  
  
 정렬에 중점을 두고이 절차는 <xref:System.Windows.Forms.SplitContainer> 및 기타 컨트롤이 폼에, 응용 프로그램을 Microsoft Outlook을 모방 하는 기능을 추가 하는 방법에 없습니다.  
  
 내에서 모든 컨트롤을 배치 하면이 사용자 인터페이스를 만들려면를 <xref:System.Windows.Forms.SplitContainer> 포함 하는 컨트롤을 <xref:System.Windows.Forms.TreeView> 왼쪽 패널에서 컨트롤입니다. 오른쪽 패널을 <xref:System.Windows.Forms.SplitContainer> 컨트롤에 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 <xref:System.Windows.Forms.ListView> 컨트롤 위의 <xref:System.Windows.Forms.RichTextBox> 컨트롤. 이러한 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼에 다른 컨트롤의 독립적인 크기 조정을 사용 합니다. 자신만의 사용자 지정 사용자 인터페이스를 작성 하는이 절차에 설명 된 기술을 조정할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>디자인 타임에 Outlook 스타일 사용자 인터페이스를 만들려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 만듭니다 (**파일** > **새로 만들기** > **프로젝트** > **Visual C#** 나 **Visual Basic** > **클래식 바탕 화면** > **Windows Forms 응용 프로그램**).  
  
2.  끌어서를 <xref:System.Windows.Forms.SplitContainer> 에서 제어 합니다 **도구 상자** 폼입니다. **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
3.  끌어서를 <xref:System.Windows.Forms.TreeView> 에서 제어 합니다 **도구 상자** 의 왼쪽 패널에는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. 에 **속성** 창에서 설정 합니다 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left> 아래쪽 화살표를 클릭할 때 표시 되는 값 편집기의 왼쪽 패널을 클릭 하 여 합니다.  
  
4.  다른 <xref:System.Windows.Forms.SplitContainer> 에서 제어 합니다 **도구 상자**;의 오른쪽 패널에 배치 합니다 <xref:System.Windows.Forms.SplitContainer> 폼에 추가 된 컨트롤입니다. 에 **속성** 창에서 설정 합니다 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill> 및 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성을 <xref:System.Windows.Forms.Orientation.Horizontal>합니다.  
  
5.  끌어서를 <xref:System.Windows.Forms.ListView> 에서 제어 합니다 **도구 상자** 초의 위 패널에 <xref:System.Windows.Forms.SplitContainer> 폼에 추가 된 컨트롤입니다. <xref:System.Windows.Forms.SplitContainer.Dock%2A> 컨트롤의 <xref:System.Windows.Forms.ListView> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
6.  끌어서를 <xref:System.Windows.Forms.RichTextBox> 에서 제어 합니다 **도구 상자** 두 번째의 아래쪽 패널에 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. <xref:System.Windows.Forms.SplitContainer.Dock%2A> 컨트롤의 <xref:System.Windows.Forms.RichTextBox> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
     이 시점에서 f5 키를 눌러 응용 프로그램을 실행 하는 경우 폼 비슷합니다 Microsoft Outlook의 세 부분으로 이루어진 사용자 인터페이스를 표시 합니다.  
  
    > [!NOTE]
    >  내에서 분할자의 중 하나를 통해 마우스 포인터를 놓으면는 <xref:System.Windows.Forms.SplitContainer> 컨트롤 내부 크기를 조정할 수 있습니다.  
  
     이 시점에서 응용 프로그램 개발에는 정교한 사용자 인터페이스를 트 했습니다. 다음 단계는 자체 응용 프로그램의 프로그래밍을 사용 하 여 계속 아마도 연결 하 여 합니다 <xref:System.Windows.Forms.TreeView> 컨트롤 및 <xref:System.Windows.Forms.ListView> 일부 종류의 데이터 소스 컨트롤입니다. 데이터에 컨트롤을 연결 하는 방법에 대 한 자세한 내용은 참조 하세요. [데이터 바인딩 및 Windows Forms](../data-binding-and-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 컨트롤](splitcontainer-control-windows-forms.md)
