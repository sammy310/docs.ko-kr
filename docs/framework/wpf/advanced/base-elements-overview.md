---
title: 기본 요소 개요
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 7d52d951d4fa4df83bbcca6b4cb479e18e532d2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141630"
---
# <a name="base-elements-overview"></a>기본 요소 개요
에 있는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 높은 백분율은 일반적으로 기본 요소 클래스로 SDK 설명서에서 참조 되는 4 개의 클래스에서 파생 됩니다. 이러한 <xref:System.Windows.UIElement>클래스는 <xref:System.Windows.FrameworkElement> <xref:System.Windows.ContentElement>" <xref:System.Windows.FrameworkContentElement>및 . 클래스는 <xref:System.Windows.DependencyObject> 둘 다의 <xref:System.Windows.UIElement> 공통 기본 클래스이기 때문에<xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>WPF 클래스의 기본 요소 API  
 둘 <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> 다에서 <xref:System.Windows.DependencyObject>파생됩니다 . 이 수준에서 분할은 사용자 <xref:System.Windows.UIElement> 인터페이스에서 또는 <xref:System.Windows.ContentElement> 사용되는 방법과 응용 프로그램에서 제공하는 용도를 다룹니다. <xref:System.Windows.UIElement>또한 <xref:System.Windows.Media.Visual> 의 기본 으로 낮은 수준의 그래픽 지원을 노출 하는 클래스 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]계층 구조에 있습니다. <xref:System.Windows.Media.Visual>은 독립적인 직사각형 화면 영역을 정의하여 렌더링 프레임워크를 제공합니다. 실제로 <xref:System.Windows.UIElement> 더 큰 개체 모델을 지원하는 요소는 직사각형 화면 영역으로 설명할 수 있는 영역으로 렌더링및 레이아웃을 지정하고 콘텐츠 모델이 의도적으로 더 개방되어 있는 영역으로 레이아웃하여 다양한 요소 조합을 허용하는 것입니다. <xref:System.Windows.ContentElement>에서 <xref:System.Windows.Media.Visual>파생되지 않습니다. 이 모델은 요소를 <xref:System.Windows.ContentElement> 해석한 다음 사용할 수 있는 전체를 <xref:System.Windows.Media.Visual> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 생성하는 판독기 또는 뷰어와 같은 다른 것에 의해 사용됩니다. 특정 <xref:System.Windows.UIElement> 클래스는 콘텐츠 호스트로 의도됩니다. <xref:System.Windows.ContentElement> <xref:System.Windows.Controls.DocumentViewer> <xref:System.Windows.ContentElement>다소 작은 개체 모델이 있는 요소의 기본 클래스로 사용되며 <xref:System.Windows.UIElement>에서 호스팅될 수 있는 텍스트, 정보 또는 문서 내용을 더 많이 처리합니다.  
  
### <a name="framework-level-and-core-level"></a>프레임워크 수준 및 코어 수준  
 <xref:System.Windows.UIElement><xref:System.Windows.FrameworkElement>의 기본 클래스 역할을 <xref:System.Windows.ContentElement> 하며 에 대한 <xref:System.Windows.FrameworkContentElement>기본 클래스역할을 합니다. 이 다음 수준의 클래스의 이유는 WPF 프레임워크 수준과 는 별개의 WPF 코어 수준을 지원하기 위해이 부서도 프레젠테이션 코어와 프레젠테이션 프레임 워크 어셈블리 간에 API를 분할하는 방법에 존재합니다. WPF 프레임워크 수준은 프레젠테이션을 위한 레이아웃 관리자의 구현을 포함하여 기본 애플리케이션 요구 사항을 충족하는 보다 완벽한 솔루션을 제공합니다. WPF 코어 수준은 추가 어셈블리의 오버헤드 없이 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용할 수 있습니다. 이러한 수준 간의 차이는 대부분의 일반적인 응용 프로그램 개발 시나리오에서 매우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 드물게 중요하며 일반적으로 API를 전체적으로 생각하고 WPF 프레임워크 수준과 WPF 코어 수준 간의 차이에 신경 쓰지 않아야 합니다. 전체 솔루션에 이미 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컴퍼지션 및 레이아웃 구현이 있는 경우와 같이 애플리케이션 디자인에서 WPF 프레임워크 수준 기능의 실질적인 상당한 부분을 대체하도록 선택하는 경우에는 이러한 수준 구분에 대해 알고 있어야 합니다.  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>파생될 요소 선택  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 확장하는 사용자 지정 클래스를 만드는 가장 실질적인 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 중 하나에서 기존 클래스 계층 구조를 통해 필요한 기능을 가능한 많이 얻을 수 있는 클래스가 파생되는 것입니다. 이 섹션에서는 상속할 클래스를 결정하는 데 도움이 되는 가장 중요한 세 가지 요소 클래스와 함께 제공되는 기능을 나열합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에서 파생되는 일반적인 이유 중 하나인 컨트롤을 구현하는 경우 실용적인 컨트롤, 컨트롤 패밀리 기본 클래스 또는 적어도 <xref:System.Windows.Controls.Control> 기본 클래스에서 파생하려는 경우를 볼 수 있습니다. 몇 가지 지침과 실제 예제는 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하세요.  
  
 컨트롤을 만들지 않고 계층 구조의 더 높은 수준에 있는 클래스에서 파생되어야 하는 경우 다음 섹션이 각 기본 요소 클래스에 정의된 특성에 대한 지침으로 사용됩니다.  
  
 에서 <xref:System.Windows.DependencyObject>파생 되는 클래스를 만드는 경우 다음 기능을 상속 합니다.  
  
- <xref:System.Windows.DependencyObject.GetValue%2A>지원, <xref:System.Windows.DependencyObject.SetValue%2A> 일반 재산 시스템 지원.  
  
- 종속성 속성 및 종속성 속성으로 구현되는 연결된 속성을 사용할 수 있는 기능  
  
 에서 <xref:System.Windows.UIElement>파생 되는 클래스를 만드는 경우 <xref:System.Windows.DependencyObject>다음 에서 제공 하는 기능 외에 다음 기능을 상속 합니다.  
  
- 애니메이션 속성 값에 대한 기본 지원 - 자세한 내용은 [애니메이션 개요를](../graphics-multimedia/animation-overview.md)참조하십시오.  
  
- 기본 입력 이벤트 지원 및 명령 지원 - 자세한 내용은 [입력 개요](input-overview.md) 및 [명령 개요](commanding-overview.md)를 참조하세요.  
  
- 레이아웃 시스템에 정보를 제공하도록 재정의될 수 있는 가상 메서드  
  
 에서 <xref:System.Windows.FrameworkElement>파생 되는 클래스를 만드는 경우 <xref:System.Windows.UIElement>다음 에서 제공 하는 기능 외에 다음 기능을 상속 합니다.  
  
- 스타일 지정 및 스토리보드 지원 - 자세한 내용은 및 <xref:System.Windows.Style> [스토리보드 개요를](../graphics-multimedia/storyboards-overview.md)참조하십시오.  
  
- 데이터 바인딩 지원 - 자세한 내용은 [데이터 바인딩 개요를](../data/data-binding-overview.md)참조하십시오.  
  
- 동적 리소스 참조 지원 - 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.  
  
- 속성 값 상속 지원 및 프레임워크 서비스(예: 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현)에 대한 속성 조건을 보고하는 데 도움이 되는 메타데이터의 기타 플래그 - 자세한 내용은 [프레임워크 속성 메타데이터](framework-property-metadata.md)를 참조하세요.  
  
- 논리 트리의 개념 - 자세한 내용은 [WPF의 트리](trees-in-wpf.md)를 참조하세요.  
  
- 레이아웃에 영향을 주는 속성에 대한 변경 내용을 검색할 수 있는 재정의를 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 포함하여 레이아웃 시스템의 실제 WPF 프레임워크 수준 구현을 지원합니다.  
  
 에서 <xref:System.Windows.ContentElement>파생 되는 클래스를 만드는 경우 <xref:System.Windows.DependencyObject>다음 에서 제공 하는 기능 외에 다음 기능을 상속 합니다.  
  
- 애니메이션 지원 - 자세한 내용은 [애니메이션 개요를](../graphics-multimedia/animation-overview.md)참조하십시오.  
  
- 기본 입력 이벤트 지원 및 명령 지원 - 자세한 내용은 [입력 개요](input-overview.md) 및 [명령 개요](commanding-overview.md)를 참조하세요.  
  
 에서 <xref:System.Windows.FrameworkContentElement>파생 되는 클래스를 만드는 경우 다음 에서 <xref:System.Windows.ContentElement>제공 하는 것 외에도 다음 기능을 얻을 수 있습니다.  
  
- 스타일 지정 및 스토리보드 지원 - 자세한 내용은 및 <xref:System.Windows.Style> [애니메이션 개요를](../graphics-multimedia/animation-overview.md)참조하십시오.  
  
- 데이터 바인딩 지원 - 자세한 내용은 [데이터 바인딩 개요를](../data/data-binding-overview.md)참조하십시오.  
  
- 동적 리소스 참조 지원 - 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.  
  
- 속성 값 상속 지원 및 프레임워크 서비스(예: 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현)에 대한 속성 조건을 보고하는 데 도움이 되는 메타데이터의 기타 플래그 - 자세한 내용은 [프레임워크 속성 메타데이터](framework-property-metadata.md)를 참조하세요.  
  
- 레이아웃 시스템 수정(예:)에 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>대한 액세스는 상속되지 않습니다. 레이아웃 시스템 구현은 에서만 <xref:System.Windows.FrameworkElement>사용할 수 있습니다. 그러나 레이아웃에 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 영향을 주는 속성에 대한 변경 내용을 검색하고 콘텐츠 호스트에 보고할 수 있는 재정의를 상속합니다.  
  
 컨텐츠 모델은 다양한 클래스에서 사용할 수 있도록 문서화되어 있습니다. 클래스의 콘텐츠 모델은 파생될 적절한 클래스를 찾을 때 고려해야 할 요소입니다. 자세한 내용은 [WPF 콘텐츠 모델을](../controls/wpf-content-model.md)참조하십시오.  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>기타 기본 클래스  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델에 대한 지원을 제공하고 응용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그램에 대해 생성된 <xref:System.Windows.Threading.Dispatcher>모든 개체를 에 연결할 수 있습니다. <xref:System.Windows.UIElement>에서 파생되지 <xref:System.Windows.DependencyObject>않더라도 이 <xref:System.Windows.Media.Visual>스레딩 모델 지원을 얻으려면 <xref:System.Windows.Threading.DispatcherObject> 파생하는 것이 좋습니다. 자세한 내용은 [스레딩 모델](threading-model.md)을 참조하세요.  
  
### <a name="visual"></a>시각적 개체  
 <xref:System.Windows.Media.Visual>일반적으로 대략 직사각형 영역에서 시각적 인 프리젠 테이션을 필요로하는 2D 개체의 개념을 구현합니다. 실제 렌더링은 <xref:System.Windows.Media.Visual> 다른 클래스에서 발생하지만(독립적이지 않음) <xref:System.Windows.Media.Visual> 클래스는 다양한 수준에서 프로세스를 렌더링하는 데 사용되는 알려진 형식을 제공합니다. <xref:System.Windows.Media.Visual>적중 테스트를 구현하지만 적중 테스트 긍정을 보고하는 이벤트는 노출되지 않습니다.) <xref:System.Windows.UIElement> 자세한 내용은 [시각적 계층 프로그래밍](../graphics-multimedia/visual-layer-programming.md)을 참조하세요.  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable>성능상의 이유로 변경할 수 없는 개체가 필요하거나 원하는 경우 개체의 복사본을 생성하는 수단을 제공하여 변경 가능한 개체에서 불변성을 시뮬레이션합니다. 이 <xref:System.Windows.Freezable> 형식은 애니메이션뿐만 아니라 형상 및 브러시와 같은 특정 그래픽 요소에 대한 공통적인 기준을 제공합니다. 특히, <xref:System.Windows.Freezable> <xref:System.Windows.Media.Visual>a는; 다른 개체의 속성 값을 채우기 <xref:System.Windows.Freezable> 위해 적용될 때 하위 속성이 되는 속성을 보유할 수 있으며 이러한 하위 속성은 렌더링에 영향을 줄 수 있습니다. 자세한 내용은 [Freezable 개체 개요](freezable-objects-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>는 <xref:System.Windows.Freezable> 현재 애니메이션된 속성을 애니메이션되지 않은 속성과 구별할 수 있도록 애니메이션 컨트롤 레이어와 일부 유틸리티 멤버를 특별히 추가하는 파생 클래스입니다.  
  
### <a name="control"></a>제어  
 <xref:System.Windows.Controls.Control>는 기술에 따라 컨트롤 또는 구성 요소라고 다양하게 불리는 개체 유형에 대한 의도된 기본 클래스입니다. 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 클래스는 UI 컨트롤을 직접 나타내거나 컨트롤 컴퍼지션에 밀접하게 참여하는 클래스입니다. 이를 가능하게 <xref:System.Windows.Controls.Control> 하는 기본 기능은 컨트롤 템플릿입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.Control>
- [종속성 속성 개요](dependency-properties-overview.md)
- [컨트롤 제작 개요](../controls/control-authoring-overview.md)
- [WPF 아키텍처](wpf-architecture.md)
