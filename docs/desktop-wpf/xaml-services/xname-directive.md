---
title: x:Name 지시문
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 9f812a49a3217a563be1bd7f1d999b641c28463d
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432715"
---
# <a name="xname-directive"></a>x:Name 지시문

XAML 네임스코프에서 XAML 정의 요소를 고유하게 식별합니다. XAML 네임스코프 및 고유성 모델은 프레임워크가 API를 제공하거나 런타임에 XAML에서 만든 개체 그래프에 액세스하는 동작을 구현하는 경우 인스턴스화된 개체에 적용할 수 있습니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`XAMLNameValue`|[XamlName 문법의](xamlname-grammar.md)제한을 준수하는 문자열입니다.|

## <a name="remarks"></a>설명

프레임워크의 백업 프로그래밍 모델에 적용된 후 `x:Name` 이름은 생성자가 반환하는 개체 참조 또는 인스턴스를 보유하는 변수와 동일합니다.

지시문 `x:Name` 사용값은 XAML 네임스코프 내에서 고유해야 합니다. 기본적으로 .NET XAML 서비스 API에서 사용할 때 기본 XAML 네임스코프는 단일 XAML 프로덕션의 XAML 루트 요소에 정의되며 해당 XAML 프로덕션에 포함된 요소를 포함합니다. 단일 XAML 프로덕션 내에서 발생할 수 있는 추가 불연속 XAML 네임스코프는 특정 시나리오를 해결하기 위해 프레임워크에 의해 정의될 수 있습니다. 예를 들어 WPF에서 새 XAML 네임스코프는 해당 XAML 프로덕션에 정의된 모든 템플릿에 의해 정의되고 만들어집니다. XAML 네임스코프(WPF용으로 작성되었지만 많은 XAML 네임스코프 개념과 관련이 있음)에 대한 자세한 내용은 [WPF XAML 네임스코프를](../../framework/wpf/advanced/wpf-xaml-namescopes.md)참조하십시오.

일반적으로 을 `x:Name` 사용하는 `x:Key`상황에서는 적용해서는 안 됩니다. 특정 기존 프레임워크에 의한 XAML 구현은 과 `x:Key` `x:Name`사이의 대체 개념을 도입했지만 권장되는 방법은 아닙니다. .NET XAML 서비스는 이름/키 정보 등을 <xref:System.Windows.Markup.INameScope> 처리할 때 이러한 대체 개념을 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>지원하지 않습니다.

허용 `x:Name` 규칙과 이름 고유성 적용은 특정 구현 프레임워크에 의해 잠재적으로 정의됩니다. 그러나 .NET XAML 서비스에서 사용할 수 있도록 XAML 네임스코프 고유성의 프레임워크 정의는 <xref:System.Windows.Markup.INameScope> 이 설명서의 정보 정의와 일치해야 하며 정보가 적용되는 위치와 동일한 규칙을 사용해야 합니다. 예를 들어 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 구현에서는 다양한 태그 요소를 <xref:System.Windows.NameScope> 리소스 사전, 페이지 수준 XAML, 템플릿 및 기타 지연된 콘텐츠로 만든 논리 트리와 같은 별도의 범위로 나눈 다음 각 XAML 네임스코프 내에서 XAML 이름 고유성을 적용합니다.

.NET XAML 서비스 XAML 개체 작성기를 사용하는 사용자 `x:Name` 지정 형식의 경우 형식에 매핑하는 속성을 설정하거나 변경할 수 있습니다. 형식 정의 코드에서 매핑할 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 속성의 이름을 참조하여 이 동작을 정의합니다.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>은 형식 수준 특성입니다.

XAML 서비스에 Using.NET XAML 네임스코프 지원에 대한 백업 논리는 <xref:System.Windows.Markup.INameScope> 인터페이스를 구현하여 프레임워크 중립적인 방식으로 정의할 수 있습니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

XAML, 부분 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 클래스 및 코드 숨결을 사용하는 응용 프로그램의 표준 `x:Name` 빌드 구성에서 지정된 필드는 태그 컴파일 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 빌드 태스크에 의해 처리될 때 기본 코드에서 만들어지는 필드의 이름이 되며 해당 필드에는 개체에 대한 참조가 있습니다. 기본적으로 생성된 필드는 내부 필드입니다. [x:FieldModifier 특성을](xfieldmodifier-directive.md)지정하여 필드 액세스를 변경할 수 있습니다. WPF 및 Silverlight에서 시퀀스는 태그 컴파일이 부분 클래스의 필드를 정의하고 이름을 지정하지만 값이 처음에는 비어 있다는 것입니다. 그런 다음 클래스 `InitializeComponent` 생성자 내에서 호출 된 생성 된 메서드가 호출 됩니다. `InitializeComponent`는 `FindName` 부분 클래스의 `x:Name` XAML 정의 부분에 있는 각 값을 입력 문자열로 사용하는 호출로 구성됩니다. 그런 다음 반환 값이 같은 이름의 필드 참조에 할당되어 XAML 구문 분석에서 만든 개체로 필드 값을 채웁니다. 실행은 `InitializeComponent` XAML 정의 개체에 대한 참조가 필요할 때마다 명시적으로 호출할 필요 없이 `x:Name` /필드 이름을 사용하여 런타임 개체 그래프를 직접 참조할 `FindName` 수 있도록 합니다.

Microsoft Visual Basic 대상을 사용하고 빌드 작업이 `Page` 있는 XAML 파일을 포함하는 WPF 응용 프로그램의 경우 이벤트 `WithEvents` 처리기 대리자에 `x:Name`대한 구문을 지원하기 `Handles` 위해 의 키워드를 추가하는 컴파일 중에 별도의 참조 속성이 만들어집니다. 이 속성은 항상 공용입니다. 자세한 내용은 [Visual Basic 및 WPF 이벤트 처리](../../framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)를 참조하세요.

`x:Name`WPF XAML 프로세서에서 로드 시 XAML 네임스코프에 이름을 등록하는 데 사용되며, 빌드 작업에 의해 페이지가 마크업 컴파일되지 않는 경우에도(예: 리소스 사전의 느슨한 XAML). 이 동작의 한 가지 `x:Name` 이유는 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩에 필요할 수 있기 때문입니다. 자세한 내용은 [데이터 바인딩 개요를](../data/data-binding-overview.md)참조하십시오.

앞에서 설명한 `x:Name` 것처럼 `Name`(또는) 을 사용하는 `x:Key`상황에서는 적용해서는 안 됩니다. 는 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> XAML 네임스코프로 자신을 정의하지만 이 동작을 적용하는 <xref:System.Windows.Markup.INameScope> 방법으로 API에 대해 구현되지 않음 또는 null 값을 반환하는 특별한 동작이 있습니다. WPF XAML 파서가 `Name` 발생하거나 `x:Name` XAML 정의에서 <xref:System.Windows.ResourceDictionary>발생하면 이름은 XAML 이름 범위에 추가되지 않습니다. XAML `FindName` 네임스코프및메서드에서 해당 이름을 찾으려고 하면 유효한 결과가 반환되지 않습니다.

### <a name="xname-and-name"></a>x:이름과 이름

많은 WPF 응용 프로그램 시나리오는 `x:Name` 기본 XAML 네임스페이스에 지정된 대로 `Name` 종속성 속성과 같은 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 여러 중요한 기본 클래스에 대해 동일한 용도로 만족하므로 특성의 사용을 피할 수 있습니다. 프레임워크 수준에서 속성이 없는 `Name` 요소에 대한 코드 액세스가 중요한 몇 가지 일반적인 XAML 및 WPF 시나리오가 여전히 있습니다. 예를 들어 특정 애니메이션 및 스토리보드 지원 `Name` 클래스는 속성을 지원하지 않지만 애니메이션을 제어하려면 코드에서 참조해야 하는 경우가 많습니다. 나중에 코드에서 참조하려는 경우 XAML에서 만든 타임라인 및 변환에 대한 특성으로 지정해야 `x:Name` 합니다.

<xref:System.Windows.FrameworkElement.Name%2A> 클래스에서 속성으로 사용할 수 <xref:System.Windows.FrameworkElement.Name%2A> 있고 `x:Name` 속성으로 상호 교환하여 사용할 수 있지만 둘 다 동일한 요소에 지정된 경우 구문 분석 예외가 발생합니다. XAML이 컴파일된 경우 태그 컴파일에서 예외가 발생하고 그렇지 않으면 로드시 발생합니다.

<xref:System.Windows.FrameworkElement.Name%2A>XAML 특성 구문을 사용하여 설정할 수 <xref:System.Windows.DependencyObject.SetValue%2A>있으며; 그러나 코드에서 <xref:System.Windows.FrameworkElement.Name%2A> 속성을 설정해도 XAML이 이미 로드된 대부분의 경우 XAML 네임스코프 내에서 대표 필드 참조가 생성되지는 않습니다. 코드에서 설정하려고 <xref:System.Windows.FrameworkElement.Name%2A> 하는 대신 <xref:System.Windows.NameScope> 적절한 네임스코프에 대해 코드의 메서드를 사용합니다.

<xref:System.Windows.FrameworkElement.Name%2A>내부 텍스트가 있는 속성 요소 구문을 사용하여 설정할 수도 있지만 이는 드문 경우입니다. 반대로 XAML 속성 요소 구문또는 다음을 사용하는 `x:Name` <xref:System.Windows.DependencyObject.SetValue%2A>코드에서 설정할 수 없습니다. 지시문이므로 개체에 대한 특성 구문을 사용하여만 설정할 수 있습니다.

## <a name="silverlight-usage-notes"></a>실버라이트 사용 노트

`x:Name`실버라이트에 대한 설명은 별도로 문서화되어 있습니다. 자세한 내용은 [XAML 네임스페이스(x:)를 참조하십시오. 언어 기능 (실버 라이트)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>참조

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [WPF의 트리](../../framework/wpf/advanced/trees-in-wpf.md)
