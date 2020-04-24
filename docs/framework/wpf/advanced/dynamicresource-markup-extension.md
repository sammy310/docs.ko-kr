---
title: DynamicResource 태그 확장
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 5ccda8ba8f41a30e0ce1c832a6d3176b7fb8e8c2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646270"
---
# <a name="dynamicresource-markup-extension"></a>DynamicResource 태그 확장
정의된 리소스에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 대한 참조로 해당 값을 연기하여 모든 속성 특성에 대한 값을 제공합니다. 해당 리소스에 대한 조회 동작은 런타임 조회와 유사합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>XAML 속성 요소 사용  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`key`|요청한 리소스의 키입니다. 이 키는 처음에 [x:Key 지시문에](../../../desktop-wpf/xaml-services/xkey-directive.md) 의해 할당 된 경우 리소스가 마크업에서 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 만들어졌거나 코드에서 리소스가 생성된 경우 호출 할 때 `key` 매개 변수로 제공되었습니다.|  
  
## <a name="remarks"></a>설명  
 A는 `DynamicResource` 초기 컴파일 중에 임시 식을 만들고 개체를 생성하기 위해 요청된 리소스 값이 실제로 필요할 때까지 리소스 조회를 연기합니다. 페이지가 로드된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 후일 수 있습니다. 리소스 값은 현재 페이지 범위에서 시작하는 모든 활성 리소스 사전에 대한 키 검색을 기반으로 찾을 수 있으며 컴파일에서 자리 표시자 식으로 대체됩니다.  
  
> [!IMPORTANT]
> 종속성 속성 우선 순위측면에서 `DynamicResource` 식은 동적 리소스 참조가 적용되는 위치와 같습니다. 이전에 `DynamicResource` 식이 있던 속성에 대한 로컬 값을 로컬 값으로 `DynamicResource` 설정하면 이 값이 완전히 제거됩니다. 자세한 내용은 [종속성 속성 값 우선 순위](dependency-property-value-precedence.md)를 참조하세요.  
  
 특정 리소스 액세스 시나리오는 `DynamicResource` [StaticResource 마크업 확장과](staticresource-markup-extension.md)는 달리 특히 적합합니다. `DynamicResource` 및 `StaticResource` 의 상대적인 장점 및 성능 영향에 대한 자세한 내용은 [XAML리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.  
  
 지정된 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 리소스는 페이지, 응용 프로그램, 사용 가능한 제어 테마 및 외부 리소스 또는 시스템 리소스의 일부 수준에서 [x:Key 지시문에](../../../desktop-wpf/xaml-services/xkey-directive.md) 의해 결정된 기존 리소스에 해당해야 하며 리소스 조회는 순서대로 수행됩니다. 정적 및 동적 리소스에 대한 리소스 조회에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.  
  
 리소스 키는 [XamlName 문법에](../../../desktop-wpf/xaml-services/xamlname-grammar.md)정의된 모든 문자열일 수 있습니다. 리소스 키는 <xref:System.Type>에서와 같은 다른 개체 형식일 수도 있습니다. 핵심은 <xref:System.Type> 컨트롤을 테마로 스타일을 정하는 방법의 기본입니다. 자세한 내용은 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하세요.  
  
 와 같은 <xref:System.Windows.FrameworkElement.FindResource%2A>리소스 값을 조회하기 위한 API는 에서 사용되는 것과 `DynamicResource`동일한 리소스 조회 논리를 따릅니다.  
  
 리소스를 참조하는 대체 선언적 수단은 [정적 리소스 마크업 확장입니다.](staticresource-markup-extension.md)  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `DynamicResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 확장명 클래스의 <xref:System.Windows.DynamicResourceExtension> 값으로 할당됩니다.  
  
 `DynamicResource`개체 요소 구문에서 사용할 수 있습니다. 이 경우 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 속성 값을 지정해야 합니다.  
  
 `DynamicResource` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>을 사용할 수 있습니다.  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다. `DynamicResource`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 프로세서 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.DynamicResourceExtension> 클래스에 의해 정의됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `DynamicResource`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [리소스 및 코드](resources-and-code.md)
- [x:Key 지시문](../../../desktop-wpf/xaml-services/xkey-directive.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [StaticResource 태그 확장](staticresource-markup-extension.md)
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
