---
title: RichTextBox 컨트롤에서 스크롤 막대 표시
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745555"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤에서 스크롤 막대 표시
기본적으로 Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 필요한 경우 가로 및 세로 스크롤 막대를 표시 합니다. 아래 표에서 설명 하는 <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성에는 7 가지 값을 사용할 수 있습니다.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>RichTextBox 컨트롤에서 스크롤 막대를 표시 하려면  
  
1. <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성을 `true`으로 설정합니다. <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 속성이 `false`로 설정 되어 있으면 가로를 포함 하는 스크롤 막대의 형식이 표시 되지 않습니다.  
  
2. <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 속성을 <xref:System.Windows.Forms.RichTextBoxScrollBars> 열거형의 적절 한 값으로 설정 합니다.  
  
    |값|설명|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both>(기본)|텍스트가 컨트롤의 너비나 길이를 초과 하는 경우에만 가로 또는 세로 스크롤 막대를 표시 하거나 둘 다 표시 합니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|스크롤 막대의 유형을 표시 하지 않습니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|텍스트가 컨트롤의 너비를 초과 하는 경우에만 가로 스크롤 막대를 표시 합니다. 이를 수행 하려면 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 `false`로 설정 해야 합니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|텍스트가 컨트롤의 높이를 초과할 때만 세로 스크롤 막대를 표시 합니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정 된 경우 가로 스크롤 막대를 표시 합니다. 텍스트가 컨트롤의 너비를 초과 하지 않으면 스크롤 막대가 흐리게 표시 됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|항상 세로 스크롤 막대를 표시 합니다. 텍스트가 컨트롤의 길이를 초과 하지 않으면 스크롤 막대가 흐리게 표시 됩니다.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|항상 세로 스크롤 막대를 표시 합니다. <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성이 `false`로 설정 된 경우 가로 스크롤 막대를 표시 합니다. 텍스트가 컨트롤의 너비나 길이를 초과 하지 않는 경우 스크롤 막대가 회색으로 표시 됩니다.|  
  
3. <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|설명|  
    |-----------|-----------------|  
    |`false`|컨트롤의 텍스트는 컨트롤의 너비에 맞게 자동으로 조정 되지 않으므로 줄 바꿈에 도달할 때까지 오른쪽으로 스크롤합니다. 위의 가로 스크롤 막대나 둘 다를 선택한 경우이 값을 사용 합니다.|  
    |`true`(기본)|컨트롤의 텍스트는 컨트롤의 너비에 맞게 자동으로 조정 됩니다. 가로 스크롤 막대는 표시 되지 않습니다. 위쪽의 세로 스크롤 막대 또는 없음을 선택 하 여 하나 이상의 단락을 표시 하는 경우이 값을 사용 합니다.|  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
