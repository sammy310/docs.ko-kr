---
title: 콘텐츠 모델
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187400"
---
# <a name="wpf-content-model"></a>WPF 콘텐츠 모델
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 다양한 형식의 콘텐츠를 표시하는 것을 기본 용도로 하는 많은 컨트롤 형식 및 컨트롤과 유사한 형식을 제공하는 프레젠테이션 플랫폼입니다. 사용할 컨트롤이나 파생시킬 컨트롤을 결정하려면 특정 컨트롤이 가장 잘 표시할 수 있는 개체 유형을 이해해야 합니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 형식 및 컨트롤과 비슷한 형식에 대한 콘텐츠 모델을 요약하여 보여 줍니다. 콘텐츠 모델은 컨트롤에 사용될 수 있는 컨트롤에 대해 설명합니다. 또한 이 항목에서는 각 컨트롤 모델에 대한 콘텐츠 속성을 보여 줍니다. 콘텐츠 속성은 개체의 콘텐츠를 저장하는 데 사용되는 속성입니다.  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a>임의의 콘텐츠가 들어 있는 클래스  
 일부 컨트롤에는 문자열, <xref:System.DateTime> 개체 또는 추가 항목에 대한 컨테이너인 <xref:System.Windows.UIElement> a와 같은 모든 형식의 개체가 포함될 수 있습니다. 예를 들어, <xref:System.Windows.Controls.Button> a는 이미지와 일부 텍스트를 포함할 수 있습니다. 또는 <xref:System.Windows.Controls.CheckBox> 의 값을 포함할 수 <xref:System.DateTime.Now%2A?displayProperty=nameWithType>있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 임의의 콘텐츠가 들어 있는 네 개의 클래스가 있습니다. 다음 표에는 에서 상속되는 <xref:System.Windows.Controls.Control>클래스가 나열됩니다.  
  
|임의의 콘텐츠가 들어 있는 클래스|콘텐츠|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|임의의 단일 개체입니다.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|헤더 및 단일 항목이며 둘 모두 임의의 개체입니다.|  
|<xref:System.Windows.Controls.ItemsControl>|임의 개체의 컬렉션입니다.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|헤더와 항목 컬렉션이며 모두 임의의 개체입니다.|  
  
 이러한 클래스에서 상속하는 컨트롤은 동일한 형식의 콘텐츠를 포함하며 콘텐츠를 동일한 방식으로 처리할 수 있습니다. 다음 그림에서는 이미지와 일부 텍스트를 포함하는 각 콘텐츠 모델의 컨트롤 을 보여 주며 있습니다.  
  
 ![각 콘텐츠 모델에서 하나씩 네 가지 컨트롤을 보여 주는 스크린샷입니다.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>임의의 단일 개체가 들어 있는 컨트롤  
 클래스에는 <xref:System.Windows.Controls.ContentControl> 임의의 콘텐츠의 단일 조각이 포함되어 있습니다. 해당 콘텐츠 속성은 <xref:System.Windows.Controls.ContentControl.Content%2A>합니다. 다음 컨트롤은 <xref:System.Windows.Controls.ContentControl> 해당 콘텐츠 모델에서 상속및 사용합니다.  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 다음 그림에서는 문자열, <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.DateTime> 개체, <xref:System.Windows.Shapes.Rectangle>A 및 <xref:System.Windows.Controls.Panel> a를 포함하는 문자열로 설정된 <xref:System.Windows.Shapes.Ellipse> 네 <xref:System.Windows.Controls.TextBlock>개의 단추를 보여 주며 다음과 같은 단추를 보여 줄 수 있습니다.  
  
 ![콘텐츠 유형이 다른 네 개의 단추를 보여 주는 스크린샷입니다.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 설정하는 방법에 대한 예는 <xref:System.Windows.Controls.ContentControl>을 참조하십시오.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>헤더와 임의의 단일 개체가 들어 있는 컨트롤  
 클래스에서 <xref:System.Windows.Controls.HeaderedContentControl> 상속 <xref:System.Windows.Controls.ContentControl> 하 고 헤더와 콘텐츠를 표시 합니다. 에서 에서 콘텐츠 속성을 <xref:System.Windows.Controls.ContentControl.Content%2A>상속 <xref:System.Windows.Controls.ContentControl> 하 고 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 형식의 <xref:System.Object>속성을 정의 합니다. 따라서 둘 다 임의의 개체일 수 있습니다.  
  
 다음 컨트롤은 <xref:System.Windows.Controls.HeaderedContentControl> 해당 콘텐츠 모델에서 상속및 사용합니다.  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 다음 그림에서는 <xref:System.Windows.Controls.TabItem> 두 개체를 보여 주십습니다. 첫 <xref:System.Windows.Controls.TabItem> 번째 <xref:System.Windows.UIElement> 개체에는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 와 <xref:System.Windows.Controls.ContentControl.Content%2A>가. 과 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 를 포함하는 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Shapes.Ellipse> 로 <xref:System.Windows.Controls.TextBlock>설정됩니다. 과 <xref:System.Windows.Controls.ContentControl.Content%2A> 를 포함하는 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> 로 <xref:System.Windows.Controls.Label>설정됩니다. 두 <xref:System.Windows.Controls.TabItem> 번째 문자열은 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 에 <xref:System.Windows.Controls.TextBlock> 문자열과 <xref:System.Windows.Controls.ContentControl.Content%2A>에 있는 문자열이 있습니다.  
  
 ![헤더 속성에서 다른 형식을 사용하는 TabControl입니다.](./media/wpf-content-model/control-content-model-tab.png)  
  
 개체를 만드는 <xref:System.Windows.Controls.TabItem> 방법의 예는 <xref:System.Windows.Controls.HeaderedContentControl>을 참조하십시오.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>임의 개체의 컬렉션을 포함하는 컨트롤  
 클래스는 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.Control> 문자열, 개체 또는 기타 요소와 같은 여러 항목을 상속하고 포함할 수 있습니다. 해당 콘텐츠 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은 및 <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>은 일반적으로 데이터 <xref:System.Windows.Controls.ItemsControl> 컬렉션으로 채우는 데 사용됩니다. 컬렉션을 사용하여 <xref:System.Windows.Controls.ItemsControl>을 채우기 위해 사용하지 않으려면 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성을 사용하여 항목을 추가할 수 있습니다.  
  
 다음 컨트롤은 <xref:System.Windows.Controls.ItemsControl> 해당 콘텐츠 모델에서 상속및 사용합니다.  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 다음 그림에서는 <xref:System.Windows.Controls.ListBox> 이러한 유형의 항목이 포함된 a를 보여 주며 다음과 같은 유형의 항목을 보여 주며 있습니다.  
  
- 문자열입니다.  
  
- <xref:System.DateTime> 개체입니다.  
  
- <xref:System.Windows.UIElement>입니다.  
  
- <xref:System.Windows.Shapes.Ellipse> A와 <xref:System.Windows.Controls.TextBlock>를 포함하는 . <xref:System.Windows.Controls.Panel>  
  
 ![네 가지 유형의 콘텐츠가 있는 ListBox를 보여 주는 스크린샷입니다.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>헤더와 임의 개체의 컬렉션을 포함하는 컨트롤  
 클래스는 <xref:System.Windows.Controls.HeaderedItemsControl> 문자열, <xref:System.Windows.Controls.ItemsControl> 개체 또는 기타 요소 및 헤더와 같은 여러 항목을 상속하고 포함할 수 있습니다. <xref:System.Windows.Controls.ItemsControl> 콘텐츠 속성을 상속 하 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>고 <xref:System.Windows.Controls.ItemsControl.Items%2A>및 임의의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 개체일 수 있는 속성을 정의 합니다.  
  
 다음 컨트롤은 <xref:System.Windows.Controls.HeaderedItemsControl> 해당 콘텐츠 모델에서 상속및 사용합니다.  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>UIElement 개체 컬렉션을 포함하는 클래스  
 클래스는 <xref:System.Windows.Controls.Panel> 자식 <xref:System.Windows.UIElement> 개체의 위치와 정렬을 배치합니다. 해당 콘텐츠 속성은 <xref:System.Windows.Controls.Panel.Children%2A>합니다.  
  
 다음 클래스는 <xref:System.Windows.Controls.Panel> 클래스에서 상속되며 해당 콘텐츠 모델을 사용합니다.  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 자세한 내용은 [패널 개요](panels-overview.md)를 참조하세요.  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>UIElement의 모양에 영향을 주는 클래스  
 이 <xref:System.Windows.Controls.Decorator> 클래스는 단일 자식 <xref:System.Windows.UIElement>에 또는 그 주변에 시각 효과를 적용합니다. 해당 콘텐츠 속성은 <xref:System.Windows.Controls.Decorator.Child%2A>합니다. 다음 클래스는 <xref:System.Windows.Controls.Decorator> 해당 콘텐츠 모델을 상속하고 사용합니다.  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 다음 그림은 주변에 <xref:System.Windows.Controls.TextBox> (장식된) a를 <xref:System.Windows.Controls.Border> 보여 주어 있습니다.  
  
 ![검은색 테두리가 있는 TextBox](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
테두리가 있는 TextBlock  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>UIElement에 대한 시각적 피드백을 제공하는 클래스  
 클래스는 <xref:System.Windows.Documents.Adorner> 사용자에게 시각적 신호를 제공합니다. 예를 들어 를 <xref:System.Windows.Documents.Adorner> 사용하여 요소에 기능 핸들을 추가하거나 컨트롤에 대한 상태 정보를 제공합니다. 클래스는 <xref:System.Windows.Documents.Adorner> 사용자 고유의 표시기를 만들 수 있도록 프레임 워크를 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 구현된 표시기를 제공하지 않습니다. 자세한 내용은 [표시기 개요](adorners-overview.md)를 참조하세요.  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a>사용자가 텍스트를 입력할 수 있는 클래스  
 WPF는 사용자가 텍스트를 입력할 수 있는 세 개의 기본 컨트롤을 제공합니다. 각 컨트롤에는 텍스트가 다르게 표시됩니다. 다음 표에서는 이 세 가지 텍스트 관련 컨트롤과 텍스트를 표시할 때의 기능 및 컨트롤 텍스트를 포함하는 속성을 보여 줍니다.  
  
|제어|텍스트 표시|콘텐츠 속성|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|일반 텍스트|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|서식 있는 텍스트|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|숨겨진 텍스트(문자가 마스킹됨)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a>텍스트를 표시하는 클래스  
 여러 클래스를 사용하여 일반 텍스트나 서식이 지정된 텍스트를 표시할 수 있습니다. 소량의 <xref:System.Windows.Controls.TextBlock> 텍스트를 표시하는 데 사용할 수 있습니다. 많은 양의 텍스트를 표시하려면 에서 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>또는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 컨트롤을 사용합니다.  
  
 의 <xref:System.Windows.Controls.TextBlock> 두 가지 <xref:System.Windows.Controls.TextBlock.Text%2A> 콘텐츠 <xref:System.Windows.Controls.TextBlock.Inlines%2A>속성이 있습니다. 일관된 서식을 사용하는 텍스트를 표시하려는 <xref:System.Windows.Controls.TextBlock.Text%2A> 경우 속성이 가장 적합한 경우가 많습니다. 텍스트 전체에서 다른 서식을 사용하려는 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 경우 속성을 사용합니다. 속성은 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 텍스트의 <xref:System.Windows.Documents.Inline> 서식을 지정하는 개체의 컬렉션입니다.  
  
 다음 표에는 에 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>대한 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 클래스에 대한 콘텐츠 속성이 나열됩니다.  
  
|제어|콘텐츠 속성|콘텐츠 속성 형식|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|문서|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|문서|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|문서|<xref:System.Windows.Documents.FlowDocument>|  
  
 인터페이스를 <xref:System.Windows.Documents.FlowDocument> 구현합니다. <xref:System.Windows.Documents.IDocumentPaginatorSource> 따라서 세 클래스 모두 <xref:System.Windows.Documents.FlowDocument> 콘텐츠로 사용할 수 있습니다.  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a>텍스트 서식을 지정하는 클래스  
 <xref:System.Windows.Documents.TextElement>및 관련 클래스를 사용하면 텍스트의 서식을 지정할 수 있습니다. <xref:System.Windows.Documents.TextElement>는 개체에 <xref:System.Windows.Controls.TextBlock> 텍스트와 <xref:System.Windows.Documents.FlowDocument> 개체의 서식을 포함하고 서식을 지정합니다. 개체의 <xref:System.Windows.Documents.TextElement> 두 가지 <xref:System.Windows.Documents.Block> 기본 <xref:System.Windows.Documents.Inline> 유형은 요소와 요소입니다. 요소는 <xref:System.Windows.Documents.Block> 단락 이나 목록 등 텍스트의 블록을 나타냅니다. 요소는 <xref:System.Windows.Documents.Inline> 블록의 텍스트 일부를 나타냅니다. 많은 <xref:System.Windows.Documents.Inline> 클래스에서 적용되는 텍스트에 대한 서식을 지정합니다. 각각에는 <xref:System.Windows.Documents.TextElement> 고유한 콘텐츠 모델이 있습니다. 자세한 내용은 [TextElement 콘텐츠 모델 개요](../advanced/textelement-content-model-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [고급](../advanced/index.md)
