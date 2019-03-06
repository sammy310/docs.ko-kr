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
ms.openlocfilehash: d51f8f5fd704b0c95b8e6f841b9b0ff8567899cb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364816"
---
# <a name="dependency-property-security"></a>종속성 속성 보안
종속성 속성은 일반적으로 public 속성으로 간주됩니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템의 특성으로 인해 종속성 속성 값에 대한 보안을 보장할 수 없습니다.  
  
  
<a name="AccessSecurity"></a>   
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>래퍼 및 종속성 속성의 액세스 및 보안  
 일반적으로 종속성 속성은 인스턴스에서 속성 가져오기 또는 설정을 간단하게 하는 "래퍼" [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성과 함께 구현됩니다. 래퍼는 기본 구현 하는 매우 정당한 편의 메서드 <xref:System.Windows.DependencyObject.GetValue%2A> 고 <xref:System.Windows.DependencyObject.SetValue%2A> 종속성 속성과 상호 작용할 때 사용 되는 정적 호출 합니다. 또 다른 측면에서 볼 때 속성은 private 필드가 아닌 종속성 속성에서 지원하는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성으로 노출됩니다. 래퍼에 적용되는 보안 메커니즘은 속성 시스템 동작 및 기본 종속성 속성의 액세스와 관련이 없습니다. 래퍼에 대해 보안 요청을 배치 하면 편리한 메서드의 사용만 방지 됩니다 있지만 호출 해도 <xref:System.Windows.DependencyObject.GetValue%2A> 또는 <xref:System.Windows.DependencyObject.SetValue%2A>합니다. 마찬가지로 래퍼에 보호된 액세스 또는 개인 액세스 수준을 적용해도 효과적인 보안을 제공하지는 않습니다.  
  
 고유한 종속성 속성을 작성 하는 경우 래퍼를 선언 해야 하며 <xref:System.Windows.DependencyProperty> 호출자가 수행 되지 올바른 정보를 가져올 속성의 액세스 수준에 대 한 (때문에 되 고 해당 저장소를 public 멤버로 식별자 필드 구현 된 종속성 속성으로).  
  
 사용자 지정 종속성 속성에 대 한 읽기 전용 종속성 속성으로 속성을 등록할 수 있습니다 하 고이 속성에 대 한 참조를 보유 하지 않는 모든 사용자에 의해 설정 되는 효과적인 수단을 제공 합니다 <xref:System.Windows.DependencyPropertyKey> 해당 속성에 대 한 합니다. 자세한 내용은 [읽기 전용 종속성 속성](read-only-dependency-properties.md)을 참조하세요.  
  
> [!NOTE]
>  선언 된 <xref:System.Windows.DependencyProperty> 식별자 필드를 private을 사용할 수 및 사용자 지정 클래스의 바로 노출 되는 네임 스페이스를 줄이는 데 사용할 수 있다고 볼 수 있지만 이러한 속성을 고려 하지 않아야와 동일한 의미에서 "개인"는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 언어 정의는 다음 섹션에 설명 된 이유로 해당 액세스 수준을 정의 합니다.  
  
<a name="PropertySystemExposure"></a>   
## <a name="property-system-exposure-of-dependency-properties"></a>종속성 속성의 속성 시스템 노출  
 일반적으로 유용 하지 않습니다 하 고 잠재적으로 잘못 선언 하는 것을 <xref:System.Windows.DependencyProperty> 공용 이외의 모든 액세스 수준입니다. 해당 액세스 수준 설정은 다른 사용자가 선언하는 클래스에서 인스턴스에 대한 참조를 가져올 수 없도록만 합니다. 하지만 반환 하는 속성 시스템의 여러 측면을 가지는 <xref:System.Windows.DependencyProperty> 클래스의 인스턴스나 파생된 클래스 인스턴스를 존재 하 고이 식별자에 계속 사용할 수 있는 특정 속성을 식별 하는 수단으로는 <xref:System.Windows.DependencyObject.SetValue%2A> 도 호출 원래 정적 식별자 nonpublic로 선언 합니다. 또한 <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 가상 메서드는 값이 변경 된 모든 기존 종속성 속성의 정보를 받습니다. 또한는 <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> 메서드 인스턴스에 로컬로 설정 된 모든 속성에 대 한 식별자를 반환 값입니다.  
  
### <a name="validation-and-security"></a>유효성 검사 및 보안  
 요청을 적용 한 <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> 는 적절 한 보안 메커니즘이 아닙니다 속성을 설정 하지 않도록 요청 실패 시 유효성 검사 오류를 예상 합니다. 값 설정 무효화를 통해 적용 <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> 해당 호출자에 게 응용 프로그램 도메인 내에서 작동 하는 경우 악의적인 호출자가 표시도 수 있습니다.  
  
## <a name="see-also"></a>참고자료
- [사용자 지정 종속성 속성](custom-dependency-properties.md)
