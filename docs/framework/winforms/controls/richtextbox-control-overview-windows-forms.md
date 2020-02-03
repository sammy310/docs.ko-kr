---
title: RichTextBox 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742399"
---
# <a name="richtextbox-control-overview-windows-forms"></a>RichTextBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 서식을 사용 하 여 텍스트를 표시, 입력 및 조작 하는 데 사용 됩니다. <xref:System.Windows.Forms.RichTextBox> 컨트롤은 <xref:System.Windows.Forms.TextBox> 컨트롤에서 수행 하는 모든 작업을 수행 하지만 글꼴, 색 및 링크를 표시할 수도 있습니다. 파일에서 텍스트 및 포함 된 이미지 로드 지정 된 문자를 찾습니다. <xref:System.Windows.Forms.RichTextBox> 컨트롤은 일반적으로 텍스트 조작을 제공 하 고 Microsoft Word와 같은 워드 프로세싱 응용 프로그램과 비슷한 기능을 표시 하는 데 사용 됩니다. <xref:System.Windows.Forms.TextBox> 컨트롤과 마찬가지로 <xref:System.Windows.Forms.RichTextBox> 컨트롤은 스크롤 막대를 표시할 수 있습니다. 그러나 <xref:System.Windows.Forms.TextBox> 컨트롤과 달리 기본 설정은 필요에 따라 가로 및 세로 스크롤 막대를 모두 표시 하 고 추가 스크롤 막대 설정을 포함 합니다.  
  
## <a name="working-with-the-richtextbox-control"></a>RichTextBox 컨트롤 작업  
 <xref:System.Windows.Forms.TextBox> 컨트롤과 마찬가지로 표시 되는 텍스트는 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성으로 설정 됩니다. <xref:System.Windows.Forms.RichTextBox> 컨트롤에는 텍스트 서식을 지정 하는 다양 한 속성이 있습니다. 이러한 속성에 대한 자세한 내용은 [방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) 및 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)을 참조하세요. 파일을 조작 하기 위해 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 및 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드는 일반 텍스트, 유니코드 일반 텍스트 및 RTF (서식 있는 텍스트)를 비롯 한 여러 파일 형식을 표시 하 고 쓸 수 있습니다. 가능한 파일 형식은 <xref:System.Windows.Forms.RichTextBoxStreamType>나열 되어 있습니다. <xref:System.Windows.Forms.RichTextBox.Find%2A> 메서드를 사용 하 여 텍스트 문자열 또는 특정 문자를 찾을 수 있습니다.  
  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성을 `true` 하 고 코드를 작성 하 여 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트를 처리할 수 있도록 설정 하 여 웹 스타일 링크에 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용할 수도 있습니다. 자세한 내용은 [방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)를 참조하세요. <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> 속성을 `true`로 설정 하 여 사용자가 컨트롤에 있는 텍스트의 일부 또는 전부를 조작 하지 못하게 할 수 있습니다.  
  
 <xref:System.Windows.Forms.TextBoxBase.Undo%2A> 및 <xref:System.Windows.Forms.RichTextBox.Redo%2A> 메서드를 호출 하 여 <xref:System.Windows.Forms.RichTextBox> 컨트롤에서 대부분의 편집 작업을 실행 취소 하 고 다시 실행할 수 있습니다. <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> 메서드를 사용 하면 사용자가 취소 한 마지막 작업을 컨트롤에 다시 적용할 수 있는지 여부를 확인할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [TextBox 컨트롤 개요](textbox-control-overview-windows-forms.md)
