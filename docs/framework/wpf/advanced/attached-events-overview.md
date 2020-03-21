---
title: 연결된 이벤트 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: e125c9a57090049f4319da96c7004f06606d0147
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141564"
---
# <a name="attached-events-overview"></a>연결된 이벤트 개요

확장 가능한 응용 프로그램 태그 언어(XAML)는 *연결된 이벤트라는*언어 구성 요소 및 이벤트 유형을 정의합니다. 연결된 이벤트의 개념을 사용하면 실제로 정의하거나 이벤트를 상속하는 요소가 아닌 임의의 요소에 특정 이벤트의 핸들러를 추가할 수 있습니다. 이 경우 이벤트를 잠재적으로 발생시키는 개체나 인스턴스를 처리하는 대상이 정의하지 않으며 또는 그렇지 않으면 이벤트를 "소유"합니다.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [라우트된 이벤트 개요](routed-events-overview.md) 및 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)를 읽었다고 가정합니다.  
  
<a name="Syntax"></a>
## <a name="attached-event-syntax"></a>연결된 이벤트 구문  
 연결된 이벤트에는 XAML 구문과 연결된 이벤트 사용을 지원하기 위해 백업 코드에서 사용해야 하는 코딩 패턴이 있습니다.  
  
 XAML 구문에서 연결된 이벤트는 이벤트 이름뿐만 아니라 자체 형식과 이벤트 이름으로 지정되며 dot(.)으로 구분됩니다. 이벤트 이름이 소유 형식의 이름으로 정규화되기 때문에, 연결된 이벤트 구문을 모든 연결된 이벤트를 인스턴스화할 수 있는 모든 요소에 연결할 수 있습니다.  
  
 예를 들어 다음은 사용자 지정 `NeedsCleaning` 연결 이벤트에 대한 처리기를 연결하기 위한 XAML 구문입니다.  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 `aqua:` 접두사. 연결된 이벤트가 사용자 지정 맵핑된 xmlns에서 오는 사용자 지정 이벤트이기 때문에 이 경우에 접두사가 필요합니다.  
  
<a name="WPFImplements"></a>
## <a name="how-wpf-implements-attached-events"></a>WPF가 연결된 이벤트를 구현하는 방법

WPF에서 연결된 이벤트는 <xref:System.Windows.RoutedEvent> 필드에 의해 백업되며 발생 후 트리를 통해 라우팅됩니다. 일반적으로 연결된 이벤트(이벤트를 발생하는 개체)의 소스는 시스템이나 서비스 소스이며, 이벤트를 발생하는 코드를 실행하는 개체는 직접적인 요소 트리 파트가 아닙니다.  
  
<a name="Scenarios"></a>
## <a name="scenarios-for-attached-events"></a>연결된 이벤트에 대한 시나리오  
 WPF에서 연결된 이벤트는 정적 <xref:System.Windows.Input.Mouse> 클래스 또는 <xref:System.Windows.Controls.Validation> 클래스에서 활성화된 이벤트와 같이 서비스 수준 추상화가 있는 특정 기능 영역에 있습니다. 서비스와 상호 작용하거나 사용하는 클래스는 연결된 이벤트 구문에서 이벤트를 사용하거나, 클래스가 서비스의 기능을 통합하는 방법의 일부인 라우트된 이벤트로 연결된 이벤트를 나타내도록 선택할 수 있습니다.  
  
 WPF는 여러 연결된 이벤트를 정의하지만 연결된 이벤트를 직접 사용하거나 처리하는 시나리오는 매우 제한적입니다. 일반적으로 연결된 이벤트는 아키텍처 목적으로 사용되지만 연결되지 않은 이벤트(CLR 이벤트 "래퍼"로 백업)로 전달됩니다.  
  
 예를 들어 XAML <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> 또는 코드에서 연결된 <xref:System.Windows.UIElement> 이벤트 <xref:System.Windows.UIElement.MouseDown> 구문을 <xref:System.Windows.UIElement> 처리하는 대신 기본 연결 이벤트를 사용하여 지정된 이벤트를 보다 쉽게 처리할 수 있습니다. 입력 디바이스의 향후 확장을 허용하므로 연결된 이벤트는 아키텍처의 용도로 사용됩니다. 가상 의 장치는 마우스 입력을 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> 시뮬레이션하기 위해 상승해야하며, <xref:System.Windows.Input.Mouse> 그렇게하기 위해 파생 할 필요가 없습니다. 그러나 이 시나리오에는 이벤트의 코드 처리가 포함되며 연결된 이벤트의 XAML 처리는 이 시나리오와 관련이 없습니다.  
  
<a name="Handling"></a>
## <a name="handling-an-attached-event-in-wpf"></a>WPF에서 연결된 이벤트 처리  
 연결된 이벤트를 처리하기 위한 프로세스 및 작성할 처리기 코드는 기본적으로 라우트된 이벤트의 경우와 동일합니다.  
  
 일반적으로 WPF 연결 된 이벤트는 WPF 라우트된 이벤트와 크게 다르지 않습니다. 차이점은 이벤트의 소스와 클래스가 멤버로 노출되는 방식(XAML 처리기 구문에도 영향을 줍니다)입니다.  
  
 그러나 앞에서 설명한 것처럼 기존 WPF 연결 이벤트는 특히 WPF에서 처리하기 위한 것이 아닙니다. 이벤트의 목적은 합성 이벤트가 작성 시 부모 요소에 상태를 보고할 수 있게 하는 것으로, 이 경우 이벤트는 일반적으로 코드에서 발생하며 관련 부모 클래스에서 처리하는 클래스에도 사용됩니다. 예를 들어, a <xref:System.Windows.Controls.Primitives.Selector> 내의 항목은 <xref:System.Windows.Controls.Primitives.Selector.Selected> 연결된 이벤트를 발생시킨 다음 <xref:System.Windows.Controls.Primitives.Selector> 클래스에서 처리한 다음 <xref:System.Windows.Controls.Primitives.Selector> 클래스에서 다른 라우트된 이벤트로 변환될 수 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>있습니다. 라우트된 이벤트 및 클래스 처리에 대한 자세한 내용은 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](marking-routed-events-as-handled-and-class-handling.md)를 참조하십시오.  
  
<a name="Custom"></a>
## <a name="defining-your-own-attached-events-as-routed-events"></a>연결된 이벤트를 라우트된 이벤트로 정의  
 일반적인 WPF 기본 클래스에서 파생되는 경우 클래스에 특정 패턴 메서드를 포함하고 기본 클래스에 이미 있는 유틸리티 메서드를 사용하여 고유한 연결된 이벤트를 구현할 수 있습니다.  
  
 패턴은 다음과 같습니다.  
  
- 두 개의 매개 변수가 있는 __*이벤트 이름*처리기 추가__ 메서드입니다. 첫 번째 매개 변수는 이벤트 처리기가 추가되는 인스턴스입니다. 두 번째 매개 변수는 추가할 이벤트 처리기입니다. 메서드는 반환 `public` `static`값이 없어야 합니다.  
  
- 두 개의 매개 변수를 사용하여 __*EventName*처리기를 제거하는__ 메서드입니다. 첫 번째 매개 변수는 이벤트 처리기가 제거되는 인스턴스입니다. 두 번째 매개 변수는 제거할 이벤트 처리기입니다. 메서드는 반환 `public` `static`값이 없어야 합니다.  
  
 __EventName*EventName*처리기 추가__ 접근자 메서드는 연결된 이벤트 처리기 특성이 요소에 선언될 때 XAML 처리를 용이하게 합니다. __이벤트*이름*처리기 추가__ 및 __이벤트*이름*처리기 제거__ 메서드는 연결된 이벤트에 대한 이벤트 처리기 저장소에 대한 코드 액세스를 활성화합니다.  
  
 주어진 XAML 판독기 구현에는 지원 언어 및 아키텍처에서 기본 이벤트를 식별하기 위한 다른 체계가 있을 수 있으므로 이 일반적인 패턴은 프레임워크에서 실제 구현하기에 충분하지 않습니다. WPF가 연결된 이벤트를 라우트된 이벤트로 구현하는 이유 중 하나입니다. 이벤트에 사용할 식별자 ()<xref:System.Windows.RoutedEvent>이미 WPF 이벤트 시스템에 의해 정의되어 있습니다. 또한 이벤트를 라우팅하는 것은 연결된 이벤트의 XAML 언어 수준 개념에 대한 자연스러운 구현 확장입니다.  
  
 WPF 연결 된 이벤트에 대 한 __추가*EventName*처리기__ 구현 라우트 된 이벤트 와 처리기를 인수로 호출 <xref:System.Windows.UIElement.AddHandler%2A> 하는 구성 됩니다.  
  
 이 구현 전략 및 라우트된 이벤트 시스템은 일반적으로 해당 <xref:System.Windows.UIElement> 클래스만 <xref:System.Windows.ContentElement> 구현을 갖기 <xref:System.Windows.UIElement.AddHandler%2A> 때문에 연결된 이벤트에 대한 처리를 파생 클래스 또는 파생 클래스로 제한합니다.  
  
 예를 들어 다음 코드는 `NeedsCleaning` 연결된 이벤트를 라우트된 `Aquarium`이벤트로 선언하는 WPF 연결 이벤트 전략을 사용하여 소유자 클래스에서 연결된 이벤트를 정의합니다.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 연결된 이벤트 식별자 필드를 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>설정하는 데 사용되는 메서드는 실제로 연결되지 않은 라우트된 이벤트를 등록하는 데 사용되는 메서드와 동일합니다. 연결된 이벤트 및 라우트된 이벤트 모두 중앙 집중화된 내부 저장소에 등록됩니다. 이 이벤트 저장소 구현은 [라우트된 이벤트 개요](routed-events-overview.md)에서 설명하는 “인터페이스로서의 이벤트” 개념 고려 사항을 사용합니다.  
  
<a name="Raising"></a>
## <a name="raising-a-wpf-attached-event"></a>WPF 연결된 이벤트 발생  
 일반적으로 코드에서 기존 WPF 정의 연결된 이벤트를 발생시킬 필요가 없습니다. 이러한 이벤트는 일반적인 "서비스" 개념 모델을 따르며 이벤트 <xref:System.Windows.Input.InputManager> 발생과 같은 서비스 클래스는 이벤트를 발생시합니다.  
  
 <xref:System.Windows.RoutedEvent>그러나 에 연결된 이벤트의 WPF 모델을 기반으로 사용자 지정 연결 된 이벤트를 정의 <xref:System.Windows.UIElement.RaiseEvent%2A> 하는 경우 모든 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.ContentElement>에서 연결 된 이벤트를 발생 시킬 수 있습니다. 라우트된 이벤트를 발생(연결 여부)하려면 요소 트리의 특정 요소를 이벤트 소스로 선언해야 합니다. 해당 소스가 <xref:System.Windows.UIElement.RaiseEvent%2A> 호출자로 보고됩니다. 트리에서 소스로 보고되는 요소 판별은 서비스에 따라 다릅니다.  
  
## <a name="see-also"></a>참고 항목

- [라우트된 이벤트 개요](routed-events-overview.md)
- [XAML 구문 정보](xaml-syntax-in-detail.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](xaml-and-custom-classes-for-wpf.md)
