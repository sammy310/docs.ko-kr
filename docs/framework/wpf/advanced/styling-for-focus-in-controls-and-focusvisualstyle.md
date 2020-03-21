---
title: 컨트롤의 포커스 스타일 지정 및 FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: fda7ed12d232af5a7cfb8eb43cbb09eb793da171
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141201"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>컨트롤의 포커스 스타일 지정 및 FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 컨트롤이 키보드 포커스를 받을 때 컨트롤의 시각적 모양을 변경하는 두 가지 병렬 메커니즘을 제공합니다. 첫 번째 메커니즘은 컨트롤에 적용되는 스타일 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 이나 템플릿 내에서 와 같은 속성에 속성 setter를 사용 하는 것입니다. 두 번째 메커니즘은 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성값으로 별도의 스타일을 제공하는 것입니다. "포커스 비주얼 스타일"은 컨트롤 또는 다른 UI 요소의 시각적 트리를 대체하여 변경하는 대신 컨트롤 위에 그리는 표시기에 대해 별도의 시각적 트리를 만듭니다. 이 항목에서는 이러한 각 메커니즘이 적절하게 적용되는 시나리오를 설명합니다.  

<a name="Purpose"></a>
## <a name="the-purpose-of-focus-visual-style"></a>포커스 비주얼 스타일의 목적  
 포커스 비주얼 스타일 기능은 UI 요소에 대한 키보드 탐색에 따라 시각적 사용자 피드백을 추가하기 위한 공통 “개체 모델”을 제공합니다. 이 작업은 컨트롤에 새 템플릿을 적용하거나 특정 템플릿 컴퍼지션을 인식하지 않아도 가능합니다.  
  
 하지만 정확히는 포커스 비주얼 스타일 기능은 컨트롤 템플릿을 인식하지 않고 작동하므로 포커스 비주얼 스타일을 통해 컨트롤에 대해 표시될 수 있는 시각적 피드백은 제한되어야 합니다. 이 기능이 실제로 수행하는 작업은 템플릿을 사용한 컨트롤 렌더링에서 만들어진 것처럼 시각적 트리 위에 다른 시각적 트리(표시기)를 오버레이하는 것입니다. 속성을 채우는 스타일을 사용하여 이 별도의 시각적 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 트리를 정의합니다.  
  
<a name="Default"></a>
## <a name="default-focus-visual-style-behavior"></a>기본 포커스 비주얼 스타일 동작  
 포커스 비주얼 스타일은 포커스 작업이 키보드에서 시작된 경우에만 적용됩니다. 마우스 작업이나 프로그래밍 방식 포커스 변경인 경우에는 포커스 비주얼 스타일 모드가 적용되지 않습니다. 포커스 모드 간의 차이점에 대한 자세한 내용은 [포커스 개요](focus-overview.md)를 참조하세요.  
  
 컨트롤에 대한 테마에는 테마의 모든 컨트롤에 대한 포커스 비주얼 스타일이 되는 기본 포커스 비주얼 스타일 동작이 포함됩니다. 이 테마 스타일은 정적 키의 <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>값으로 식별됩니다. 애플리케이션 수준에서 자체 포커스 비주얼 스타일을 선언하면 테마에서 이 기본 스타일 동작이 대체됩니다. 또는 전체 테마를 정의할 경우 이 동일한 키를 사용하여 전체 테마의 기본 동작에 대한 스타일을 정의해야 합니다.  
  
 일반적으로 테마에서 기본 포커스 비주얼 스타일은 매우 간단합니다. 대략적인 설명은 다음과 같습니다.  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>
## <a name="when-to-use-focus-visual-styles"></a>포커스 비주얼 스타일을 사용하는 시점  
 개념상 컨트롤에 적용되는 포커스 비주얼 스타일의 모양은 컨트롤 간에 일관되어야 합니다. 일관성을 유지하는 한 가지 방법은 전체 테마를 작성할 경우에만 포커스 비주얼 스타일을 변경하는 것입니다. 이 경우 테마에 정의된 각 컨트롤이 똑같은 포커스 비주얼 스타일을 가져오거나 컨트롤 간에 시각적으로 관련된 스타일의 일부 변형을 가져옵니다. 또는 같은 스타일(또는 비슷한 스타일)을 사용하여 페이지 또는 UI에서 모든 키보드 포커스 가능 요소에 스타일을 지정할 수 있습니다.  
  
 테마에 포함되지 않은 개별 컨트롤 스타일을 설정하는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 것은 포커스 비주얼 스타일을 의도한 용도가 아닙니다. 이는 컨트롤 간에 시각적 동작이 일치하지 않으면 키보드 포커스에 대한 사용자 환경이 복잡해질 수 있기 때문입니다. 의도적으로 테마 간에 일관성이 없는 키보드 포커스에 대한 컨트롤 별 동작을 계획하는 경우, 훨씬 더 나은 방법은 또는 또는 와 <xref:System.Windows.UIElement.IsFocused%2A> <xref:System.Windows.UIElement.IsKeyboardFocused%2A>같은 개별 입력 상태 속성에 대한 스타일에서 트리거를 사용하는 것입니다.  
  
 포커스 비주얼 스타일은 키보드 포커스와 함께 사용되지 않습니다. 마찬가지로 포커스 비주얼 스타일은 접근성 기능의 형식입니다. 마우스, 키보드 또는 프로그래밍 방식이든 관계없이 포커스 형식에 따라 UI가 변경되게 하려면 포커스 비주얼 스타일을 사용하면 안 되며 <xref:System.Windows.UIElement.IsFocused%2A> 또는 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>과 같은 일반 포커스 속성의 값에 따라 작동하는 스타일 또는 템플릿에서 setter 및 트리거를 사용해야 합니다.  
  
<a name="How"></a>
## <a name="how-to-create-a-focus-visual-style"></a>포커스 비주얼 스타일을 만드는 방법  
 포커스 비주얼 스타일에 대해 만든 스타일에는 <xref:System.Windows.Style.TargetType%2A> 항상 <xref:System.Windows.Controls.Control>의 가 있어야 합니다. 스타일은 주로 로 구성되어야 <xref:System.Windows.Controls.ControlTemplate>합니다. 포커스 시각적 스타일이 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>에 할당된 유형으로 대상 유형을 지정하지 않습니다.  
  
 대상 형식은 항상 <xref:System.Windows.Controls.Control>있으므로 모든 컨트롤에 공통적인 <xref:System.Windows.Controls.Control> 속성(클래스 및 해당 기본 클래스의 속성 사용)을 사용하여 스타일을 지정해야 합니다. UI 요소에 대한 오버레이로 제대로 작동하고 컨트롤의 기능 영역을 가리지 않는 템플릿을 만들어야 합니다. 일반적으로 이는 시각적 피드백은 컨트롤 여백 외부에 표시되거나 포커스 비주얼 스타일이 적용되는 컨트롤에 대한 적중 테스트를 차단하지 않는 일시적이거나 간섭하지 않는 효과로 표시어야 함을 의미합니다. 오버레이 템플릿의 크기 조정 및 위치를 결정하는 데 유용한 템플릿 바인딩에 <xref:System.Windows.FrameworkElement.ActualHeight%2A>사용할 <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.Margin%2A>수 <xref:System.Windows.Controls.Control.Padding%2A>있는 속성에는 및 .  
  
<a name="Alternatives"></a>
## <a name="alternatives-to-using-a-focus-visual-style"></a>포커스 비주얼 스타일 사용의 대체 방법  
 포커스 비주얼 스타일이 적절하지 않은 상황에서는 단일 컨트롤에만 스타일을 지정하거나 컨트롤 템플릿보다 더 큰 컨트롤이 필요하기 때문에 포커스 변경에 대한 응답으로 시각적 동작을 만들 수 있는 많은 다른 액세스 가능한 속성 및 기술이 있습니다.  
  
 트리거, setter 및 이벤트 setter는 모두 [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)에서 자세히 설명합니다. 라우트된 이벤트 처리는 [라우트된 이벤트 개요](routed-events-overview.md)에서 설명합니다.  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 키보드 포커스에 특히 관심이 있는 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 경우 속성에 대 한 <xref:System.Windows.Trigger>종속성 속성을 사용할 수 있습니다. 단일 컨트롤에만 관련되고 다른 컨트롤의 키보드 포커스 동작과 시각적으로 일치하지 않는 키보드 포커스 동작을 정의할 경우 스타일 또는 템플릿의 속성 트리거가 더 적절한 기술입니다.  
  
 또 다른 유사한 종속성 속성은 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>키보드 포커스가 합성 내 또는 컨트롤의 기능 영역 내에 있음을 시각적으로 호출하려는 경우 사용하기에 적합할 수 있습니다. 예를 들어 키보드 포커스가 해당 패널 내의 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 개별 요소에 더 정확하게 배치될 수 있더라도 여러 컨트롤을 그룹화하는 패널이 다르게 표시되도록 트리거를 배치할 수 있습니다.  
  
 이벤트 <xref:System.Windows.UIElement.GotKeyboardFocus> 및 <xref:System.Windows.UIElement.LostKeyboardFocus> 프리뷰 등가물을 사용할 수도 있습니다. 이러한 이벤트를 <xref:System.Windows.EventSetter>의 기준으로 사용하거나 코드 숨결에서 이벤트에 대한 처리기를 작성할 수 있습니다.  
  
### <a name="other-focus-properties"></a>기타 포커스 속성  
 포커스를 변경하여 시각적 동작을 생성하려는 경우 setter 또는 <xref:System.Windows.UIElement.IsFocused%2A> 트리거를 종속성 속성에 기반하거나 <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus> <xref:System.Windows.EventSetter>에 사용되는 또는 이벤트에 대해 수행해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [포커스 개요](focus-overview.md)
- [입력 개요](input-overview.md)
