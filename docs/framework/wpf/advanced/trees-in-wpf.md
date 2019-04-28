---
title: WPF의 트리
ms.date: 03/30/2017
helpviewer_keywords:
- logical tree [WPF]
- element tree [WPF]
- visual tree [WPF]
ms.assetid: e83f25e5-d66b-4fc7-92d2-50130c9a6649
ms.openlocfilehash: f9b507c874dfe0ab3feca19e7fcf79df5af93e10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775000"
---
# <a name="trees-in-wpf"></a>WPF의 트리
대부분의 기술에서 요소와 구성 요소는 트리 구조로 구성됩니다. 이 트리 구조에서 개발자는 트리의 개체 노드를 직접 조작하여 애플리케이션의 동작이나 렌더링에 영향을 줍니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서도 여러 가지 트리 구조 메타포를 사용하여 프로그램 요소 간의 관계를 정의합니다. 대부분 경우 WPF 개발자는 개념적으로 개체 트리 메타포를 고려하면서 코드로 애플리케이션을 만들거나 XAML로 애플리케이션의 일부를 정의할 수 있지만 XML DOM에서 사용할 수 있는 몇 가지 일반적인 개체 트리 조작 API 대신 특정 API를 호출하거나 특정 태그를 사용하여 이 작업을 수행합니다. WPF 트리 메타포 보기를 제공 하는 두 개의 도우미 클래스를 노출 <xref:System.Windows.LogicalTreeHelper> 고 <xref:System.Windows.Media.VisualTreeHelper>입니다. 또한 WPF 설명서에서는 시각적 트리와 논리 트리라는 용어를 사용하는데 이러한 동일한 트리는 특정 주요 WPF 기능의 동작을 이해하는 데 유용하기 때문입니다. 이 항목에서는 시각적 트리와 논리 트리가 나타내는 항목 정의 전체 개체 트리 개념과 이러한 트리 관계에 대해 설명 하 고 소개 <xref:System.Windows.LogicalTreeHelper> 고 <xref:System.Windows.Media.VisualTreeHelper>s입니다.  

<a name="element_tree"></a>   
## <a name="trees-in-wpf"></a>WPF의 트리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 가장 완벽한 트리 구조는 개체 트리입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 응용 프로그램 페이지를 정의한 후 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 로드하는 경우 트리 구조는 태그에 있는 요소의 중첩 관계에 따라 만들어집니다. 코드에서 애플리케이션이나 애플리케이션 일부를 정의하는 경우 트리 구조는 지정된 개체에 대한 콘텐츠 모델을 구현하는 속성에 대해 속성 값을 할당하는 방법에 따라 만들어집니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 완벽한 트리 구조는 논리 트리와 시각적 트리라는 두 가지 방법으로 개념화하고 공용 API에 보고할 수 있습니다. 논리 트리와 시각적 트리의 구분이 항상 반드시 중요한 것은 아니지만 경우에 따라 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하위 시스템에서 문제를 발생시키고 태그나 코드에서 선택하는 항목에 영향을 줄 수 있습니다.  
  
 항상 논리 트리나 시각적 트리를 직접 조작하지 않는 경우에도 트리가 상호 작용하는 방식에 대한 개념을 이해하면 WPF를 기술로 이해하는 데 도움이 됩니다. 또한 WPF를 일종의 트리 메타포로 생각하는 것은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 속성 상속 및 이벤트 라우팅의 작동 방식을 이해하는 데 매우 중요합니다.  
  
> [!NOTE]
>  개체 트리는 실제 API라기보다는 일종의 개념이기 때문에 이 개념을 개체 그래프로 생각할 수도 있습니다. 실제로 트리 메타포가 분류되는 런타임에 개체 간에 관계가 있습니다. 그러나 특히 XAML 정의 UI를 사용하는 경우 트리 메타포는 대부분의 WPF 설명서에서 이 일반적인 개념을 참조할 때 개체 트리라는 용어를 사용할 정도로 충분히 관련이 있습니다.  
  
<a name="logical_tree"></a>   
## <a name="the-logical-tree"></a>논리 트리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 해당 요소를 지원하는 개체의 속성을 설정하여 UI 요소에 콘텐츠를 추가합니다. 항목을 추가 하는 예는 <xref:System.Windows.Controls.ListBox> 컨트롤을 조작 하 여 해당 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성입니다. 이 작업을 수행 하면 항목을 배치 하 고는 <xref:System.Windows.Controls.ItemCollection> 즉는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성 값입니다. 마찬가지로, 추가할 개체를 <xref:System.Windows.Controls.DockPanel>, 조작 해당 <xref:System.Windows.Controls.Panel.Children%2A> 속성 값입니다. 여기에서 개체를 추가 하는 <xref:System.Windows.Controls.UIElementCollection>합니다. 코드 예제를 참조 하세요. [방법: 요소를 동적으로 추가](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms752374(v=vs.100))합니다.  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]의 목록 항목을 배치 하는 경우를 <xref:System.Windows.Controls.ListBox> 컨트롤 또는 기타 UI 요소에는 <xref:System.Windows.Controls.DockPanel>, 또한 사용 하 여를 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 <xref:System.Windows.Controls.Panel.Children%2A> 속성을 명시적 또는 암시적으로 다음 예제와 같이 합니다.  
  
 [!code-xaml[TreeOvwsSupport#AllCode](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeOvwsSupport/CS/page1.xaml#allcode)]  
  
 문서 개체 모델에서 이 XAML을 XML로 처리하려는 경우 및 적합해야 하는 태그를 암시적으로 주석 처리하여 포함한 경우 결과 XML DOM 트리에는 `<ListBox.Items>`에 대한 요소 및 기타 암시적 항목이 포함됩니다. 그러나 XAML은 태그를 읽고 개체에 쓸 때 이런 방식으로 처리하지 않으며 결과 개체 그래프에 `ListBox.Items`가 포함되지 않습니다. 그러나 않은 <xref:System.Windows.Controls.ListBox> 라는 속성이 `Items` 포함 하는 <xref:System.Windows.Controls.ItemCollection>, 및 <xref:System.Windows.Controls.ItemCollection> 초기화 되지만 비어 있으면는 <xref:System.Windows.Controls.ListBox> XAML 처리 됩니다. 그런 다음 각 자식 개체 요소에 대 한 콘텐츠로 존재 하는 합니다 <xref:System.Windows.Controls.ListBox> 에 추가 되는 <xref:System.Windows.Controls.ItemCollection> 파서를 호출 하 여 `ItemCollection.Add`. 지금까지 XAML을 개체 트리로 처리하는 이 예제는 생성된 개체 트리가 기본적으로 논리 트리인 경우로 보입니다.  
  
 그러나 XAML 암시적 구문 항목이 팩터링된 경우에도 논리 트리는 런타임에 애플리케이션 UI에 대해 존재하는 전체 개체 그래프가 아닙니다. 주요 이유는 시각 효과 및 템플릿 때문입니다. 예를 들어를 <xref:System.Windows.Controls.Button>입니다. 논리적 트리 보고서를 <xref:System.Windows.Controls.Button> 개체와 해당 문자열 `Content`합니다. 하지만 런타임 개체 트리의 이 단추에는 더 많은 정보가 있습니다. 특히 단추만 화면에 표시 되는 있기 때문으로 특정 <xref:System.Windows.Controls.Button> 컨트롤 템플릿이 적용 되지 않았습니다. 적용 된 템플릿에서 제공 되는 시각적 개체 (템플릿 정의 같은 <xref:System.Windows.Controls.Border> 시각적 단추 주위 진한 회색의) 런타임 중 논리 트리를 보는 경우에 논리 트리에서 보고 되지 않습니다 (의 입력된 이벤트를 처리 하는 등의 표시 되는 UI 및 다음 논리 트리 읽기). 템플릿 시각 효과를 찾으려면 시각적 트리를 대신 검사해야 합니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문이 생성된 개체 그래프에 매핑되는 방법 및 XAML의 암시적 구문에 대한 자세한 내용은 [XAML 구문 정보](xaml-syntax-in-detail.md) 또는 [XAML 개요(WPF)](xaml-overview-wpf.md)를 참조하세요.  
  
<a name="tree_property_inheritance_event_routing"></a>   
### <a name="the-purpose-of-the-logical-tree"></a>논리 트리의 용도  
 논리 트리를 통해 콘텐츠 모델은 해당 자식 개체를 쉽게 반복할 수 있고 콘텐츠 모델을 확장할 수 있습니다. 또한 논리 트리는 논리 트리의 모든 개체가 로드된 경우 등의 특정 알림에 대한 프레임워크를 제공합니다. 기본적으로 논리 트리는 시각 효과를 제외한 프레임워크 수준의 런타임 개체 그래프와 유사하지만 고유한 런타임 애플리케이션의 구성에 대한 많은 쿼리 작업에 적합합니다.  
  
 논리적 트리에서 위쪽으로 조사 하 여 두 정적 및 동적 리소스 참조는 확인 하는 또한 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션에는 초기 요청 개체를 다음 논리 트리 위로 계속 및 각 <xref:System.Windows.FrameworkElement> (또는 <xref:System.Windows.FrameworkContentElement>) 다른 `Resources` 포함 하는 값을 <xref:System.Windows.ResourceDictionary>, 가능한 경우 해당 키가 들어 있는입니다. 논리 트리와 시각적 트리가 모두 있을 경우 논리 트리가 리소스 조회에 사용됩니다. 리소스 사전 및 조회에 대한 자세한 내용은 [XAML 리소스](xaml-resources.md)를 참조하세요.  
  
<a name="composition"></a>   
### <a name="composition-of-the-logical-tree"></a>논리 트리의 구성  
 논리적 트리는 WPF 프레임 워크 수준, 즉 논리 트리 작업과 가장 관련이 있는 WPF 기본 요소 중 하나에 정의 됩니다 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다. 그러나 볼 수 있듯이 실제로 사용 하는 경우는 <xref:System.Windows.LogicalTreeHelper> API를 포함 하거나 하지 않은 노드 경우도 논리적 트리 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다. 논리 트리에서 보고 하는 예를 들어를 <xref:System.Windows.Controls.TextBlock.Text%2A> 값을 <xref:System.Windows.Controls.TextBlock>, 문자열인입니다.  
  
<a name="override_logical_tree"></a>   
### <a name="overriding-the-logical-tree"></a>논리 트리 재정의  
 고급 컨트롤 작성자는 일반적인 개체 또는 콘텐츠 모델이 논리 트리 내에서 개체를 추가하거나 제거하는 방법을 정의하는 여러 가지 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 재정의하여 논리 트리를 재정의할 수 있습니다. 논리 트리를 재정의하는 방법에 대한 예제는 [논리 트리 재정의](how-to-override-the-logical-tree.md)를 참조하세요.  
  
<a name="pvi"></a>   
### <a name="property-value-inheritance"></a>속성 값 상속  
 속성 값 상속은 혼합 트리를 통해 작동합니다. 포함 하는 실제 메타 데이터를 <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 속성 상속을 사용할 수 있는 속성은 WPF 프레임 워크 수준 <xref:System.Windows.FrameworkPropertyMetadata> 클래스입니다. 따라서 원래 값을 보유 하는 부모와 해당 값을 상속 하는 자식 개체는 둘 다 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>, 모두 일부 논리 트리에 속해야 시켜야 하 고 있습니다. 그러나 속성 상속을 지원하는 기존 WPF 속성의 경우 속성 값 상속은 논리 트리에 없는 중간 개체를 통해 지속될 수 있습니다. 주로 이 기능은 템플릿 요소가 템플릿 기반의 인스턴스 또는 더 높은 수준의 페이지 수준 구성 및 논리 트리의 더 높은 위치에서 설정된 상속된 속성 값을 사용하도록 하려는 경우와 관련이 있습니다. 속성 값 상속이 이러한 경계에서 일관되게 작동하려면 상속하는 속성을 연결된 속성으로 등록해야 하며 속성 상속 동작으로 사용자 지정 종속성 속성을 정의하려는 경우 이 패턴을 따라야 합니다. 속성 상속에 사용되는 정확한 트리는 도우미 클래스 유틸리티 메서드에서 완전히 예상할 수 없으며, 런타임에도 마찬가지입니다. 자세한 내용은 [속성 값 상속](property-value-inheritance.md)을 참조하세요.  
  
<a name="two_trees"></a>   
## <a name="the-visual-tree"></a>시각적 트리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 논리 트리의 개념 외에 시각적 트리라는 개념도 있습니다. 시각적 트리에 의해 표시 된 대로 시각적 개체의 구조를 설명 합니다 <xref:System.Windows.Media.Visual> 기본 클래스입니다. 컨트롤에 대한 템플릿을 작성하면 해당 컨트롤에 적용되는 시각적 트리를 정의하거나 다시 정의하는 것입니다. 또한 시각적 트리는 성능 및 최적화를 위해 그리기를 낮은 수준으로 제어하려는 개발자에게 유용합니다. 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션 프로그래밍의 일부로 시각적 트리가 노출되는 한 가지 경우는 라우트된 이벤트에 대한 이벤트 경로가 대부분 논리 트리가 아닌 시각적 트리를 따라 이동하는 경우입니다. 이렇게 미묘한 라우트된 이벤트 동작은 컨트롤 작성자가 아닌 경우 바로 파악되지 않을 수 있습니다. 시각적 트리를 통한 이벤트 라우팅에서는 시각적 수준에서 구성을 구현하는 컨트롤을 사용하여 이벤트를 처리하거나 이벤트 setter를 만들 수 있습니다.  
  
<a name="trees_content"></a>   
## <a name="trees-content-elements-and-content-hosts"></a>트리, 콘텐츠 요소 및 콘텐츠 호스트  
 콘텐츠 요소 (에서 파생 된 클래스 <xref:System.Windows.ContentElement>) 시각적 트리의 일부가 아닌;에서 상속 하지 않는 <xref:System.Windows.Media.Visual> 시각적 표시를 하지 않습니다. 전혀 UI에 표시 하기 위해를 <xref:System.Windows.ContentElement> 둘 다 있는 콘텐츠 호스트에서 호스트 되어야 합니다는 <xref:System.Windows.Media.Visual> 및 논리 트리 참가자가 있습니다. 이러한 개체는 일반적으로 <xref:System.Windows.FrameworkElement>합니다. 콘텐츠 호스트는 콘텐츠에 대한 "브라우저"와 약간 비슷하며 호스트가 제어하는 화면 영역 내에서 해당 콘텐츠를 표시하는 방법을 선택하는 것으로 개념화할 수 있습니다. 호스트된 콘텐츠는 일반적으로 시각적 트리와 연관된 특정 트리 프로세스의 참가자가 될 수 있습니다. 일반적으로 <xref:System.Windows.FrameworkElement> 호스트 클래스에는 모든 호스트를 추가 하는 구현 코드가 포함 되어 <xref:System.Windows.ContentElement> 콘텐츠 논리 트리의 하위 노드를 통해 이벤트 경로에 호스트 된 콘텐츠의 일부가 아닌 true 시각적 트리. 이 작업이 필요 하도록는 <xref:System.Windows.ContentElement> 자체 이외의 모든 요소로 라우트되는 라우트된 이벤트를 경험할 수 있습니다.  
  
<a name="tree_traversal"></a>   
## <a name="tree-traversal"></a>트리 순회  
 합니다 <xref:System.Windows.LogicalTreeHelper> 클래스를 제공 합니다 <xref:System.Windows.LogicalTreeHelper.GetChildren%2A>를 <xref:System.Windows.LogicalTreeHelper.GetParent%2A>, 및 <xref:System.Windows.LogicalTreeHelper.FindLogicalNode%2A> 논리 트리 순회에 대 한 메서드. 대부분의 경우 기존 컨트롤의 논리 트리를 트래버스할 필요가 없습니다. 이러한 컨트롤은 거의 항상 논리 자식 요소를 `Add`, 인덱서 등 컬렉션 액세스를 지원하는 전용 컬렉션 속성으로 노출하기 때문입니다. 트리 순회는 시나리오와 같은 컨트롤 패턴에서 파생 하지 않도록 선택 컨트롤 작성자는 주로 <xref:System.Windows.Controls.ItemsControl> 또는 <xref:System.Windows.Controls.Panel> 여기서 컬렉션 속성 이미 정의 되어 있으며 자체 컬렉션을 제공 하려는 속성 지원입니다.  
  
 시각적 트리의 시각적 트리 순회에 대 한 도우미 클래스를도 지원 <xref:System.Windows.Media.VisualTreeHelper>합니다. 시각적 트리는 컨트롤 관련 속성을 통해으로 편리 하 게 노출 되지 않으므로 <xref:System.Windows.Media.VisualTreeHelper> 클래스는 프로그래밍 시나리오에 필요한 경우 시각적 트리를 트래버스에 권장 되는 방법입니다. 자세한 내용은 [WPF 그래픽 렌더링 개요](../graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하세요.  
  
> [!NOTE]
>  경우에 따라 적용된 템플릿의 시각적 트리를 검사해야 합니다. 이 기술을 사용할 때는 주의해야 합니다. 템플릿을 정의한 컨트롤의 시각적 트리를 트래버스하는, 하는 경우에 컨트롤 소비자는 항상 템플릿을 설정 하 여 변경 된 <xref:System.Windows.Controls.Control.Template%2A> 인스턴스 및 최종 사용자의 속성을 변경 하 여 적용된 된 템플릿에 영향을 줄 수를 시스템 테마입니다.  
  
<a name="routes"></a>   
## <a name="routes-for-routed-events-as-a-tree"></a>"트리"로 라우트된 이벤트에 대한 경로  
 앞서 언급했듯이 지정된 라우트된 이벤트의 경로는 시각적 트리와 논리 트리 표현이 혼합된 트리의 미리 결정된 단일 경로를 따라 이동합니다. 이벤트 경로는 라우트된 터널링 이벤트인지 버블링 이벤트인지에 따라 트리 내에서 위쪽이나 아래쪽 방향으로 이동할 수 있습니다. 이벤트 경로 개념에는 실제로 라우트되는 이벤트를 발생시키는 것과 별개로 이벤트 경로를 "이동"하는 데 사용할 수 있는 직접적인 지원 도우미 클래스가 없습니다. 경로 나타내는 클래스가 <xref:System.Windows.EventRoute>, 하지만 해당 클래스의 메서드는 일반적으로 내부 에서만 사용 합니다.  
  
<a name="resourcesandtrees"></a>   
## <a name="resource-dictionaries-and-trees"></a>리소스 사전 및 트리  
 페이지에 정의된 모든 `Resources`에 대한 리소스 사전 조회는 기본적으로 논리 트리를 트래버스합니다. 논리 트리에 없는 개체는 키 지정 리소스를 참조할 수 있지만 리소스 조회 시퀀스는 해당 개체가 논리 트리와 연결되는 지점에서 시작됩니다. Wpf에서는 논리 트리 노드에만 수 있습니다는 `Resources` 포함 하는 속성을 <xref:System.Windows.ResourceDictionary>, 따라서은 아무런 의미가에서 키 지정된 리소스를 찾으시나요 시각적 트리를 이동는 <xref:System.Windows.ResourceDictionary>합니다.  
  
 그러나 리소스 조회는 직접적인 논리 트리를 넘어 확장될 수도 있습니다. 애플리케이션 태그의 경우 리소스 조회가 애플리케이션 수준 리소스 사전까지 계속된 다음 정적 속성이나 키로 참조되는 테마 지원 및 시스템 값까지 계속될 수 있습니다. 테마 자체는 리소스 참조가 동적인 경우 테마 논리 트리 외부의 시스템 값을 참조할 수도 있습니다. 리소스 사전 및 조회 논리에 대한 자세한 내용은 [XAML 리소스](xaml-resources.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [입력 개요](input-overview.md)
- [WPF 그래픽 렌더링 개요](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [라우트된 이벤트 개요](routed-events-overview.md)
- [개체 트리에 없는 개체 요소 초기화](initialization-for-object-elements-not-in-an-object-tree.md)
- [WPF 아키텍처](wpf-architecture.md)
