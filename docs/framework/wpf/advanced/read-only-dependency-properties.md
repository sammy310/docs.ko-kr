---
title: 읽기 전용 종속성 속성
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: 8adc90182f0f42f52e6ace4e13c68acb3539516b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187175"
---
# <a name="read-only-dependency-properties"></a>읽기 전용 종속성 속성
이 항목에서는 기존 읽기 전용 종속성 속성과 사용자 지정 읽기 전용 종속성 속성을 만드는 시나리오 및 방법을 포함하여 읽기 전용 종속성 속성을 설명합니다.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 종속성 속성을 구현하는 기본 시나리오와 메타데이터가 사용자 지정 종속성 속성에 적용되는 방법을 이해하고 있다고 가정합니다. 컨텍스트는 [사용자 지정 종속성 속성](custom-dependency-properties.md) 및 [종속성 속성 메타데이터](dependency-property-metadata.md)를 참조하세요.  
  
<a name="existing"></a>
## <a name="existing-read-only-dependency-properties"></a>기존 읽기 전용 종속성 속성  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 프레임워크에 정의된 일부 종속성 속성은 읽기 전용입니다. 일반적으로 읽기 전용 종속성 속성을 지정하는 이유는 상태 결정에 이러한 속성을 사용해야 하지만 많은 요소가 해당 상태에 영향을 미치는 경우 속성을 해당 상태로 설정하는 것은 사용자 인터페이스 디자인 측면에서 바람직하지 않기 때문입니다. 예를 들어, <xref:System.Windows.UIElement.IsMouseOver%2A> 속성은 실제로 마우스 입력에서 결정 된 대로 표면 상태입니다. 실제 마우스 입력을 우회하여 프로그래밍 방식으로 이 값을 설정하는 시도는 예측이 불가능하고 이로 인해 불일치가 발생합니다.  
  
 설정이 불가능하기 때문에 읽기 전용 종속성 속성은 정상적으로는 종속성 속성이 솔루션(값, 유효성 검사, 애니메이션, 상속에 직접 스타일 지정 가능한 데이터 바인딩)을 제공하는 많은 시나리오에 적절하지 않습니다. 설정 불가능하지만 읽기 전용 종속성 속성에는 속성 시스템의 종속성 시스템을 통해 지원되는 몇 가지 추가 기능이 있습니다. 가장 중요한 나머지 기능은 읽기 전용 종속성 속성은 속성 트리거로 사용될 수 있다는 것입니다. 일반 공통 언어 런타임(CLR) 속성으로는 트리거를 활성화할 수 없습니다. 종속성 속성이어야 합니다. 앞에서 언급한 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성은 컨트롤의 스타일을 정의하는 데 매우 유용할 수 있는 시나리오의 완벽한 예로, 사용자가 컨트롤의 정의된 일부 영역에 마우스를 배치할 때 컨트롤 내의 배경, 전경 또는 이와 유사한 복합 요소의 유사한 속성이 변경됩니다. 읽기 전용 종속성 속성의 변경 내용은 속성 시스템의 기본 무효화 프로세스를 통해 검색 및 보고할 수 있고, 실제로 속성 트리거 기능을 내부적으로 지원합니다.  
  
<a name="new"></a>
## <a name="creating-custom-read-only-dependency-properties"></a>사용자 지정 읽기 전용 종속성 속성 만들기  
 위 섹션에서 읽기 전용 종속성 속성이 많은 일반적인 종속성 속성 시나리오에 적용되지 않는 이유를 확인해야 합니다. 하지만 적절한 시나리오가 있는 경우 자체 읽기 전용 종속성 속성을 만들려고 할 수 있습니다.  
  
 읽기 전용 종속성 속성을 만드는 프로세스의 많은 부분은 [사용자 지정 종속성 속성](custom-dependency-properties.md) 및 [종속성 속성 구현](how-to-implement-a-dependency-property.md) 항목에 설명된 것과 같습니다. 세 가지 중요한 차이점이 있습니다.  
  
- 속성을 등록할 때 속성 <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> 등록을 위한 <xref:System.Windows.DependencyProperty.Register%2A> 일반적인 방법 대신 메서드를 호출합니다.  
  
- CLR "래퍼" 속성을 구현할 때 래퍼도 설정된 구현이 없는지 확인하여 노출하는 공용 래퍼에 대한 읽기 전용 상태에 불일치가 없도록 합니다.  
  
- 읽기 전용 등록에서 반환되는 <xref:System.Windows.DependencyPropertyKey> 개체는 <xref:System.Windows.DependencyProperty>가 아닌 입니다. 이 필드는 멤버로 저장해야 하지만 일반적으로 형식의 public 멤버로 설정하지 않습니다.  
  
 지원하는 private 필드 또는 값이 무엇이든 관계없이 읽기 전용 종속성 속성은 결정한 논리가 무엇이든 이를 사용하여 충분히 쓰기 가능합니다. 그러나 속성을 처음에 또는 런타임 논리의 일부로 설정하는 가장 간단한 방법은 속성 시스템을 우회하고 개인 백업 필드를 직접 설정하는 대신 속성 시스템의 API를 사용하는 것입니다. 특히 형식의 <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.DependencyPropertyKey>매개 변수를 허용하는 시그니처가 있습니다. 응용 프로그램 논리 내에서 프로그래밍 방식으로 이 값을 프로그래밍 방식으로 설정하는 방법과 방법은 <xref:System.Windows.DependencyPropertyKey> 종속성 속성을 처음 등록할 때 생성된 에 대한 액세스를 설정하는 방법에 영향을 줍니다. private로 설정할 수 있는 클래스 내에서 이 논리를 모두 처리할 경우 또는 어셈블리의 다른 부분에서 클래스를 설정해야 하는 경우 이 클래스를 internal로 설정할 수 있습니다. 한 가지 방법은 <xref:System.Windows.DependencyObject.SetValue%2A> 저장된 속성 값을 변경해야 한다는 클래스 인스턴스를 알리는 관련 이벤트의 클래스 이벤트 처리기 내에서 호출하는 것입니다. 또 다른 방법은 등록 하는 동안 해당 <xref:System.Windows.PropertyChangedCallback> <xref:System.Windows.CoerceValueCallback> 속성의 메타 데이터의 일부로 쌍을 이루는 콜백을 사용 하 여 종속성 속성을 함께 연결 하는 것입니다.  
  
 <xref:System.Windows.DependencyPropertyKey> 는 개인이며 코드 외부의 속성 시스템에 의해 전파되지 않으므로 읽기 전용 종속성 속성은 읽기 쓰기 종속성 속성보다 보안을 더 잘 설정합니다. 읽기-쓰기 종속성 속성의 경우 식별 필드는 명시적 또는 암시적으로 public이므로 속성을 광범위하게 설정할 수 있습니다. 자세한 내용은 [종속성 속성 보안](dependency-property-security.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [종속성 속성 개요](dependency-properties-overview.md)
- [사용자 지정 종속성 속성](custom-dependency-properties.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
