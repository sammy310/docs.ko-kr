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
ms.openlocfilehash: 89459223108c0190a485b25193e44d379a1e1c19
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379031"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey 태그 확장
정의 하 고 외부 어셈블리에서 로드 되는 리소스에 대 한 키를 참조 합니다. 따라서 리소스 조회 클래스 또는 어셈블리의 명시적 리소스 사전 보다는 어셈블리의 대상 형식을 지정할 수 있습니다.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML 특성 사용 (설정 키, compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML 특성 사용 (키, 자세한 정보 표시 설정)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML 특성 사용 (리소스 요청, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML 특성 사용 (리소스 요청을 자세한 정보)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`targetTypeName`|공용 이름 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 리소스 어셈블리에 정의 된 형식입니다.|  
|`targetID`|리소스에 대 한 키입니다. 리소스를 조회할 때 `targetID` 비슷합니다 됩니다 합니다 [X:key 지시문](../../xaml-services/x-key-directive.md) 리소스입니다.|  
  
## <a name="remarks"></a>설명  
 위의 사용법에서 볼 수 있듯이 {`ComponentResourceKey`} 태그 확장 사용은 두 위치에서 찾을 수:  
  
-   컨트롤 작성자가 제공한 테마 리소스 사전 내에서 키의 정의입니다.  
  
-   어셈블리에서 테마 리소스에 액세스 하면 컨트롤 템플릿을 하지만 컨트롤의 테마에서 제공 하는 리소스에서 제공 되는 속성 값을 사용 하려면.  
  
 테마에서 제공 하는 구성 요소 리소스를 참조 하는 것에 대 한 것이 좋습니다를 사용 하는 `{DynamicResource}` 대신 `{StaticResource}`합니다. 이 사용법에 표시 됩니다. `{DynamicResource}` 테마 자체는 사용자가 변경할 수 있으므로 것이 좋습니다. 구성 요소 리소스를 가장 일치 하는 테마를 지원 하기 위한 컨트롤 작성자의 의도 하려는 경우를 동적 사용자 구성 요소 리소스 참조를 사용 해야 합니다.  
  
 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 리소스 실제로 정의 되는 대상 어셈블리에 존재 하는 형식을 식별 합니다. A `ComponentResourceKey` 정의 하 고 정확 하 게 파악 하는 독립적으로 사용할 수 있는 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 정의 되었지만 참조 된 어셈블리를 통해 형식을 최종적으로 해결 해야 합니다.  
  
 에 대 한 일반적인 사용법 <xref:System.Windows.ComponentResourceKey> 클래스의 멤버로 노출 되는 키를 정의 하는 것입니다. 사용이 사용 된 <xref:System.Windows.ComponentResourceKey> 클래스 생성자, 태그 확장 되지 않습니다. 자세한 내용은 <xref:System.Windows.ComponentResourceKey>, 또는 항목의 "정의 및 참조 키에 대 한 테마 리소스" 섹션 [컨트롤 제작 개요](../controls/control-authoring-overview.md)합니다.  
  
 특성 구문에 대 한 일반적으로 모두 키를 설정 하 고 참조 하는 리소스 키가 지정 된에 대 한는 `ComponentResourceKey` 태그 확장 합니다.  
  
 표시 된 간단한 구문을 사용 합니다 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 생성자 시그니처 및 태그 확장의 위치 매개 변수를 사용 합니다. 순서를 `targetTypeName` 및 `targetID` 된 것이 중요 합니다. 자세한 구문에 의존 합니다 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 기본 생성자 및 집합 합니다 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 개체 요소에 실제 특성 구문과 유사한 방식으로 합니다. 자세한 구문에서 속성이 설정 된 순서가 중요 하지 않습니다. 관계 및 이들 두 가지 방법 (compact 및 자세한 정보) 메커니즘을 항목에 자세히 설명 되어 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)합니다.  
  
 기술적으로 값 `targetID` 할 수 있는 개체, 문자열을 사용할 필요가 없습니다. 그러나 WPF의 가장 일반적인 사용법을 정렬 하는 합니다 `targetID` 문자열 있으며 이러한 문자열에 사용할 수 있는 형식으로 값을 [XamlName 문법](../../xaml-services/xamlname-grammar.md)합니다.  
  
 `ComponentResourceKey` 개체 요소 구문에서 사용할 수 있습니다. 이 예제의 경우 둘 다의 값을 지정 하는 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 속성은 확장을 제대로 초기화 해야 합니다.  
  
 에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 구현을이 태그 확장에 대 한 처리는 정의한는 <xref:System.Windows.ComponentResourceKey> 클래스입니다.  
  
 `ComponentResourceKey`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [컨트롤 제작 개요](../controls/control-authoring-overview.md)
- [XAML 개요(WPF)](xaml-overview-wpf.md)
- [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
