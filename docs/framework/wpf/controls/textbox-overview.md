---
title: TextBox 개요
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 9fbae5ac4de4c78a1086bcbd9bfc9e01eb597fb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186638"
---
# <a name="textbox-overview"></a>TextBox 개요
클래스를 <xref:System.Windows.Controls.TextBox> 사용하면 형식이 지정되지 않은 텍스트를 표시하거나 편집할 수 있습니다. 의 <xref:System.Windows.Controls.TextBox> 일반적인 용도는 형식이 지정되지 않은 텍스트를 양식으로 편집하는 것입니다. 예를 들어 사용자의 이름, 전화 번호 등을 묻는 양식은 <xref:System.Windows.Controls.TextBox> 텍스트 입력에 컨트롤을 사용합니다. 이 항목에서는 <xref:System.Windows.Controls.TextBox> 클래스를 소개하고 클래스와 C#모두에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용하는 방법에 대한 예제를 제공합니다.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>TextBox 또는 RichTextBox?  
 둘 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> 다 사용자가 텍스트를 입력할 수 있지만 두 컨트롤은 서로 다른 시나리오에 사용됩니다. A는 <xref:System.Windows.Controls.TextBox> 시스템 리소스가 <xref:System.Windows.Controls.RichTextBox> 적기 때문에 일반 텍스트만 편집해야 하는 경우(예: 양식의 사용) 이상적입니다. A는 <xref:System.Windows.Controls.RichTextBox> 사용자가 서식이 지정된 텍스트, 이미지, 테이블 또는 기타 지원되는 콘텐츠를 편집해야 하는 경우에 더 나은 선택입니다. 예를 들어 서식이 필요한 문서, 문서 또는 블로그를 편집하는 것이 가장 <xref:System.Windows.Controls.RichTextBox>좋습니다. 아래 표에는 <xref:System.Windows.Controls.TextBox> 의 <xref:System.Windows.Controls.TextBox>주요 기능이 요약되어 있습니다.  
  
|제어|실시간 맞춤법 검사|상황에 맞는 메뉴|(Ctr+B)와 같은 <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> 명령 서식 지정|<xref:System.Windows.Documents.FlowDocument>이미지, 단락, 표 등과 같은 콘텐츠.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|yes|yes|예|아니요.|  
|<xref:System.Windows.Controls.RichTextBox>|yes|yes|예([RichTextBox 개요](richtextbox-overview.md) 참조)|예([RichTextBox 개요](richtextbox-overview.md) 참조)|  
  
> [!NOTE]
> (Ctr +B)와 같은 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> 관련 편집 명령서식 지정을 지원하지 는 않지만 <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>많은 기본 명령은 와 같은 두 컨트롤에서 지원됩니다. 자세한 내용은 <xref:System.Windows.Documents.EditingCommands>을 참조하세요.  
  
 <xref:System.Windows.Controls.TextBox> 지원되는 기능은 아래 섹션에서 다룹니다. 자세한 <xref:System.Windows.Controls.RichTextBox>내용은 [리치텍스트박스 개요를](richtextbox-overview.md)참조하십시오.  
  
### <a name="real-time-spellchecking"></a>실시간 맞춤법 검사  
 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.RichTextBox>에서 실시간 맞춤법 검사를 활성화할 수 있습니다. 맞춤법 검사 기능이 켜져 있으면 맞춤법이 틀린 단어 밑에 빨간색 선이 나타납니다(아래 그림 참조).  
  
 ![맞춤법이&#45;체크 박스가 있는 텍스트 상자](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 맞춤법 검사를 사용하도록 설정하는 방법에 대한 자세한 내용은 [텍스트 편집 컨트롤에서 맞춤법 검사 사용](how-to-enable-spell-checking-in-a-text-editing-control.md)을 참조하세요.  
  
### <a name="context-menu"></a>상황에 맞는 메뉴  
 기본적으로 둘 <xref:System.Windows.Controls.TextBox> 다 <xref:System.Windows.Controls.RichTextBox> 사용자가 컨트롤 내에서 마우스 오른쪽 단추로 클릭할 때 나타나는 컨텍스트 메뉴가 있습니다. 상황에 맞는 메뉴를 통해 사용자는 항목을 잘라내거나, 복사하거나, 붙여넣을 수 있습니다(아래 그림 참조).  
  
 ![상황에 맞는 메뉴가 있는 TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 자체적인 사용자 지정 상황에 맞는 메뉴를 만들어 기본 동작을 재정의할 수 있습니다. 자세한 내용은 [TextBox에 사용자 지정 컨텍스트 메뉴 사용](how-to-use-a-custom-context-menu-with-a-textbox.md)을 참조하세요.  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>TextBox 만들기  
 A는 <xref:System.Windows.Controls.TextBox> 높이의 단일 선이거나 여러 선을 구성할 수 있습니다. 한 줄은 <xref:System.Windows.Controls.TextBox> 소량의 일반 텍스트(예: "이름", "전화 번호" 등)를 입력하는 데 가장 적합합니다. 다음 예제에서는 한 줄을 <xref:System.Windows.Controls.TextBox>만드는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 사용자가 여러 줄의 텍스트를 입력할 수 있는 를 <xref:System.Windows.Controls.TextBox> 만들 수도 있습니다. 예를 들어 양식에서 사용자의 약력 스케치를 요청하는 경우 여러 줄의 텍스트를 지원하는 을 <xref:System.Windows.Controls.TextBox> 사용할 수 있습니다. 다음 예제에서는 여러 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 줄의 <xref:System.Windows.Controls.TextBox> 텍스트를 수용하도록 자동으로 확장되는 컨트롤을 정의하는 데 사용하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 컨트롤의 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 가장자리에 `Wrap` 도달하면 텍스트가 새 줄로 바꿈하도록 특성을 설정하면 <xref:System.Windows.Controls.TextBox> 필요한 경우 새 줄에 대한 공간을 포함하도록 컨트롤이 자동으로 확장됩니다. <xref:System.Windows.Controls.TextBox>  
  
 특성을 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 설정하면 `true` RETURN 키를 누를 때 새 줄이 삽입되고 필요한 <xref:System.Windows.Controls.TextBox> 경우 새 줄에 대한 공간을 포함하도록 자동으로 확장됩니다.  
  
 특성은 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> <xref:System.Windows.Controls.TextBox>에 스크롤 막대를 추가하여 둘러싸는 <xref:System.Windows.Controls.TextBox> 프레임 또는 창의 <xref:System.Windows.Controls.TextBox> 크기를 초과하여 확장되는 경우 의 내용을 스크롤할 수 있습니다.  
  
 <xref:System.Windows.Controls.TextBox>사용과 관련된 다양한 작업에 대한 자세한 내용은 [를 참조하십시오.](textbox-how-to-topics.md)  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>콘텐츠가 변경되는 시점 감지  
 일반적으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트는 예상대로 <xref:System.Windows.Controls.TextBox> 텍스트가 <xref:System.Windows.Controls.RichTextBox> 변경될 <xref:System.Windows.UIElement.KeyDown> 때마다 감지하는 데 사용해야 합니다. 예제를 보려면 [TextBox에서 텍스트가 변경되는 시점 감지](how-to-detect-when-text-in-a-textbox-has-changed.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [방법 주제](textbox-how-to-topics.md)
- [RichTextBox 개요](richtextbox-overview.md)
