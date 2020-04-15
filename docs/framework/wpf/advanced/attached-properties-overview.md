---
title: 연결된 속성 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 5086401f4616074d364c1d387b751116120d5969
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389007"
---
# <a name="attached-properties-overview"></a>연결된 속성 개요

연결된 속성은 XAML로 정의되는 개념입니다. 연결된 속성은 모든 개체에 설정할 수 있는 전역 속성의 형식으로 사용할 수 있습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서, 연결된 속성은 일반적으로 기존 속성 "래퍼"가 없는 종속성 속성의 특수 형식으로 정의됩니다.

## <a name="prerequisites"></a>필수 구성 요소<a name="prerequisites"></a>

이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에서 기존 종속성 속성의 이용자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](dependency-properties-overview.md)를 읽었다고 가정합니다. 이 항목의 예제를 따르려면 XAML을 이해하고 WPF 응용 프로그램을 작성하는 방법을 알고 있어야 합니다.

## <a name="why-use-attached-properties"></a>연결된 속성을 사용하는 이유<a name="attached_properties_usage"></a>

연결된 속성의 한 가지 목적은 다른 자식 요소가 부모 요소에서 실제로 정의되는 속성의 고유 값을 저장하도록 하는 것입니다. 이 시나리오의 특정 애플리케이션에서 자식 요소는 부모 요소에 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에서 표시되는 방법을 알립니다. 한 가지 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 예는 속성입니다. 속성은 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.DockPanel> 자체가 아니라 에 포함된 요소에 설정되도록 설계되었기 때문에 연결된 속성으로 만들어집니다. <xref:System.Windows.Controls.DockPanel> 클래스는 명명된 <xref:System.Windows.DependencyProperty> <xref:System.Windows.Controls.DockPanel.DockProperty>정적 필드를 정의한 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 다음 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 및 메서드를 연결된 속성에 대한 공용 접근자로 제공합니다.

## <a name="attached-properties-in-xaml"></a>XAML의 연결된 속성<a name="attached_properties_xaml"></a>

XAML에서 구문 *AttachedPropertyProvider*.* PropertyName*을 사용하여 연결된 속성을 설정합니다.

다음은 XAML에서 설정하는 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 방법의 예입니다.

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

사용량은 정적 속성과 다소 유사합니다. 이름으로 지정된 인스턴스를 참조하는 대신 항상 연결된 속성을 소유하고 등록하는 형식을 <xref:System.Windows.Controls.DockPanel> 참조합니다.

또한 XAML에서 연결된 속성은 표시로 설정한 특성이므로 집합 작업만 관련됩니다. 스타일의 트리거와 같은 값을 비교하기 위한 일부 간접 메커니즘이 있더라도 XAML에서 속성을 직접 가져올 수 없습니다(자세한 내용은 [스타일 및 템플릿](../controls/styling-and-templating.md) 참조).

### <a name="attached-property-implementation-in-wpf"></a>WPF에서 연결된 속성 구현

에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]UI 프레젠테이션과 관련된 WPF 형식에 있는 대부분의 연결된 속성은 종속성 속성으로 구현됩니다. 연결된 속성은 XAML 개념이지만 종속성 속성은 WPF 개념입니다. WPF 연결 속성은 종속성 속성이므로 속성 메타데이터와 같은 종속성 속성 개념 및 해당 속성 메타데이터의 기본값을 지원합니다.

## <a name="how-attached-properties-are-used-by-the-owning-type"></a>소유 형식에서 연결된 속성을 사용하는 방법<a name="howused"></a>

연결된 속성을 개체에 설정할 수 있지만, 속성 설정이 명확한 결과를 생성하거나 다른 개체에서 값을 사용함을 의미하지 않습니다. 일반적으로 다양한 논리적 관계 또는 클래스 계층 구조의 개체가 연결된 속성을 정의하는 형식에 각 보고서 공통 정보를 보고할 수 있도록 연결된 속성이 사용됩니다. 연결된 속성을 정의하는 형식은 이러한 모델 중 하나를 따릅니다.

- 연결된 속성의 값을 설정하는 요소의 부모 요소가 될 수 있도록 연결된 속성을 정의하는 형식을 사용할 수 있습니다. 그러면 형식은 일부 개체 트리 구조에 대조적으로 내부 논리를 통해 자식 개체를 반복하며, 값을 가져오며 다른 방법으로 이러한 값에 작업을 수행합니다.

- 연결된 속성을 정의하는 형식은 가능한 다양한 부모 요소와 콘텐츠 모델에 대한 자식 요소로 사용됩니다.

- 연결된 속성을 정의하는 형식은 서비스를 나타냅니다. 다른 형식은 연결된 속성에 대한 값을 설정합니다. 그런 다음 속성을 설정하는 요소를 서비스의 컨텍스트에서 계산하는 경우, 연결된 속성 값은 서비스 클래스의 내부 논리를 통해 얻습니다.

### <a name="an-example-of-a-parent-defined-attached-property"></a>부모 정의되어 연결된 속성의 예

WPF가 연결된 속성을 정의하는 가장 일반적인 시나리오는 부모 요소가 자식 요소 컬렉션을 지원하고 각 자식 요소에 대해 동작의 세부 사항이 개별적으로 보고되는 동작을 구현하는 경우입니다.

<xref:System.Windows.Controls.DockPanel>연결된 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 속성을 정의 <xref:System.Windows.Controls.DockPanel> 하 고 렌더링 논리 (특히) <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> 및 <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>클래스 수준 코드의 일부로 있습니다. 인스턴스는 <xref:System.Windows.Controls.DockPanel> 항상 해당 하위 요소중 어느 요소에 대한 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>값을 설정했는지 확인합니다. 그런 경우, 이 값은 해당 자식 요소에 적용된 렌더링 논리에 대한 입력이 됩니다. 중첩된 <xref:System.Windows.Controls.DockPanel> 인스턴스는 각각 고유한 자식 요소 컬렉션을 처리하지만 해당 <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 동작은 값을 처리하는 방법에 따라 구현에 따라 다릅니다. 이론적으로 직계 부모를 넘어서 요소에 영향을 주는 연결된 속성이 있을 수 있습니다. <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 연결된 속성이 해당 요소에 대해 작동할 상위 요소가 없는 <xref:System.Windows.Controls.DockPanel> 요소에 설정되어 있으면 오류 나 예외가 발생하지 않습니다. 이는 단순히 전역 속성 값이 설정되었지만 정보를 사용할 <xref:System.Windows.Controls.DockPanel> 수 있는 현재 부모가 없음을 의미합니다.

## <a name="attached-properties-in-code"></a>코드에서 첨부된 속성<a name="attached_properties_code"></a>

WPF에 연결된 속성에는 쉽게 액세스/설정할 수 있는 일반적인 CLR "래퍼" 메서드가 없습니다. 이는 연결된 속성이 속성이 설정된 인스턴스의 CLR 네임스페이스의 일부가 아닐 수 있기 때문입니다. 그러나 XAML 프로세서는 XAML을 구문 분석할 때 이러한 값을 설정할 수 있어야 합니다. 효과적인 연결된 속성 사용을 지원하려면 연결된 속성의 소유자 형식은 **Get_PropertyName_** 및 **Set_PropertyName_** 형식으로 전용 접근자 메서드를 구현해야 합니다. 이 전용 접근자 메서드는 코드로 연결된 속성을 가져오거나 설정하는 데도 유용합니다. 코드의 관점에서 연결된 속성은 속성 접근자 대신 메서드 접근자가 있는 지원 필드와 유사하며, 지원 필드는 구체적으로 정의될 필요 없이 모든 개체에 있을 수 있습니다.

다음 예제에서는 코드에서 연결된 속성을 설정하는 방법을 보여 줍니다. 이 예제에서는 `myCheckBox` 클래스의 인스턴스입니다. <xref:System.Windows.Controls.CheckBox>

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

XAML 사례와 마찬가지로 `myCheckBox` 네 번째 코드 줄에 `myDockPanel` 의해 자식 요소로 아직 추가되지 않은 경우 다섯 번째 코드 줄은 예외를 <xref:System.Windows.Controls.DockPanel> 발생시키지 않지만 속성 값은 부모와 상호 작용하지 않으므로 아무 일도 하지 않습니다. 부모 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 요소의 존재와 결합된 자식 요소에 설정된 값만 렌더링된 응용 프로그램에서 효과적인 동작을 일으킵니다. <xref:System.Windows.Controls.DockPanel> (이 경우 연결된 속성을 설정한 다음 트리에 연결할 수 있습니다. 또는 트리에 연결한 다음 연결된 속성을 설정할 수 있습니다. 또는 동작 순서가 동일한 결과를 제공합니다.)

## <a name="attached-property-metadata"></a>첨부된 속성 메타데이터<a name="attached_properties_metadata"></a>

속성을 등록할 때 <xref:System.Windows.FrameworkPropertyMetadata> 속성이 렌더링, 측정 등에 영향을 미치는지 여부와 같은 속성의 특성을 지정하도록 설정됩니다. 연결된 속성에 대한 메타데이터는 일반적으로 종속성 속성과 차이가 없습니다. 연결된 속성 메타데이터 재정의에서 기본값을 지정하는 경우, 해당 값은 재정의 클래스의 인스턴스에서 암시적 연결된 속성의 기본값이 됩니다. 특히, 일부 프로세스가 해당 속성에 대한 `Get` 메서드 접근자를 통해 연결된 속성의 값을 쿼리하는 경우 기본값이 보고되어, 메타데이터를 지정한 클래스의 인스턴스 및 연결된 속성이 설정되지 않은 값을 지정합니다.

속성에 속성 값 상속을 사용하도록 설정하려는 경우, 연결되지 않은 종속성 속성이 아니라 연결된 속성을 사용해야 합니다. 자세한 내용은 [속성 값 상속을](property-value-inheritance.md)참조하십시오.

## <a name="custom-attached-properties"></a>사용자 지정 연결 속성<a name="custom"></a>

### <a name="when-to-create-an-attached-property"></a>첨부된 속성을 작성하는 시기<a name="create_attached_properties"></a>

클래스 정의 외에 클래스에 사용할 수 있는 메커니즘을 설정하는 이유가 있는 경우 연결된 속성을 만들 수 있습니다. 이에 대한 가장 일반적인 시나리오는 레이아웃입니다. 기존 레이아웃 속성의 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>예는 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>에서 입니다. 여기에서 사용 가능한 시나리오에서는 레이아웃 제어 요소에 대한 자식 요소로 존재하는 요소가 개별적으로 해당 레이아웃 부모 요소에 대한 레이아웃 요구사항을 표현할 수 있으며, 각각은 부모가 연결된 속성으로 정의한 속성 값을 설정합니다.

연결된 속성을 사용하기 위한 다른 시나리오는 클래스가 서비스를 나타내는 경우이며, 클래스는 서비스를 더 투명하게 통합할 수 있습니다.

또 다른 시나리오는 **속성** 창 편집과 같은 Visual Studio WPF 디자이너 지원을 받는 것입니다. 자세한 내용은 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하세요.

앞서 언급했듯이, 속성 값 상속을 사용하려는 경우 연결된 속성으로 등록해야 합니다.

### <a name="how-to-create-an-attached-property"></a>첨부된 속성을 작성하는 방법<a name="how_do_i_create_attached_properties"></a>

클래스가 다른 형식에서 사용하도록 연결된 속성을 엄격하게 정의하는 경우 클래스는 에서 <xref:System.Windows.DependencyObject>파생될 필요가 없습니다. 그러나 연결된 속성도 <xref:System.Windows.DependencyObject> 종속성 속성이 되는 전체 WPF 모델을 따르는 경우 파생해야 합니다.

형식 <xref:System.Windows.DependencyProperty>필드를 선언하여 연결된 속성을 종속성 `public static readonly` 속성으로 정의합니다. 메서드의 반환 값을 사용 하 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 여이 필드를 정의 합니다. 필드 이름은 문자열과 `Property`함께 추가된 연결된 속성 이름과 일치해야 식별 필드의 이름을 지정하는 기존 WPF 패턴을 따르고 해당 필드의 이름을 지정합니다. 연결된 속성 공급자는 연결된 속성에 대한 접근자로 정적 **Get_PropertyName_** 및 **Set_PropertyName_** 메서드도 제공해야 합니다. 이렇게 하지 않으면 속성 시스템이 연결된 속성을 사용할 수 없게 됩니다.

> [!NOTE]
> 연결된 속성의 get 접근자를 생략하면 Visual Studio 및 Visual Studio용 Blend와 같은 디자인 도구에서 속성의 데이터 바인딩이 작동하지 않습니다.

#### <a name="the-get-accessor"></a>Get 접근자

**Get_PropertyName_** 접근자의 서명은 다음과 같은 여야 합니다.

`public static object GetPropertyName(object target)`

- 구현에서 보다 구체적인 형식으로 `target` 개체를 지정할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> 메서드는 연결된 <xref:System.Windows.UIElement>속성이 <xref:System.Windows.UIElement> 인스턴스에서만 설정될 수 있도록 하기 때문에 매개 변수를 로 입력합니다.

- 구현에서 보다 구체적인 형식으로 반환 값을 지정할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 메서드는 값을 <xref:System.Windows.Controls.Dock>해당 열거형으로만 설정할 수 있으므로 을 로 입력합니다.

#### <a name="the-set-accessor"></a>Set 접근자

**Set_PropertyName_** 접근자의 서명은 다음과 같은 여야 합니다.

`public static void SetPropertyName(object target, object value)`

- 구현에서 보다 구체적인 형식으로 `target` 개체를 지정할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드는 연결된 <xref:System.Windows.UIElement>속성이 인스턴스에서만 <xref:System.Windows.UIElement> 설정될 수 있도록 하기 때문에 을 로 입력합니다.

- 구현에서 보다 구체적인 형식으로 `value` 개체를 지정할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드는 값을 <xref:System.Windows.Controls.Dock>해당 열거형으로만 설정할 수 있으므로 을 로 입력합니다. 태그의 연결된 속성 사용에서 연결된 속성에 있는 경우, 이 메서드의 값은 XAML 로더에서 오는 입력값임을 기억하십시오. 해당 입력값은 태그에는 XAML 특성 값으로 지정된 값입니다. 따라서 형식 변환, 값 직렬 변환기 또는 사용하는 형식에 대한 태그 확장 지원이 있어야, 적절한 형식이 특성 값(궁극적으로 문자열만)에서 생성될 수 있습니다.

다음 예제에서는 및 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> **Set_PropertyName_** 접근자 **Get_PropertyName_뿐만** 아니라 종속성 속성 등록(메서드 사용)을 보여 주며 있습니다. 예제에서 연결된 속성 이름은 `IsBubbleSource`입니다. 따라서 접근자의 이름은 `GetIsBubbleSource` 및 `SetIsBubbleSource`입니다.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>연결된 속성 특성

WPF는 리플렉션 프로세스에 연결된 속성에 대한 정보와 디자이너와 같은 리플렉션 및 속성 정보의 일반적인 사용자에게 정보를 제공하기 위한 여러 .NET 특성을 정의합니다. 연결된 속성에 제한이 없는 범위의 형식이 있기 때문에 디자이너는 XAML을 사용하는 특정 기술 구현에 정의된 모든 연결된 속성의 전역 목록을 사용하여 사용자의 과부하를 피할 수 있는 방법이 필요합니다. WPF가 연결된 속성에 대해 정의하는 .NET 특성을 사용하여 지정된 연결된 속성을 속성 창에 표시해야 하는 상황을 범위를 지정할 수 있습니다. 또한 사용자 고유의 사용자 지정 연결된 속성에 대한 이러한 특성을 적용하는 것이 좋습니다. .NET 특성의 목적과 구문은 적절한 참조 페이지에 설명되어 있습니다.

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## <a name="learning-more-about-attached-properties"></a>연결된 속성에 대해 자세히 알아보기<a name="more"></a>

- 연결된 속성을 만드는 방법에 대한 자세한 내용은 [연결된 속성 등록](how-to-register-an-attached-property.md)을 참조하십시오.

- 종속성 속성 및 연결된 속성에 대한 고급 사용 시나리오는 [사용자 지정 종속성 속성](custom-dependency-properties.md)을 참조하십시오.

- 연결된 속성 및 종속성 속성으로 속성을 등록할 수도 있지만 "래퍼" 구현이 여전히 표시됩니다. 이 경우 속성은 해당 요소 또는 XAML 연결된 속성 구문을 통해 모든 요소에 설정될 수 있습니다. 표준 및 연결된 용도 모두에 적합한 시나리오가 있는 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>속성의 예는 다음과 입니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.DependencyProperty>
- [종속성 속성 개요](dependency-properties-overview.md)
- [사용자 지정 종속성 속성](custom-dependency-properties.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [연결된 속성 등록](how-to-register-an-attached-property.md)
