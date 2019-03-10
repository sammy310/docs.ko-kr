---
title: '방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b81cb839664499d69710d81b7b0c8a479966d569
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724949"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤
설정 하 여 폼의 가장자리에 맞춰서 컨트롤을 정렬할 수 있게 된 <xref:System.Windows.Forms.Control.Dock%2A>합니다. 이 속성은 양식에서 컨트롤의 위치를 지정합니다. 
  <xref:System.Windows.Forms.Control.Dock%2A> 속성은 다음 값으로 설정할 수 있습니다.  
  
|설정|컨트롤에 대한 영향|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|양식의 아래쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|양식의 나머지 공간을 모두 채웁니다.|  
|<xref:System.Windows.Forms.DockStyle.Left>|양식의 왼쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle.None>|지정 된 위치에 표시를 도킹 하지 않고 해당 <xref:System.Windows.Forms.Control.Location%2A>합니다.|  
|<xref:System.Windows.Forms.DockStyle.Right>|컨트롤을 양식의 오른쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle.Top>|양식의 위쪽에 도킹합니다.|  
  
 또한 코드에서 이러한 값을 설정할 수 있습니다. 자세한 내용은 [방법: 컨트롤을 폼의 가장자리에 맞춤](how-to-align-a-control-to-the-edges-of-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a>디자인 타임에 컨트롤에 대 한 Dock 속성을 설정 하려면  
  
1.  Windows Forms 디자이너에서 컨트롤을 선택 합니다.  
  
2.  에 **속성** 창에서 클릭 드롭다운 목록 상자 옆에는 <xref:System.Windows.Forms.Control.Dock%2A> 속성입니다.  
  
     여섯 개의 사용 가능한 그래픽 인터페이스 <xref:System.Windows.Forms.Control.Dock%2A> 설정이 표시 됩니다.  
  
3.  적절 한 설정을 선택 합니다.  
  
4.  설정에서 지정한 방식으로 컨트롤을 도킹 이제 됩니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [방법: 컨트롤을 폼의 가장자리에 맞춤](how-to-align-a-control-to-the-edges-of-forms.md)
- [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [방법: Windows Forms에서 컨트롤 고정](how-to-anchor-controls-on-windows-forms.md)
- [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [연습: TableLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [연습: FlowLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [디자인 타임에 Windows Forms 컨트롤 개발](developing-windows-forms-controls-at-design-time.md)
