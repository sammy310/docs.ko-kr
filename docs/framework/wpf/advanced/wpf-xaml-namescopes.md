---
title: XAML 네임스코프
ms.date: 03/30/2017
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
ms.openlocfilehash: f9d4439c6b102d0d430b5201e3649985daee0b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186280"
---
# <a name="wpf-xaml-namescopes"></a>WPF XAML 이름 범위
XAML 이름 범위는 XAML에 정의된 개체를 식별하는 개념입니다. XAML 이름 범위의 이름은 XAML로 정의된 개체 이름과 개체 트리에서 그에 해당하는 인스턴스 간의 관계를 설정하는 데 사용할 수 있습니다. 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 관리 코드의 XAML 이름 범위는 XAML 애플리케이션의 개별 XAML 페이지 루트를 로드할 때 만들어집니다. 프로그래밍 개체로 XAML 이름 범위는 인터페이스에 <xref:System.Windows.Markup.INameScope> 의해 정의 되 고 <xref:System.Windows.NameScope>또한 실용적인 클래스에 의해 구현 됩니다.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>
## <a name="namescopes-in-loaded-xaml-applications"></a>로드된 XAML 애플리케이션의 이름 범위  
 더욱 폭넓은 프로그래밍이나 컴퓨터 과학의 측면에서 프로그래밍 개념에는 흔히 개체에 액세스하는 데 사용할 수 있는 고유한 식별자 또는 이름의 원칙이 포함됩니다. 식별자나 이름을 사용하는 시스템의 경우 이름 범위는 해당 이름의 개체가 요청되는 경우 프로세스 또는 기술을 통해 검색할 위치의 경계나 식별 이름의 고유성이 적용되는 경계를 정의합니다. 이러한 일반적인 원칙은 XAML 이름 범위에도 해당됩니다. WPF에서 XAML 이름 범위는 페이지가 로드될 때 XAML 페이지의 루트 요소에 만들어집니다. XAML 페이지 내의 페이지 루트에서부터 지정된 각 이름은 관련 XAML 이름 범위에 추가됩니다.  
  
 WPF XAML에서 공통 루트 요소(예: <xref:System.Windows.Controls.Page>및)인 <xref:System.Windows.Window>요소는 항상 XAML 네임스코프를 제어합니다. 마크업에서 페이지의 <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> 루트 요소와 같은 요소가 있는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 <xref:System.Windows.Controls.Page> 루트를 암시적으로 <xref:System.Windows.Controls.Page> 추가하여 작업 중인 XAML 네임스코프를 제공할 수 있습니다.  
  
> [!NOTE]
> WPF 빌드 작업에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그의 모든 요소에 대해 `Name` 또는 `x:Name` 특성이 정의되지 않은 경우에도 XAML 프로덕션을 위한 XAML 이름 범위가 만들어집니다.  
  
 한 XAML 이름 범위에서 같은 이름을 두 번 사용하려고 하면 예외가 발생합니다. 코드 숨김 파일이 있고 컴파일된 애플리케이션의 일부인 WPF XAML의 경우에는 빌드 시 WPF 빌드 작업에서 초기 태그 컴파일 중 페이지에 대해 생성된 클래스를 만들 때 예외가 발생합니다. 빌드 작업을 통해 태그 컴파일되지 않은 XAML의 경우에는 XAML이 로드될 때 XAML 이름 범위 문제와 관련된 예외가 발생할 수 있습니다. XAML 디자이너가 디자인 타임에 XAML 이름 범위 문제를 예상할 수도 있습니다.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>런타임 개체 트리에 개체 추가  
 XAML이 구문 분석되는 시점은 WPF XAML 이름 범위가 만들어지고 정의되는 시점입니다. 개체 트리를 생성한 XAML이 구문 분석된 후에 개체 트리에 개체를 추가할 경우에는 새 개체의 `Name` 또는 `x:Name` 값에 따라 XAML 이름 범위의 정보가 자동으로 업데이트되지 않습니다. XAML이 로드된 후 WPF XAML 네임스코프에 개체이름을 추가하려면 일반적으로 <xref:System.Windows.Markup.INameScope.RegisterName%2A> XAML 페이지 루트인 XAML 네임스코프를 정의하는 개체의 적절한 구현을 호출해야 합니다. 이름이 등록되지 않은 경우 추가된 개체는 <xref:System.Windows.FrameworkElement.FindName%2A>와 같은 메서드를 통해 이름으로 참조할 수 없으며 애니메이션 대상 지정에 해당 이름을 사용할 수 없습니다.  
  
 응용 프로그램 개발자를 위한 가장 일반적인 <xref:System.Windows.FrameworkElement.RegisterName%2A> 시나리오는 페이지의 현재 루트에 있는 XAML 네임스코프에 이름을 등록하는 데 사용됩니다. <xref:System.Windows.FrameworkElement.RegisterName%2A>는 애니메이션에 대한 오브젝트를 대상으로 하는 스토리보드의 중요한 시나리오의 일부입니다. 자세한 내용은 [스토리보드 개요](../graphics-multimedia/storyboards-overview.md)를 참조하세요.  
  
 XAML <xref:System.Windows.FrameworkElement.RegisterName%2A> 네임스코프를 정의하는 개체가 아닌 다른 개체를 호출하는 경우 XAML namescope 정의 개체에 호출한 <xref:System.Windows.FrameworkElement.RegisterName%2A> 것처럼 호출 개체가 유지되는 XAML 네임스코프에 이름이 계속 등록됩니다.  
  
### <a name="xaml-namescopes-in-code"></a>코드의 XAML 이름 범위  
 코드에서 XAML 이름 범위를 만든 다음 사용할 수 있습니다. XAML 이름 범위를 만드는 데 관련된 API 및 개념은 순수형 코드를 사용하는 경우에도 동일합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]용 XAML 프로세서에서는 XAML 자체를 처리할 때 이러한 API 및 개념을 사용하기 때문입니다. 이 개념 및 API는 대개 일부 또는 전체가 XAML로 정의된 개체 트리 내에서 개체를 이름으로 찾을 수 있도록 하기 위한 것입니다.  
  
 로드된 XAML이 아닌 프로그래밍 방식으로 만들어진 응용 프로그램의 경우 XAML 네임스코프를 <xref:System.Windows.Markup.INameScope>정의하는 개체는 해당 인스턴스에서 XAML 네임스코프 생성을 지원하기 위해 구현하거나 또는 <xref:System.Windows.FrameworkElement> 파생된 클래스여야 <xref:System.Windows.FrameworkContentElement> 합니다.  
  
 또한 XAML 프로세서로 로드 및 처리되지 않는 모든 요소에 대해서는 기본적으로 개체의 XAML 이름 범위가 만들어지거나 초기화되지 않습니다. 따라서 이후에 이름을 등록하려는 모든 개체에 대해 명시적으로 새 XAML 이름 범위를 만들어야 합니다. XAML 네임스코프를 만들려면 <xref:System.Windows.NameScope.SetNameScope%2A> 정적 메서드를 호출합니다. 매개 변수로 `dependencyObject` 소유할 개체를 지정하고 <xref:System.Windows.NameScope.%23ctor%2A> 새 생성자 `value` 호출을 매개 변수로 지정합니다.  
  
 `dependencyObject` 제공 <xref:System.Windows.NameScope.SetNameScope%2A> 된 개체가 <xref:System.Windows.Markup.INameScope> 구현 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에 대한 <xref:System.Windows.FrameworkElement.RegisterName%2A> 호출이 아닌 경우 자식 요소에 대한 호출은 영향을 미치지 않습니다. 새 XAML 네임스코프를 명시적으로 만들지 못하면 <xref:System.Windows.FrameworkElement.RegisterName%2A> 호출이 예외를 발생시게 됩니다.  
  
 코드에서 XAML 이름 범위 API를 사용하는 예제를 보려면 [이름 범위 정의](../graphics-multimedia/how-to-define-a-name-scope.md)를 참조하세요.  
  
<a name="Namescopes_in_Styles_and_Templates"></a>
## <a name="xaml-namescopes-in-styles-and-templates"></a>스타일 및 템플릿의 XAML 이름 범위  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 스타일 및 템플릿을 사용하면 간편하게 콘텐츠를 다시 사용 및 적용할 수 있지만 템플릿 수준에서 XAML 이름이 정의된 요소가 스타일 및 템플릿에 포함될 수 있습니다. 이런 템플릿은 한 페이지에서 여러 번 사용될 수 있기 때문에 스타일과 템플릿은 모두 해당 스타일 또는 템플릿이 적용되는 개체 트리 내의 위치와는 상관없이 고유한 XAML 이름 범위를 정의합니다.  
  
 다음과 같은 예제를 참조하세요.  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 여기에서는 두 개의 단추에 동일한 템플릿이 적용됩니다. 템플릿에 개별 XAML 이름 범위가 없으면 템플릿에 사용된 `TheBorder` 이름 때문에 XAML 이름 범위에서 이름 충돌이 발생합니다. 템플릿의 각 인스턴스에는 고유한 XAML 이름 범위가 있으므로 이 예제에서 인스턴스화된 각 템플릿의 XAML 이름 범위에는 정확하게 하나의 이름만 포함됩니다.  
  
 스타일도 고유한 XAML 이름 범위를 정의하므로 대부분의 경우 스토리보드의 각 부분에 특정 이름이 할당될 수 있습니다. 이러한 이름을 사용하면 컨트롤 사용자 지정 과정에서 템플릿이 재정의된 경우에도 해당 이름의 요소를 대상으로 하는 특정 동작을 제어할 수 있습니다.  
  
 XAML 이름 범위가 분리되어 있으므로 템플릿에서 명명된 요소를 찾는 것이 페이지에서 템플릿 형식이 아닌 명명된 요소를 찾는 것보다 복잡합니다. 먼저 템플릿이 적용되는 컨트롤의 <xref:System.Windows.Controls.Control.Template%2A> 속성 값을 얻어 적용된 템플릿을 결정해야 합니다. 그런 다음 템플릿이 두 <xref:System.Windows.FrameworkTemplate.FindName%2A>번째 매개 변수로 적용된 컨트롤을 전달하는 템플릿 버전의 을 호출합니다.  
  
 컨트롤 작성자인 경우 적용된 템플릿의 특정 명명된 요소가 컨트롤 자체에 의해 정의된 동작의 대상인 규칙을 생성하는 경우 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 컨트롤 구현 코드에서 메서드를 사용할 수 있습니다. 메서드는 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 보호되므로 컨트롤 작성자만 이 메서드에 액세스할 수 있습니다.  
  
 템플릿 내에서 작업하는 경우 템플릿이 적용되는 XAML 네임스코프로 이동하려면 <xref:System.Windows.FrameworkElement.TemplatedParent%2A>에서 의 값을 얻은 <xref:System.Windows.FrameworkElement.FindName%2A> 다음 이 곳에 호출합니다. 적용된 템플릿의 요소에서 이벤트가 발생되는 이벤트 처리기를 구현하는 경우가 템플릿 내에서 작업하는 예에 해당합니다.  
  
<a name="Namescopes_and_Name_related_APIs"></a>
## <a name="xaml-namescopes-and-name-related-apis"></a>XAML 이름 범위 및 이름 관련 API  
 <xref:System.Windows.FrameworkElement>및 <xref:System.Windows.FrameworkElement.FindName%2A> <xref:System.Windows.FrameworkElement.RegisterName%2A> <xref:System.Windows.FrameworkElement.UnregisterName%2A> 메서드를 가합니다. 이러한 메서드를 호출하는 개체에 고유한 XAML 이름 범위가 있는 경우 이러한 메서드는 관련 XAML 이름 범위의 메서드를 호출합니다. 그렇지 않은 경우에는 부모 요소에 고유한 XAML 이름 범위가 있는지 확인하며, 이 확인 과정은 XAML 이름 범위를 찾을 때까지 재귀적으로 계속됩니다(XAML 프로세서의 동작 때문에 루트에는 반드시 XAML 이름 범위가 있음). <xref:System.Windows.FrameworkContentElement>XAML 네임스코프를 소유하지 않는 <xref:System.Windows.FrameworkContentElement> 경우를 제외하고는 유사한 동작이 있습니다. 호출이 결국 <xref:System.Windows.FrameworkContentElement> 부모 요소로 전달될 수 <xref:System.Windows.FrameworkElement> 있도록 메서드가 존재합니다.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>은 새 XAML 네임스코프를 기존 개체에 매핑하는 데 사용됩니다. XAML <xref:System.Windows.NameScope.SetNameScope%2A> 네임스코프를 재설정하거나 지우기 위해 두 번 이상 호출할 수 있지만 일반적인 용도는 아닙니다. <xref:System.Windows.NameScope.GetNameScope%2A> 또한 일반적으로 코드에서 사용되지 않습니다.  
  
### <a name="xaml-namescope-implementations"></a>XAML 이름 범위 구현  
 다음 클래스는 <xref:System.Windows.Markup.INameScope> 직접 구현합니다.  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>XAML 이름 이나 네임 스코프를 사용 하지 않습니다. 사전 구현이기 때문에 대신 키를 사용합니다. <xref:System.Windows.ResourceDictionary> 구현하는 <xref:System.Windows.Markup.INameScope> 유일한 이유는 실제 XAML 이름 범위와 키 <xref:System.Windows.ResourceDictionary> 를 처리하는 방법 간의 구분을 명확히 하고 XAML 이름 범위가 부모 요소에 적용되지 않도록 하는 데 <xref:System.Windows.ResourceDictionary> 도움이 되는 사용자 코드에 예외를 발생시킬 수 있기 때문입니다.  
  
 <xref:System.Windows.FrameworkTemplate><xref:System.Windows.Style> 명시적 <xref:System.Windows.Markup.INameScope> 인터페이스 정의를 통해 구현할 수 있습니다. 명시적 구현을 통해 이러한 XAML 네임스코프는 <xref:System.Windows.Markup.INameScope> 인터페이스를 통해 액세스할 때 일반적으로 실행될 수 있으며, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이는 XAML 네임스코프가 내부 프로세스에서 전달되는 방식입니다. 그러나 명시적 인터페이스 정의는 의 기존 API <xref:System.Windows.FrameworkTemplate> <xref:System.Windows.Style>표면의 일부가 아니며, <xref:System.Windows.Markup.INameScope> 메서드를 <xref:System.Windows.FrameworkTemplate> <xref:System.Windows.Style> 직접 호출할 필요가 거의 없기 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>때문에 대신 에 와 같은 다른 API를 사용합니다.  
  
 다음 클래스는 도우미 클래스를 <xref:System.Windows.NameScope?displayProperty=nameWithType> 사용하고 연결된 속성을 통해 XAML 네임스코프 구현에 <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> 연결하여 자체 XAML 네임스코프를 정의합니다.  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>참고 항목

- [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [x:Name 지시문](../../../desktop-wpf/xaml-services/xname-directive.md)
