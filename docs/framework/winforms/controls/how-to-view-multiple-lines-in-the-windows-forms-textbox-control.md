---
title: TextBox 컨트롤에서 여러 줄 보기
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728281"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>방법: Windows Forms TextBox 컨트롤에 여러 줄 표시
기본적으로 Windows Forms <xref:System.Windows.Forms.TextBox> 컨트롤은 한 줄의 텍스트를 표시 하 고 스크롤 막대를 표시 하지 않습니다. 텍스트가 사용 가능한 공간 보다 길면 텍스트의 일부만 표시 됩니다. <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>및 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절 한 값으로 설정 하 여이 기본 동작을 변경할 수 있습니다.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>TextBox 컨트롤에서 캐리지 리턴을 표시 하려면  
  
- 여러 줄 <xref:System.Windows.Forms.TextBox>에서 캐리지 리턴을 표시 하려면 <xref:System.Environment.NewLine%2A> 속성을 사용 합니다.  
  
     이스케이프 문자 (\\)의 해석은 언어 마다 다릅니다. Visual Basic는 캐리지 리턴 및 줄 바꿈 문자 조합에 `Chr$(13) & Chr$(10)`를 사용 합니다.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>TextBox 컨트롤에서 여러 줄을 보려면  
  
1. <xref:System.Windows.Forms.TextBox.Multiline%2A> 속성을 `true`로 설정합니다. <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `true` (기본값) 이면 컨트롤의 텍스트가 하나 이상의 단락으로 표시 됩니다. 그렇지 않으면 목록으로 표시 되며,이는 일부 줄이 컨트롤의 가장자리에서 잘릴 수 있습니다.  
  
2. <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|Description|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|텍스트가 거의 항상 컨트롤에 맞는 단락이 면이 값을 사용 합니다. 텍스트가 너무 길어서 한 번에 표시할 수 없는 경우 사용자는 마우스 포인터를 사용 하 여 컨트롤 내에서 이동할 수 있습니다.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|줄 목록을 표시 하려는 경우이 값을 사용 합니다 .이 중 일부는 <xref:System.Windows.Forms.TextBox> 컨트롤의 너비 보다 길 수 있습니다.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|목록이 컨트롤의 높이 보다 길면이 값을 사용 합니다.|  
  
3. <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 속성을 적절한 값으로 설정합니다.  
  
    |값|Description|  
    |-----------|-----------------|  
    |`false`|컨트롤의 텍스트는 자동으로 래핑되지 않으므로 줄 바꿈에 도달할 때까지 오른쪽으로 스크롤합니다. 위의 스크롤 막대나 <xref:System.Windows.Forms.ScrollBars.Both><xref:System.Windows.Forms.ScrollBars.Horizontal> 선택한 경우이 값을 사용 합니다.|  
    |`true`(기본값)|가로 스크롤 막대는 표시 되지 않습니다. 위의 스크롤 막대나 <xref:System.Windows.Forms.ScrollBars.None>를 <xref:System.Windows.Forms.ScrollBars.Vertical> 하 여 하나 이상의 단락을 표시 하는 경우이 값을 사용 합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.TextBox>
- [TextBox 컨트롤 개요](textbox-control-overview-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 삽입 지점 제어](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [방법: Windows Forms TextBox 컨트롤을 사용하여 암호 텍스트 상자 만들기](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [방법: 읽기 전용 텍스트 상자 만들기](how-to-create-a-read-only-text-box-windows-forms.md)
- [방법: 문자열에 인용 부호 넣기](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [방법: Windows Forms TextBox 컨트롤에서 텍스트 선택](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
