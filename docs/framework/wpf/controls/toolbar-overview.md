---
title: ToolBar 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
ms.openlocfilehash: b5498b8b88c7403ffe51256a57544261de3ace08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186611"
---
# <a name="toolbar-overview"></a>ToolBar 개요
<xref:System.Windows.Controls.ToolBar>컨트롤은 일반적으로 해당 함수와 관련된 명령 또는 컨트롤 그룹에 대한 컨테이너입니다. 일반적으로 <xref:System.Windows.Controls.ToolBar> A에는 명령을 호출하는 단추가 포함되어 있습니다.  

<a name="ToolBarControl"></a>
## <a name="toolbar-control"></a>ToolBar 컨트롤  
 컨트롤은 <xref:System.Windows.Controls.ToolBar> 단추 또는 다른 컨트롤의 막대 와 같은 배열에서 이름을 단일 행 또는 열로 이동합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.ToolBar> 컨트롤은 크기 제한 영역 내에 자연스럽게 맞지 않는 항목을 특수 <xref:System.Windows.Controls.ToolBar> 오버플로 영역으로 배치하는 오버플로 메커니즘을 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 또한 컨트롤은 일반적으로 도구 <xref:System.Windows.Controls.ToolBarTray> 모음의 사용자 시작 크기 조정 및 정렬에 대한 지원뿐만 아니라 특별한 레이아웃 동작을 제공하는 관련 컨트롤과 함께 사용됩니다.  
  
<a name="Creating_ToolBars"></a>
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a>ToolBarTray에서 ToolBar 위치 지정  
 <xref:System.Windows.Controls.ToolBar.Band%2A> 및 속성을 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 사용하여 에 위치 합니다. <xref:System.Windows.Controls.ToolBar> <xref:System.Windows.Controls.ToolBarTray> <xref:System.Windows.Controls.ToolBar.Band%2A>은 <xref:System.Windows.Controls.ToolBar> 의 상위 <xref:System.Windows.Controls.ToolBarTray>에 배치되는 위치를 나타냅니다. <xref:System.Windows.Controls.ToolBar.BandIndex%2A>은 밴드 내에 <xref:System.Windows.Controls.ToolBar> 배치되는 순서를 나타냅니다. 다음 예제에서는 배치에이 속성을 사용 방법 <xref:System.Windows.Controls.ToolBar> 내부의 컨트롤을 <xref:System.Windows.Controls.ToolBarTray>입니다.  
  
 [!code-xaml[ToolBarExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>
## <a name="toolbars-with-overflow-items"></a>오버플로 항목이 있는 ToolBar  
 컨트롤에는 <xref:System.Windows.Controls.ToolBar> 도구 모음의 크기에 맞출 수 있는 것보다 많은 항목이 포함된 경우가 많습니다. 이 경우 오버플로 버튼이 <xref:System.Windows.Controls.ToolBar> 표시됩니다. 오버플로 항목을 보려면 사용자가 오버플로 단추를 클릭하고 항목이 <xref:System.Windows.Controls.ToolBar>아래의 팝업 창에 표시됩니다. 다음 그래픽에는 <xref:System.Windows.Controls.ToolBar> 오버플로 항목이 있는 a가 표시됩니다.  
  
 ![오버플로 항목이 있는 도구 모음을 보여 주는 스크린샷입니다.](./media/toolbar-overview/toolbar-overflow-items.png)  
  
 도구 모음의 항목이 오버플로 패널에 배치되는 <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> 시기를 에 첨부된 속성을 로 설정하거나 <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType> <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType> <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>. 다음 예제에서는 도구 모음에 있는 마지막 네 개의 단추가 오버플로 패널에 항상 표시되도록 지정합니다.  
  
 [!code-xaml[ToolBarExample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 의 <xref:System.Windows.Controls.ToolBar> a와 <xref:System.Windows.Controls.Primitives.ToolBarPanel> <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 를 <xref:System.Windows.Controls.ControlTemplate>사용합니다.  도구 <xref:System.Windows.Controls.Primitives.ToolBarPanel> 모음의 항목 레이아웃을 담당합니다.  에 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 맞지 않는 항목의 레이아웃에 대한 책임은 <xref:System.Windows.Controls.ToolBar>있습니다. 에 <xref:System.Windows.Controls.ControlTemplate> 대한 <xref:System.Windows.Controls.ToolBar>예는  
  
 [도구 모음 스타일 및 템플릿 .](toolbar-styles-and-templates.md)  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Primitives.ToolBarPanel>
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>
- [ToolBar 컨트롤의 스타일 지정](how-to-style-controls-on-a-toolbar.md)
- [WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)(WPF 컨트롤 갤러리 샘플)
