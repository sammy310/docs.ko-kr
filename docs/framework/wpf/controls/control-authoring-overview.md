---
title: 컨트롤 제작 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: a6ab5463cc28aa590454ae1304714d3d12ee7c6b
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646131"
---
# <a name="control-authoring-overview"></a>작성 개요 제어

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 컨트롤 모델의 확장성 덕분에 새 컨트롤을 만들 필요성이 상당히 줄어들었습니다. 그러나 어떤 경우에는 여전히 사용자 지정 컨트롤을 만들어야 할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 사용자 지정 컨트롤과 다양한 컨트롤 제작 모델을 만들 필요성을 최소화시키는 기능에 대해 설명합니다. 또한 새 컨트롤을 만드는 방법을 설명합니다.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>새 컨트롤 작성에 대한 대안

지금까지 기존 컨트롤에서 사용자 지정 환경을 구현하려고 하면 배경색, 테두리 너비 및 글꼴 크기와 같은 컨트롤의 표준 속성을 변경하는 것으로 제한되어 있었습니다. 미리 정의된 이러한 매개 변수 이상으로 컨트롤의 모양이나 동작을 확장하려면 일반적으로 기존 컨트롤에서 상속받게 하고 컨트롤 그리기를 담당하는 메서드를 재정의하여 새 컨트롤을 만들어야 했습니다.  여전히 옵션이기는 하지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 풍부한 콘텐츠 모델, 스타일, 템플릿 및 트리거를 사용하여 기존 컨트롤을 사용자 지정할 수 있습니다. 다음 목록에는 새 컨트롤을 만들지 않고 이러한 기능을 사용하여 사용자 지정 및 일관된 환경을 만드는 예제가 나와 있습니다.

- **풍부한 콘텐츠.** 많은 표준 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 풍부한 콘텐츠를 지원합니다. 예를 들어 a의 <xref:System.Windows.Controls.Button> 콘텐츠 속성은 <xref:System.Object>형식이므로 이론적으로 모든 것을 <xref:System.Windows.Controls.Button>에 표시할 수 있습니다.  단추에 이미지와 텍스트를 표시하려면 <xref:System.Windows.Controls.TextBlock> 이미지와 a를 추가하여 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 할당할 수 있습니다. 이러한 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 요소와 임의의 데이터를 표시할 수 있기 때문에 복잡한 시각화를 지원하기 위해 새 컨트롤을 만들거나 기존 컨트롤을 수정할 필요성이 적습니다. 의 콘텐츠 모델 및 <xref:System.Windows.Controls.Button> 기타 콘텐츠 모델에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]대한 자세한 내용은 [WPF 콘텐츠 모델을](wpf-content-model.md)참조하십시오.

- **스타일.** A는 <xref:System.Windows.Style> 컨트롤의 속성을 나타내는 값의 컬렉션입니다. 스타일을 사용하면 새 컨트롤을 작성하지 않고도 원하는 컨트롤 모양과 동작을 재사용 가능한 표현으로 만들 수 있습니다. 예를 들어 모든 <xref:System.Windows.Controls.TextBlock> 컨트롤에 글꼴 크기가 14인 Arial 글꼴을 빨간색으로 설정한다고 가정합니다. 스타일을 리소스로 만들고 이에 따라 적절한 속성을 설정할 수 있습니다. 그런 <xref:System.Windows.Controls.TextBlock> 다음 응용 프로그램에 추가하는 모든 모양이 동일합니다.

- **데이터 템플릿.** A를 <xref:System.Windows.DataTemplate> 사용하면 컨트롤에 데이터가 표시되는 방식을 사용자 지정할 수 있습니다. 예를 들어, <xref:System.Windows.DataTemplate> 에 데이터가 표시되는 방법을 지정하는 <xref:System.Windows.Controls.ListBox>데 사용할 수 있습니다.  이에 대한 예제는 [데이터 템플릿 개요](../data/data-templating-overview.md)를 참조하세요.  데이터 모양을 사용자 지정하는 것 <xref:System.Windows.DataTemplate> 외에도 사용자 지정 UI에서 많은 유연성을 제공하는 UI 요소가 포함될 수 있습니다.  예를 들어 <xref:System.Windows.DataTemplate>을 사용하여 각 항목에 <xref:System.Windows.Controls.ComboBox> 확인란이 포함된 를 만들 수 있습니다.

- **제어 템플릿.** 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ControlTemplate> 사용하여 컨트롤의 모양과 컨트롤의 기능을 구분하는 컨트롤의 구조와 모양을 정의하는 데 사용되는 많은 컨트롤이 있습니다. 을 재정의하여 컨트롤의 모양을 크게 <xref:System.Windows.Controls.ControlTemplate>변경할 수 있습니다.  예를 들어 신호등 모양의 컨트롤이 필요하다고 가정해 보겠습니다. 이 컨트롤에는 간단한 사용자 인터페이스 및 기능이 있습니다.  컨트롤은 세 개의 원으로, 한 번에 하나씩만 불을 켤 수 있습니다. 일부 리플렉션 후 <xref:System.Windows.Controls.RadioButton> 한 번에 하나만 선택되는 기능을 제공하지만 기본 모양은 <xref:System.Windows.Controls.RadioButton> 스톱라이트의 라이트와 같은 모양이 아니라는 것을 알게 될 수 있습니다.  컨트롤 <xref:System.Windows.Controls.RadioButton> 템플릿을 사용하여 모양을 정의하기 때문에 컨트롤의 요구 <xref:System.Windows.Controls.ControlTemplate> 사항에 맞게 을 재정의하고 라디오 단추를 사용하여 스톱라이트를 만드는 것이 쉽습니다.

  > [!NOTE]
  > a를 <xref:System.Windows.Controls.RadioButton> 사용할 <xref:System.Windows.DataTemplate>수 <xref:System.Windows.DataTemplate> 있지만 a는 이 예제에서는 충분하지 않습니다.  는 <xref:System.Windows.DataTemplate> 컨트롤의 내용의 모양을 정의 합니다. 의 경우 <xref:System.Windows.Controls.RadioButton>, 콘텐츠는 선택 여부를 나타내는 원의 오른쪽에 나타나는 <xref:System.Windows.Controls.RadioButton> 무엇이든이다.  신호등의 예제에서 라디오 버튼은 "불을 켤 수 있는" 원이어야 합니다. 스톱라이트에 대한 모양 요구 사항은 의 기본 모양과 너무 다르기 <xref:System.Windows.Controls.RadioButton>때문에 <xref:System.Windows.Controls.ControlTemplate>을 재정의할 필요가 있습니다.  일반적으로 a는 <xref:System.Windows.DataTemplate> 컨트롤의 컨텐터(또는 데이터)를 정의하는 <xref:System.Windows.Controls.ControlTemplate> 데 사용되며, a는 컨트롤의 구조화 방식을 정의하는 데 사용된다.

- **트리거.** A를 <xref:System.Windows.Trigger> 사용하면 새 컨트롤을 만들지 않고도 컨트롤의 모양과 동작을 동적으로 변경할 수 있습니다. 예를 들어 응용 프로그램에 <xref:System.Windows.Controls.ListBox> 여러 컨트롤이 있고 각 <xref:System.Windows.Controls.ListBox> 항목이 선택될 때 굵게 및 빨간색으로 표시하려고 한다고 가정합니다. 첫 번째 본능은 선택한 항목의 모양을 <xref:System.Windows.Controls.ListBox> 변경하는 <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> 메서드를 상속하고 재정의하는 클래스를 만드는 것이지만 더 나은 방법은 선택한 <xref:System.Windows.Controls.ListBoxItem> 항목의 모양을 변경하는 a의 스타일에 트리거를 추가하는 것입니다. 트리거를 사용하면 속성 값을 변경하거나 속성 값을 기반으로 작업을 수행할 수 있습니다. A를 <xref:System.Windows.EventTrigger> 사용하면 이벤트가 발생할 때 작업을 수행할 수 있습니다.

스타일, 템플릿 및 트리거에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)을 참조하세요.

일반적으로 컨트롤이 기존 컨트롤의 기능을 반영하지만 컨트롤이 다르게 보이게 하려면 이 섹션에서 설명하는 메서드 중 하나를 사용하여 기존 컨트롤의 모양을 변경할 수 있는지 여부를 먼저 고려해야 합니다.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>컨트롤 제작 모델

풍부한 콘텐츠 모델, 스타일, 템플릿 및 트리거를 사용하면 새 컨트롤을 만들어야 하는 필요성이 최소화됩니다. 그러나 새 컨트롤을 만들어야 한다면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다양한 컨트롤 제작 모델을 이해하는 것이 중요합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 컨트롤을 만들기 위해 세 가지 일반적인 모델을 제공하며 각 모델은 서로 다른 일련의 기능과 유연성 수준을 제공합니다. 세 모델의 기본 클래스는 <xref:System.Windows.Controls.Control>및 <xref:System.Windows.FrameworkElement>. <xref:System.Windows.Controls.UserControl>

### <a name="deriving-from-usercontrol"></a>UserControl에서 파생

에서 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 만드는 가장 간단한 방법은 <xref:System.Windows.Controls.UserControl>에서 파생하는 것입니다. 에서 <xref:System.Windows.Controls.UserControl>상속하는 컨트롤을 빌드할 때 <xref:System.Windows.Controls.UserControl>의 에서 기존 구성 요소를 추가 합니다. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 그런 다음 코드에서 명명된 요소를 참조하고 이벤트 처리기를 정의할 수 있습니다. 이 개발 모델은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 애플리케이션 개발에 사용된 모델과 매우 유사합니다.

올바르게 빌드된 <xref:System.Windows.Controls.UserControl> 경우 a는 풍부한 콘텐츠, 스타일 및 트리거의 이점을 활용할 수 있습니다. 그러나 컨트롤이 <xref:System.Windows.Controls.UserControl>에서 상속되는 경우 컨트롤을 사용하는 사용자는 을 <xref:System.Windows.DataTemplate> 사용하거나 <xref:System.Windows.Controls.ControlTemplate> 모양을 사용자 지정할 수 없습니다.  템플릿을 지원하는 사용자 <xref:System.Windows.Controls.Control> 지정 컨트롤을 만들려면 클래스 또는 <xref:System.Windows.Controls.UserControl>파생 클래스 중 하나에서 파생해야 합니다.

#### <a name="benefits-of-deriving-from-usercontrol"></a>UserControl에서 파생하는 이점

다음이 모두 <xref:System.Windows.Controls.UserControl> 적용되는지 파생하는 것이 좋습니다.

- 애플리케이션을 빌드하는 방법과 유사하게 컨트롤을 빌드하려고 합니다.

- 컨트롤이 기존 구성 요소로만 구성됩니다.

- 복잡한 사용자 지정을 지원하지 않아도 됩니다.

### <a name="deriving-from-control"></a>Control에서 파생

<xref:System.Windows.Controls.Control> 클래스에서 파생되는 모델은 대부분의 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 사용되는 모델입니다. 클래스에서 상속하는 컨트롤을 <xref:System.Windows.Controls.Control> 만들 때 템플릿을 사용하여 모양을 정의합니다. 그렇게 함으로써 작동 논리를 시각적 표현과 분리합니다. 또한 이벤트 대신 명령과 바인딩을 사용하고 가능하면 요소를 참조하지 않도록 하여 UI와 논리의 <xref:System.Windows.Controls.ControlTemplate> 분리를 보장할 수 있습니다.  컨트롤의 UI와 논리가 제대로 분리된 경우 컨트롤의 사용자가 컨트롤의 모양을 <xref:System.Windows.Controls.ControlTemplate> 사용자 지정하도록 컨트롤을 재정의할 수 있습니다. 사용자 지정을 <xref:System.Windows.Controls.Control> 빌드하는 것은 <xref:System.Windows.Controls.UserControl>을 빌드하는 <xref:System.Windows.Controls.Control> 것만큼 간단하지는 않지만 사용자 지정은 가장 유연하게 합니다.

#### <a name="benefits-of-deriving-from-control"></a>Control에서 파생하는 이점

다음 중 한 <xref:System.Windows.Controls.Control> 가지라도 <xref:System.Windows.Controls.UserControl> 적용되는 경우 클래스를 사용하는 대신 파생하는 것이 좋습니다.

- 을 통해 컨트롤의 모양을 사용자 지정할 <xref:System.Windows.Controls.ControlTemplate>수 있습니다.

- 컨트롤이 다른 테마를 지원하게 하려고 합니다.

### <a name="deriving-from-frameworkelement"></a>FrameworkElement에서 파생

기존 요소에서 <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Control> 파생되거나 구성에 의존하는 컨트롤입니다. 많은 시나리오에서 상속되는 모든 개체가 <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>에 있을 수 있으므로 이 솔루션은 허용 가능한 솔루션입니다. 그러나 컨트롤의 모양이 단순한 요소 컴퍼지션 이상의 기능을 필요로 하는 경우가 있습니다. 이러한 시나리오에서는 구성 요소를 <xref:System.Windows.FrameworkElement> 기반으로 하는 것이 올바른 선택입니다.

직접 렌더링 및 사용자 <xref:System.Windows.FrameworkElement>지정 요소 컴포지션의 두 가지 기본 구성 요소를 빌드하는 방법에는 두 가지가 있습니다. 직접 렌더링에는 구성 <xref:System.Windows.UIElement.OnRender%2A> 요소 <xref:System.Windows.FrameworkElement> 시각적 <xref:System.Windows.Media.DrawingContext> 개체를 명시적으로 정의하는 메서드를 재정의하고 제공하는 작업이 포함됩니다. 이 방법은 및 <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Border>에서 사용하는 메서드입니다. 사용자 지정 요소 컴포지션에는 형식의 <xref:System.Windows.Media.Visual> 개체를 사용하여 구성 요소의 모양을 구성합니다. 예제는 [DrawingVisual 개체 사용](../graphics-multimedia/using-drawingvisual-objects.md)을 참조하세요. <xref:System.Windows.Controls.Primitives.Track>사용자 지정 요소 컴포지션을 사용하는 컨트롤의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 예입니다. 직접 렌더링과 사용자 지정 요소 컴퍼지션을 같은 컨트롤에서 혼합하여 사용할 수도 있습니다.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>FrameworkElement에서 파생하는 이점

다음 중 어느 <xref:System.Windows.FrameworkElement> 것이 적용되는지 에서 파생하는 것이 좋습니다.

- 단순한 요소 컴퍼지션에서 제공하는 기능 이상으로 컨트롤의 모양을 정확하게 제어하려고 합니다.

- 자체 렌더링 논리를 정의하여 컨트롤의 모양을 정의하려고 합니다.

- 기존 요소를 가능한 것 이상으로 새로운 방식으로 <xref:System.Windows.Controls.UserControl> 구성하려고 합니다. <xref:System.Windows.Controls.Control>

<a name="control_authoring_basics"></a>

## <a name="control-authoring-basics"></a>컨트롤 제작 기본 사항

앞에서 설명한 것처럼 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 가장 강력한 기능 중 하나는 컨트롤의 기본 속성 설정 이상으로 모양 및 동작을 변경하면서 사용자 지정 컨트롤을 만들지 않아도 되는 것입니다. 스타일 지정, 데이터 바인딩 및 트리거 기능은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템에 의해 가능합니다. 다음 섹션에서는 사용자 지정 컨트롤을 만드는 데 사용하는 모델에 관계없이 따라야 하는 몇 가지 방법을 설명합니다. 이에 따라 사용자 지정 컨트롤의 사용자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 포함된 컨트롤의 경우처럼 이러한 기능을 사용할 수 있습니다.

### <a name="use-dependency-properties"></a>종속성 속성 사용

속성이 종속성 속성인 경우 다음을 수행할 수 있습니다.

- 스타일에서 속성을 설정합니다.

- 속성을 데이터 소스에 바인딩합니다.

- 속성의 값으로 동적 리소스를 사용합니다.

- 속성에 애니메이션 효과를 줍니다.

컨트롤의 속성이 이 기능을 지원하도록 하려면 종속성 속성으로 구현해야 합니다. 다음 예제에서는 다음을 수행하여 `Value`라는 종속성 속성을 정의합니다.

- 필드로 <xref:System.Windows.DependencyProperty> 명명된 `ValueProperty` 식별자를 정의합니다. `public` `static` `readonly`

- 을 호출하여 <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>속성 이름을 속성 시스템에 등록하여 다음을 지정합니다.

  - 속성의 이름입니다.

  - 속성의 형식입니다.

  - 속성을 소유하는 형식입니다.

  - 속성의 메타데이터입니다. 메타데이터에는 속성의 기본값, <xref:System.Windows.CoerceValueCallback> a <xref:System.Windows.PropertyChangedCallback>및 a가 포함됩니다.

- 속성 `Value` `get` 및 `set` 접근자를 구현하여 종속성 속성을 등록하는 데 사용되는 이름과 동일한 이름의 CLR 래퍼 속성을 정의합니다. `get` 및 `set` 접근자는 각각 호출하고 <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> 각각 호출합니다. 종속성 속성의 접근자는 클라이언트와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호출을 <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> 우회할 수 있으므로 추가 논리를 포함하지 않는 것이 좋습니다. 예를 들어 속성이 데이터 소스에 바인딩되면 해당 속성의 `set` 접근자가 호출되지 않습니다.  get 및 set 접근자에 추가 논리를 추가하는 <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.CoerceValueCallback>대신 <xref:System.Windows.PropertyChangedCallback> 에서 를 사용하고 대리인은 에 응답하거나 변경될 때 값을 확인합니다.  이 콜백에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../advanced/dependency-property-callbacks-and-validation.md)를 참조하세요.

- 명명된 `CoerceValue`에 <xref:System.Windows.CoerceValueCallback> 대한 메서드를 정의합니다. `CoerceValue`는 `Value`가 `MinValue`보다 크거나 같고 `MaxValue`보다 작거나 같도록 합니다.

- <xref:System.Windows.PropertyChangedCallback>에 대한 메서드를 `OnValueChanged`정의합니다. `OnValueChanged`을 <xref:System.Windows.RoutedPropertyChangedEventArgs%601> 사용하여 개체를 만들고 `ValueChanged` 라우트된 이벤트를 발생시킬 준비를 합니다. 라우트된 이벤트는 다음 섹션에서 설명합니다.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

자세한 내용은 [사용자 지정 종속성 속성](../advanced/custom-dependency-properties.md)을 참조하세요.

### <a name="use-routed-events"></a>라우트된 이벤트 사용

종속성 속성이 추가 기능을 사용하여 CLR 속성의 개념을 확장하는 것처럼 라우트된 이벤트는 표준 CLR 이벤트의 개념을 확장합니다. 라우트된 이벤트는 다음 동작을 지원하기 때문에 새로운 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 만들 때 이벤트를 라우트된 이벤트로 구현하는 것도 좋습니다.

- 이벤트는 여러 컨트롤의 부모에서 처리될 수 ​​있습니다. 이벤트가 버블링 이벤트인 경우 요소 트리의 단일 부모가 이벤트를 구독할 수 있습니다. 그런 다음 애플리케이션 작성자는 하나의 처리기를 사용하여 여러 컨트롤의 이벤트에 응답할 수 있습니다. 예를 들어 컨트롤이 a에 <xref:System.Windows.Controls.ListBox> 포함되어 <xref:System.Windows.DataTemplate>있기 때문에) 각 항목의 일부인 경우 응용 프로그램 개발자는 <xref:System.Windows.Controls.ListBox>에서 컨트롤의 이벤트에 대한 이벤트 처리기를 정의할 수 있습니다. 이벤트가 컨트롤 중 하나에서 발생할 때마다 이벤트 처리기가 호출됩니다.

- 응용 프로그램 개발자가 스타일 <xref:System.Windows.EventSetter>내에서 이벤트의 처리기를 지정할 수 있는 는 에서 라우트된 이벤트를 사용할 수 있습니다.

- 라우트된 이벤트를 <xref:System.Windows.EventTrigger>사용할 수 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 자세한 내용은 [애니메이션 개요를](../graphics-multimedia/animation-overview.md)참조하십시오.

다음 예제는 다음을 수행하여 라우트된 이벤트를 정의합니다.

- 필드로 <xref:System.Windows.RoutedEvent> 명명된 `ValueChangedEvent` 식별자를 정의합니다. `public` `static` `readonly`

- 메서드를 호출하여 라우트된 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> 이벤트를 등록합니다. 이 예제는 호출할 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>때 다음 정보를 지정합니다.

  - 이벤트의 이름은 `ValueChanged`입니다.

  - 라우팅 전략은 <xref:System.Windows.RoutingStrategy.Bubble>소스의 이벤트 처리기(이벤트를 발생시키는 개체)가 먼저 호출된 다음 가장 가까운 상위 요소의 이벤트 처리기로 시작하여 소스의 부모 요소에 대한 이벤트 처리기가 연속적으로 호출된다는 것을 의미합니다.

  - 이벤트 처리기의 형식은 <xref:System.Windows.RoutedPropertyChangedEventHandler%601>type으로 <xref:System.Decimal> 생성됩니다.

  - 이벤트의 소유 형식은 `NumericUpDown`입니다.

- `ValueChanged`라는 공용 이벤트를 선언하고 이벤트 접근자 선언을 포함합니다. 이 예제는 `add` 접근자 선언및 <xref:System.Windows.UIElement.RemoveHandler%2A> `remove` 접근자 선언에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 서비스를 사용하여 호출합니다. <xref:System.Windows.UIElement.AddHandler%2A>

- `ValueChanged` 이벤트를 발생시키는 `OnValueChanged`라는 보호된 가상 메서드를 만듭니다.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

자세한 내용은 [라우트된 이벤트 개요](../advanced/routed-events-overview.md) 및 [사용자 지정 라우트된 이벤트 만들기](../advanced/how-to-create-a-custom-routed-event.md)를 참조하세요.

### <a name="use-binding"></a>바인딩 사용

해당 논리에서 컨트롤의 UI를 분리하려면 데이터 바인딩 사용을 고려합니다. 을 사용하여 컨트롤의 모양을 정의하는 경우 특히 <xref:System.Windows.Controls.ControlTemplate>중요합니다. 데이터 바인딩을 사용하면 코드에서 UI의 특정 부분을 참조하지 않아도 될 수 있습니다. 코드가 에 있는 <xref:System.Windows.Controls.ControlTemplate> 요소를 <xref:System.Windows.Controls.ControlTemplate> 참조하고 <xref:System.Windows.Controls.ControlTemplate> 변경될 때 참조된 요소를 새 <xref:System.Windows.Controls.ControlTemplate>에 포함해야 하기 때문에 에 있는 요소를 참조하지 않는 것이 좋습니다.

다음 예제에서는 <xref:System.Windows.Controls.TextBlock> `NumericUpDown` 컨트롤의 이름을 지정 하 고 코드에서 이름으로 텍스트 상자를 참조 하는 컨트롤을 업데이트 합니다.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

다음 예제에서는 바인딩을 사용하여 동일한 작업을 수행합니다.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조하세요.

### <a name="design-for-designers"></a>디자이너를 위한 디자인

비주얼 스튜디오용 WPF 디자이너에서 사용자 지정 WPF 컨트롤에 대한 지원을 받으려면(예: 속성 창으로 속성 편집) 다음 지침을 따르십시오.  WPF 디자이너를 위한 개발에 대한 자세한 내용은 [Visual Studio의 디자인 XAML을](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)참조하십시오.

#### <a name="dependency-properties"></a>종속성 속성

앞에서 설명한 대로 `get` `set` "종속성 속성 사용"에서 CLR 및 접근자를 구현해야 합니다. 디자이너는 래퍼를 사용하여 종속성 속성의 존재를 감지할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 컨트롤의 클라이언트와 마찬가지로 속성을 가져오거나 설정할 때 접근자를 호출할 필요가 없습니다.

#### <a name="attached-properties"></a>연결된 속성

다음 지침을 사용하여 사용자 지정 컨트롤에서 연결된 속성을 구현해야 합니다.

- `public` `Property` <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드를 사용하여 만든 속성 Name 형식이 있습니다. *PropertyName* `static` `readonly` <xref:System.Windows.DependencyProperty> 전달되는 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 속성 이름은 *PropertyName*을 일치해야 합니다.

- `Set`*PropertyName* 및 `Get`*PropertyName*이라는 `public` `static` CLR 메서드 쌍을 구현합니다. 두 메서드 모두 첫 번째 <xref:System.Windows.DependencyProperty> 인수에서 파생된 클래스를 수락해야 합니다. `Set`*PropertyName* 메서드는 그 형식이 속성의 등록된 데이터 형식과 일치하는 인수도 수락합니다. `Get`*PropertyName* 메서드는 동일한 형식의 값을 반환해야 합니다. `Set`*PropertyName* 메서드가 누락된 경우 속성이 읽기 전용으로 표시됩니다.

- `Set`*PropertyName* `Get`및 *PropertyName* 대상 <xref:System.Windows.DependencyObject.GetValue%2A> 종속성 개체에 대 한 메서드와 <xref:System.Windows.DependencyObject.SetValue%2A> 메서드에 직접 라우팅 해야 합니다. 디자이너는 메서드 래퍼를 통해 호출하거나 대상 종속성 개체를 직접 호출하여 연결된 속성에 액세스할 수 있습니다.

연결된 속성에 대한 자세한 내용은 [연결된 속성 개요](../advanced/attached-properties-overview.md)를 참조하세요.

### <a name="define-and-use-shared-resources"></a>공유 리소스 정의 및 사용

애플리케이션과 동일한 어셈블리에 컨트롤을 포함하거나 여러 애플리케이션에서 사용할 수 있는 별도의 어셈블리에 컨트롤을 패키지화할 수 있습니다. 대부분, 이 항목에서 설명하는 정보는 사용하는 메서드에 관계없이 적용됩니다.  그러나 주목할 만한 차이점이 하나 있습니다.  애플리케이션과 동일한 어셈블리에 컨트롤을 배치하면 App.xaml 파일에 전역 리소스를 자유롭게 추가할 수 있습니다. 그러나 컨트롤만 포함하는 어셈블리에는 <xref:System.Windows.Application> 연결된 개체가 없으므로 App.xaml 파일을 사용할 수 없습니다.

애플리케이션이 리소스를 찾을 때 다음 순서로 세 가지 수준을 조사합니다.

1. 요소 수준

   시스템이 리소스를 참조하는 요소로 시작한 다음 루트 요소에 도달할 때까지 논리 부모 등의 리소스를 검색합니다.

2. 애플리케이션 수준

   개체에 의해 <xref:System.Windows.Application> 정의된 리소스입니다.

3. 테마 수준

   테마 수준 사전은 Themes라는 하위 폴더에 저장됩니다.  Themes 폴더의 파일은 테마에 해당합니다.  예를 들어 Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml 등이 있을 수 있습니다.  generic.xaml이라는 파일이 있을 수도 있습니다.  시스템이 테마 수준에서 리소스를 찾으면 먼저 테마별 파일에서 찾은 다음 generic.xaml에서 찾습니다.

컨트롤이 애플리케이션과 별도의 어셈블리에 있을 때는 전역 리소스를 요소 수준이나 테마 수준에 배치해야 합니다. 두 가지 방법 모두 장점이 있습니다.

#### <a name="defining-resources-at-the-element-level"></a>요소 수준에서 리소스 정의

사용자 지정 리소스 사전을 만들고 컨트롤의 리소스 사전과 병합하여 요소 수준에서 공유 리소스를 정의할 수 있습니다.  이 메서드를 사용하면 리소스 파일의 이름을 원하는 대로 지정할 수 있으며 컨트롤과 동일한 폴더에 배치할 수 있습니다. 요소 수준의 리소스는 간단한 문자열을 키로 사용할 수도 있습니다. 다음 예제는 <xref:System.Windows.Media.LinearGradientBrush> Dictionary1.xaml이라는 리소스 파일을 만듭니다.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

사전을 정의한 후에는 컨트롤의 리소스 사전과 병합해야 합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드를 사용하여 이 작업을 수행할 수 있습니다.

다음 예제는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 리소스 사전을 병합합니다.

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

이 방법의 단점은 객체를 참조할 <xref:System.Windows.ResourceDictionary> 때마다 개체가 생성된다는 것입니다.  예를 들어 라이브러리에 10개의 사용자 지정 컨트롤이 있고 XAML을 사용하여 각 컨트롤에 대한 공유 <xref:System.Windows.ResourceDictionary> 리소스 사전을 병합하는 경우 10개의 동일한 개체를 만듭니다.  코드에서 리소스를 병합 하고 결과 <xref:System.Windows.ResourceDictionary>반환 하는 정적 클래스를 만들어이 작업을 방지할 수 있습니다.

다음 예제는 공유 <xref:System.Windows.ResourceDictionary>를 반환 하는 클래스를 만듭니다.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

다음 예제에서는 공유 리소스를 `InitializeComponent`를 호출하기 전에 컨트롤의 생성자에 있는 사용자 지정 컨트롤의 리소스와 병합합니다.  는 `SharedDictionaryManager.SharedDictionary` 정적 속성이므로 <xref:System.Windows.ResourceDictionary> 한 번만 만들어집니다. `InitializeComponent`가 호출되기 전에 리소스 사전이 병합되었기 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 컨트롤에서 리소스를 사용할 수 있습니다.

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>테마 수준에서 리소스 정의

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 다양한 Windows 테마를 위한 리소스를 만들 수 있습니다.  컨트롤 작성자는 특정 테마의 리소스를 정의하여 사용 중인 테마에 따라 컨트롤의 모양을 변경할 수 있습니다. 예를 들어 Windows 클래식 <xref:System.Windows.Controls.Button> 테마(Windows 2000의 기본 테마)의 모양은 각 <xref:System.Windows.Controls.Button> 테마마다 다른 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> 테마를 사용하기 때문에 Windows Luna 테마(Windows XP의 기본 테마)와 다릅니다.

테마와 관련된 리소스는 특정 파일 이름의 리소스 사전에 보관됩니다. 이러한 파일은 컨트롤이 포함된 폴더의 하위 폴더인 `Themes`라는 폴더에 있어야 합니다. 다음 표에는 각 파일과 관련된 리소스 사전 파일과 테마가 나와 있습니다.

|리소스 사전 파일 이름|Windows 테마|
|-----------------------------------|-------------------|
|`Classic.xaml`|Windows XP의 고전 Windows 9x/2000 모양|
|`Luna.NormalColor.xaml`|Windows XP의 기본 파란색 테마|
|`Luna.Homestead.xaml`|Windows XP의 올리브색 테마|
|`Luna.Metallic.xaml`|Windows XP의 은색 테마|
|`Royale.NormalColor.xaml`|Windows XP Media Center Edition의 기본 테마|
|`Aero.NormalColor.xaml`|Windows Vista의 기본 테마|

모든 테마에 대해 리소스를 정의할 필요는 없습니다. 특정 테마에 대해 리소스가 정의되지 않은 경우 컨트롤이 리소스에 대해 `Classic.xaml`을 확인합니다. 현재 테마에 해당하는 파일 또는 `Classic.xaml`에 리소스가 정의되지 않은 경우 컨트롤이 `generic.xaml`이라는 리소스 사전 파일에 있는 제네릭 리소스를 사용합니다.  `generic.xaml` 파일은 테마별 리소스 사전 파일과 같은 폴더에 있습니다. `generic.xaml`은 특정 Windows 테마에 해당하지 않지만 여전히 테마 수준의 사전입니다.

테마 및 UI 자동화 지원 샘플이 있는 [C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) 또는 [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) NumericUpDown `NumericUpDown` 사용자 지정 컨트롤에는 컨트롤에 대한 두 가지 리소스 사전이 포함되어 있습니다.

테마별 리소스 <xref:System.Windows.Controls.ControlTemplate> 사전 파일에 를 넣을 때 컨트롤에 대한 정적 생성자(정적 생성자)를 만들고 다음 예제와 같이 에 <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> 메서드를 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>호출해야 합니다.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>테마 리소스에 대한 키 정의 및 참조

요소 레벨에서 리소스를 정의할 때 문자열을 키로 지정하고 문자열을 통해 리소스에 액세스할 수 있습니다. 테마 수준에서 리소스를 정의할 때는 을 <xref:System.Windows.ComponentResourceKey> 키로 사용해야 합니다.  다음 예제에서는 generic.xaml에서 리소스를 정의합니다.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

다음 예제는 를 <xref:System.Windows.ComponentResourceKey> 키로 지정하여 리소스를 참조합니다.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>테마 리소스의 위치 지정

컨트롤에 대한 리소스를 찾으려면 호스팅 애플리케이션이 어셈블리에 컨트롤 관련 리소스가 있는지 알아야 합니다. 컨트롤을 포함하는 <xref:System.Windows.ThemeInfoAttribute> 어셈블리에 추가하여 이를 수행할 수 있습니다. 에는 <xref:System.Windows.ThemeInfoAttribute> 일반 <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> 리소스의 위치를 지정하는 <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> 속성과 테마별 리소스의 위치를 지정하는 속성이 있습니다.

다음 예제에서는 <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> 및 <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> 속성을 <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>로 설정하여 일반 및 테마별 리소스가 컨트롤과 동일한 어셈블리에 있는지 지정합니다.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>참고 항목

- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [WPF의 Pack URI](../app-development/pack-uris-in-wpf.md)
- [컨트롤 사용자 지정](control-customization.md)
