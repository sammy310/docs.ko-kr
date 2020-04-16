---
title: XAML 리소스 정의
description: .NET 코어에 대한 WPF의 XAML 리소스에 대해 알아봅니다. XAML 리소스의 유형을 이해하고 XAML 리소스를 정의하는 방법을 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: b278bb92afc308578d60e347871e0150b26a95db
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "81432571"
---
# <a name="overview-of-xaml-resources"></a>XAML 리소스 개요

리소스는 앱의 다른 위치에서 다시 사용할 수 있는 개체입니다. 리소스의 예로는 브러시와 스타일이 있습니다. 이 개요에서는 확장 가능한 응용 프로그램 태그 언어(XAML)에서 리소스를 사용하는 방법을 설명합니다. 코드를 사용하여 리소스를 만들고 액세스할 수도 있습니다.

> [!NOTE]
> 이 문서에서 설명하는 XAML 리소스는 일반적으로 콘텐츠, 데이터 또는 포함된 파일과 같이 앱에 추가된 파일인 앱 *리소스와* 다릅니다.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>XAML에서 리소스 사용

다음 예제는 페이지의 <xref:System.Windows.Media.SolidColorBrush> 루트 요소에 대한 리소스로 a를 정의합니다. 그런 다음 예제는 리소스를 참조하고 이 리소스를 사용하여 <xref:System.Windows.Shapes.Ellipse>" <xref:System.Windows.Controls.TextBlock>및 <xref:System.Windows.Controls.Button>을 포함한 여러 자식 요소의 속성을 설정합니다.

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

모든 프레임워크 수준<xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>요소(또는)에는 정의된 리소스를 <xref:System.Windows.FrameworkElement.Resources%2A> 포함하는 형식인 <xref:System.Windows.ResourceDictionary> 속성이 있습니다. <xref:System.Windows.Controls.Button>. 그러나 리소스는 예제에 있는 루트 요소에 <xref:System.Windows.Controls.Page> 가장 자주 정의됩니다.

리소스 디렉터리의 각 리소스에는 고유 키가 있어야 합니다. 태그에서 리소스를 정의할 때 [x:Key 지시문을](../xaml-services/xkey-directive.md)통해 고유 키를 할당합니다. 일반적으로 키는 문자열이지만, 적절한 태그 확장을 사용하여 다른 개체 형식으로도 설정할 수 있습니다. 리소스에 대한 비문자열 키는 WPF의 특정 기능 영역, 특히 스타일, 구성 요소 리소스 및 데이터 스타일 지정에 사용됩니다.

리소스의 키 이름을 지정하는 리소스 태그 확장 구문과 함께 정의된 리소스를 사용할 수 있습니다. 예를 들어 리소스를 다른 요소의 속성 값으로 사용합니다.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

위의 예제에서 XAML `{StaticResource MyBrush}` 로더에서 <xref:System.Windows.Controls.Control.Background%2A> 속성에 대 한 <xref:System.Windows.Controls.Button>값을 처리 하는 경우 resource 조회 논리 <xref:System.Windows.Controls.Button> 먼저 요소에 대 한 리소스 사전을 확인 합니다. 리소스 <xref:System.Windows.Controls.Button> `MyBrush` 키에 대한 정의가 없는 경우(이 예에서는 리소스 컬렉션이 비어 있지 않습니다. 해당 리소스 <xref:System.Windows.Controls.Button>컬렉션이 <xref:System.Windows.Controls.Page>비어 있음) 다음에 조회는 의 부모 요소를 확인합니다. <xref:System.Windows.Controls.Page> 루트 요소에 대한 리소스를 정의하는 경우 의 논리 트리에 <xref:System.Windows.Controls.Page> 있는 모든 요소가 리소스에 액세스할 수 있습니다. 또한 리소스가 나타내는 것과 동일한 형식을 허용하는 속성의 값을 설정하기 위해 동일한 리소스를 다시 사용할 수 있습니다. 이전 예제에서 `MyBrush` 동일한 리소스는 두 개의 <xref:System.Windows.Controls.Control.Background%2A> 서로 <xref:System.Windows.Controls.Button>다른 속성을 <xref:System.Windows.Shapes.Shape.Fill%2A> 설정합니다: 의 및 의 <xref:System.Windows.Shapes.Rectangle>.

## <a name="static-and-dynamic-resources"></a>정적 및 동적 리소스

리소스를 정적 또는 동적으로 참조할 수 있습니다. 참조는 [StaticResource 마크업 확장](../../framework/wpf/advanced/staticresource-markup-extension.md) 또는 [DynamicResource 마크업 확장을](../../framework/wpf/advanced/dynamicresource-markup-extension.md)사용하여 만들어집니다. 태그 확장은 태그 확장이 특성 문자열을 처리하고 개체를 XAML 로더에 반환하도록 하여 개체 참조를 지정할 수 있는 XAML 기능입니다. 마크업 확장 동작에 대한 자세한 내용은 [마크업 확장 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하십시오.

태그 확장을 사용하는 경우 일반적으로 특정 태그 확장에서 처리되는 문자열 형태로 하나 이상의 매개 변수를 제공합니다. [StaticResource 마크업 확장은](../../framework/wpf/advanced/staticresource-markup-extension.md) 사용 가능한 모든 리소스 사전에서 해당 키에 대한 값을 찾아키를 처리합니다. 로드 프로세스가 속성 값을 할당해야 하는 경우인 로드 중에 처리가 수행됩니다. [DynamicResource 마크업 확장대신](../../framework/wpf/advanced/dynamicresource-markup-extension.md) 식을 만들어 키를 처리하고 해당 식은 앱이 실행될 때까지 평가되지 않은 상태로 유지되며, 이 때 식이 평가되고 값을 제공합니다.

리소스를 참조할 때 정적 리소스 참조를 사용하는지 아니면 동적 리소스 참조를 사용하는지에 상관없이 영향을 미칠 수 있는 고려 사항은 다음과 같습니다.

- 앱에 대한 리소스를 만드는 방법(페이지당, 앱, 느슨한 XAML 또는 리소스 전용 어셈블리)의 전반적인 디자인을 결정할 때 다음을 고려하십시오.

- 앱의 기능입니다. 앱 요구 사항의 실시간 리소스 업데이트가 있습니까?
- 해당 리소스 참조 형식의 각 조회 동작.
- 특정 속성 또는 리소스 형식 및 해당 형식의 기본 동작.

## <a name="static-resources"></a>정적 리소스

정적 리소스 참조는 다음 환경에 가장 적합합니다.

- 앱 디자인은 대부분의 리소스를 페이지 또는 응용 프로그램 수준 리소스 사전에 집중합니다. 정적 리소스 참조는 페이지 다시 로드와 같은 런타임 동작에 따라 다시 평가되지 않습니다. 따라서 리소스 및 앱 디자인에 따라 필요하지 않은 경우 많은 수의 동적 리소스 참조를 피하면 성능이 향상될 수 있습니다.

- 에 없는 속성의 값을 설정 하는 경우 입니다. <xref:System.Windows.DependencyObject> <xref:System.Windows.Freezable>

- DLL로 컴파일되고 앱의 일부로 패키징되거나 앱 간에 공유되는 리소스 사전을 만드는 것입니다.

- 사용자 지정 컨트롤에 대한 테마를 만들고 테마 내에서 사용되는 리소스를 정의하고 있습니다. 이 경우 일반적으로 동적 리소스 참조 조회 동작을 원하지 않습니다. 대신 정적 리소스 참조 동작을 사용하여 조회를 예측 가능하고 테마에 독립적으로 사용할 수 있도록 해야 합니다. 동적 리소스 참조를 사용하면 테마 내의 참조도 런타임까지 평가되지 않습니다. 테마가 적용될 때 일부 로컬 요소는 테마가 참조하려고 하는 키를 재정의하고 로컬 요소는 조회에서 테마 자체보다 앞서 떨어질 가능성이 있습니다. 이 경우 테마가 예상대로 행동하지 않습니다.

- 리소스를 사용하여 많은 수의 종속성 속성을 설정합니다. 종속성 속성은 속성 시스템에서 사용하도록 설정된 대로 유효 값 캐싱을 가지므로 로드 시 평가할 수 있는 종속성 속성에 대한 값을 제공하는 경우 종속성 속성은 다시 평가된 식을 확인할 필요가 없으며 마지막 유효 값을 반환할 수 있습니다. 이 기술을 사용하면 성능상의 이점이 있습니다.

- 모든 소비자에 대한 기본 리소스를 변경하거나 [x:Shared 특성을](../xaml-services/xshared-attribute.md)사용하여 각 소비자에 대해 별도의 쓰기 가능한 인스턴스를 유지 하려고 합니다.

### <a name="static-resource-lookup-behavior"></a>정적 리소스 조회 동작

다음은 정적 리소스가 속성 또는 요소에 의해 참조될 때 자동으로 발생하는 조회 프로세스에 대해 설명합니다.

01. 조회 프로세스가 속성을 설정하는 요소를 통해 정의된 리소스 사전에서 요청된 키를 확인합니다.

01. 그런 다음 조회 프로세스는 논리 트리를 상위 요소 및 리소스 사전으로 이동합니다. 이 프로세스는 루트 요소에 도달할 때까지 계속됩니다.

01. 앱 리소스가 선택됩니다. 앱 리소스는 WPF 앱의 개체에 <xref:System.Windows.Application> 의해 정의된 리소스 사전 내의 리소스입니다.

리소스 사전 내의 정적 리소스 참조는 리소스 참조 전에 사전순으로 이미 정의된 리소스를 참조해야 합니다. 전방 참조는 정적 리소스 참조로 확인할 수 없습니다. 이러한 이유로 각 리소스 사전의 시작 부분 또는 그 근처에 리소스가 정의되도록 리소스 사전 구조를 디자인합니다.

정적 리소스 조회는 테마 또는 시스템 리소스로 확장할 수 있지만 XAML 로더가 요청을 연기하기 때문에 이 조회가 지원됩니다. 페이지 로드 시점의 런타임 테마가 앱에 제대로 적용되도록 지연이 필요합니다. 그러나 테마또는 시스템 리소스로만 존재하는 것으로 알려진 키에 대한 정적 리소스 참조는 사용자가 실시간으로 테마를 변경하는 경우 이러한 참조가 다시 평가되지 않으므로 권장되지 않습니다. 동적 리소스 참조는 테마나 시스템 리소스를 요청할 때 더욱 안정적입니다. 테마 요소 자체가 다른 리소스를 요청할 때는 예외입니다. 이러한 참조는 앞서 설명한 이유때문에 정적 리소스 참조여야 합니다.

정적 리소스 참조를 찾을 수 없는 경우 예외 동작은 다양합니다. 리소스가 지연되면 런타임 시 예외가 발생합니다. 리소스가 지연되지 않으면 로드 시 예외가 발생합니다.

## <a name="dynamic-resources"></a>동적 리소스

동적 리소스는 다음과 같은 경우에 가장 잘 작동합니다.

- 시스템 리소스 또는 사용자 설정 가능한 리소스를 포함한 리소스값은 런타임까지 알려지지 않은 조건에 따라 달라집니다. 예를 들어 시스템 속성을 에 <xref:System.Windows.SystemColors> <xref:System.Windows.SystemFonts> <xref:System.Windows.SystemParameters>의해 노출된 것으로 참조하는 setter 값을 만들 수 있습니다. 이러한 값은 궁극적으로 운영 체제와 사용자의 런타임 환경에서 오므로 정말로 동적입니다. 변경할 수 있는 애플리케이션 수준 테마도 있습니다. 이 경우 페이지 수준 리소스 액세스를 통해서도 변경 사항을 캡처해야 합니다.

- 사용자 지정 컨트롤에 대한 테마 스타일을 만들거나 참조하는 것입니다.

- 앱 수명 <xref:System.Windows.ResourceDictionary> 동안의 내용을 조정하려고 합니다.

- 상호 종속된 복잡한 리소스 구조체 가 있으며, 이 경우에는 전방 참조가 필요할 수 있습니다. 정적 리소스 참조는 전달 참조를 지원하지 않지만 동적 리소스 참조는 런타임까지 리소스를 평가할 필요가 없으므로 전달 참조가 관련 개념이 아니기 때문에 해당 참조를 지원합니다.

- 컴파일 또는 작업 집합의 관점에서 큰 리소스를 참조하는 경우 페이지가 로드될 때 리소스가 즉시 사용되지 않을 수 있습니다. 정적 리소스 참조는 페이지가 로드될 때 항상 XAML에서 로드됩니다. 그러나 동적 리소스 참조가 사용될 때까지 로드되지 않습니다.

- 테마 또는 기타 사용자 설정의 영향을 받는 다른 값에서 setter 값이 올 수 있는 스타일을 만드는 것입니다.

- 앱 수명 동안 논리 트리에서 다시 부모가 될 수 있는 요소에 리소스를 적용합니다. 부모를 변경하면 리소스 조회 범위도 변경될 수 있으므로, 부모가 재지정된 요소의 리소스를 새 범위에 따라 재평가하려면 항상 동적 리소스 참조를 사용하세요.

### <a name="dynamic-resource-lookup-behavior"></a>동적 리소스 조회 동작

동적 리소스 참조에 대한 리소스 조회 동작은 호출하거나 <xref:System.Windows.FrameworkElement.FindResource%2A> <xref:System.Windows.FrameworkElement.SetResourceReference%2A>호출하는 경우 코드의 조회 동작과 유사합니다.

01. 조회는 속성을 설정하는 요소에서 정의한 리소스 사전 내에서 요청된 키를 확인합니다.

    - 요소가 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 정의하는 경우 <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> 요소의 사전에 대한 <xref:System.Windows.Style.Resources> 사전이 선택됩니다.

    - 요소가 <xref:System.Windows.Controls.Control.Template%2A> 속성을 정의하는 경우 요소의 <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> 사전이 검사됩니다.

01. 조회는 논리 트리를 상위 요소 및 리소스 사전으로 위쪽으로 이동합니다. 이 프로세스는 루트 요소에 도달할 때까지 계속됩니다.

01. 앱 리소스가 선택됩니다. 앱 리소스는 WPF 앱의 개체에 <xref:System.Windows.Application> 의해 정의된 리소스 사전 내의 리소스입니다.

01. 테마 리소스 사전이 현재 활성 테마에 대해 검사됩니다. 런타임 시 테마가 변경되면 값을 재평가합니다.

01. 시스템 리소스를 확인합니다.

예외 동작이 있는 경우 다음과 같이 다양합니다.

- <xref:System.Windows.FrameworkElement.FindResource%2A> 호출에서 리소스를 요청받았고 찾지 못하면 예외가 throw됩니다.

- <xref:System.Windows.FrameworkElement.TryFindResource%2A> 호출에서 리소스를 요청받았고 찾지 않은 경우 예외가 throw되지 않으며 `null`반환된 값은 입니다. 설정된 속성이 수락되지 `null`않는 경우 설정되는 개별 속성에 따라 더 깊은 예외가 throw될 수 있습니다.

- XAML의 동적 리소스 참조에서 리소스를 요청받았고 찾을 수 없는 경우 동작은 일반 속성 시스템에 따라 다릅니다. 일반적인 동작은 리소스가 있는 수준에서 속성 설정 작업이 발생하지 않은 것처럼 작동합니다. 예를 들어 평가할 수 없는 리소스를 사용하여 개별 단추 요소에 대한 배경을 설정하려고 하면 값 집합 결과가 없지만 유효 값은 속성 시스템 및 값 우선 순위의 다른 참여자로부터 계속 올 수 있습니다. 예를 들어 배경 값은 로컬로 정의된 단추 스타일 또는 테마 스타일에서 올 수 있습니다. 테마 스타일에 의해 정의되지 않은 속성의 경우 리소스 평가 실패 후의 유효 값은 속성 메타데이터의 기본값에서 올 수 있습니다.

### <a name="restrictions"></a>제한

동적 리소스 참조에는 몇 가지 주목할 만한 제한 사항이 있습니다. 다음 조건 중 하나 이상이 true여야 합니다.

- 설정되는 속성은 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에 있는 속성이어야 합니다. 해당 속성은 <xref:System.Windows.DependencyProperty>을 통해 백업되어야 합니다.

- 참조는 `StyleSetter`에 있는 값에 대한 값입니다.

- 설정되는 <xref:System.Windows.Freezable> 속성은 a <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 속성 또는 값의 값으로 제공되는 속성이어야 <xref:System.Windows.Setter> 합니다.

설정되는 속성은 또는 <xref:System.Windows.DependencyProperty> <xref:System.Windows.Freezable> 속성이어야 하므로 속성 변경(변경된 동적 리소스 값)이 속성 시스템에서 승인되므로 대부분의 속성 변경 내용이 UI에 전파될 수 있습니다. 대부분의 컨트롤에는 변경 및 해당 속성이 <xref:System.Windows.DependencyProperty> 레이아웃에 영향을 줄 수 있는 경우 컨트롤의 다른 레이아웃을 강제로 만드는 논리가 포함됩니다. 그러나 [DynamicResource 마크업 확장이](../../framework/wpf/advanced/dynamicresource-markup-extension.md) 있는 모든 속성이 해당 값으로 UI에서 실시간 업데이트를 제공하는 것은 아닙니다. 해당 기능은 속성뿐만 아니라 속성을 소유하는 형식 또는 앱의 논리적 구조에 따라 달라질 수 있습니다.

## <a name="styles-datatemplates-and-implicit-keys"></a>스타일, 데이터 템플릿 및 암시적 키

a의 <xref:System.Windows.ResourceDictionary> 모든 항목에는 키가 있어야 하지만 모든 리소스에 명시적 `x:Key`이 있어야 한다는 의미는 아닙니다. 리소스로 정의된 경우 여러 개체 형식에서 암시적 키를 지원하며, 이 경우 키 값이 다른 속성의 값과 연결됩니다. 이러한 유형의 키는 암시적 키라고 `x:Key` 하는 반면 특성은 명시적 키입니다. 명시적 키를 지정하여 암시적 키를 덮어쓸 수 있습니다.

리소스에 대한 한 가지 중요한 <xref:System.Windows.Style>시나리오는 을 정의할 때입니다. 실제로 a는 <xref:System.Windows.Style> 스타일이 본질적으로 재사용을 목적으로 하기 때문에 리소스 사전의 항목으로 거의 항상 정의됩니다. 스타일에 대한 자세한 내용은 [스타일 지정 및 템플릿을](styles-templates-overview.md)참조하십시오.

컨트롤의 스타일은 암시적 키로 만들어 참조될 수 있습니다. 컨트롤의 기본 모양을 정의하는 테마 스타일은 이 암시적 키에 따라 달라집니다. 요청의 관점에서 암시적 키는 컨트롤 <xref:System.Type> 자체의 것입니다. 리소스를 정의하는 관점에서 암시적 키는 스타일입니다. <xref:System.Windows.Style.TargetType%2A> 따라서 사용자 지정 컨트롤에 대한 테마를 만들거나 기존 테마 스타일과 상호 작용하는 스타일을 만드는 경우 에 <xref:System.Windows.Style>대한 [x:Key 지시문을](../xaml-services/xkey-directive.md) 지정할 필요가 없습니다. 테마로 지정된 스타일을 사용하려면 스타일을 전혀 지정하지 않아도 됩니다. 예를 들어 <xref:System.Windows.Style> 리소스에 키가 없는 경우에도 다음 스타일 정의가 작동합니다.

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

암시적 키 `typeof(System.Windows.Controls.Button)`: 그 스타일은 정말 키가 있습니다 . 태그에서 형식 이름으로 <xref:System.Windows.Style.TargetType%2A> 직접 지정할 수 있습니다(또는 [{x:Type...}](../xaml-services/xtype-markup-extension.md) 을 <xref:System.Type>반환합니다.

WPF에서 사용하는 기본 테마 스타일 메커니즘을 통해 해당 스타일은 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Button> 해당 <xref:System.Windows.FrameworkElement.Style%2A> 속성 또는 스타일에 대한 특정 리소스 참조를 지정하지 않더라도 해당 스타일은 페이지의 런타임 스타일로 적용됩니다. 페이지에 정의된 스타일은 테마 사전 스타일과 동일한 키를 사용하여 테마 사전 스타일보다 조회 시퀀스의 이전 위치에 있습니다. 페이지의 아무 `<Button>Hello</Button>` 곳이나 지정할 수 있으며 이 <xref:System.Windows.Style.TargetType%2A> `Button` 단추에 정의한 스타일이 적용됩니다. 원하는 경우 태그의 명확성을 <xref:System.Windows.Style.TargetType%2A> 위해 동일한 형식 값으로 스타일을 명시적으로 키지정할 수 있지만 선택 사항입니다.

스타일에 대한 암시적 키는 컨트롤에 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> `true`적용되지 않습니다. 또한 컨트롤의 <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> 인스턴스에서 명시적으로 설정하지 않고 컨트롤 클래스에 대한 기본 동작의 일부로 설정할 수도 있습니다. 또한 파생 된 클래스 시나리오에 대 한 암시적 키를 지원 하기 위해 컨트롤을 재정의 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> 해야 합니다 (WPF의 일부로 제공 된 모든 기존 컨트롤이 이 재정의를 포함). 스타일, 테마 및 컨트롤 디자인에 대한 자세한 내용은 [스타일 지정 가능한 컨트롤 디자인 지침을](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md)참조하십시오.

<xref:System.Windows.DataTemplate>암시적 키도 있습니다. a의 <xref:System.Windows.DataTemplate> 암시적 키는 <xref:System.Windows.DataTemplate.DataType%2A> 속성 값입니다. <xref:System.Windows.DataTemplate.DataType%2A>[{x:Type...}](../xaml-services/xtype-markup-extension.md)을 명시적으로 사용하는 대신 형식의 이름으로 지정할 수도 있습니다. 자세한 내용은 [데이터 템플릿 개요를](../../framework/wpf/data/data-templating-overview.md)참조하십시오.

## <a name="see-also"></a>참조

- <xref:System.Windows.ResourceDictionary>
- [애플리케이션 리소스](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [리소스 및 코드](../../framework/wpf/advanced/resources-and-code.md)
- [리소스 정의 및 참조](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [응용 프로그램 관리 개요](../../framework/wpf/app-development/application-management-overview.md)
- [x:마크업 확장유형](../xaml-services/xtype-markup-extension.md)
- [정적 자원 마크업 확장](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [동적 리소스 마크업 확장](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
