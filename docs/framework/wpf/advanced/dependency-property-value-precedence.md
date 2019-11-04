---
title: 종속성 속성 값 우선 순위
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], classes as owners
- dependency properties [WPF], metadata
- classes [WPF], owners of dependency properties
- metadata [WPF], dependency properties
ms.assetid: 1fbada8e-4867-4ed1-8d97-62c07dad7ebc
ms.openlocfilehash: 2abe89abf1ab246464c8f7a7ca7c87295b0b3946
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458982"
---
# <a name="dependency-property-value-precedence"></a>종속성 속성 값 우선 순위
<a name="introduction"></a> 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템의 작업 방식이 종속성 속성 값에 영향을 주는 방식을 설명하고 속성 시스템의 일면이 속성의 유효 값이 적용되는 우선 순위에 관해 설명합니다.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에서 기존 종속성 속성의 이용자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](dependency-properties-overview.md)를 읽었다고 가정합니다. 이 항목의 예제를 따르려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 이해하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션을 작성하는 방법도 알아야 합니다.  
  
<a name="intro"></a>   
## <a name="the-wpf-property-system"></a>WPF 속성 시스템  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템에서는 실시간 속성 유효성 검사, 지연 바인딩, 다른 속성의 값에 관련 속성의 변경 사항 알림과 같은 기능을 사용하여 다양한 요소에 따라 종속성 속성 값을 결정할 강력한 방법을 제공합니다. 종속성 속성 값을 결정하는 데 사용되는 정확한 순서와 논리는 상당히 복잡합니다. 이 순서를 알면 불필요한 속성 설정을 피할 수 있으며 종속성 속성 값을 예상하거나 영향을 주려고 했을 때 예상과 다른 값이 나온 이유를 정확하게 파악할 수 있습니다.  
  
<a name="multiple_sets"></a>   
## <a name="dependency-properties-might-be-set-in-multiple-places"></a>종속성 속성을 여러 곳에 "설정"할 수 있음  
 다음은 동일한 속성 (<xref:System.Windows.Controls.Control.Background%2A>)에 값에 영향을 줄 수 있는 세 가지 다른 "설정" 작업이 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제입니다.  
  
 [!code-xaml[PropertiesOvwSupport#DPPrecedence](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#dpprecedence)]  
  
 여기에서 적용될 것으로 예상되는 색은 빨간색, 녹색, 파란색 중에 어느 것입니까?  
  
 애니메이션된 값과 강제 변환을 제외하면, 로컬 속성 설정이 가장 높은 우선 순위로 설정됩니다. 값을 로컬로 설정하면 그 값은 스타일이나 컨트롤 템플릿보다도 우선적으로 적용됩니다. 이 예제에서는 <xref:System.Windows.Controls.Control.Background%2A>를 로컬로 Red로 설정 합니다. 따라서이 범위에서 정의 된 스타일은 해당 범위에서 해당 형식의 모든 요소에 적용 되는 암시적 스타일 이더라도 <xref:System.Windows.Controls.Control.Background%2A> 속성 값을 제공 하는 데 가장 높은 우선 순위가 아닙니다.  그 단추 인스턴스에서 로컬 값 Red를 제거하면 스타일이 우선적으로 적용되어 단추에 스타일의 Background 값을 가져옵니다.  스타일 내에서는 트리거가 우선적으로 적용되므로 마우스가 위에 있을 때는 파란색, 그렇지 않을 때는 녹색이 됩니다.  
  
<a name="listing"></a>   
## <a name="dependency-property-setting-precedence-list"></a>종속성 속성 설정 우선 순위 목록  
 다음은 속성 시스템에서 종속성 속성의 런타임 값을 할당할 때 사용하는 최종적인 순서입니다. 가장 높은 우선 순위가 가장 먼저 나열됩니다. 이 목록은 [종속성 속성 개요](dependency-properties-overview.md)에 나와 있는 일반적인 순서를 확장한 것입니다.  
  
1. **속성 시스템 강제 변환.** 강제 변환에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [강제 변환, 애니메이션 및 기준 값](#animations)을 참조하십시오.  
  
2. **활성 애니메이션 또는 보류 동작이 있는 애니메이션.** 속성 애니메이션이 실제로 효과를 발휘하려면 기준 값이 로컬로 설정된 경우에도 애니메이션되지 않은 기준 값보다 높은 우선 순위를 가질 수 있어야 합니다. 자세한 내용은 이 항목의 뒷부분에 있는 [강제 변환, 애니메이션 및 기준 값](#animations)을 참조하십시오.  
  
3. **로컬 값.** 로컬 값은 "래퍼" 속성의 편의를 통해 설정할 수 있습니다 .이 속성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 특성 또는 속성 요소로 설정 하거나 특정 인스턴스의 속성을 사용 하 여 <xref:System.Windows.DependencyObject.SetValue%2A> API를 호출 하는 것과 같습니다. 바인딩이나 리소스를 사용하여 로컬 값을 설정하면 이들 각각은 직접 값을 설정한 것과 같은 우선 순위가 적용됩니다.  
  
4. **TemplatedParent 템플릿 속성.** 요소는 템플릿의 일부로 생성 된 경우에 <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 있습니다 (<xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.DataTemplate>). 적용 시기에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [TemplatedParent](#templatedparent)를 참조하십시오. 템플릿 내에서는 다음과 같은 우선 순위가 적용됩니다.  
  
    1. <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿의 트리거입니다.  
  
    2. <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿의 속성 집합 (일반적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성을 통해)  
  
5. **암시적 스타일.** `Style` 속성에만 적용됩니다. `Style` 속성은 해당 요소의 유형과 일치하는 키를 가진 스타일 리소스로 채워집니다. 해당 스타일 리소스가 페이지나 애플리케이션에 있어야 합니다. 암시적 스타일 리소스의 조회는 테마로 이어지지 않습니다.  
  
6. **스타일 트리거.** 페이지나 애플리케이션의 스타일에 있는 트리거(명시적 또는 암시적인 스타일일 수 있으나 우선 순위가 더 낮은 기본 스타일은 제외).  
  
7. **템플릿 트리거.** 스타일에 있는 템플릿 또는 직접 적용된 템플릿의 모든 트리거.  
  
8. **스타일 setter.** 페이지 또는 응용 프로그램의 스타일 내 <xref:System.Windows.Setter>의 값입니다.  
  
9. **기본(테마) 스타일.** 이 스타일이 적용되는 시기, 그리고 테마 스타일에 있는 템플릿과 테마 스타일의 관계에 대한 자세한 내용은 이 항목의 뒷부분에 있는 [기본(테마) 스타일](#themestyles)을 참조하십시오. 기본 스타일 내에서는 다음과 같은 우선 순위가 적용됩니다.  
  
    1. 테마 스타일의 활성 트리거.  
  
    2. 테마 스타일의 setter.  
  
10. **상속.** 몇 가지 종속성 속성은 상위 요소에서 하위 요소로 값을 상속하므로 애플리케이션 전체에서 각 요소에 따로 설정할 필요가 없습니다. 자세한 내용은 [속성 값 상속](property-value-inheritance.md)을 참조하십시오.  
  
11. **종속성 속성 메타데이터의 기본값.** 종속성 속성에는 해당 속성의 속성 시스템 등록에 따라 설정된 기본값이 있을 수 있습니다. 또한 종속성 속성을 상속하는 파생 클래스에서는 유형별로 해당 메타데이터를 재정의할 수 있습니다(기본값 포함). 자세한 내용은 [종속성 속성 메타데이터](dependency-property-metadata.md)를 참조하십시오. 기본값보다 먼저 상속을 확인하므로, 상속된 속성의 경우는 상위 요소의 기본값이 하위 요소의 기본값보다 우선적으로 적용됩니다.  따라서 상속 가능한 속성이 어디에서도 설정되어 있지 않으면 하위 요소의 기본값 대신 루트나 상위에 지정된 기본값이 사용됩니다.  
  
<a name="templatedparent"></a>   
## <a name="templatedparent"></a>TemplatedParent  
 우선 순위 항목으로서의 TemplatedParent는 표준 애플리케이션 마크업에서 직접 선언한 요소의 어느 속성에도 적용되지 않습니다. TemplatedParent 개념은 템플릿 적용을 통해 생긴 시각적 트리의 하위 항목에만 존재합니다. 속성 시스템이 <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿에서 값을 검색 하는 경우 해당 요소를 만든 템플릿을 검색 합니다. <xref:System.Windows.FrameworkElement.TemplatedParent%2A> 템플릿의 속성 값은 일반적으로 자식 요소에서 로컬 값으로 설정 된 것 처럼 동작 하지만, 템플릿이 잠재적으로 공유 될 수 있으므로 로컬 값과 우선 순위가 낮습니다. 자세한 내용은 <xref:System.Windows.FrameworkElement.TemplatedParent%2A>를 참조하십시오.  
  
<a name="style_property"></a>   
## <a name="the-style-property"></a>스타일 속성  
 앞에서 설명한 조회 순서는 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 제외 하 고 가능한 모든 종속성 속성에 적용 됩니다. <xref:System.Windows.FrameworkElement.Style%2A> 속성은 자체적으로 스타일을 지정할 수 없다는 고유 하므로 5 ~ 8 선행 항목은 적용 되지 않습니다. 또한 <xref:System.Windows.FrameworkElement.Style%2A> 애니메이션 또는 강제 변환 하지 않는 것이 좋으며, <xref:System.Windows.FrameworkElement.Style%2A>에 애니메이션을 적용 하려면 사용자 지정 애니메이션 클래스가 필요 합니다. 이는 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 설정할 수 있는 세 가지 방법을 유지 합니다.  
  
- **명시적 스타일.** <xref:System.Windows.FrameworkElement.Style%2A> 속성이 직접 설정 됩니다. 대부분의 시나리오에서 스타일은 인라인으로 정의되지 않고 명시적 키를 통해 리소스로 참조됩니다. 이 경우는 스타일 속성 자체가 우선 순위 항목 3인 로컬 값처럼 작동합니다.  
  
- **암시적 스타일.** <xref:System.Windows.FrameworkElement.Style%2A> 속성이 직접 설정 되지 않았습니다. 그러나 <xref:System.Windows.FrameworkElement.Style%2A>는 리소스 조회 시퀀스 (페이지, 응용 프로그램)에서 특정 수준으로 존재 하며 스타일이 적용 되는 형식과 일치 하는 리소스 키를 사용 하 여 키가 지정 됩니다. 이 경우 <xref:System.Windows.FrameworkElement.Style%2A> 속성 자체는 시퀀스에서 항목 5로 식별 된 우선 순위로 작동 합니다. 이 조건은 <xref:System.Windows.FrameworkElement.Style%2A> 속성에 대해 <xref:System.Windows.DependencyPropertyHelper>를 사용 하 고 결과에서 <xref:System.Windows.BaseValueSource.ImplicitStyleReference>을 검색 하 여 검색할 수 있습니다.  
  
- **기본 스타일**, 즉 **테마 스타일.** <xref:System.Windows.FrameworkElement.Style%2A> 속성은 직접 설정 되지 않으며 런타임까지 `null`으로 읽습니다. 이 경우 스타일은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 엔진에 포함된 런타임 테마 평가에서 옵니다.  
  
 테마가 아닌 암시적 스타일의 경우 형식이 정확히 일치 해야 합니다. `MyButton` `Button`파생 클래스는 `Button`에 대 한 스타일을 암시적으로 사용 하지 않습니다.  
  
<a name="themestyles"></a>   
## <a name="default-theme-styles"></a>기본(테마) 스타일  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 모든 컨트롤에는 기본 스타일이 있습니다. 이러한 기본 스타일은 테마에 따라 달라질 수 있으므로 테마 스타일이라고도 합니다.  
  
 컨트롤의 기본 스타일에 있는 가장 중요 한 정보는 해당 컨트롤 템플릿이 며, 테마 스타일에서 해당 <xref:System.Windows.Controls.Control.Template%2A> 속성의 setter로 존재 합니다. 기본 스타일에 템플릿이 없으면 사용자 지정 스타일에 사용자 지정 템플릿이 포함되어 있지 않은 컨트롤에는 시각적인 모양이 전혀 없습니다. 기본 스타일의 템플릿은 각 컨트롤의 시각적인 모양에 기본적인 구조를 정해 주며 템플릿에 정의된 속성과 해당 컨트롤 클래스 사이의 연결을 정의합니다. 각 컨트롤은 템플릿을 완전히 교체하지 않고 컨트롤의 시각적인 모양에 영향을 줄 수 있는 속성의 집합을 노출합니다. 예를 들어 <xref:System.Windows.Controls.Primitives.ScrollBar>의 구성 요소인 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤의 기본 시각적 모양을 고려 합니다.  
  
 <xref:System.Windows.Controls.Primitives.Thumb>에는 특정 한 사용자 지정 가능 속성이 있습니다. <xref:System.Windows.Controls.Primitives.Thumb>의 기본 템플릿은 여러 중첩 된 <xref:System.Windows.Controls.Border> 구성 요소가 포함 된 기본 구조/시각적 트리를 만들어 빗면 모양을 만듭니다. 템플릿에 포함 된 속성이 <xref:System.Windows.Controls.Primitives.Thumb> 클래스에서 사용자 지정을 위해 노출 되도록 하려면 해당 속성을 템플릿 내에서 [TemplateBinding](templatebinding-markup-extension.md)으로 노출 해야 합니다. <xref:System.Windows.Controls.Primitives.Thumb>의 경우 이러한 테두리의 다양 한 속성은 <xref:System.Windows.Controls.Border.Background%2A> 또는 <xref:System.Windows.Controls.Border.BorderThickness%2A>같은 속성에 대 한 템플릿 바인딩을 공유 합니다. 하지만 다른 특정 속성 또는 시각적 배치는 컨트롤 템플릿에 하드 코딩되거나 테마에서 직접 제공되는 값에 바인딩되어 템플릿 전체를 바꾸지 않는 한은 변경할 수 없습니다. 일반적으로, 속성이 템플릿 상위에서 오며 템플릿 바인딩을 통해 노출되지 않는 경우는, 쉽게 대상으로 지정할 방법이 없기 때문에 스타일을 통해 조정할 수 없습니다. 그러나 그 속성도 적용된 템플릿에서 상속된 속성 값이나 기본값의 영향을 받을 수는 있습니다.  
  
 테마 스타일에서는 유형을 정의에서 키로 사용합니다. 그러나 테마가 지정 된 요소 인스턴스에 적용 되는 경우이 형식의 테마 조회는 컨트롤의 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> 속성을 확인 하 여 수행 됩니다. 암시적 스타일과 같이 리터럴 Type을 사용하는 방법과는 대조적입니다. <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>의 값은 구현 자가 변경 하지 않은 경우에도 파생 클래스로 상속 됩니다. 속성을 변경 하는 방법은 속성 수준에서 재정의 하지 않고 속성 메타 데이터에서 기본값을 변경 하는 것입니다. 이 간접 참조를 사용하면 기본 클래스에서 원래는 스타일이 없었을(그 스타일에 템플릿이 없어 기본적인 시각적 모양이 전혀 없었을) 파생 요소의 테마 스타일을 정의할 수 있습니다. 따라서 <xref:System.Windows.Controls.Button>에서 `MyButton`를 파생 시킬 수 있으며, <xref:System.Windows.Controls.Button> 기본 템플릿이 계속 제공 됩니다. `MyButton`의 컨트롤 작성자가 다른 동작을 원하는 경우 `MyButton`의 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>에 대 한 종속성 속성 메타 데이터를 재정의 하 여 다른 키를 반환한 다음 `MyButton`에 대 한 템플릿을 포함 하 여 관련 테마 스타일을 정의할 수 있습니다. `MyButton` 컨트롤을 사용 하 여 패키지 해야 합니다. 테마, 스타일 및 컨트롤 작성에 대한 자세한 내용은 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하십시오.  
  
<a name="resources"></a>   
## <a name="dynamic-resource-references-and-binding"></a>동적 리소스 참조 및 바인딩  
 동적 리소스 참조 및 바인딩 작업에서는 설정된 위치의 우선 순위를 따릅니다. 예를 들어 로컬 값에 적용한 동적 리소스는 우선 순위 항목 3에 따라 작동하고, 테마 스타일에 있는 속성 setter의 바인딩은 우선 순위 항목 9에 따라 작동합니다. 동적 리소스 참조 및 바인딩은 모두 애플리케이션의 런타임 상태에서 값을 얻을 수 있어야 하므로 특정 속성의 속성 값 우선 순위를 결정하는 실제 프로세스가 런타임으로도 확장됩니다.  
  
 동적 리소스 참조는 엄밀하게 말해 속성 시스템에 포함되지 않지만, 위에 나열된 시퀀스와 상호 작용하는 자체 조회 순서가 있습니다. 그 우선 순위에 관한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)에 자세히 나와 있습니다. 기본적인 우선 순위를 요약해 보면 요소에서 페이지 루트, 애플리케이션, 테마, 시스템 순입니다.  
  
 동적 리소스 및 바인딩은 설정 위치의 우선 순위를 따르지만, 값은 지연됩니다. 그 때문에 생기는 결과 중 하나는 동적 리소스나 바인딩을 로컬 값에 설정하라 경우 로컬 값의 변화가 동적 리소스나 바인딩을 완전히 대체한다는 것입니다. <xref:System.Windows.DependencyObject.ClearValue%2A> 메서드를 호출 하 여 로컬로 설정 된 값을 지우면 동적 리소스 또는 바인딩이 복원 되지 않습니다. 실제로 동적 리소스나 바인딩이 있는 속성 (리터럴 로컬 값 없음)에서 <xref:System.Windows.DependencyObject.ClearValue%2A>를 호출 하는 경우에는 <xref:System.Windows.DependencyObject.ClearValue%2A> 호출에 의해 지워집니다.  
  
<a name="setcurrentvalue"></a>   
## <a name="setcurrentvalue"></a>SetCurrentValue  
 <xref:System.Windows.DependencyObject.SetCurrentValue%2A> 메서드는 속성을 설정 하는 또 다른 방법 이지만 우선 순위는 아닙니다. 대신 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용 하 여 이전 값의 소스를 덮어쓰지 않고 속성 값을 변경할 수 있습니다. 로컬 값의 우선 순위를 지정 하지 않고 값을 설정 하려는 경우 언제 든 지 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>을 사용할 수 있습니다. 예를 들어 트리거를 통해 속성을 설정 하 고 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 통해 다른 값을 할당 한 경우 속성 시스템은 계속 해 서 트리거를 발생 하 고 트리거의 동작이 발생 하면 속성이 변경 됩니다. <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용 하면 우선 순위가 더 높은 원본을 제공 하지 않고도 속성의 값을 변경할 수 있습니다. 마찬가지로 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>를 사용 하 여 바인딩을 덮어쓰지 않고 속성 값을 변경할 수 있습니다.  
  
<a name="animations"></a>   
## <a name="coercion-animations-and-base-value"></a>강제 변환, 애니메이션 및 기준 값  
 강제 변환 및 애니메이션은 모두 이 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] 전체에서 "기준 값"이라고 부르는 값에 적용됩니다. 따라서 기준 값은 항목 2에 도달할 때까지 위쪽으로 평가하여 결정된 값입니다.  
  
 애니메이션의 경우, 그 애니메이션이 특정 동작의 "From" 및 "To"를 모두 지정하지 않거나 애니메이션이 완료되었을 때 기준 값으로 돌아가도록 되어 있는 경우는 애니메이션된 값에서 기준 값의 효과를 적용할 수 있습니다. 이 작동을 실제로 확인하려면 [From, To 및 By 애니메이션 대상 값 샘플](https://go.microsoft.com/fwlink/?LinkID=159988)을 실행하십시오. 예에서 직사각형 높이의 로컬 값을 초기 로컬 값이 애니메이션에 있는 "From" 값과 달라지도록 설정해 보십시오. 애니메이션은 "From" 값을 사용하여 시작하며, 시작된 후에는 기준 값을 대체합니다. 애니메이션은 중지 <xref:System.Windows.Media.Animation.FillBehavior>를 지정 하 여 완료 된 후 애니메이션에 대해 발견 된 값으로 돌아가도록 지정할 수 있습니다. 그 후에는 일반적인 우선 순위를 사용하여 기준 값을 결정합니다.  
  
 여러 애니메이션을 단일 속성에 적용할 수 있으며, 이러한 애니메이션 각각은 값 우선 순위의 여러 지점에서 정의할 수 있습니다. 그러나 이러한 애니메이션을 사용하면 높은 우선 순위의 애니메이션이 그냥 적용되지 않고 값이 복합될 수도 있습니다. 결과는 애니메이션을 정의하는 정확한 방식과 애니메이션되는 값의 유형에 따라 달라집니다. 속성 애니메이션에 대한 자세한 내용은 [애니메이션 개요](../graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 강제 변환이 가장 높은 수준에서 적용됩니다. 이미 실행 중인 애니메이션도 값을 강제 변환할 수 있습니다. 어떤 기존 종속성 속성은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 기본 제공 강제 변환이 있습니다. 사용자 지정 종속성 속성의 경우 속성을 만들 때 <xref:System.Windows.CoerceValueCallback>을 작성 하 고 메타 데이터의 일부로 콜백을 전달 하 여 사용자 지정 종속성 속성에 대 한 강제 변환 동작을 정의 합니다. 파생 클래스에서 해당 속성의 메타데이터를 재정의하여 기존 속성의 강제 변환 동작을 재정의할 수도 있습니다. 적용 시점에 존재하는 강제 변환의 제약 조건을 따르면서 기준 값은 유지하는 방식으로 강제 변환과 기준 값이 상호 작용합니다. 따라서 나중에 강제 변환의 제약 조건이 제거되면 강제 변환에서 가능한 가장 가까운 값을 기준 값으로 반환하며, 그러면 모든 제약 조건이 제거되는 즉시 속성에 미치는 강제 변환의 영향이 사라집니다. 강제 변환 동작에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](dependency-property-callbacks-and-validation.md)를 참조하십시오.  
  
<a name="triggers"></a>   
## <a name="trigger-behaviors"></a>트리거 동작  
 컨트롤에서 테마에 있는 기본 스타일의 일부로서 트리거 동작을 정의하는 경우가 많습니다. 컨트롤에 로컬 속성을 설정하면 트리거가 시각적으로 또는 동작을 통해 사용자 기반 이벤트에 응답하지 못할 수 있습니다. 속성 트리거의 가장 일반적인 용도는 <xref:System.Windows.Controls.Primitives.Selector.IsSelected%2A>와 같은 컨트롤 또는 상태 속성에 대 한 것입니다. 예를 들어 기본적으로 <xref:System.Windows.Controls.Button> 사용 하지 않도록 설정 된 경우 (<xref:System.Windows.UIElement.IsEnabled%2A>에 대 한 트리거를 `false`하는 경우) 테마 스타일의 <xref:System.Windows.Controls.Control.Foreground%2A> 값으로 인해 컨트롤이 "회색으로 표시 됩니다."가 표시 됩니다. 그러나 로컬 <xref:System.Windows.Controls.Control.Foreground%2A> 값을 설정 하는 경우이 속성에서 트리거된 시나리오에도 불구 하 고 로컬 속성 집합에 의해 일반 회색 아웃 색이 우선 순위를 초과 합니다. 테마 수준 트리거 동작이 있는 속성의 값을 설정할 때 주의해야 하며, 해당 컨트롤의 사용자 경험을 과도하게 방해하지 않도록 주의해야 합니다.  
  
<a name="clearvalue"></a>   
## <a name="clearvalue-and-value-precedence"></a>ClearValue 및 값 우선 순위  
 <xref:System.Windows.DependencyObject.ClearValue%2A> 메서드는 요소에 설정 된 종속성 속성에서 로컬로 적용 되는 모든 값을 지우는 편리 함을 제공 합니다. 그러나 <xref:System.Windows.DependencyObject.ClearValue%2A>를 호출 하는 것은 속성 등록 중 메타 데이터에 설정 된 기본값이 새로운 유효 값이 되도록 보장 되지 않습니다. 값의 우선 순위에 있는 다른 항목도 모두 여전히 활성 상태입니다. 로컬에서 설정된 값만 우선 순위 시퀀스에서 제거되었습니다. 예를 들어 테마 스타일을 사용 하 여 속성을 설정 하는 속성에 대 한 <xref:System.Windows.DependencyObject.ClearValue%2A>를 호출 하는 경우 테마 값은 메타 데이터 기반 기본값이 아닌 새 값으로 적용 됩니다. 모든 속성 값 참가자를 프로세스에서 제외 하 고 값을 등록 된 메타 데이터 기본값으로 설정 하려는 경우 종속성 속성 메타 데이터를 쿼리하여 해당 기본값을 확인할 수 있습니다. 그런 다음 기본값을 로컬로 사용할 수 있습니다. <xref:System.Windows.DependencyObject.SetValue%2A>에 대 한 호출을 사용 하 여 속성을 설정 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.DependencyObject>
- <xref:System.Windows.DependencyProperty>
- [종속성 속성 개요](dependency-properties-overview.md)
- [사용자 지정 종속성 속성](custom-dependency-properties.md)
- [종속성 속성 콜백 및 유효성 검사](dependency-property-callbacks-and-validation.md)
