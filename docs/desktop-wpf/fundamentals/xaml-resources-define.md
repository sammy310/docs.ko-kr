---
title: XAML 리소스 정의
description: .NET Core용 WPF의 XAML 리소스에 대해 알아봅니다. XAML 리소스의 형식을 이해하고 XAML 리소스를 정의하는 방법을 학습합니다.
author: adegeo
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: f8eaf3fd931aa6804b0b9a9c19c6bcc042678ebf
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325715"
---
# <a name="overview-of-xaml-resources"></a>XAML 리소스 개요

리소스는 앱의 여러 위치에서 다시 사용할 수 있는 개체입니다. 리소스의 예로는 브러시와 스타일이 있습니다. 이 개요에서는 XAML(Extensible Application Markup Language)에서 리소스를 사용하는 방법을 설명합니다. 코드를 사용하여 리소스를 만들고 액세스할 수도 있습니다.

> [!NOTE]
> 이 문서에서 설명하는 XAML 리소스는 콘텐츠, 데이터, 포함된 파일 등 일반적으로 앱에 추가되는 파일인 *앱 리소스*와는 다릅니다.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>XAML에서 리소스 사용

다음 예제에서는 페이지의 루트 요소에서 <xref:System.Windows.Media.SolidColorBrush>를 리소스로 정의합니다. 그런 다음 이 리소스를 참조하고 사용하여 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Controls.TextBlock>, <xref:System.Windows.Controls.Button>을 비롯한 여러 자식 요소의 속성을 설정합니다.

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

모든 프레임워크 수준 요소(<xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>)에는 정의된 리소스를 포함하는 <xref:System.Windows.ResourceDictionary> 형식의 <xref:System.Windows.FrameworkElement.Resources%2A> 속성이 있습니다. 모든 요소(예: <xref:System.Windows.Controls.Button>)에서 리소스를 정의할 수 있습니다. 그러나 리소스는 루트 요소(예제에서 <xref:System.Windows.Controls.Page>)에서 정의되는 경우가 가장 많습니다.

리소스 디렉터리의 각 리소스에는 고유 키가 있어야 합니다. 태그에서 리소스를 정의하는 경우 [x:Key 지시문](../xaml-services/xkey-directive.md)을 통해 고유 키를 할당합니다. 일반적으로 키는 문자열이지만, 적절한 태그 확장을 사용하여 다른 개체 형식으로도 설정할 수 있습니다. 문자열이 아닌 리소스 키는 특히 스타일, 구성 요소 리소스 및 데이터 스타일링을 위해 WPF의 특정 기능 영역에서 사용됩니다.

리소스의 키 이름을 지정하는 리소스 태그 확장 구문을 사용하여 정의된 리소스를 사용할 수 있습니다. 예를 들어 리소스를 다른 요소의 속성 값으로 사용합니다.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

앞의 예제에서 XAML 로더가 <xref:System.Windows.Controls.Button>에 대한 <xref:System.Windows.Controls.Control.Background%2A> 속성의 `{StaticResource MyBrush}` 값을 처리할 때 리소스 조회 논리는 먼저 <xref:System.Windows.Controls.Button> 요소에 대한 리소스 사전을 확인합니다. <xref:System.Windows.Controls.Button>에 리소스 키 `MyBrush`의 정의가 없는 경우(위 예제에는 없음, 즉 해당 리소스 컬렉션이 비어 있음) 조회는 다음으로 <xref:System.Windows.Controls.Button>의 부모 요소 <xref:System.Windows.Controls.Page>를 확인합니다. <xref:System.Windows.Controls.Page> 루트 요소에서 리소스를 정의하는 경우 <xref:System.Windows.Controls.Page>의 논리적 트리에 있는 모든 요소가 액세스할 수 있습니다. 그리고 리소스가 나타내는 것과 동일한 형식을 허용하는 모든 속성의 값을 설정하는 데 동일한 리소스를 다시 사용할 수 있습니다. 이전 예제에서 동일한 `MyBrush` 리소스는 두 가지 속성, 즉 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A>와 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 설정합니다.

## <a name="static-and-dynamic-resources"></a>정적 및 동적 리소스

리소스를 정적 또는 동적으로 참조할 수 있습니다. 참조는 [StaticResource 태그 확장](../../framework/wpf/advanced/staticresource-markup-extension.md) 또는 [DynamicResource 태그 확장](../../framework/wpf/advanced/dynamicresource-markup-extension.md)을 사용하여 만듭니다. 태그 확장은 XAML 기능입니다. 이 기능을 사용하면 태그 확장이 특성 문자열을 처리하고 개체를 XAML 로더에 반환하도록 하여 개체 참조를 지정할 수 있습니다. 태그 확장 동작에 대한 자세한 내용은 [태그 확장 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.

태그 확장을 사용하는 경우 일반적으로 특정 태그 확장에 의해 처리되는 하나 이상의 매개 변수를 문자열 형식으로 제공합니다. [StaticResource 태그 확장](../../framework/wpf/advanced/staticresource-markup-extension.md)은 사용 가능한 모든 리소스 사전에서 해당 키의 값을 검색하여 키를 처리합니다. 처리는 로드하는 동안 이루어집니다. 이때 로드 프로세스가 속성 값을 할당해야 합니다. 대신 [DynamicResource 태그 확장](../../framework/wpf/advanced/dynamicresource-markup-extension.md)에서는 식을 만들어 키를 처리하며, 이 식은 앱이 실행되어야만 계산되어 값을 제공합니다.

리소스를 참조할 때 정적 리소스 참조를 사용하는지 아니면 동적 리소스 참조를 사용하는지에 상관없이 영향을 미칠 수 있는 고려 사항은 다음과 같습니다.

- 앱용 리소스를 만드는 방법에 대한 전체 디자인을 결정하는 경우(페이지별, 앱에서, 느슨한 XAML에서 또는 리소스 전용 어셈블리에서) 다음 사항을 고려하세요.

- 앱의 기능. 실시간 리소스 업데이트가 앱 요구 사항의 일부인가요?
- 해당 리소스 참조 형식의 각 조회 동작.
- 특정 속성 또는 리소스 형식 및 해당 형식의 기본 동작.

## <a name="static-resources"></a>정적 리소스

정적 리소스 참조는 다음 환경에 가장 적합합니다.

- 앱 디자인에서는 대부분의 리소스를 페이지 또는 애플리케이션 수준 리소스 사전에 집중합니다. 정적 리소스 참조는 페이지 다시 로드 등의 런타임 동작에 따라 다시 평가되지 않습니다. 따라서 리소스 및 앱 디자인을 기반으로 필요하지 않을 때 많은 수의 동적 리소스 참조를 방지하는 성능상의 이점을 누릴 수 있습니다.

- <xref:System.Windows.DependencyObject> 또는 <xref:System.Windows.Freezable>에 없는 속성의 값을 설정합니다.

- DLL로 컴파일되고 앱의 일부로 패키지되거나 앱 간에 공유될 리소스 사전을 만듭니다.

- 사용자 지정 컨트롤의 테마를 만들고 테마에서 사용되는 리소스를 정의합니다. 이 경우 일반적으로 동적 리소스 참조 조회 동작을 사용하지 않습니다. 대신, 조회가 예측 가능하고 테마에 자체 포함되도록 정적 리소스 참조 동작을 사용합니다. 동적 리소스 참조를 사용하는 경우에도 테마 내의 참조가 런타임까지 평가되지 않습니다. 그리고 테마를 적용하는 경우 일부 로컬 요소가 테마에서 참조하려는 키를 다시 정의하고, 로컬 요소가 조회에서 테마에 앞서 실패할 가능성이 있습니다. 이 경우 테마가 예상대로 작동하지 않습니다.

- 리소스를 사용하여 다수의 종속성 속성을 설정합니다. 종속성 속성에는 속성 시스템에서 사용하게 설정한 유효 값이 캐싱이 있습니다. 따라서 로드 시 평가될 수 있는 종속성 속성의 값을 제공하는 경우, 종속성 속성에서 재평가된 식을 확인하지 않아도 되며 마지막 유효 값을 반환할 수 있습니다. 이 기술을 사용하면 성능상의 이점이 있습니다.

- 모든 소비자의 기본 리소스를 변경하거나 [x:Shared 특성](../xaml-services/xshared-attribute.md)을 사용하여 각 소비자의 별도 작성 가능 인스턴스를 유지하려고 합니다.

### <a name="static-resource-lookup-behavior"></a>정적 리소스 조회 동작

다음은 속성 또는 요소가 정적 리소스를 참조하는 경우 자동으로 발생하는 조회 프로세스에 대한 설명입니다.

01. 조회 프로세스가 속성을 설정하는 요소를 통해 정의된 리소스 사전에서 요청된 키를 확인합니다.

01. 그런 다음 조회 프로세스가 논리적 트리를 상향식으로 통과하여 부모 요소와 해당 리소스 사전으로 이동합니다. 이 프로세스는 루트 요소에 도달할 때까지 계속됩니다.

01. 앱 리소스를 확인합니다. 앱 리소스는 WPF 앱에 대한 <xref:System.Windows.Application> 개체에서 정의한 리소스 사전 내 리소스입니다.

리소스 사전 내의 정적 리소스 참조는 리소스 참조 전에 사전순으로 이미 정의된 리소스를 참조해야 합니다. 전방 참조는 정적 리소스 참조로 확인할 수 없습니다. 이러한 이유로 각 리소스 사전의 시작 부분 또는 그 근처에서 리소스가 정의되도록 리소스 사전 구조를 디자인합니다.

정적 리소스 조회는 테마나 시스템 리소스로 확장될 수 있습니다. 그러나 이 조회는 오로지 XAML 로더가 요청을 지연하기 때문에 지원됩니다. 페이지가 로드될 때 런타임 테마가 앱에 적절하게 적용되기 위해 지연이 필요합니다. 그러나 테마에만 또는 시스템 리소스로만 존재하는 것으로 알려진 키에 대한 정적 리소스 참조는 사용자가 실시간으로 테마를 변경하는 경우에는 다시 평가되지 않으므로 사용하지 않는 것이 좋습니다. 동적 리소스 참조는 테마나 시스템 리소스를 요청할 때 더욱 안정적입니다. 테마 요소 자체가 다른 리소스를 요청할 때는 예외입니다. 이러한 참조는 앞서 설명한 이유때문에 정적 리소스 참조여야 합니다.

정적 리소스 참조가 발견되지 않을 경우의 예외 동작은 다양합니다. 리소스가 지연되면 런타임 시 예외가 발생합니다. 리소스가 지연되지 않으면 로드 시 예외가 발생합니다.

## <a name="dynamic-resources"></a>동적 리소스

동적 리소스는 다음과 같은 경우에 가장 잘 작동합니다.

- 시스템 리소스 또는 사용자가 설정할 수 있는 리소스를 포함하여 리소스의 값은 런타임까지 알려지지 않은 조건에 따라 달라집니다. 예를 들어 <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts> 또는 <xref:System.Windows.SystemParameters>에 의해 노출되는 시스템 속성을 참조하는 setter 값을 만들 수 있습니다. 이러한 값은 궁극적으로 운영 체제와 사용자의 런타임 환경에서 오므로 정말로 동적입니다. 변경할 수 있는 애플리케이션 수준 테마도 있습니다. 이 경우 페이지 수준 리소스 액세스를 통해서도 변경 사항을 캡처해야 합니다.

- 사용자 지정 컨트롤의 테마 스타일을 만들거나 참조합니다.

- 앱 수명 동안 <xref:System.Windows.ResourceDictionary>의 내용을 조정하려고 합니다.

- 상호 종속된 복잡한 리소스 구조체 가 있으며, 이 경우에는 전방 참조가 필요할 수 있습니다. 정적 리소스 참조에서는 전방 참조를 지원하지 않지만, 동적 리소스 참조에서는 런타임 시까지 리소스를 평가하지 않아도 되므로 전방 참조를 지원하지 않습니다. 따라서 전방 참조는 관련 개념이 아닙니다.

- 컴파일 또는 작업 집합 면에서 큰 리소스를 참조하며, 페이지를 로드할 때 즉시 리소스를 사용하지 않을 수도 있습니다. 정적 리소스 참조는 페이지가 로드될 때 항상 XAML에서 로드합니다. 그러나 동적 리소스 참조는 사용될 때까지 로드되지 않습니다.

- setter 값이 테마나 다른 사용자 설정의 영향을 받는 다른 값에서 오는 스타일을 만듭니다.

- 앱 수명 중에 논리적 트리에서 다시 부모가 지정될 수 있는 요소에 리소스를 적용합니다. 부모를 변경하면 리소스 조회 범위도 변경될 수 있으므로, 부모가 재지정된 요소의 리소스를 새 범위에 따라 재평가하려면 항상 동적 리소스 참조를 사용하세요.

### <a name="dynamic-resource-lookup-behavior"></a>동적 리소스 조회 동작

<xref:System.Windows.FrameworkElement.FindResource%2A> 또는 <xref:System.Windows.FrameworkElement.SetResourceReference%2A>를 호출하는 경우 동적 리소스 참조의 리소스 조회 동작은 코드의 조회 동작과 유사합니다.

01. 조회가 속성을 설정하는 요소를 통해 정의된 리소스 사전에서 요청된 키를 확인합니다.

    - 요소가 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 정의하는 경우 요소의 <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName>에 <xref:System.Windows.Style.Resources> 사전이 확인되어 있습니다.

    - 요소가 <xref:System.Windows.Controls.Control.Template%2A> 속성을 정의하는 경우 요소의 <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> 사전이 확인됩니다.

01. 그런 다음 조회가 논리적 트리를 상향식으로 통과하여 부모 요소와 해당 리소스 사전으로 이동합니다. 이 프로세스는 루트 요소에 도달할 때까지 계속됩니다.

01. 앱 리소스를 확인합니다. 앱 리소스는 WPF 앱에 대한 <xref:System.Windows.Application> 개체에서 정의한 리소스 사전 내 리소스입니다.

01. 현재 활성 테마의 테마 리소스 사전을 확인합니다. 런타임 시 테마가 변경되면 값을 재평가합니다.

01. 시스템 리소스를 확인합니다.

예외 동작이 있는 경우 다음과 같이 다양합니다.

- <xref:System.Windows.FrameworkElement.FindResource%2A> 호출에서 리소스를 요청했지만 찾을 수 없는 경우 예외가 throw됩니다.

- <xref:System.Windows.FrameworkElement.TryFindResource%2A> 호출에서 리소스를 요청했지만 찾을 수 없는 경우 예외가 throw되지 않고 반환된 값이 `null`입니다. 설정되는 속성에서 `null`을 허용하지 않는 경우에도 여전히 심층 예외가 throw될 수 있습니다(설정되는 개별 속성에 따라 다름).

- XAML의 동적 리소스 참조에서 리소스를 요청했지만 찾을 수 없는 경우 동작은 일반 속성 시스템에 따라 달라집니다. 일반적인 동작은 리소스가 존재하는 수준에서 속성 설정 작업이 발생하지 않은 것과 같습니다. 예를 들어, 평가할 수 없는 리소스를 사용하여 개별 단추 요소에서 배경을 설정하려고 하면 값 집합이 생기지 않지만, 속성 시스템 및 값 우선 순위의 다른 참가자로부터 유효 값을 여전히 가져올 수 있습니다. 예를 들어, 배경색은 로컬에 정의한 단추 스타일 또는 테마 스타일에서 여전히 가져올 수 있습니다. 테마 스타일이 정의하지 않은 속성의 경우, 실패한 리소스 평가 후 유효 값은 속성 메타데이터의 기본값에서 가져올 수 있습니다.

### <a name="restrictions"></a>제한

동적 리소스 참조에는 몇 가지 주목할 만한 제한 사항이 있습니다. 다음 조건 중 하나 이상이 충족되어야 합니다.

- 설정되는 속성은 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 속성이어야 합니다. 해당 속성은 <xref:System.Windows.DependencyProperty>에 의해 지원되어야 합니다.

- `StyleSetter` 내의 값이 참조됩니다.

- 설정되는 속성은 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 속성의 값 또는 <xref:System.Windows.Setter> 값으로 제공되는 <xref:System.Windows.Freezable>의 속성이어야 합니다.

설정되는 속성은 <xref:System.Windows.DependencyProperty> 또는 <xref:System.Windows.Freezable> 속성이어야 하므로 속성 변경(변경된 동적 리소스 값)이 속성 시스템에서 승인되기 때문에 대부분의 속성 변경 내용이 UI에 전파될 수 있습니다. 대부분의 컨트롤에는 <xref:System.Windows.DependencyProperty> 변경 내용 및 해당 속성이 레이아웃에 영향을 미칠 수 있는 경우 컨트롤의 다른 레이아웃에 적용될 논리가 포함됩니다. 그러나 [DynamicResource 태그 확장](../../framework/wpf/advanced/dynamicresource-markup-extension.md)을 값을 갖는 모든 속성이 UI에서 실시간 업데이트를 제공하도록 보장되지는 않습니다. 이 기능은 속성 외에도 속성을 소유하는 형식, 심지어는 앱의 논리 구조체에 따라서도 여전히 달라질 수 있습니다.

## <a name="styles-datatemplates-and-implicit-keys"></a>스타일, DataTemplates 및 암시적 키

<xref:System.Windows.ResourceDictionary>의 모든 항목에는 키가 있어야 하지만 이것이 모든 리소스에 명시적 `x:Key`가 있어야 한다는 의미는 아닙니다. 리소스로 정의된 경우 여러 개체 형식에서 암시적 키를 지원하며, 이 경우 키 값이 다른 속성의 값과 연결됩니다. 이 형식의 키는 암시적 키로 알려진 반면, `x:Key` 특성은 명시적 키입니다. 명시적 키를 지정하여 암시적 키를 덮어쓸 수 있습니다.

리소스에 대한 중요한 시나리오 한 가지는 <xref:System.Windows.Style>을 정의하는 경우입니다. 실제로 <xref:System.Windows.Style>은 거의 항상 리소스 사전에 항목으로 정의됩니다. 기본적으로 스타일은 재사용되기 때문입니다. 스타일에 대한 자세한 내용은 [스타일 지정 및 템플릿](styles-templates-overview.md)을 참조하세요.

컨트롤의 스타일은 암시적 키로 만들어 참조될 수 있습니다. 컨트롤의 기본 모양을 정의하는 테마 스타일은 이 암시적 키에 따라 달라집니다. 키를 요청하는 관점에서 암시적 키는 컨트롤 자체의 <xref:System.Type>입니다. 리소스를 정의하는 관점에서 암시적 키는 스타일의 <xref:System.Windows.Style.TargetType%2A>입니다. 그러므로 사용자 지정 컨트롤의 테마를 만들고, 기존 테마 스타일과 상호 작용하는 스타일을 만드는 경우, 해당 <xref:System.Windows.Style>의 [x:Key 지시문](../xaml-services/xkey-directive.md)을 지정하지 않아도 됩니다. 테마로 지정된 스타일을 사용하려면 스타일을 전혀 지정하지 않아도 됩니다. 예를 들어, 다음 스타일 정의는 <xref:System.Windows.Style> 리소스에 키가 없어 보여도 작동합니다.

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

해당 스타일에는 암시적 키 `typeof(System.Windows.Controls.Button)`이 있습니다. 태그에서 <xref:System.Windows.Style.TargetType%2A>을 형식 이름으로 직접 지정할 수 있습니다. (또는 선택적으로 [{x:Type...}](../xaml-services/xtype-markup-extension.md)을 사용하여 <xref:System.Type>을 반환할 수 있습니다.)

WPF가 사용하는 기본 테마 스타일 메커니즘을 통해 해당 스타일은 <xref:System.Windows.Controls.Button> 자체에서 해당 <xref:System.Windows.FrameworkElement.Style%2A> 속성 또는 스타일에 대한 특정 리소스 참조를 지정하려고 하지 않더라도 페이지에서 <xref:System.Windows.Controls.Button>의 런타임 스타일로 적용됩니다. 페이지에 정의된 스타일은 테마 사전 스타일에 있는 동일한 키를 사용하여 조회 순서에서 테마 사전 스타일보다 먼저 발견됩니다. 페이지의 어디서나 `<Button>Hello</Button>`를 지정할 수 있으며 `Button`의 <xref:System.Windows.Style.TargetType%2A>으로 정의한 스타일이 해당 단추에 적용됩니다. 원하는 경우 태그에서 명확하게 표시되도록 <xref:System.Windows.Style.TargetType%2A>과 같은 형식 값을 사용하여 스타일의 키를 명시적으로 지정할 수 있지만 이는 선택 사항입니다.

스타일에 대한 암시적 키는 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A>이 `true`인 경우 컨트롤에서 적용되지 않습니다. (<xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A>은 컨트롤의 인스턴스에서 명시적이 아닌 컨트롤 클래스에 대한 기본 동작의 일부로 설정될 수도 있습니다.) 또한 파생된 클래스 시나리오에 암시적 키를 지원하려면 컨트롤이 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>를 재정의해야 합니다(WPF의 일부로 제공되는 모든 기존 컨트롤은 이 재정의를 포함함). 스타일, 테마 및 컨트롤 디자인에 대한 자세한 내용은 [스타일을 지정할 수 있는 컨트롤을 디자인하기 위한 지침](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md)을 참조하세요.

<xref:System.Windows.DataTemplate>에는 암시적 키도 있습니다. <xref:System.Windows.DataTemplate>의 암시적 키는 <xref:System.Windows.DataTemplate.DataType%2A> 속성 값입니다. <xref:System.Windows.DataTemplate.DataType%2A>은 [{x:Type...}](../xaml-services/xtype-markup-extension.md)을 명시적으로 사용하는 대신 형식의 이름으로 지정할 수도 있습니다. 자세한 내용은 [데이터 템플릿 개요](../../framework/wpf/data/data-templating-overview.md)를 참조하세요.

## <a name="see-also"></a>참조

- <xref:System.Windows.ResourceDictionary>
- [애플리케이션 리소스](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [리소스 및 코드](../../framework/wpf/advanced/resources-and-code.md)
- [리소스 정의 및 참조](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [애플리케이션 관리 개요](../../framework/wpf/app-development/application-management-overview.md)
- [x:Type 태그 확장](../xaml-services/xtype-markup-extension.md)
- [StaticResource 태그 확장](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [DynamicResource 태그 확장](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
