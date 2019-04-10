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
ms.openlocfilehash: bb35a4d47f583aad710e178bdb12cb9adf6321e0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340024"
---
# <a name="control-authoring-overview"></a>컨트롤 제작 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 컨트롤 모델의 확장성 덕분에 새 컨트롤을 만들 필요성이 상당히 줄어들었습니다. 그러나 어떤 경우에는 여전히 사용자 지정 컨트롤을 만들어야 할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 사용자 지정 컨트롤과 다양한 컨트롤 제작 모델을 만들 필요성을 최소화시키는 기능에 대해 설명합니다. 또한 새 컨트롤을 만드는 방법을 설명합니다.  

<a name="when_to_write_a_new_control"></a>   
## <a name="alternatives-to-writing-a-new-control"></a>새 컨트롤 작성에 대한 대안  
 지금까지 기존 컨트롤에서 사용자 지정 환경을 구현하려고 하면 배경색, 테두리 너비 및 글꼴 크기와 같은 컨트롤의 표준 속성을 변경하는 것으로 제한되어 있었습니다. 미리 정의된 이러한 매개 변수 이상으로 컨트롤의 모양이나 동작을 확장하려면 일반적으로 기존 컨트롤에서 상속받게 하고 컨트롤 그리기를 담당하는 메서드를 재정의하여 새 컨트롤을 만들어야 했습니다.  여전히 옵션이기는 하지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 풍부한 콘텐츠 모델, 스타일, 템플릿 및 트리거를 사용하여 기존 컨트롤을 사용자 지정할 수 있습니다. 다음 목록에는 새 컨트롤을 만들지 않고 이러한 기능을 사용하여 사용자 지정 및 일관된 환경을 만드는 예제가 나와 있습니다.  
  
-   **풍부한 콘텐츠입니다.** 많은 표준 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 풍부한 콘텐츠를 지원합니다. 예를 들어의 content 속성을 <xref:System.Windows.Controls.Button> 형식입니다 <xref:System.Object>, 이론적에 아무 것도 표시할 수 있습니다를 <xref:System.Windows.Controls.Button>.  단추 이미지와 텍스트를 표시 하도록 이미지를 추가할 수 있습니다 및 <xref:System.Windows.Controls.TextBlock> 에 <xref:System.Windows.Controls.StackPanel> 할당를 <xref:System.Windows.Controls.StackPanel> 에 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성. 이러한 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 요소와 임의의 데이터를 표시할 수 있기 때문에 복잡한 시각화를 지원하기 위해 새 컨트롤을 만들거나 기존 컨트롤을 수정할 필요성이 적습니다. 콘텐츠 모델에 대 한 자세한 내용은 <xref:System.Windows.Controls.Button> 다른 콘텐츠 모델 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 참조 하십시오 [WPF 콘텐츠 모델](wpf-content-model.md)합니다.  
  
-   **스타일입니다.** <xref:System.Windows.Style> 은 컨트롤의 속성을 나타내는 값의 컬렉션입니다. 스타일을 사용하면 새 컨트롤을 작성하지 않고도 원하는 컨트롤 모양과 동작을 재사용 가능한 표현으로 만들 수 있습니다. 예를 들어, 모든 것을 가정 하면 <xref:System.Windows.Controls.TextBlock> 컨트롤 14 글꼴 크기를 사용 하 여 빨간색, Arial 글꼴에 있습니다. 스타일을 리소스로 만들고 이에 따라 적절한 속성을 설정할 수 있습니다. 다음 모든 <xref:System.Windows.Controls.TextBlock> 응용 프로그램에 추가한 모양이 동일 해야 합니다.  
  
-   **데이터 템플릿입니다.** <xref:System.Windows.DataTemplate> 데이터 컨트롤에 표시 되는 방식을 사용자 지정할 수 있습니다. 예를 들어, 한 <xref:System.Windows.DataTemplate> 에서 데이터를 표시 하는 방법을 지정할 수는 <xref:System.Windows.Controls.ListBox>합니다.  이에 대한 예제는 [데이터 템플릿 개요](../data/data-templating-overview.md)를 참조하세요.  데이터의 모양 사용자 지정 하는 것 외에도 <xref:System.Windows.DataTemplate> 제공 하는 다양 한 사용자 지정 Ui에서 UI 요소를 포함할 수 있습니다.  사용 하 여 예를 들어를 <xref:System.Windows.DataTemplate>를 만들 수 있습니다를 <xref:System.Windows.Controls.ComboBox> 각 항목에 포함 하는 확인란 합니다.  
  
-   **컨트롤 템플릿입니다.** 많은 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용을 <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 구조 및 컨트롤의 기능에서 컨트롤의 모양을 분리 하는 모양을 정의할 수 있습니다. 다시 정의 하 여 컨트롤의 모양을 대폭 변경할 수 있습니다 해당 <xref:System.Windows.Controls.ControlTemplate>합니다.  예를 들어 신호등 모양의 컨트롤이 필요하다고 가정해 보겠습니다. 이 컨트롤에는 간단한 사용자 인터페이스 및 기능이 있습니다.  컨트롤은 세 개의 원으로, 한 번에 하나씩만 불을 켤 수 있습니다. 약간의 리플렉션을 후는 알 수 있습니다는 <xref:System.Windows.Controls.RadioButton> 한 번만의 기본 모양을 하나만 선택 된 기능을 제공 합니다 <xref:System.Windows.Controls.RadioButton> 신호등에서 등과 같습니다.  때문에 합니다 <xref:System.Windows.Controls.RadioButton> 해당 모양을 정의 하는 컨트롤 템플릿을 사용 재정의 하기 쉽습니다는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 요구 사항에 맞게 라디오 단추를 사용 하 여 신호등을 확인 하 합니다.  
  
    > [!NOTE]
    >  하지만 <xref:System.Windows.Controls.RadioButton> 사용할 수는 <xref:System.Windows.DataTemplate>, <xref:System.Windows.DataTemplate> 이 예제의 충분 하지 않습니다.  <xref:System.Windows.DataTemplate> 콘텐츠 컨트롤의 모양을 정의 합니다. 경우는 <xref:System.Windows.Controls.RadioButton>, 콘텐츠를 나타내는 원의 오른쪽에 나타나는 모든 여부를 <xref:System.Windows.Controls.RadioButton> 선택 합니다.  신호등의 예제에서 라디오 버튼은 "불을 켤 수 있는" 원이어야 합니다. 신호등의 모양 요구 사항은의 기본 모양을 다르기 때문에 <xref:System.Windows.Controls.RadioButton>, 다시 정의 하는 데 필요한 것은 <xref:System.Windows.Controls.ControlTemplate>.  일반적을 <xref:System.Windows.DataTemplate> 컨트롤 및 콘텐츠 (또는 데이터)의 정의 <xref:System.Windows.Controls.ControlTemplate> 컨트롤 구성 되는 방식을 정의 하기 위해 사용 됩니다.  
  
-   **트리거합니다.** <xref:System.Windows.Trigger> 동적으로 새 컨트롤을 만들지 않고 컨트롤의 동작과 모양을 변경할 수 있습니다. 예를 들어, 여러 개의 <xref:System.Windows.Controls.ListBox> 응용 프로그램에서 컨트롤의 각 항목에 들고 <xref:System.Windows.Controls.ListBox> 되며 굵은 빨간색 선택 하는 경우에 합니다. 직감을에서 상속 되는 클래스를 만드는 것 <xref:System.Windows.Controls.ListBox> 시키고 합니다 <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> 더 나은 방법은 선택한 항목의 모양을 변경 하는 방법은의 스타일에 트리거를 추가 하는 것을 <xref:System.Windows.Controls.ListBoxItem> 의 모양을 변경 하는 선택한 항목입니다. 트리거를 사용하면 속성 값을 변경하거나 속성 값을 기반으로 작업을 수행할 수 있습니다. <xref:System.Windows.EventTrigger> 이벤트가 발생할 때 작업을 수행할 수 있습니다.  
  
 스타일, 템플릿 및 트리거에 대한 자세한 내용은 [스타일 지정 및 템플릿](styling-and-templating.md)을 참조하세요.  
  
 일반적으로 컨트롤이 기존 컨트롤의 기능을 반영하지만 컨트롤이 다르게 보이게 하려면 이 섹션에서 설명하는 메서드 중 하나를 사용하여 기존 컨트롤의 모양을 변경할 수 있는지 여부를 먼저 고려해야 합니다.  
  
<a name="models_for_control_authoring"></a>   
## <a name="models-for-control-authoring"></a>컨트롤 제작 모델  
 풍부한 콘텐츠 모델, 스타일, 템플릿 및 트리거를 사용하면 새 컨트롤을 만들어야 하는 필요성이 최소화됩니다. 그러나 새 컨트롤을 만들어야 한다면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다양한 컨트롤 제작 모델을 이해하는 것이 중요합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다양 한 기능 및 유연성 수준을 제공 하는 각 컨트롤을 만들기 위한 세 가지 일반 모델을 제공 합니다. 세 가지 모델에 대 한 기본 클래스 <xref:System.Windows.Controls.UserControl>하십시오 <xref:System.Windows.Controls.Control>, 및 <xref:System.Windows.FrameworkElement>합니다.  
  
### <a name="deriving-from-usercontrol"></a>UserControl에서 파생  
 컨트롤을 만드는 가장 간단한 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 파생 하는 것 <xref:System.Windows.Controls.UserControl>입니다. 상속 하는 컨트롤을 빌드할 때 <xref:System.Windows.Controls.UserControl>, 기존 구성 요소를 추가 합니다 <xref:System.Windows.Controls.UserControl>구성 요소 이름을 지정 하 고 이벤트 처리기에서 참조, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 그런 다음 코드에서 명명된 요소를 참조하고 이벤트 처리기를 정의할 수 있습니다. 이 개발 모델은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 애플리케이션 개발에 사용된 모델과 매우 유사합니다.  
  
 올바르게 빌드된 경우를 <xref:System.Windows.Controls.UserControl> 풍부한 콘텐츠, 스타일 및 트리거의 이점을 활용할 수 있습니다. 그러나 컨트롤에서 상속 하는 경우 <xref:System.Windows.Controls.UserControl>, 컨트롤을 사용 하는 사용자가 사용할 수는 <xref:System.Windows.DataTemplate> 또는 <xref:System.Windows.Controls.ControlTemplate> 모양을 사용자 지정할 수 있습니다.  파생 하는 데 필요한 것은 <xref:System.Windows.Controls.Control> 클래스 또는 해당 파생된 클래스 중 하나 (이외의 <xref:System.Windows.Controls.UserControl>) 템플릿을 지 원하는 사용자 지정 컨트롤을 만들려면.  
  
#### <a name="benefits-of-deriving-from-usercontrol"></a>UserControl에서 파생하는 이점  
 파생 하는 것이 좋습니다. <xref:System.Windows.Controls.UserControl> 모두 적용 하는 경우:  
  
-   애플리케이션을 빌드하는 방법과 유사하게 컨트롤을 빌드하려고 합니다.  
  
-   컨트롤이 기존 구성 요소로만 구성됩니다.  
  
-   복잡한 사용자 지정을 지원하지 않아도 됩니다.  
  
### <a name="deriving-from-control"></a>Control에서 파생  
 파생 된 <xref:System.Windows.Controls.Control> 클래스는 대부분의 기존 사용 모델은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤입니다. 상속 되는 컨트롤을 만들 때의 <xref:System.Windows.Controls.Control> 클래스 모양을 사용 하 여 정의한 템플릿. 그렇게 함으로써 작동 논리를 시각적 표현과 분리합니다. 이벤트 및 피해에 요소를 참조 하는 대신 명령 및 바인딩을 사용 하 여 UI 및 논리 분리를 보장할 수도 있습니다는 <xref:System.Windows.Controls.ControlTemplate> 가능 합니다.  컨트롤의 사용자 컨트롤의 UI와 컨트롤의 논리가 적절히 분리 되 하는 경우 재정의할 수 <xref:System.Windows.Controls.ControlTemplate> 모양을 사용자 지정할 수 있습니다. 사용자 지정 빌드 하지만 <xref:System.Windows.Controls.Control> 구성으로 간단 하지 않습니다는 <xref:System.Windows.Controls.UserControl>, 사용자 지정 <xref:System.Windows.Controls.Control> 최대한의 유연성을 제공 합니다.  
  
#### <a name="benefits-of-deriving-from-control"></a>Control에서 파생하는 이점  
 파생 되는 것이 좋습니다 <xref:System.Windows.Controls.Control> 사용 하는 대신는 <xref:System.Windows.Controls.UserControl> 클래스 경우 다음이 적용 됩니다.  
  
-   통해 사용자 지정이 가능 컨트롤의 모양을 원하는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
-   컨트롤이 다른 테마를 지원하게 하려고 합니다.  
  
### <a name="deriving-from-frameworkelement"></a>FrameworkElement에서 파생  
 파생 된 컨트롤 <xref:System.Windows.Controls.UserControl> 또는 <xref:System.Windows.Controls.Control> 기존 요소를 구성에 의존 합니다. 대부분의 시나리오에 적합 한 솔루션, 때문에 이것이에서 상속 되는 모든 개체 <xref:System.Windows.FrameworkElement> 수는 <xref:System.Windows.Controls.ControlTemplate>합니다. 그러나 컨트롤의 모양이 단순한 요소 컴퍼지션 이상의 기능을 필요로 하는 경우가 있습니다. 이러한 시나리오에 대 한 구성 요소를 기반으로 <xref:System.Windows.FrameworkElement> 적합 합니다.  
  
 두 가지가 있습니다 표준 구성에 대 한 <xref:System.Windows.FrameworkElement>-기반 구성: 직접 렌더링과 사용자 지정 요소 컴퍼지션입니다. 직접 렌더링에서는 재정의 <xref:System.Windows.UIElement.OnRender%2A> 메서드의 <xref:System.Windows.FrameworkElement> 제공 하 고 <xref:System.Windows.Media.DrawingContext> 구성 요소 시각적 개체를 명시적으로 정의 하는 작업입니다. 이 사용 하는 방법 <xref:System.Windows.Controls.Image> 고 <xref:System.Windows.Controls.Border>입니다. 형식의 개체를 사용 하 여 사용자 지정 요소 컴퍼지션을 포함 <xref:System.Windows.Media.Visual> 모양을 구성 하는 구성 요소에 있습니다. 예제는 [DrawingVisual 개체 사용](../graphics-multimedia/using-drawingvisual-objects.md)을 참조하세요. <xref:System.Windows.Controls.Primitives.Track> 컨트롤의 예로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 지정 요소 컴퍼지션을 사용 하는 합니다. 직접 렌더링과 사용자 지정 요소 컴퍼지션을 같은 컨트롤에서 혼합하여 사용할 수도 있습니다.  
  
#### <a name="benefits-of-deriving-from-frameworkelement"></a>FrameworkElement에서 파생하는 이점  
 파생 하는 것이 좋습니다. <xref:System.Windows.FrameworkElement> 경우 다음이 적용 됩니다.  
  
-   단순한 요소 컴퍼지션에서 제공하는 기능 이상으로 컨트롤의 모양을 정확하게 제어하려고 합니다.  
  
-   자체 렌더링 논리를 정의하여 컨트롤의 모양을 정의하려고 합니다.  
  
-   이동 가능한 것 보다 많은 새로운 방식으로 기존 요소를 구성 하려는 <xref:System.Windows.Controls.UserControl> 고 <xref:System.Windows.Controls.Control>입니다.  
  
<a name="control_authoring_basics"></a>   
## <a name="control-authoring-basics"></a>컨트롤 제작 기본 사항  
 앞에서 설명한 것처럼 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 가장 강력한 기능 중 하나는 컨트롤의 기본 속성 설정 이상으로 모양 및 동작을 변경하면서 사용자 지정 컨트롤을 만들지 않아도 되는 것입니다. 스타일 지정, 데이터 바인딩 및 트리거 기능은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템에 의해 가능합니다. 다음 섹션에서는 사용자 지정 컨트롤을 만드는 데 사용하는 모델에 관계없이 따라야 하는 몇 가지 방법을 설명합니다. 이에 따라 사용자 지정 컨트롤의 사용자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 포함된 컨트롤의 경우처럼 이러한 기능을 사용할 수 있습니다.  
  
### <a name="use-dependency-properties"></a>종속성 속성 사용  
 속성이 종속성 속성인 경우 다음을 수행할 수 있습니다.  
  
-   스타일에서 속성을 설정합니다.  
  
-   속성을 데이터 소스에 바인딩합니다.  
  
-   속성의 값으로 동적 리소스를 사용합니다.  
  
-   속성에 애니메이션 효과를 줍니다.  
  
 컨트롤의 속성이 이 기능을 지원하도록 하려면 종속성 속성으로 구현해야 합니다. 다음 예제에서는 다음을 수행하여 `Value`라는 종속성 속성을 정의합니다.  
  
-   정의 된 <xref:System.Windows.DependencyProperty> 라는 식별자 `ValueProperty` 으로 `public` `static` `readonly` 필드.  
  
-   호출 하 여 속성 시스템에 속성 이름을 등록 <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>, 다음을 지정 합니다.  
  
    -   속성의 이름입니다.  
  
    -   속성의 형식입니다.  
  
    -   속성을 소유하는 형식입니다.  
  
    -   속성의 메타데이터입니다. 메타 데이터 속성의 기본값을 포함 한 <xref:System.Windows.CoerceValueCallback> 및 <xref:System.Windows.PropertyChangedCallback>합니다.  
  
-   속성의 `get` 및 `set` 접근자를 구현하여 종속성 속성을 등록하는 데 사용된 이름과 동일한 이름인 `Value`라는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 래퍼 속성을 정의합니다. 합니다 `get` 하 고 `set` 접근자 에서만 호출할 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 각각. 것이 좋습니다는 종속성 속성의 접근자 추가 논리가 포함 되지 때문에 클라이언트와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 접근자 및 호출을 무시할 수 있습니다 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 직접. 예를 들어 속성이 데이터 소스에 바인딩되면 해당 속성의 `set` 접근자가 호출되지 않습니다.  Get에 논리를 추가 하는 대신 set 접근자를 사용 하 여 합니다 <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback>, 및 <xref:System.Windows.PropertyChangedCallback> 응답할 변경 되 면 값을 확인 하는 대리자입니다.  이 콜백에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../advanced/dependency-property-callbacks-and-validation.md)를 참조하세요.  
  
-   메서드를 정의 합니다 <xref:System.Windows.CoerceValueCallback> 라는 `CoerceValue`합니다. `CoerceValue` 되도록 `Value` 크거나 같음 `MinValue` 보다 작거나 같음 `MaxValue`합니다.  
  
-   메서드를 정의 합니다 <xref:System.Windows.PropertyChangedCallback>명명 된 `OnValueChanged`합니다. `OnValueChanged` 만듭니다는 <xref:System.Windows.RoutedPropertyChangedEventArgs%601> 개체를 발생 시킬 준비를 `ValueChanged` 라우트된 이벤트입니다. 라우트된 이벤트는 다음 섹션에서 설명합니다.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 자세한 내용은 [사용자 지정 종속성 속성](../advanced/custom-dependency-properties.md)을 참조하세요.  
  
### <a name="use-routed-events"></a>라우트된 이벤트 사용  
 종속성 속성이 추가 기능으로 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성의 개념을 확장하는 것처럼 라우트된 이벤트가 표준 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트의 개념을 확장합니다. 라우트된 이벤트는 다음 동작을 지원하기 때문에 새로운 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 만들 때 이벤트를 라우트된 이벤트로 구현하는 것도 좋습니다.  
  
-   이벤트는 여러 컨트롤의 부모에서 처리될 수 ​​있습니다. 이벤트가 버블링 이벤트인 경우 요소 트리의 단일 부모가 이벤트를 구독할 수 있습니다. 그런 다음 애플리케이션 작성자는 하나의 처리기를 사용하여 여러 컨트롤의 이벤트에 응답할 수 있습니다. 예를 들어, 컨트롤의 각 항목의 일부인 경우는 <xref:System.Windows.Controls.ListBox> (에 포함 되어 있기 때문에 <xref:System.Windows.DataTemplate>), 응용 프로그램 개발자에 컨트롤의 이벤트에 대 한 이벤트 처리기를 정의할 수는 <xref:System.Windows.Controls.ListBox>합니다. 이벤트가 컨트롤 중 하나에서 발생할 때마다 이벤트 처리기가 호출됩니다.  
  
-   라우트된 이벤트에 사용할 수는 <xref:System.Windows.EventSetter>, 응용 프로그램 개발자가 스타일 내에서 이벤트 처리기를 지정할 수 있습니다.  
  
-   라우트된 이벤트에 사용할 수는 <xref:System.Windows.EventTrigger>, 속성에 애니메이션 효과 사용 하 여 유용한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 자세한 내용은 [애니메이션 개요](../graphics-multimedia/animation-overview.md)를 참조하세요.  
  
 다음 예제는 다음을 수행하여 라우트된 이벤트를 정의합니다.  
  
-   정의 된 <xref:System.Windows.RoutedEvent> 라는 식별자 `ValueChangedEvent` 으로 `public` `static` `readonly` 필드.  
  
-   라우트된 이벤트를 호출 하 여 등록 된 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> 메서드. 예제를 호출할 때 다음 정보를 지정 합니다 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>:  
  
    -   이벤트의 이름은 `ValueChanged`입니다.  
  
    -   라우팅 전략은 <xref:System.Windows.RoutingStrategy.Bubble>, 즉, 원본 (이벤트를 발생 시키는 개체)에서 이벤트 처리기를 먼저 호출 하 고 연속으로 가장 가까운에서 이벤트 처리기를 사용 하 여 시작 소스의 부모 요소에서 이벤트 처리기가 호출 하는 다음 부모 요소입니다.  
  
    -   이벤트 처리기의 유형은 <xref:System.Windows.RoutedPropertyChangedEventHandler%601>를 통해 생성 된를 <xref:System.Decimal> 형식입니다.  
  
    -   이벤트의 소유 형식은 `NumericUpDown`입니다.  
  
-   `ValueChanged`라는 공용 이벤트를 선언하고 이벤트 접근자 선언을 포함합니다. 예제에서는 <xref:System.Windows.UIElement.AddHandler%2A> 에 `add` 접근자 선언의 및 <xref:System.Windows.UIElement.RemoveHandler%2A> 에 `remove` 접근자 선언을 사용 하 여는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 서비스.  
  
-   `ValueChanged` 이벤트를 발생시키는 `OnValueChanged`라는 보호된 가상 메서드를 만듭니다.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 자세한 내용은 [라우트된 이벤트 개요](../advanced/routed-events-overview.md) 및 [사용자 지정 라우트된 이벤트 만들기](../advanced/how-to-create-a-custom-routed-event.md)를 참조하세요.  
  
### <a name="use-binding"></a>바인딩 사용  
 해당 논리에서 컨트롤의 UI를 분리하려면 데이터 바인딩 사용을 고려합니다. 이 사용 하 여 컨트롤의 모양을 정의 하는 경우에 특히 중요 한 <xref:System.Windows.Controls.ControlTemplate>합니다. 데이터 바인딩을 사용하면 코드에서 UI의 특정 부분을 참조하지 않아도 될 수 있습니다. 요소를 참조 하지 않도록 하는 것이 좋습니다 합니다 <xref:System.Windows.Controls.ControlTemplate> 코드에 있는 요소를 참조 하는 경우 하기 때문에 <xref:System.Windows.Controls.ControlTemplate> 및 <xref:System.Windows.Controls.ControlTemplate> 변경 되는 참조 된 요소가 포함 해야 새 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 다음 예에서는 업데이트를 <xref:System.Windows.Controls.TextBlock> 의 `NumericUpDown` 컨트롤 이름을 할당 하 고 텍스트 상자 코드에서 이름으로 참조 합니다.  
  
 [!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 다음 예제에서는 바인딩을 사용하여 동일한 작업을 수행합니다.  
  
 [!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.  
  
### <a name="design-for-designers"></a>디자이너를 위한 디자인  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]에서 사용자 지정 WPF 컨트롤에 대한 지원을 받으려면(예:속성 창에서 속성 편집) 다음 지침을 따릅니다.  개발에 대 한 자세한 내용은 합니다 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]를 참조 하세요 [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)합니다.  
  
#### <a name="dependency-properties"></a>종속성 속성  
 앞의 "종속성 속성 사용"에서 설명한 대로 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] `get` 및 `set` 접근자를 구현해야 합니다. 디자이너는 래퍼를 사용하여 종속성 속성의 존재를 감지할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 컨트롤의 클라이언트와 마찬가지로 속성을 가져오거나 설정할 때 접근자를 호출할 필요가 없습니다.  
  
#### <a name="attached-properties"></a>연결된 속성  
 다음 지침을 사용하여 사용자 지정 컨트롤에서 연결된 속성을 구현해야 합니다.  
  
-   가 `public` `static` `readonly` <xref:System.Windows.DependencyProperty> 형식의 *PropertyName* `Property` 사용 하 여 만들기가 있는 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드. 에 전달 되는 속성 이름을 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 같아야 *PropertyName*합니다.  
  
-   `Set`*PropertyName* 및 `Get`*PropertyName*이라는 `public` `static` CLR 메서드 쌍을 구현합니다. 두 메서드 모두에서 파생 된 클래스를 허용 해야 <xref:System.Windows.DependencyProperty> 첫 번째 인수로 합니다. `Set`*PropertyName* 메서드는 그 형식이 속성의 등록된 데이터 형식과 일치하는 인수도 수락합니다. `Get`*PropertyName* 메서드는 동일한 형식의 값을 반환해야 합니다. `Set`*PropertyName* 메서드가 누락된 경우 속성이 읽기 전용으로 표시됩니다.  
  
-   `Set` **PropertyName* 및 `Get` *PropertyName* 직접 라우팅해야 합니다 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 각각의 대상 종속성 메서드 개체입니다.D디자이너는 메서드 래퍼를 통해 호출하거나 대상 종속성 개체를 직접 호출하여 연결된 속성에 액세스할 수 있습니다.  
  
 연결된 속성에 대한 자세한 내용은 [연결된 속성 개요](../advanced/attached-properties-overview.md)를 참조하세요.  
  
### <a name="define-and-use-shared-resources"></a>공유 리소스 정의 및 사용  
 애플리케이션과 동일한 어셈블리에 컨트롤을 포함하거나 여러 애플리케이션에서 사용할 수 있는 별도의 어셈블리에 컨트롤을 패키지화할 수 있습니다. 대부분, 이 항목에서 설명하는 정보는 사용하는 메서드에 관계없이 적용됩니다.  그러나 주목할 만한 차이점이 하나 있습니다.  애플리케이션과 동일한 어셈블리에 컨트롤을 배치하면 App.xaml 파일에 전역 리소스를 자유롭게 추가할 수 있습니다. 컨트롤만 포함 되어 있는 어셈블리로 없는 <xref:System.Windows.Application> App.xaml 파일을 사용할 수 있도록 연결 된 개체입니다.  
  
 애플리케이션이 리소스를 찾을 때 다음 순서로 세 가지 수준을 조사합니다.  
  
1. 요소 수준  
  
     시스템이 리소스를 참조하는 요소로 시작한 다음 루트 요소에 도달할 때까지 논리 부모 등의 리소스를 검색합니다.  
  
2. 애플리케이션 수준  
  
     정의 된 리소스는 <xref:System.Windows.Application> 개체입니다.  
  
3. 테마 수준  
  
     테마 수준 사전은 Themes라는 하위 폴더에 저장됩니다.  Themes 폴더의 파일은 테마에 해당합니다.  예를 들어 Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml 등이 있을 수 있습니다.  generic.xaml이라는 파일이 있을 수도 있습니다.  시스템이 테마 수준에서 리소스를 찾으면 먼저 테마별 파일에서 찾은 다음 generic.xaml에서 찾습니다.  
  
 컨트롤이 애플리케이션과 별도의 어셈블리에 있을 때는 전역 리소스를 요소 수준이나 테마 수준에 배치해야 합니다. 두 가지 방법 모두 장점이 있습니다.  
  
#### <a name="defining-resources-at-the-element-level"></a>요소 수준에서 리소스 정의  
 사용자 지정 리소스 사전을 만들어 컨트롤 리소스 사전과 병합하면 요소 수준에서 공유 리소스를 정의할 수 있습니다.  이 메서드를 사용하면 리소스 파일의 이름을 원하는 대로 지정할 수 있으며 컨트롤과 동일한 폴더에 배치할 수 있습니다. 요소 수준의 리소스는 간단한 문자열을 키로 사용할 수도 있습니다. 다음 예제에서는 <xref:System.Windows.Media.LinearGradientBrush> Dictionary1.xaml 라는 리소스 파일입니다.  
  
 [!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 사전을 정의한 후에는 컨트롤의 리소스 사전과 병합해야 합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드를 사용하여 이 작업을 수행할 수 있습니다.  
  
 다음 예제는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 리소스 사전을 병합합니다.  
  
 [!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 이 방식의 단점은 <xref:System.Windows.ResourceDictionary> 개체가 참조 될 때마다 만들어집니다.  예를 들어 10 개의 사용자 지정 컨트롤 라이브러리에 XAML을 사용 하 여 각 컨트롤에 대 한 공유 리소스 사전을 병합 하는 경우 만든 10 동일한 <xref:System.Windows.ResourceDictionary> 개체입니다.  코드에서 리소스를 병합 하 고 결과 반환 하는 정적 클래스를 만들어이 방지 하려면 <xref:System.Windows.ResourceDictionary>합니다.  
  
 다음 예제에서는 공유를 반환 하는 클래스를 만듭니다 <xref:System.Windows.ResourceDictionary>합니다.  
  
 [!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 다음 예제에서는 공유 리소스를 `InitializeComponent`를 호출하기 전에 컨트롤의 생성자에 있는 사용자 지정 컨트롤의 리소스와 병합합니다.  때문에 `SharedDictionaryManager.SharedDictionary` 는 정적 속성에는 <xref:System.Windows.ResourceDictionary> 한 번만 만들어집니다. `InitializeComponent`가 호출되기 전에 리소스 사전이 병합되었기 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 컨트롤에서 리소스를 사용할 수 있습니다.  
  
 [!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### <a name="defining-resources-at-the-theme-level"></a>테마 수준에서 리소스 정의  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다양 한 Windows 테마에 대 한 리소스를 만들 수 있습니다.  컨트롤 작성자는 특정 테마의 리소스를 정의하여 사용 중인 테마에 따라 컨트롤의 모양을 변경할 수 있습니다. 모양의 예를 들어를 <xref:System.Windows.Controls.Button> Windows 클래식에서 테마 (Windows 2000의 기본 테마)에서 다릅니다를 <xref:System.Windows.Controls.Button> Windows Luna 테마 (Windows XP의 기본 테마) 때문에 <xref:System.Windows.Controls.Button> 다른을 사용 하 여 <xref:System.Windows.Controls.ControlTemplate> 각 테마입니다.  
  
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
  
 [테마 및 UI 자동화 지원이 있는 NumericUpDown 사용자 지정 컨트롤 샘플](https://go.microsoft.com/fwlink/?LinkID=160025)에는 `NumericUpDown` 컨트롤에 대한 두 개의 리소스 사전이 있습니다. 하나는 generic.xaml에 있고 다른 하나는 Luna.NormalColor.xaml에 있습니다.  애플리케이션을 실행하고 Windows XP의 은색 테마와 다른 테마 사이를 전환하여 두 컨트롤 템플릿의 차이점을 확인할 수 있습니다. (Windows Vista를 실행하는 경우 Luna.NormalColor.xaml의 이름을 Aero.NormalColor.xaml로 바꾸고 Windows 고전 및 Windows Vista의 기본 테마와 같은 두 테마 사이에서 전환할 수 있습니다.)  
  
 삽입 했을 때를 <xref:System.Windows.Controls.ControlTemplate> 제어 및 호출에 대 한 정적 생성자는 테마별 리소스 사전 파일 중 하나를 만들어야 합니다 <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> 메서드를는 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>다음 예제에서와 같이 합니다.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### <a name="defining-and-referencing-keys-for-theme-resources"></a>테마 리소스에 대한 키 정의 및 참조  
 요소 레벨에서 리소스를 정의할 때 문자열을 키로 지정하고 문자열을 통해 리소스에 액세스할 수 있습니다. 테마 수준에서 리소스를 정의할 때 사용 해야는 <xref:System.Windows.ComponentResourceKey> 키로 합니다.  다음 예제에서는 generic.xaml에서 리소스를 정의합니다.  
  
 [!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]  
  
 다음 예제에서는 리소스를 지정 하 여 참조를 <xref:System.Windows.ComponentResourceKey> 키로 합니다.  
  
 [!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]  
  
##### <a name="specifying-the-location-of-theme-resources"></a>테마 리소스의 위치 지정  
 컨트롤에 대한 리소스를 찾으려면 호스팅 애플리케이션이 어셈블리에 컨트롤 관련 리소스가 있는지 알아야 합니다. 추가 하 여 수행할 수 있습니다는 <xref:System.Windows.ThemeInfoAttribute> 컨트롤이 포함 된 어셈블리에 있습니다. 합니다 <xref:System.Windows.ThemeInfoAttribute> 에 <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> 제네릭 리소스의 위치를 지정 하는 속성 및 <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> 테마별 리소스의 위치를 지정 하는 속성입니다.  
  
 다음 예제에서는 합니다 <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> 하 고 <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> 속성을 <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>제네릭 및 테마별 리소스가 컨트롤과 동일한 어셈블리에는 지정 합니다.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## <a name="see-also"></a>참고자료

- [Visual Studio에서 XAML 디자인](/visualstudio/designers/designing-xaml-in-visual-studio)
- [WPF의 Pack URI](../app-development/pack-uris-in-wpf.md)
- [컨트롤 사용자 지정](control-customization.md)
