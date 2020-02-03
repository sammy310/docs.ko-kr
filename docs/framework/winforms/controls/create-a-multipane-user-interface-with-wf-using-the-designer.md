---
title: 디자이너를 사용 하 여 다중 창 사용자 인터페이스 만들기
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 6b41d538f1cd1633cec51c89e27adf3c5b47f9a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737280"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기
다음 절차에서는 **폴더** 목록, **메시지** 창 및 **미리 보기** 창을 사용 하 여 Microsoft Outlook에서 사용 되는 것과 유사한 다중 창 사용자 인터페이스를 만듭니다. 이러한 정렬은 폼을 사용 하 여 도킹 컨트롤을 통해 주로 됩니다.

 컨트롤을 도킹할 때 컨트롤이 고정 되는 부모 컨테이너의 가장자리를 결정 합니다. 따라서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Right>로 설정 하면 컨트롤의 오른쪽 가장자리가 부모 컨트롤의 오른쪽 가장자리에 도킹 됩니다. 또한 컨트롤의 도킹 된 가장자리는 컨테이너 컨트롤의 크기에 맞게 조정 됩니다. <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성의 작동 방식에 대 한 자세한 내용은 [방법: Windows Forms에 컨트롤 도킹](how-to-dock-controls-on-windows-forms.md)을 참조 하세요.

 이 절차에서는 응용 프로그램이 Microsoft Outlook을 모방 하는 기능을 추가 하는 것이 아니라 폼의 <xref:System.Windows.Forms.SplitContainer> 및 기타 컨트롤을 정렬 하는 방법을 집중적으로 설명 합니다.

 이 사용자 인터페이스를 만들려면 왼쪽 패널에서 <xref:System.Windows.Forms.TreeView> 컨트롤을 포함 하는 <xref:System.Windows.Forms.SplitContainer> 컨트롤 내에 모든 컨트롤을 저장 합니다. <xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽 패널에는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 위에 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 있습니다. 이러한 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 폼에서 다른 컨트롤의 크기를 독립적으로 조정할 수 있도록 합니다. 사용자 고유의 사용자 지정 사용자 인터페이스를 만들 수 있도록이 절차의 기술을 적용할 수 있습니다.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>디자인 타임에 Outlook 스타일 사용자 인터페이스를 만들려면

1. 새 Windows 응용 프로그램 프로젝트 (**파일** > **새** > **프로젝트** > **Visual C#**  또는 **Visual Basic** > **클래식 데스크톱** > **응용 프로그램**)를 만듭니다.

2. <xref:System.Windows.Forms.SplitContainer> 컨트롤을 **도구 상자** 에서 폼으로 끌어 옵니다. **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.

3. **도구 상자** 에서 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 왼쪽 패널로 <xref:System.Windows.Forms.TreeView> 컨트롤을 끌어 옵니다. **속성** 창에서 아래쪽 화살표를 클릭할 때 표시 되는 값 편집기의 왼쪽 패널을 클릭 하 여 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left>로 설정 합니다.

4. **도구 상자**에서 다른 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 끕니다. 폼에 추가한 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽 패널에 놓습니다. **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정 하 고 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성을 <xref:System.Windows.Forms.Orientation.Horizontal>로 설정 합니다.

5. **도구 상자** 의 <xref:System.Windows.Forms.ListView> 컨트롤을 폼에 추가한 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 위쪽 패널로 끕니다. <xref:System.Windows.Forms.SplitContainer.Dock%2A> 컨트롤의 <xref:System.Windows.Forms.ListView> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.

6. **도구 상자** 에서 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 아래쪽 패널로 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 끕니다. <xref:System.Windows.Forms.SplitContainer.Dock%2A> 컨트롤의 <xref:System.Windows.Forms.RichTextBox> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.

     이제 F5 키를 눌러 응용 프로그램을 실행 하는 경우 Microsoft Outlook의 경우와 유사한 세 부분으로 구성 된 사용자 인터페이스가 폼에 표시 됩니다.

    > [!NOTE]
    > <xref:System.Windows.Forms.SplitContainer> 컨트롤 내에 있는 분할자 중 하나 위에 마우스 포인터를 놓으면 내부 차원의 크기를 조정할 수 있습니다.

응용 프로그램 개발의이 시점에서 정교한 사용자 인터페이스를 만들었습니다. 다음 단계는 <xref:System.Windows.Forms.TreeView> 컨트롤과 <xref:System.Windows.Forms.ListView> 컨트롤을 일종의 데이터 소스에 연결 하 여 응용 프로그램 자체의 프로그래밍을 진행 합니다. 컨트롤을 데이터에 연결 하는 방법에 대 한 자세한 내용은 [데이터 바인딩 및 Windows Forms](../data-binding-and-windows-forms.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 컨트롤](splitcontainer-control-windows-forms.md)
