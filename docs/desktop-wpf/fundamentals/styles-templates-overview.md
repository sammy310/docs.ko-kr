---
title: 스타일 및 템플릿
description: .NET 코어에 대한 Windows 프레젠테이션 파운데이션(WPF)의 XAML 리소스에 대해 알아봅니다. 스타일 및 테마와 관련된 XAML 리소스의 유형을 이해합니다.
author: thraka
ms.author: adegeo
ms.date: 09/09/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: f845e739ec3cae502d1e4fd6631f987c5364a42e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433099"
---
# <a name="styles-and-templates-in-wpf"></a>WPF의 스타일 및 템플릿

WPF(Windows 프레젠테이션 파운데이션) 스타일 및 템플릿은 개발자와 디자이너가 시각적으로 매력적인 효과와 제품에 대한 일관된 모양을 만들 수 있는 기능 모음을 참조합니다. 앱의 모양을 사용자 지정할 때 앱 내부 및 앱 간에 모양을 유지 관리하고 공유할 수 있는 강력한 스타일 지정 및 템플릿 모델을 원합니다. WPF는 해당 모델을 제공합니다.

WPF 스타일링 모델의 또 다른 특징은 프레젠테이션과 논리의 분리입니다. 디자이너는 개발자가 C# 또는 Visual Basic을 사용하여 프로그래밍 논리에서 작업하는 동시에 XAML만 사용하여 앱의 모양을 작업할 수 있습니다.

이 개요는 앱의 스타일 지정 및 템플릿 측면에 중점을 두고 데이터 바인딩 개념에 대해 설명하지 않습니다. 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.

스타일과 템플릿을 다시 사용할 수 있는 리소스를 이해하는 것이 중요합니다. 리소스에 대한 자세한 내용은 [XAML 리소스](xaml-resources-define.md)를 참조하세요.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sample"></a>예제

이 개요에 제공된 샘플 코드는 다음 그림에 표시된 [간단한 사진 브라우징 응용 프로그램을](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) 기반으로 합니다.

![스타일 지정된 ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

이 간단한 사진 샘플에서는 스타일 지정 및 템플릿을 사용하여 시각적으로 눈에 띄는 사용자 환경을 만듭니다. 샘플에는 이미지 <xref:System.Windows.Controls.TextBlock> 목록에 <xref:System.Windows.Controls.ListBox> 바인딩된 두 가지 요소와 컨트롤이 있습니다.

전체 샘플을 보려면 [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(스타일 지정 및 템플릿 샘플 소개)을 참조하세요.

## <a name="styles"></a>스타일

속성 <xref:System.Windows.Style> 값 집합을 여러 요소에 적용하는 편리한 방법으로 생각할 수 있습니다. <xref:System.Windows.FrameworkElement> 에서 파생되었거나 <xref:System.Windows.FrameworkContentElement> <xref:System.Windows.Window> <xref:System.Windows.Controls.Button>또는 a와 같은 모든 요소에서 스타일을 사용할 수 있습니다.

스타일을 선언하는 가장 일반적인 방법은 XAML `Resources` 파일의 섹션에 있는 리소스입니다. 스타일은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 준수합니다. 간단히 말해서 스타일을 선언하는 위치가 스타일을 적용할 수 있는 위치에 영향을 줍니다. 예를 들어 앱 정의 XAML 파일의 루트 요소에서 스타일을 선언하는 경우 앱의 어느 곳에서나 스타일을 사용할 수 있습니다.

예를 들어 다음 XAML 코드는 모든 `TextBlock` `TextBlock` 요소에 자동으로 적용되는 스타일과 명시적으로 참조해야 하는 스타일에 대해 두 가지 스타일을 선언합니다.

[!code-xaml[SnippetDefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

다음은 위에서 사용 중인 스타일의 예입니다.

[!code-xaml[SnippetTextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

![스타일이 있는 텍스트 블록](./media/styles-and-templates-overview/stylingintro-textblocks.png)

자세한 내용은 [컨트롤에 대한 스타일 만들기를](styles-templates-create-apply-style.md)참조하십시오.

## <a name="controltemplates"></a>ControlTemplates

WPF에서 <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 컨트롤은 컨트롤의 모양을 정의합니다. 새 <xref:System.Windows.Controls.ControlTemplate> 컨트롤을 정의하고 컨트롤에 할당하여 컨트롤의 구조와 모양을 변경할 수 있습니다. 대부분의 경우 템플릿은 사용자 지정 컨트롤을 작성할 필요가 없도록 충분한 유연성을 제공합니다.

각 컨트롤에는 [Control.Template](xref:System.Windows.Controls.Control.Template) 속성에 할당된 기본 템플릿이 있습니다. 템플릿은 컨트롤의 시각적 표시를 컨트롤의 기능과 연결합니다. XAML에서 템플릿을 정의하기 때문에 코드를 작성하지 않고 컨트롤의 모양을 변경할 수 있습니다. 각 템플릿은 <xref:System.Windows.Controls.Button>에서와 같은 특정 컨트롤을 위해 설계되었습니다.

일반적으로 XAML 파일의 섹션에서 `Resources` 템플릿을 리소스로 선언합니다. 모든 리소스와 마찬가지로 범위 지정 규칙이 적용됩니다.

컨트롤 템플릿은 스타일보다 훨씬 더 관련이 있습니다. 이는 컨트롤 템플릿이 전체 컨트롤의 시각적 모양을 다시 작성하는 반면 스타일은 기존 컨트롤에 속성 변경 내용을 적용하기 때문입니다. 그러나 [Control.Template](xref:System.Windows.Controls.Control.Template) 속성을 설정하여 컨트롤의 템플릿을 적용하므로 스타일을 사용하여 템플릿을 정의하거나 설정할 수 있습니다.

디자이너는 일반적으로 기존 템플릿의 복사본을 만들고 수정할 수 있습니다. 예를 들어 Visual Studio WPF 디자이너에서 `CheckBox` 컨트롤을 선택한 다음 마우스 오른쪽 단추를 클릭하고 **템플릿** > **Create a copy**만들기를 선택합니다. 이 명령은 *템플릿을 정의하는 스타일을 생성합니다.*

```xaml
<Style x:Key="CheckBoxStyle1" TargetType="{x:Type CheckBox}">
    <Setter Property="FocusVisualStyle" Value="{StaticResource FocusVisual1}"/>
    <Setter Property="Background" Value="{StaticResource OptionMark.Static.Background1}"/>
    <Setter Property="BorderBrush" Value="{StaticResource OptionMark.Static.Border1}"/>
    <Setter Property="Foreground" Value="{DynamicResource {x:Static SystemColors.ControlTextBrushKey}}"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type CheckBox}">
                <Grid x:Name="templateRoot" Background="Transparent" SnapsToDevicePixels="True">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto"/>
                        <ColumnDefinition Width="*"/>
                    </Grid.ColumnDefinitions>
                    <Border x:Name="checkBoxBorder" Background="{TemplateBinding Background}" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="1" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
                        <Grid x:Name="markGrid">
                            <Path x:Name="optionMark" Data="F1 M 9.97498,1.22334L 4.6983,9.09834L 4.52164,9.09834L 0,5.19331L 1.27664,3.52165L 4.255,6.08833L 8.33331,1.52588e-005L 9.97498,1.22334 Z " Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="1" Opacity="0" Stretch="None"/>
                            <Rectangle x:Name="indeterminateMark" Fill="{StaticResource OptionMark.Static.Glyph1}" Margin="2" Opacity="0"/>
                        </Grid>
                    </Border>
                    <ContentPresenter x:Name="contentPresenter" Grid.Column="1" Focusable="False" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}"/>
                </Grid>
                <ControlTemplate.Triggers>
                    <Trigger Property="HasContent" Value="true">
                        <Setter Property="FocusVisualStyle" Value="{StaticResource OptionMarkFocusVisual1}"/>
                        <Setter Property="Padding" Value="4,-1,0,0"/>

... content removed to save space ...
```

템플릿의 복사본을 편집하면 템플릿의 작동 방식을 알아볼 수 있습니다. 새 빈 템플릿을 만드는 대신 복사본을 편집하고 시각적 프레젠테이션의 몇 가지 측면을 변경하는 것이 더 쉽습니다.

예를 들어 [컨트롤에 대한 템플릿 만들기를](../themes/how-to-create-apply-template.md)참조하십시오.

### <a name="templatebinding"></a>TemplateBinding

이전 섹션에 정의된 템플릿 리소스에서 [TemplateBinding 태그 확장](../../framework/wpf/advanced/templatebinding-markup-extension.md)을 사용하는 것으로 나타났습니다. A는 `TemplateBinding` 템플릿 시나리오에 대해 최적화된 바인딩 양식으로, `{Binding RelativeSource={RelativeSource TemplatedParent}}`로 구성된 바인딩과 유사합니다. `TemplateBinding`는 템플릿의 일부를 컨트롤의 속성에 바인딩하는 데 유용합니다. 예를 들어 각 컨트롤에는 속성이 있습니다. <xref:System.Windows.Controls.Control.BorderThickness> 을 `TemplateBinding` 사용하여 이 컨트롤 설정의 영향을 받는 템플릿의 요소를 관리합니다.

### <a name="contentcontrol-and-itemscontrol"></a>콘텐츠 제어 및 항목 제어

에서 <xref:System.Windows.Controls.ContentPresenter> a가 선언되면 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ContentControl>및 <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 자동으로 바인딩됩니다. <xref:System.Windows.Controls.ItemsPresenter> 마찬가지로, 의에있는 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ItemsControl> 것은 자동으로 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 및 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성에 바인딩됩니다.

## <a name="datatemplates"></a>데이터 템플릿

이 샘플 앱에는 사진 <xref:System.Windows.Controls.ListBox> 목록에 바인딩된 컨트롤이 있습니다.

[!code-xaml[ListBox](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window3.xaml#SnippetListBox)]

이것은 <xref:System.Windows.Controls.ListBox> 현재 다음과 같습니다.

![템플릿 적용 전의 ListBox](./media/styles-and-templates-overview/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")

대부분 컨트롤에는 몇 가지 콘텐츠 형식이 있고 해당 콘텐츠는 보통 바인딩할 데이터에서 나옵니다. 이 샘플에서 데이터는 사진 목록입니다. WPF에서 는 를 <xref:System.Windows.DataTemplate> 사용하여 데이터의 시각적 표현을 정의합니다. 기본적으로 렌더링된 앱에서 <xref:System.Windows.DataTemplate> 데이터가 어떻게 보이는지 결정합니다.

샘플 앱에서 각 `Photo` 사용자 지정 `Source` 개체에는 이미지의 파일 경로를 지정하는 형식 문자열의 속성이 있습니다. 현재 사진 개체는 파일 경로로 표시됩니다.

[!code-csharp[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Photo.cs#PhotoClass)]
[!code-vb[PhotoClass](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/Photo.vb#PhotoClass)]

사진이 이미지로 표시되려면 를 <xref:System.Windows.DataTemplate> 리소스로 만듭니다.

[!code-xaml[DataTemplate](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window4.xaml#SnippetDataTemplate)]

속성은 <xref:System.Windows.DataTemplate.DataType%2A> 의 속성과 <xref:System.Windows.Style.TargetType%2A> 유사합니다. <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> 리소스 섹션에 있는 경우 속성 형식을 <xref:System.Windows.DataTemplate.DataType%2A> 지정 하 고 `x:Key`을 생략 할 때 해당 <xref:System.Windows.DataTemplate> 형식이 나타날 때마다 적용됩니다. 항상 <xref:System.Windows.DataTemplate> 을 `x:Key` 할당한 다음 `StaticResource` <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성이나 속성과 같은 형식을 취하는 속성에 대해 로 설정할 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 수 있습니다.

기본적으로 위의 <xref:System.Windows.DataTemplate> 예제에서는 `Photo` 개체가 있을 때마다 <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Border>에 있는 것으로 표시되어야 한다고 정의합니다. 이것으로, <xref:System.Windows.DataTemplate>우리의 응용 프로그램은 이제 다음과 같습니다.

![사진 이미지](./media/styles-and-templates-overview/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")

데이터 템플릿 모델은 다른 기능을 제공합니다. <xref:System.Windows.Controls.HeaderedItemsControl> 예를 들어 a <xref:System.Windows.Controls.Menu> 또는 a와 <xref:System.Windows.Controls.TreeView>같은 형식을 사용하여 다른 컬렉션을 포함하는 컬렉션 데이터를 <xref:System.Windows.HierarchicalDataTemplate>표시하는 경우 . 또 다른 데이터 템플릿 <xref:System.Windows.Controls.DataTemplateSelector>기능은 사용자 지정 논리에 따라 사용할 을 <xref:System.Windows.DataTemplate> 선택할 수 있는 .입니다. 자세한 내용은 다양한 데이터 템플릿 기능을 자세히 설명하는 [템플릿 개요](../../framework/wpf/data/data-templating-overview.md)를 참조하세요.

## <a name="triggers"></a>트리거

트리거는 속성 값이 변경되거나 이벤트가 발생할 때 속성을 설정하거나 애니메이션 등의 작업을 시작합니다. <xref:System.Windows.Style>s <xref:System.Windows.Controls.ControlTemplate>" <xref:System.Windows.DataTemplate> 및 `Triggers` 모든 트리거 집합을 포함할 수 있는 속성이 있습니다. 트리거에는 여러 가지 유형이 있습니다.

### <a name="propertytriggers"></a>속성 트리거

속성 <xref:System.Windows.Trigger> 값을 설정하거나 속성 값을 기반으로 작업을 시작하는 A를 속성 트리거라고 합니다.

속성 트리거를 사용하는 방법을 보여 주기 <xref:System.Windows.Controls.ListBoxItem> 위해 선택하지 않는 한 각 트리거를 부분적으로 투명하게 만들 수 있습니다. 다음 스타일은 a의 <xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Controls.ListBoxItem> 값을 `0.5`설정합니다. 그러나 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 속성이 `true`있는 경우 <xref:System.Windows.UIElement.Opacity%2A> 는 `1.0`로 설정됩니다.

[!code-xaml[PropertyTrigger](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window5.xaml#SnippetPropertyTrigger)]

이 예제에서는 <xref:System.Windows.Trigger> a를 사용하여 속성 값을 <xref:System.Windows.Trigger> 설정하지만 클래스에는 트리거가 작업을 수행할 수 있는 <xref:System.Windows.TriggerBase.EnterActions%2A> 속성도 <xref:System.Windows.TriggerBase.ExitActions%2A> 있습니다.

의 <xref:System.Windows.FrameworkElement.MaxHeight%2A> <xref:System.Windows.Controls.ListBoxItem> 속성이 로 `75`설정되어 있습니다. 다음 그림에서 세 번째 항목은 선택한 항목입니다.

![스타일 지정된 ListView](./media/styles-and-templates-overview/stylingintro-triggers.png "StylingIntro_triggers")

### <a name="eventtriggers-and-storyboards"></a>EventTrigger 및 and Storyboard

트리거의 또 다른 <xref:System.Windows.EventTrigger>유형은 이벤트의 발생에 따라 작업 집합을 시작하는 입니다. 예를 들어 다음 <xref:System.Windows.EventTrigger> 개체는 마우스 <xref:System.Windows.Controls.ListBoxItem>포인터가 에 들어갈 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 때 속성이 `0.2` 두 `90` 번째 기간 동안의 값으로 애니메이션되도록 지정합니다. 마우스가 항목을 떠나면 속성은 `1`초 기간에 걸쳐 원래 값으로 돌아갑니다. 애니메이션에 대한 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 값을 지정할 필요가 <xref:System.Windows.ContentElement.MouseLeave> 없는 방법을 설명합니다. 이는 애니메이션은 원래 값을 추적할 수 있기 때문입니다.

[!code-xaml[StyleEventTriggers](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window6.xaml#SnippetStyleEventTriggers)]

자세한 내용은 [스토리보드 개요를](../../framework/wpf/graphics-multimedia/storyboards-overview.md)참조하십시오.

다음 그림에서 마우스는 세 번째 항목을 가리킵니다.

![샘플 스크린샷 스타일링](./media/styles-and-templates-overview/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")

### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTrigger, DataTrigger 및 MultiDataTrigger

<xref:System.Windows.Trigger> 외에도 <xref:System.Windows.EventTrigger>다른 유형의 트리거가 있습니다. <xref:System.Windows.MultiTrigger>을 사용하면 여러 조건에 따라 속성 값을 설정할 수 있습니다. 조건의 <xref:System.Windows.DataTrigger> <xref:System.Windows.MultiDataTrigger> 속성이 데이터 바인딩인 경우 사용합니다.

## <a name="visual-states"></a>시각적 상태

컨트롤은 항상 특정 **상태에**있습니다. 예를 들어 마우스가 컨트롤의 표면 위로 이동하면 컨트롤이 `MouseOver`의 공통 상태로 간주됩니다. 특정 상태가 없는 컨트롤은 공통 `Normal` 상태로 간주됩니다. 상태는 그룹으로 나뉘며 앞에서 언급한 상태는 상태 그룹의 `CommonStates`일부입니다. 대부분의 컨트롤에는 두 `CommonStates` 개의 `FocusStates`상태 그룹이 있습니다. 컨트롤에 적용된 각 상태 그룹 중 컨트롤은 항상 와 같은 `CommonStates.MouseOver` `FocusStates.Unfocused`각 그룹의 한 상태에 있습니다. 그러나 컨트롤은 와 같은 `CommonStates.Normal` 동일한 그룹 내에서 두 개의 서로 `CommonStates.Disabled`다른 상태에 있을 수 없습니다. 다음은 대부분의 컨트롤이 인식하고 사용하는 상태 테이블입니다.

| VisualState 이름 | VisualStateGroup 이름 | 설명 |
| ---------------- | --------------------- | ----------- |
| 정상           | CommonStates          | 기본 상태입니다. |
| MouseOver        | CommonStates          | 마우스 포인터가 컨트롤 위에 있습니다. |
| 누름          | CommonStates          | 컨트롤을 눌렀습니다. |
| 사용 안 함         | CommonStates          | 컨트롤이 비활성화되었습니다. |
| 포커스 있음          | FocusStates           | 컨트롤에 포커스가 있습니다. |
| 포커스 없음        | FocusStates           | 컨트롤에 포커스가 없습니다. |

컨트롤 템플릿의 루트 요소에 대해 <xref:System.Windows.VisualStateManager?displayProperty=fullName> 정의하여 컨트롤이 특정 상태로 들어갈 때 애니메이션을 트리거할 수 있습니다. 어떤 `VisualStateManager` 조합을 보고 <xref:System.Windows.VisualStateGroup> <xref:System.Windows.VisualState> 볼지 선언합니다. 컨트롤이 시청 된 상태로 들어가면 에 `VisaulStateManager` 의해 정의된 애니메이션이 시작됩니다.

예를 들어 다음 XAML 코드는 `CommonStates.MouseOver` 상태를 감시하여 명명된 `backgroundElement`요소의 채우기 색상을 애니메이션합니다. 컨트롤이 `CommonStates.Normal` 상태로 돌아오면 명명된 `backgroundElement` 요소의 채우기 색상이 복원됩니다.

```xaml
<ControlTemplate x:Key="roundbutton" TargetType="Button">
    <Grid>
        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="{TemplateBinding Background}"
                                    Duration="0:0:0.3"/>
                </VisualState>
                <VisualState Name="MouseOver">
                    <ColorAnimation Storyboard.TargetName="backgroundElement"
                                    Storyboard.TargetProperty="(Shape.Fill).(SolidColorBrush.Color)"
                                    To="Yellow"
                                    Duration="0:0:0.3"/>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>

        ...
```

스토리보드에 대한 자세한 내용은 [스토리보드 개요를](../../framework/wpf/graphics-multimedia/storyboards-overview.md)참조하십시오.

## <a name="shared-resources-and-themes"></a>공유 리소스 및 테마

일반적인 WPF 앱에는 앱 전체에 적용되는 여러 UI 리소스가 있을 수 있습니다. 전체적으로 이 리소스 집합은 앱의 테마로 간주될 수 있습니다. WPF는 클래스로 캡슐화된 리소스 사전을 사용하여 UI 리소스를 테마로 <xref:System.Windows.ResourceDictionary> 패키징하는 것을 지원합니다.

WPF 테마는 WPF가 모든 요소의 시각적 개체를 사용자 지정하기 위해 노출하는 스타일 지정 및 템플릿 메커니즘을 사용하여 정의됩니다.

WPF 테마 리소스는 포함된 리소스 사전에 저장됩니다. 이러한 리소스 사전은 서명된 어셈블리에 포함되어야 하고 같은 어셈블리에 코드 자체로 포함되거나 side-by-side 어셈블리에 포함될 수 있습니다. WPF 컨트롤이 포함된 어셈블리인 PresentationFramework.dll의 경우 테마 리소스는 일련의 나란히 있는 어셈블리에 있습니다.

테마는 요소의 스타일을 검색할 때 보이는 마지막 위치가 됩니다. 일반적으로 검색은 적절한 리소스를 검색하는 요소 트리를 탐색한 다음 앱 리소스 컬렉션을 살펴보고 마지막으로 시스템을 쿼리하는 것으로 시작됩니다. 이렇게 하면 앱 개발자가 테마에 도달하기 전에 트리 또는 앱 수준에서 모든 개체에 대한 스타일을 재정의할 수 있습니다.

리소스 사전을 여러 앱에서 테마를 재사용할 수 있는 개별 파일로 정의할 수 있습니다. 또한 같은 형식의 리소스를 제공하지만 값이 서로 다른 여러 리소스 사전을 정의하여 전환 가능한 테마를 만들 수 있습니다. 앱 수준에서 이러한 스타일이나 기타 리소스를 다시 정의하는 것이 앱을 스키닝하는 데 권장되는 방법입니다.

스타일 및 템플릿을 포함한 리소스 집합을 앱 간에 공유하려면 XAML 파일을 <xref:System.Windows.ResourceDictionary> 만들고 `shared.xaml` 파일에 대한 참조를 포함하는 을 정의할 수 있습니다.

```xaml
<ResourceDictionary.MergedDictionaries>
  <ResourceDictionary Source="Shared.xaml" />
</ResourceDictionary.MergedDictionaries>
```

앱의 `shared.xaml`컨트롤이 일관된 모양을 가질 <xref:System.Windows.ResourceDictionary> 수 있도록 스타일 및 브러시 리소스 집합을 포함하는 을 정의하는 공유입니다.

자세한 내용은 [병합된 리소스 사전을](../../framework/wpf/advanced/merged-resource-dictionaries.md)참조하십시오.

사용자 지정 컨트롤에 대한 테마를 만드는 경우 [컨트롤 작성 개요의](../../framework/wpf/controls/control-authoring-overview.md#defining-resources-at-the-theme-level)테마 수준 섹션에서 **리소스 정의** 섹션을 참조하세요.

## <a name="see-also"></a>참조

- [WPF의 Pack URI](../../framework/wpf/app-development/pack-uris-in-wpf.md)
- [방법: ControlTemplate에서 생성된 요소 찾기](../../framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [데이터 템플릿 생성 요소 찾기](../../framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
