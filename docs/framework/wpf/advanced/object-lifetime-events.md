---
title: 개체 수명 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- events [WPF], ContentRendered
- events [WPF], Deactivated
- events [WPF], Unloaded
- Activated events [WPF]
- events [WPF], Loaded
- Application objects [WPF], lifetime events
- events [WPF], Activated
- ContentRendered events [WPF]
- Deactivated events [WPF]
- events [WPF], Initialized
- events [WPF], Closing
- Unloaded events [WPF]
- exit events [WPF]
- objects' lifetime events [WPF]
- Loaded events [WPF]
- Closing events [WPF]
- events [WPF], Closed
- Initialized events [WPF]
- Closed events [WPF]
- startup events [WPF]
- lifetime events of objects [WPF]
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
ms.openlocfilehash: 3b761674bd2464ee87e07d9299c805431f8fdeb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141109"
---
# <a name="object-lifetime-events"></a>개체 수명 이벤트
이 항목에서는 생성, 사용 및 소멸 등의 개체 수명 단계를 나타내는 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트에 대해 설명합니다.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 기존 종속성 속성의 소비자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](dependency-properties-overview.md) 항목을 읽었다고 가정합니다. 이 항목의 예제를 따르려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]([XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md) 참조)과 함께 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션을 작성하는 방법을 알아야 합니다.  
  
<a name="intro"></a>
## <a name="object-lifetime-events"></a>개체 수명 이벤트  
 Microsoft .NET Framework 관리 코드의 모든 개체는 비슷한 수명 단계, 생성, 사용 및 파괴 단계를 거치게 됩니다. 또한 많은 개체에는 소멸 단계의 일부로 발생하는 종료 단계가 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체, 특히 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 요소로 식별하는 시각적 개체에는 개체 수명의 공통 단계 집합이 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍 및 애플리케이션 모델은 이러한 단계를 일련의 이벤트로 노출합니다. 수명 이벤트와 관련하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 일반적인 요소, 창 요소, 탐색 호스트 및 애플리케이션 개체 등 네 가지 기본 유형의 개체가 있습니다. Windows 및 탐색 호스트도 시각적 개체(요소)의 더 큰 그룹에 속합니다. 이 항목에서는 모든 요소에 공통적으로 적용되는 수명 이벤트에 대해 설명한 다음 애플리케이션 정의, 창 또는 탐색 호스트에 적용되는 특정 이벤트를 소개합니다.  
  
<a name="common_events"></a>
## <a name="common-lifetime-events-for-elements"></a>요소에 대한 공통 수명 이벤트  
 모든 WPF 프레임워크 수준 <xref:System.Windows.FrameworkElement> 요소(또는 <xref:System.Windows.FrameworkContentElement>파생된 개체)에는 세 가지 <xref:System.Windows.FrameworkElement.Initialized> <xref:System.Windows.FrameworkElement.Loaded>공통 <xref:System.Windows.FrameworkElement.Unloaded>수명 이벤트가 있습니다.  
  
### <a name="initialized"></a>초기화됨  
 <xref:System.Windows.FrameworkElement.Initialized>먼저 발생하며 대략 해당 생성자 호출에 의해 개체의 초기화에 해당합니다. 이 이벤트는 초기화에 응답하여 발생하므로 이 이벤트가 발생하면 개체의 모든 속성이 설정되어 있음을 알 수 있습니다 (예외는 동적 리소스 또는 바인딩과 같은 식 사용입니다. 이러한 식은 평가되지 않은 식입니다.) 모든 속성이 설정되는 요구 사항의 결과로 <xref:System.Windows.FrameworkElement.Initialized> 태그에 정의된 중첩 된 요소에 의해 발생 되는 시퀀스는 요소 트리에서 가장 깊은 요소의 순서로 발생 하는 것으로 나타납니다., 다음 루트를 향해 부모 요소. 순서가 이와 같은 이유는 부모/자식 관계와 포함이 속성이고 따라서 부모는 속성을 채우는 자식 요소 또한 완전히 초기화되기 전에는 초기화를 보고할 수 없기 때문입니다.  
  
 <xref:System.Windows.FrameworkElement.Initialized> 이벤트에 대한 응답으로 처리기를 작성하는 경우 처리기가 연결된 요소 트리(논리 트리 또는 시각적 트리)의 다른 모든 요소( 특히 부모 요소가 작성되었음)가 보장되지 않는다는 점을 고려해야 합니다. 멤버 변수가 null일 수 있거나 식 수준에서도 데이터 소스가 기본 바인딩으로 채워지지 않을 수도 있습니다.  
  
### <a name="loaded"></a>로드됨  
 <xref:System.Windows.FrameworkElement.Loaded>다음에 제기됩니다. 이벤트는 <xref:System.Windows.FrameworkElement.Loaded> 최종 렌더링 전에 발생하지만 레이아웃 시스템이 렌더링에 필요한 모든 값을 계산한 후에 발생합니다. <xref:System.Windows.FrameworkElement.Loaded>요소는 내에 포함 된 논리 트리가 완료 하 고 HWND 및 렌더링 표면을 제공 하는 프레젠테이션 소스에 연결 하는 것을 수반 합니다. 표준 데이터 바인딩(다른 속성 또는 직접 정의된 데이터 원본과 같은 로컬 <xref:System.Windows.FrameworkElement.Loaded>원본에 바인딩)이 이전에 발생했을 것입니다. 비동기 데이터 바인딩(외부 또는 동적 소스)이 발생할 수도 있지만 비동기라는 용어에서 유추할 수 있듯이 그 발생 여부를 보장할 수는 없습니다.  
  
 <xref:System.Windows.FrameworkElement.Loaded> 이벤트가 발생되는 메커니즘은 와 <xref:System.Windows.FrameworkElement.Initialized>다릅니다. 이벤트는 <xref:System.Windows.FrameworkElement.Initialized> 완료된 요소 트리에 의한 직접 조정 없이 요소별로 발생합니다. 반대로 <xref:System.Windows.FrameworkElement.Loaded> 이벤트는 전체 요소 트리(특히 논리 트리)에서 조정된 노력으로 발생합니다. 트리의 모든 요소가 로드된 것으로 간주되는 상태에 있으면 <xref:System.Windows.FrameworkElement.Loaded> 루트 요소에서 이벤트가 먼저 발생합니다. 그런 <xref:System.Windows.FrameworkElement.Loaded> 다음 각 자식 요소에서 이벤트가 연속적으로 발생합니다.  
  
> [!NOTE]
> 이 동작은 표면적으로 볼 때 라우트된 이벤트의 터널링과 유사할 수 있습니다. 그러나 이벤트 간에 정보가 전달되지 않습니다. 각 요소는 항상 해당 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리할 수 있는 기회가 있으며 처리된 이벤트 데이터를 표시하면 해당 요소 이외의 영향은 없습니다.  
  
### <a name="unloaded"></a>언로드됨  
 <xref:System.Windows.FrameworkElement.Unloaded>마지막으로 발생하며 프레젠테이션 소스 또는 제거중인 시각적 부모에 의해 시작됩니다. 제기되고 <xref:System.Windows.FrameworkElement.Unloaded> 처리될 때 이벤트 소스 부모(속성에 의해 <xref:System.Windows.FrameworkElement.Parent%2A> 결정된 대로) 요소 또는 논리 또는 시각적 트리의 위쪽으로 지정된 요소가 이미 설정되지 않았을 수 있으므로 데이터 바인딩, 리소스 참조 및 스타일이 정상 또는 마지막으로 알려진 런타임 값으로 설정되지 않을 수 있습니다.  
  
<a name="application_model_elements"></a>
## <a name="lifetime-events-application-model-elements"></a>수명 이벤트 애플리케이션 모델 요소  
 요소에 대한 공통 수명 이벤트를 기반으로 하는 <xref:System.Windows.Application>것은 <xref:System.Windows.Window> <xref:System.Windows.Controls.Page>다음과 <xref:System.Windows.Navigation.NavigationWindow>같은 응용 프로그램 모델 요소입니다. <xref:System.Windows.Controls.Frame> 이러한 요소는 특정 목적과 관련된 추가 이벤트를 사용하여 공통 개체 수명 이벤트를 확장합니다. 다음 항목에서 이에 대해 자세히 설명합니다.  
  
- <xref:System.Windows.Application>: [응용 프로그램 관리 개요](../app-development/application-management-overview.md).  
  
- <xref:System.Windows.Window>: [WPF 윈도우 개요](../app-development/wpf-windows-overview.md).  
  
- <xref:System.Windows.Controls.Page>및 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame>: [탐색 개요](../app-development/navigation-overview.md).  
  
## <a name="see-also"></a>참고 항목

- [종속성 속성 값 우선 순위](dependency-property-value-precedence.md)
- [라우트된 이벤트 개요](routed-events-overview.md)
