---
title: ComponentResourceKey 태그 확장
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243364"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 태그 확장
외부 어셈블리에서 로드된 리소스에 대한 키를 정의하고 참조합니다. 이렇게 하면 리소스 조회에서 어셈블리 또는 클래스의 명시적 리소스 사전이 아니라 어셈블리에서 대상 형식을 지정할 수 있습니다.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 특성 사용(설정 키, 컴팩트)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML 특성 사용(설정 키, 자세한 내용)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 특성 사용(리소스 요청, 압축)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 특성 사용(리소스 요청, 자세한 내용)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`targetTypeName`|리소스 어셈블리에 정의된 공용 공통 언어 런타임(CLR) 형식의 이름입니다.|  
|`targetID`|리소스의 키입니다. 리소스를 조회하면 `targetID` 리소스의 [x:Key 지시문과](../../../desktop-wpf/xaml-services/xkey-directive.md) 유사합니다.|  
  
## <a name="remarks"></a>설명  
 위의 사용법에서 볼 수`ComponentResourceKey`있듯이 { } 태그 확장 사용법은 두 위치에서 발견됩니다.  
  
- 컨트롤 작성자가 제공한 테마 리소스 사전 내의 키 정의입니다.  
  
- 컨트롤을 다시 temptemptempd하지만 컨트롤의 테마에서 제공하는 리소스에서 제공하는 속성 값을 사용하려는 경우 어셈블리에서 테마 리소스에 액세스합니다.  
  
 테마에서 오는 구성 요소 리소스를 참조하는 경우 일반적으로 `{DynamicResource}` 을 `{StaticResource}`사용하는 것이 아니라 사용하는 것이 좋습니다. 이것은 사용법에 표시됩니다. `{DynamicResource}`사용자가 테마 자체를 변경할 수 있으므로 권장됩니다. 테마를 지원하기 위한 컨트롤 작성자의 의도와 가장 밀접하게 일치하는 구성 요소 리소스를 사용하려면 구성 요소 리소스 참조도 동동적이되도록 설정해야 합니다.  
  
 리소스가 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 실제로 정의된 대상 어셈블리에 있는 형식을 식별합니다. <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> A는 `ComponentResourceKey` 정의된 위치를 정확히 아는 것과 독립적으로 정의하고 사용할 수 있지만 결국 참조된 어셈블리를 통해 형식을 해결해야 합니다.  
  
 일반적인 <xref:System.Windows.ComponentResourceKey> 용도는 클래스의 멤버로 노출되는 키를 정의하는 것입니다. 이 사용의 경우 <xref:System.Windows.ComponentResourceKey> 태그 확장이 아닌 클래스 생성자(생성자)를 사용합니다. 자세한 내용은 을 <xref:System.Windows.ComponentResourceKey>참조하거나 "테마 리소스에 대한 키 정의 및 참조" 항목의 "키 정의 및 참조" 항목의 [제어 작성 개요를](../controls/control-authoring-overview.md)참조하십시오.  
  
 키를 설정하고 키리소스를 참조하는 경우 특성 구문은 태그 `ComponentResourceKey` 확장에 일반적으로 사용됩니다.  
  
 표시된 압축 구문은 태그 <xref:System.Windows.ComponentResourceKey.%23ctor%2A> 확장의 생성자 서명 및 위치 매개 변수 사용에 의존합니다. `targetTypeName` 와 `targetID` 주어진 순서가 중요합니다. 자세한 구문은 <xref:System.Windows.ComponentResourceKey.%23ctor%2A> 매개 변수 없는 생성자에 의존 하 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 고 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 개체 요소에 진정한 특성 구문과 유사한 방식으로 설정 합니다. 자세한 구문에서는 속성이 설정된 순서는 중요하지 않습니다. 이 두 대안의 관계 및 메커니즘 (컴팩트하고 자세한)은 태그 확장 [및 WPF XAML](markup-extensions-and-wpf-xaml.md)항목에서 자세히 설명합니다.  
  
 기술적으로, 값은 `targetID` 모든 개체가 될 수 있습니다, 그것은 문자열이 될 필요가 없습니다. 그러나 WPF에서 가장 일반적인 용도는 `targetID` 값을 문자열인 양식과 정렬하고 이러한 문자열이 [XamlName 문법에서](../../../desktop-wpf/xaml-services/xamlname-grammar.md)유효한 위치에 정렬하는 것입니다.  
  
 `ComponentResourceKey`개체 요소 구문에서 사용할 수 있습니다. 이 경우 확장을 올바르게 초기화하려면 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 및 속성 의 값을 지정해야 합니다.  
  
 판독기 구현에서 이 태그 확장에 대한 처리는 클래스에 <xref:System.Windows.ComponentResourceKey> 의해 정의됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `ComponentResourceKey`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [컨트롤 제작 개요](../controls/control-authoring-overview.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
