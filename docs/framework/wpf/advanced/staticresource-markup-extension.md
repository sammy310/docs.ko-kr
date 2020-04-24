---
title: StaticResource 태그 확장
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: 5c0bb247bae525658d89d53f1672e57b87aba7bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646208"
---
# <a name="staticresource-markup-extension"></a>StaticResource 태그 확장
이미 정의된 리소스에 대한 참조를 찾아서 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 속성 특성에 대한 값을 제공합니다. 해당 리소스에 대한 조회 동작은 현재 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지의 마크업과 다른 응용 프로그램 원본에서 이전에 로드된 리소스를 찾고 해당 리소스 값을 런타임 개체의 속성 값으로 생성하는 로드 타임 조회와 유사합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`key`|요청한 리소스의 키입니다. 이 키는 처음에 [x:Key 지시문에](../../../desktop-wpf/xaml-services/xkey-directive.md) 의해 할당 된 경우 리소스가 마크업에서 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 만들어졌거나 코드에서 리소스가 생성된 경우 호출 할 때 `key` 매개 변수로 제공되었습니다.|  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
> A는 `StaticResource` 파일 내에서 더 멀리 어휘적으로 정의된 리소스에 대한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 전달 참조를 시도해서는 안 됩니다. 이렇게 하려고 하면 지원되지 않으며 이러한 참조가 실패하지 않더라도 전달 참조를 시도하면 a를 <xref:System.Windows.ResourceDictionary> 나타내는 내부 해시 테이블이 검색될 때 로드 시간 성능 저하가 발생합니다. 최상의 결과를 얻으려면 전달 참조를 피할 수 있도록 리소스 사전의 구성을 조정합니다. 정방향 참조를 피할 수 없는 경우 대신 [DynamicResource 마크업 확장을](dynamicresource-markup-extension.md) 사용합니다.  
  
 지정된 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 리소스는 페이지, 응용 프로그램, 사용 가능한 제어 테마 및 외부 리소스 또는 시스템 리소스의 일부 수준에서 [x:Key 지시문으로](../../../desktop-wpf/xaml-services/xkey-directive.md) 식별된 기존 리소스에 해당해야 합니다. 리소스 조회는 해당 순서로 수행됩니다. 정적 및 동적 리소스에 대한 리소스 조회 동작에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하십시오.  
  
 리소스 키는 [XamlName 문법에](../../../desktop-wpf/xaml-services/xamlname-grammar.md)정의된 모든 문자열일 수 있습니다. 리소스 키는 <xref:System.Type>와 같은 다른 개체 형식일 수도 있습니다. <xref:System.Type> 핵심은 암시적 스타일 키를 통해 테마별로 컨트롤의 스타일을 조정하는 방법의 기본입니다. 자세한 내용은 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하세요.  
  
 리소스를 참조하는 대체 선언적 수단은 [DynamicResource 마크업 확장입니다.](dynamicresource-markup-extension.md)  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `StaticResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 확장명 클래스의 <xref:System.Windows.StaticResourceExtension> 값으로 할당됩니다.  
  
 `StaticResource`개체 요소 구문에서 사용할 수 있습니다. 이 경우 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 속성 값을 지정해야 합니다.  
  
 `StaticResource` 속성을 다음과 같이 속성=값 쌍으로 지정하는 자세한 특성 사용 구문에도 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>을 사용할 수 있습니다.  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다. `StaticResource`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 프로세서 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.StaticResourceExtension> 클래스에 의해 정의됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `StaticResource`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [리소스 및 코드](resources-and-code.md)
