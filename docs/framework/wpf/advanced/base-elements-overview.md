---
title: 기본 요소 개요
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 6f8542be5a84a4b8b4cabf594c32d6fdfd3757d2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453772"
---
# <a name="base-elements-overview"></a>기본 요소 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에는 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] 설명서에서 일반적으로 기본 요소 클래스라고 하는 네 가지 클래스에서 파생된 클래스가 많습니다. 이러한 클래스는 <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>및 <xref:System.Windows.FrameworkContentElement>입니다. <xref:System.Windows.DependencyObject> 클래스는 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement>의 공통 기본 클래스 이므로 관련이 있습니다.  

<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>WPF 클래스의 기본 요소 API  
 <xref:System.Windows.UIElement>와 <xref:System.Windows.ContentElement>는 모두 약간 다른 경로를 통해 <xref:System.Windows.DependencyObject>에서 파생 됩니다. 이 수준에서 분할은 사용자 인터페이스에서 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.ContentElement>를 사용 하는 방법 및 응용 프로그램에서 제공 하는 용도를 다룹니다. <xref:System.Windows.UIElement>의 클래스 계층 구조에는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 기반이 되는 하위 수준의 그래픽 지원을 제공 하는 클래스도 <xref:System.Windows.Media.Visual> 있습니다. <xref:System.Windows.Media.Visual>는 독립 사각형 화면 영역을 정의 하 여 렌더링 프레임 워크를 제공 합니다. 실제로는 더 큰 개체 모델을 지 원하는 요소에 대 한 <xref:System.Windows.UIElement> 이며, 사각형 화면 영역으로 설명할 수 있는 영역으로 렌더링 및 레이아웃을 사용 하 고, 서로 다른 조합을 허용 하기 위해 콘텐츠 모델이 의도적으로 더 열려 있습니다. 요소입니다. <xref:System.Windows.ContentElement> <xref:System.Windows.Media.Visual>에서 파생 되지 않습니다. 해당 모델은 <xref:System.Windows.ContentElement>를 사용 하 여 요소를 해석 하 고 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에 대 한 전체 <xref:System.Windows.Media.Visual>을 생성 하는 판독기 또는 뷰어와 같은 다른 항목에서 사용 됩니다. 특정 <xref:System.Windows.UIElement> 클래스는 콘텐츠 호스트로 사용 됩니다 .이 클래스는 하나 이상의 <xref:System.Windows.ContentElement> 클래스에 대 한 호스팅 및 렌더링을 제공 합니다 (<xref:System.Windows.Controls.DocumentViewer>는 이러한 클래스의 예). <xref:System.Windows.ContentElement>는 약간 작은 개체 모델이 있는 요소에 대 한 기본 클래스로 사용 되며, <xref:System.Windows.UIElement>내에서 호스팅될 수 있는 텍스트, 정보 또는 문서 콘텐츠를 더 많이 처리 합니다.  
  
### <a name="framework-level-and-core-level"></a>프레임워크 수준 및 코어 수준  
 <xref:System.Windows.UIElement>는 <xref:System.Windows.FrameworkElement>에 대 한 기본 클래스로 사용 되며 <xref:System.Windows.ContentElement> <xref:System.Windows.FrameworkContentElement>에 대 한 기본 클래스로 사용 됩니다. 클래스의 다음 수준에 대 한 이유는 WPF 프레임 워크 수준과는 별개의 WPF core 수준을 지 원하는 것입니다 .이 나누기는 Api가 PresentationCore 및 PresentationFramework 어셈블리 간에 분할 되는 방식에도 존재 합니다. WPF 프레임워크 수준은 프레젠테이션을 위한 레이아웃 관리자의 구현을 포함하여 기본 애플리케이션 요구 사항을 충족하는 보다 완벽한 솔루션을 제공합니다. WPF 코어 수준은 추가 어셈블리의 오버헤드 없이 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용할 수 있습니다. 이러한 수준 간의 차이는 대부분의 일반적인 응용 프로그램 개발 시나리오에서 매우 중요 하지 않으며 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api를 전체적으로 생각 하 고 WPF 프레임 워크 수준과 WPF 코어 수준 간의 차이를 걱정 하지 않아야 합니다. 전체 솔루션에 이미 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컴퍼지션 및 레이아웃 구현이 있는 경우와 같이 애플리케이션 디자인에서 WPF 프레임워크 수준 기능의 실질적인 상당한 부분을 대체하도록 선택하는 경우에는 이러한 수준 구분에 대해 알고 있어야 합니다.  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>파생될 요소 선택  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 확장하는 사용자 지정 클래스를 만드는 가장 실질적인 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 중 하나에서 기존 클래스 계층 구조를 통해 필요한 기능을 가능한 많이 얻을 수 있는 클래스가 파생되는 것입니다. 이 섹션에서는 상속할 클래스를 결정하는 데 도움이 되는 가장 중요한 세 가지 요소 클래스와 함께 제공되는 기능을 나열합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스에서 파생 하는 일반적인 이유 중 하나인 컨트롤을 구현 하는 경우 실제 컨트롤, 컨트롤 패밀리 기본 클래스 또는 적어도 <xref:System.Windows.Controls.Control> 기본 클래스의 클래스에서 파생 하는 것이 좋습니다. 몇 가지 지침과 실제 예제는 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하세요.  
  
 컨트롤을 만들지 않고 계층 구조의 더 높은 수준에 있는 클래스에서 파생되어야 하는 경우 다음 섹션이 각 기본 요소 클래스에 정의된 특성에 대한 지침으로 사용됩니다.  
  
 <xref:System.Windows.DependencyObject>에서 파생 되는 클래스를 만드는 경우 다음 기능을 상속 합니다.  
  
- <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 지원 및 일반 속성 시스템 지원.  
  
- 종속성 속성 및 종속성 속성으로 구현되는 연결된 속성을 사용할 수 있는 기능  
  
 <xref:System.Windows.UIElement>에서 파생 되는 클래스를 만드는 경우 <xref:System.Windows.DependencyObject>에서 제공 하는 것 외에도 다음 기능을 상속 합니다.  
  
- 애니메이션 속성 값에 대한 기본 지원 - 자세한 내용은 [애니메이션 개요](../graphics-multimedia/animation-overview.md)를 참조하세요.  
  
- 기본 입력 이벤트 지원 및 명령 지원 - 자세한 내용은 [입력 개요](input-overview.md) 및 [명령 개요](commanding-overview.md)를 참조하세요.  
  
- 레이아웃 시스템에 정보를 제공하도록 재정의될 수 있는 가상 메서드  
  
 <xref:System.Windows.FrameworkElement>에서 파생 되는 클래스를 만드는 경우 <xref:System.Windows.UIElement>에서 제공 하는 것 외에도 다음 기능을 상속 합니다.  
  
- 스타일 지정 및 스토리보드 지원 - 자세한 내용은 <xref:System.Windows.Style> 및 [Storyboard 개요](../graphics-multimedia/storyboards-overview.md)를 참조 하세요.  
  
- 데이터 바인딩 지원 - 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.  
  
- 동적 리소스 참조 지원 - 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.  
  
- 속성 값 상속 지원 및 프레임워크 서비스(예: 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현)에 대한 속성 조건을 보고하는 데 도움이 되는 메타데이터의 기타 플래그 - 자세한 내용은 [프레임워크 속성 메타데이터](framework-property-metadata.md)를 참조하세요.  
  
- 논리 트리의 개념 - 자세한 내용은 [WPF의 트리](trees-in-wpf.md)를 참조하세요.  
  
- 레이아웃에 영향을 주는 속성의 변경 내용을 검색할 수 있는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 재정의를 포함 하 여 레이아웃 시스템의 실용적인 WPF 프레임 워크 수준 구현을 지원 합니다.  
  
 <xref:System.Windows.ContentElement>에서 파생 되는 클래스를 만드는 경우 <xref:System.Windows.DependencyObject>에서 제공 하는 것 외에도 다음 기능을 상속 합니다.  
  
- 애니메이션 지원 - 자세한 내용은 [애니메이션 개요](../graphics-multimedia/animation-overview.md)를 참조하세요.  
  
- 기본 입력 이벤트 지원 및 명령 지원 - 자세한 내용은 [입력 개요](input-overview.md) 및 [명령 개요](commanding-overview.md)를 참조하세요.  
  
 <xref:System.Windows.FrameworkContentElement>에서 파생 되는 클래스를 만드는 경우 <xref:System.Windows.ContentElement>에서 제공 하는 것 외에 다음과 같은 기능을 사용할 수 있습니다.  
  
- 스타일 지정 및 스토리보드 지원 - 자세한 내용은 <xref:System.Windows.Style> 및 [애니메이션 개요](../graphics-multimedia/animation-overview.md)를 참조 하세요.  
  
- 데이터 바인딩 지원 - 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.  
  
- 동적 리소스 참조 지원 - 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.  
  
- 속성 값 상속 지원 및 프레임워크 서비스(예: 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현)에 대한 속성 조건을 보고하는 데 도움이 되는 메타데이터의 기타 플래그 - 자세한 내용은 [프레임워크 속성 메타데이터](framework-property-metadata.md)를 참조하세요.  
  
- 레이아웃 시스템 수정 (예: <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>)에 대 한 액세스를 상속 하지 않습니다. 레이아웃 시스템 구현은 <xref:System.Windows.FrameworkElement>에서만 사용할 수 있습니다. 그러나 레이아웃에 영향을 주는 속성의 변경 내용을 감지 하 여 콘텐츠 호스트에 보고 하는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 재정의를 상속 합니다.  
  
 컨텐츠 모델은 다양한 클래스에서 사용할 수 있도록 문서화되어 있습니다. 클래스의 콘텐츠 모델은 파생될 적절한 클래스를 찾을 때 고려해야 할 요소입니다. 자세한 내용은 [WPF 콘텐츠 모델](../controls/wpf-content-model.md)을 참조하세요.  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>기타 기본 클래스  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델을 지원 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대해 생성 된 모든 개체를 <xref:System.Windows.Threading.Dispatcher>연결 하도록 설정 합니다. <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>또는 <xref:System.Windows.Media.Visual>에서 파생 되지 않은 경우에도이 스레딩 모델을 지원 하기 위해 <xref:System.Windows.Threading.DispatcherObject>에서 파생 하는 것을 고려해 야 합니다. 자세한 내용은 [스레딩 모델](threading-model.md)을 참조하세요.  
  
### <a name="visual"></a>시각적 개체  
 <xref:System.Windows.Media.Visual>은 일반적으로 약 사각형 영역에서 시각적 프레젠테이션을 필요로 하는 2D 개체의 개념을 구현 합니다. <xref:System.Windows.Media.Visual>의 실제 렌더링은 다른 클래스에서 발생 하지만 (자체 포함 되지 않음), <xref:System.Windows.Media.Visual> 클래스는 다양 한 수준에서 렌더링 프로세스에 사용 되는 알려진 형식을 제공 합니다. <xref:System.Windows.Media.Visual> 적중 테스트를 구현 하지만 적중 테스트 긍정 (<xref:System.Windows.UIElement>)을 보고 하는 이벤트를 노출 하지 않습니다. 자세한 내용은 [시각적 계층 프로그래밍](../graphics-multimedia/visual-layer-programming.md)을 참조하세요.  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable>은 변경 불가능 한 개체가 필요 하거나 성능상의 이유로 필요한 경우 개체의 복사본을 생성 하는 수단을 제공 하 여 변경 가능한 개체의 불변성을 시뮬레이션 합니다. <xref:System.Windows.Freezable> 형식은 기 하 도형 및 브러시와 같은 특정 그래픽 요소 및 애니메이션에 대 한 공통 기반을 제공 합니다. 특히 <xref:System.Windows.Freezable>은 <xref:System.Windows.Media.Visual>되지 않습니다. 다른 개체의 속성 값을 채우기 위해 <xref:System.Windows.Freezable> 적용 될 때 하위 속성이 되는 속성을 포함할 수 있으며, 이러한 하위 속성은 렌더링에 영향을 줄 수 있습니다. 자세한 내용은 [Freezable 개체 개요](freezable-objects-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>는 애니메이션 컨트롤 계층과 일부 유틸리티 멤버를 특별히 추가 하 여 애니메이션이 적용 되지 않는 속성에서 현재 애니메이션 된 속성을 구분할 수 있도록 하는 <xref:System.Windows.Freezable> 파생 클래스입니다.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control>는 기술에 따라 컨트롤이 나 구성 요소로 다양 되는 개체 형식에 대 한 기본 클래스입니다. 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 클래스는 UI 컨트롤을 직접 나타내거나 컨트롤 컴퍼지션에 밀접하게 참여하는 클래스입니다. 을 사용 하도록 설정 <xref:System.Windows.Controls.Control>는 기본 기능은 컨트롤 템플릿입니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.Control>
- [종속성 속성 개요](dependency-properties-overview.md)
- [컨트롤 제작 개요](../controls/control-authoring-overview.md)
- [WPF 아키텍처](wpf-architecture.md)
