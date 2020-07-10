---
title: TextBox 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 86b2cf8cb0c72186fd92bdad0af6bf5bd3fa9f3f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174434"
---
# <a name="textbox-overview"></a>TextBox 개요
<xref:System.Windows.Controls.TextBox>클래스를 사용 하면 서식 없는 텍스트를 표시 하거나 편집할 수 있습니다. 는 일반적으로 <xref:System.Windows.Controls.TextBox> 양식에서 서식 없는 텍스트를 편집 하는 데 사용 됩니다. 예를 들어 사용자의 이름, 전화 번호 등을 묻는 양식은 <xref:System.Windows.Controls.TextBox> 텍스트 입력에 컨트롤을 사용 합니다. 이 항목에서는 클래스를 소개 하 <xref:System.Windows.Controls.TextBox> 고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 c #에서이를 사용 하는 방법에 대 한 예제를 제공 합니다.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>TextBox 또는 RichTextBox?  
 및 둘 다 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> 사용자가 텍스트를 입력할 수 있지만 두 개의 컨트롤이 여러 시나리오에 사용 됩니다. 에는 <xref:System.Windows.Controls.TextBox> 작은 시스템 리소스가 필요 합니다. <xref:System.Windows.Controls.RichTextBox> 따라서 일반 텍스트만 편집 해야 하는 경우 (예: 폼에서 사용)에 이상적입니다. 는 <xref:System.Windows.Controls.RichTextBox> 사용자가 서식 있는 텍스트, 이미지, 테이블 또는 지원 되는 기타 콘텐츠를 편집 해야 하는 경우에 더 적합 합니다. 예를 들어 형식 지정, 이미지 등이 필요한 문서, 문서 또는 블로그를 편집 하려면를 사용 하는 것이 가장 좋습니다 <xref:System.Windows.Controls.RichTextBox> . 아래 표에는 및의 기본 기능이 요약 <xref:System.Windows.Controls.TextBox> 되어 <xref:System.Windows.Controls.RichTextBox> 있습니다.  
  
|컨트롤|실시간 맞춤법 검사|상황에 맞는 메뉴|명령 서식 지정 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)|<xref:System.Windows.Documents.FlowDocument>이미지, 단락, 테이블 등의 콘텐츠|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|예|예|아니요|아니요.|  
|<xref:System.Windows.Controls.RichTextBox>|예|예|예([RichTextBox 개요](richtextbox-overview.md) 참조)|예([RichTextBox 개요](richtextbox-overview.md) 참조)|  
  
> [!NOTE]
> <xref:System.Windows.Controls.TextBox>는 (Ctr + B)와 같은 관련 편집 명령에 대 한 서식 지정을 지원 하지 않지만 등의 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> 여러 가지 기본 명령이 지원 됩니다 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> . 자세한 내용은 <xref:System.Windows.Documents.EditingCommands> 를 참조하세요.  
  
 에서 지 원하는 기능은 <xref:System.Windows.Controls.TextBox> 아래 섹션에 설명 되어 있습니다. 에 대 한 자세한 내용은 <xref:System.Windows.Controls.RichTextBox> [RichTextBox 개요](richtextbox-overview.md)를 참조 하세요.  
  
### <a name="real-time-spellchecking"></a>실시간 맞춤법 검사  
 또는에서 실시간 맞춤법 검사를 사용 하도록 설정할 수 있습니다 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> . 맞춤법 검사 기능이 켜져 있으면 맞춤법이 틀린 단어 밑에 빨간색 선이 나타납니다(아래 그림 참조).  
  
 ![맞춤법&#45;검사를 사용 하는 텍스트 상자](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 맞춤법 검사를 사용하도록 설정하는 방법에 대한 자세한 내용은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하세요.  
  
### <a name="context-menu"></a>상황에 맞는 메뉴  
 기본적으로 및에 <xref:System.Windows.Controls.TextBox> 는 <xref:System.Windows.Controls.RichTextBox> 사용자가 컨트롤 내에서 마우스 오른쪽 단추를 클릭할 때 표시 되는 상황에 맞는 메뉴가 있습니다. 상황에 맞는 메뉴를 통해 사용자는 항목을 잘라내거나, 복사하거나, 붙여넣을 수 있습니다(아래 그림 참조).  
  
 ![상황에 맞는 메뉴가 있는 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 자체적인 사용자 지정 상황에 맞는 메뉴를 만들어 기본 동작을 재정의할 수 있습니다. 자세한 내용은 [TextBox에 사용자 지정 컨텍스트 메뉴 사용](how-to-use-a-custom-context-menu-with-a-textbox.md)을 참조하세요.  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>TextBox 만들기  
 는 한 <xref:System.Windows.Controls.TextBox> 줄 높이로 또는 여러 줄로 구성 될 수 있습니다. 한 줄은 <xref:System.Windows.Controls.TextBox> 작은 양의 일반 텍스트 (예: "이름", "전화 번호" 등)를 입력 하는 데 가장 적합 합니다. 다음 예제에서는 한 줄을 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 <xref:System.Windows.Controls.TextBox>사용자가 여러 줄의 텍스트를 입력할 수 있도록 하는을 만들 수도 있습니다. 예를 들어 사용자의 biographical 스케치를 요청 하는 폼의 경우 <xref:System.Windows.Controls.TextBox> 여러 줄의 텍스트를 지 원하는를 사용할 수 있습니다. 다음 예제에서는를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> 여러 줄의 텍스트에 맞게 자동으로 확장 되는 컨트롤을 정의 하는 방법을 보여 줍니다.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 특성을 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 로 설정 하면 `Wrap` 컨트롤의 가장자리에 도달할 때 텍스트가 새 줄로 줄 바꿈됩니다 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> . 필요한 경우 새 줄의 공간을 포함 하도록 컨트롤을 자동으로 확장 합니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>특성을로 설정 하면 `true` 반환 키를 누를 때 새 줄이 삽입 되 고, <xref:System.Windows.Controls.TextBox> 필요한 경우 새 줄의 공간을 포함 하도록 자동으로를 확장 합니다.  
  
 특성은에 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 스크롤 막대를 추가 하 여가 해당 콘텐츠를 포함 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox> 하는 프레임 또는 창의 크기 보다 크게 확장 될 때까지 스크롤할 수 있도록 합니다.  
  
 사용과 관련 된 다양 한 작업에 대 한 자세한 내용은 <xref:System.Windows.Controls.TextBox> [방법 항목](textbox-how-to-topics.md)을 참조 하세요.  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>콘텐츠가 변경되는 시점 감지  
 일반적으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이 이벤트는 또는에서 텍스트가 변경 될 때마다 검색 하는 데 사용할 수 있습니다 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.UIElement.KeyDown> . 예제를 보려면 [TextBox에서 텍스트가 변경되는 시점 감지](how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [방법 도움말 항목](textbox-how-to-topics.md)
- [RichTextBox 개요](richtextbox-overview.md)
