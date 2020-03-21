---
title: 종속성 속성 보안
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
ms.openlocfilehash: f5640b348ccd68819052f58756489489371862d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186388"
---
# <a name="dependency-property-security"></a>종속성 속성 보안
종속성 속성은 일반적으로 public 속성으로 간주됩니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템의 특성으로 인해 종속성 속성 값에 대한 보안을 보장할 수 없습니다.  

<a name="AccessSecurity"></a>
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>래퍼 및 종속성 속성의 액세스 및 보안  
 일반적으로 종속성 속성은 인스턴스에서 속성을 얻거나 설정하는 것을 단순화하는 "래퍼" 공통 언어 런타임(CLR) 속성과 함께 구현됩니다. 그러나 래퍼는 종속성 속성과 상호 작용할 <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> 때 사용되는 기본 및 정적 호출을 구현하는 편리한 메서드일 뿐입니다. 다른 방법으로 생각하면 속성은 개인 필드가 아닌 종속성 속성에 의해 백업되는 공통 언어 런타임(CLR) 속성으로 노출됩니다. 래퍼에 적용되는 보안 메커니즘은 속성 시스템 동작 및 기본 종속성 속성의 액세스와 관련이 없습니다. 래퍼에 보안 요구를 배치하면 편의 방법의 사용을 방지할 수 있지만 <xref:System.Windows.DependencyObject.GetValue%2A> 또는 <xref:System.Windows.DependencyObject.SetValue%2A>에 대한 호출을 방지할 수는 없습니다. 마찬가지로 래퍼에 보호된 액세스 또는 개인 액세스 수준을 적용해도 효과적인 보안을 제공하지는 않습니다.  
  
 사용자 고유의 종속성 속성을 작성하는 경우 호출자가 해당 속성의 실제 액세스 수준에 대한 오해의 소지가 있는 정보를 얻지 않도록 래퍼 및 <xref:System.Windows.DependencyProperty> 식별자 필드를 공용 멤버로 선언해야 합니다(저장소가 종속성 속성으로 구현되기 때문에).  
  
 사용자 지정 종속성 속성의 경우 속성을 읽기 전용 종속성 속성으로 등록할 수 있으며, 이는 해당 속성에 <xref:System.Windows.DependencyPropertyKey> 대한 참조를 보유하지 않는 모든 사용자가 속성을 설정하는 것을 방지하는 효과적인 수단을 제공합니다. 자세한 내용은 [읽기 전용 종속성 속성](read-only-dependency-properties.md)을 참조하세요.  
  
> [!NOTE]
> <xref:System.Windows.DependencyProperty> 식별자 필드를 비공개로 선언하는 것은 금지되지 않으며 사용자 지정 클래스의 즉시 노출된 네임스페이스를 줄이는 데 사용할 수 있지만 이러한 속성은 다음 섹션에서 설명하는 이유로 해당 액세스 수준을 정의하는 공통 언어 런타임(CLR) 언어 정의와 동일한 의미에서 "private"으로 간주되어서는 안 됩니다.  
  
<a name="PropertySystemExposure"></a>
## <a name="property-system-exposure-of-dependency-properties"></a>종속성 속성의 속성 시스템 노출  
 일반적으로 유용하지 않으며 잠재적으로 오해의 소지가 있으므로 <xref:System.Windows.DependencyProperty> 공개 가 아닌 다른 액세스 수준으로 선언할 수 있습니다. 해당 액세스 수준 설정은 다른 사용자가 선언하는 클래스에서 인스턴스에 대한 참조를 가져올 수 없도록만 합니다. 그러나 클래스 또는 파생 클래스 인스턴스의 <xref:System.Windows.DependencyProperty> 인스턴스에 있는 특정 속성을 식별하는 수단으로 반환하는 속성 시스템의 여러 측면이 있으며 원래 정적 식별자가 비공개로 선언된 경우에도 이 식별자를 <xref:System.Windows.DependencyObject.SetValue%2A> 호출에서 계속 사용할 수 있습니다. 또한 <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 가상 메서드는 값을 변경한 기존 종속성 속성의 정보를 수신합니다. 또한 메서드는 <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> 로컬로 설정된 값을 가진 인스턴스의 모든 속성에 대한 식별자를 반환합니다.  
  
### <a name="validation-and-security"></a>유효성 검사 및 보안  
 에 대한 요구를 <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> 적용하고 속성이 설정되지 않도록 하는 요청 실패시 유효성 검사 실패를 예상하는 것은 적절한 보안 메커니즘이 아닙니다. 이러한 호출자는 응용 프로그램 <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> 도메인 내에서 작동하는 경우 악의적인 호출자에 의해 적용된 설정 값 무효화도 억제될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [사용자 지정 종속성 속성](custom-dependency-properties.md)
