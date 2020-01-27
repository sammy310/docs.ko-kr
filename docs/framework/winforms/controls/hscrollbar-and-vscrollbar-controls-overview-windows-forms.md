---
title: HScrollBar 및 VScrollBar 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728165"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)
응용 프로그램 또는 컨트롤 내에서 가로 또는 세로로 스크롤하여 긴 항목 목록을 통해 쉽게 탐색 하거나 많은 양의 정보를 제공 하는 데 사용 되는 Windows Forms <xref:System.Windows.Forms.ScrollBar> 컨트롤입니다. 스크롤 막대는 Windows 인터페이스의 공통 요소 이므로 <xref:System.Windows.Forms.ScrollBar> 컨트롤은 <xref:System.Windows.Forms.ScrollableControl> 클래스에서 파생 되지 않는 컨트롤과 함께 사용 되는 경우가 많습니다. 마찬가지로, 대부분의 개발자는 자체 사용자 정의 컨트롤을 제작할 때 <xref:System.Windows.Forms.ScrollBar> 컨트롤을 통합 하도록 선택 합니다.  
  
 <xref:System.Windows.Forms.HScrollBar> (가로) 및 <xref:System.Windows.Forms.VScrollBar> (수직) 컨트롤은 다른 컨트롤과 독립적으로 작동 하며 고유한 이벤트, 속성 및 메서드 집합을 가집니다. <xref:System.Windows.Forms.ScrollBar> 컨트롤은 텍스트 상자, 목록 상자, 콤보 상자 또는 MDI 폼에 연결 된 기본 제공 스크롤 막대와 동일 하지 않습니다. <xref:System.Windows.Forms.TextBox> 컨트롤에는 컨트롤에 연결 된 스크롤 막대를 표시 하거나 숨기는 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성이 있습니다.  
  
 <xref:System.Windows.Forms.ScrollBar> 컨트롤은 <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 사용 하 여 스크롤 막대를 따라 스크롤 상자 (엄지 단추 라고도 함)의 움직임을 모니터링 합니다. <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 사용 하면 스크롤 막대 값을 끌 때 해당 값에 액세스할 수 있습니다.  
  
## <a name="value-property"></a>값 속성  
 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성 (기본값은 0)은 스크롤 막대의 스크롤 상자 위치에 해당 하는 `integer` 값입니다. 스크롤 상자 위치가 최소값이 면 가장 왼쪽 위치 (가로 스크롤 막대의 경우) 또는 위쪽 위치 (세로 스크롤 막대의 경우)로 이동 합니다. 스크롤 상자가 최대값에 있으면 스크롤 상자가 맨 오른쪽 또는 맨 아래 위치로 이동 합니다. 마찬가지로, 범위의 아래쪽과 위쪽의 중간 값은 스크롤 막대의 가운데에 있는 스크롤 상자의 선행 가장자리를 배치 합니다.  
  
 사용자는 마우스 클릭을 사용 하 여 스크롤 막대 값을 변경할 뿐만 아니라 스크롤 상자를 막대의 모든 지점으로 끌 수도 있습니다. 결과 값은 스크롤 상자의 위치에 따라 달라 지지만 항상 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 범위 내에서 사용자가 설정한 속성을 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 합니다.  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange 및 SmallChange 속성  
 사용자가 스크롤 상자의 양쪽에서 PAGE UP 또는 PAGE DOWN 키를 누르거나 스크롤 막대 트랙을 클릭 하면 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성이 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 속성에 설정 된 값에 따라 변경 됩니다.  
  
 키 또는 스크롤 막대 단추 중 하나를 클릭할 때 사용자가 누를 화살표 중 하나는 <xref:System.Windows.Forms.ScrollBar.Value%2A> 에 설정 된 값에 따라 속성 변경 내용을 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 속성입니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
