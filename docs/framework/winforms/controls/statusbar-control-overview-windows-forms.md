---
title: StatusBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 5fdefa7d7e7c7ef543f677be7beb61dfee54e077
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077318"
---
# <a name="statusbar-control-overview-windows-forms"></a>StatusBar 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 대체 컨트롤과 기능을 추가 합니다 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나를 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤 하는 경우 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다 있습니다 이 옵션을 선택 합니다.  
  
 Windows Forms [StatusBar 컨트롤](statusbar-control-windows-forms.md) 폼에서 일반적으로 응용 프로그램에는 다양 한 종류의 상태 정보를 표시할 수는 창의 맨 아래에 표시 하는 영역으로 사용 됩니다. <xref:System.Windows.Forms.StatusBar> 컨트롤에 텍스트 또는 상태 또는 애니메이션에서 프로세스 중인; 나타내는 아이콘이 나타내는 아이콘을 표시 하는 상태 표시줄 패널에 있을 수 있습니다. 예를 들어 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] 나타내는 문서를 저장 하는 중입니다.  
  
## <a name="using-the-statusbar-control"></a>StatusBar 컨트롤 사용  
 Internet Explorer는 하이퍼링크; 위로 마우스를 가져가면 페이지의 URL을 표시 하는 상태 표시줄 사용 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] 페이지 위치, 섹션 위치 및 overtype 및 수정 버전을 추적 합니다; Visual Studio 상태 표시줄을 사용 하 여 도킹 가능한 창을 조작 하는 방법 등의 상황에 맞는 정보를 제공 하려면 같은 편집 모드에 대 한 정보 제공 으로 또는 이동 합니다.  
  
 설정 하 여 상태 표시줄에 단일 메시지를 표시할 수 있습니다는 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `false` (기본값) 설정 하는 <xref:System.Windows.Forms.StatusBar.Text%2A> 상태 표시줄에 표시할 텍스트는 상태 표시줄의 속성입니다. 나눌 수 있습니다 상태 표시줄 패널을 설정 하 여 둘 이상의 유형의 정보를 표시 하는 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true` 하 고 사용 하는 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> 메서드의 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [방법: Windows Forms StatusBar 컨트롤에서 패널 클릭 확인](determine-which-panel-wf-statusbar-control-was-clicked.md)
