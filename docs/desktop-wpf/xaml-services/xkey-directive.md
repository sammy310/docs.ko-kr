---
title: x:Key 지시문
ms.date: 03/30/2017
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
ms.openlocfilehash: c05f98932ceceeb1530b34a09b1923f2af1378b5
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432757"
---
# <a name="xkey-directive"></a>x:Key 지시문
XAML 정의 사전에서 생성되고 참조되는 요소를 고유하게 식별합니다. XAML 개체 요소에 `x:Key` 값을 추가하는 것은 WPF와 <xref:System.Windows.ResourceDictionary>같은 리소스 사전에서 리소스를 식별하는 가장 일반적인 방법입니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 특성 사용(WPF별)  
  
```xaml  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`stringKeyValue`|키로 사용할 텍스트 문자열입니다. 텍스트 문자열은 [XamlName 문법을](xamlname-grammar.md)준수해야 합니다.|  
|`markupExtensionUsage`|태그 확장 구분 기호 {}내에서 키로 사용할 개체를 제공하는 태그 확장 사용입니다. 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 `x:Key`XAML 리소스 사전 개념을 지원합니다. XAML은 특정 UI 프레임워크에 남아 있는 리소스 사전 구현을 정의하지 않습니다. WPF에서 XAML 리소스 사전을 구현하는 방법에 대한 자세한 내용은 [XAML 리소스를](../fundamentals/xaml-resources-define.md)참조하십시오.  
  
 XAML 2006 및 WPF에서는 특성으로 `x:Key` 제공되어야 합니다. 여전히 비문자열 키를 사용할 수 있지만 특성 양식에 문자열이 아닌 값을 제공하기 위해서는 태그 확장 사용이 필요합니다. XAML 2009를 사용하는 `x:Key` 경우 마크업 확장 중간 없이 문자열이 아닌 개체 형식별로 키에 지정된 사전을 명시적으로 지원하기 위해 요소로 지정할 수 있습니다. 이 항목의 "XAML 2009" 섹션을 참조하십시오. 주석 섹션의 나머지 부분은 XAML 2006 구현에 특히 적용됩니다.  
  
 의 `x:Key` 특성 값은 [XamlName 문법에](xamlname-grammar.md) 정의된 모든 문자열이거나 태그 확장을 통해 평가되는 개체일 수 있습니다. WPF의 예는 "WPF 사용 노트"를 참조하십시오.  
  
 <xref:System.Collections.IDictionary> 구현인 부모 요소의 자식 요소에는 `x:Key` 일반적으로 해당 사전 내에서 고유한 키 값을 지정하는 특성이 포함되어야 합니다. 프레임워크는 특정 `x:Key` 형식에서 대체할 별칭 키 속성을 구현할 수 있습니다. 이러한 속성을 정의하는 형식은 로 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>인해 사용해야 합니다.  
  
 지정에 `x:Key` 해당하는 코드는 기본 <xref:System.Collections.IDictionary>에 사용되는 키입니다. 예를 들어 `x:Key` WPF의 리소스에 대한 태그에 적용되는 것은 코드의 `key` WPF에 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> <xref:System.Windows.ResourceDictionary> 리소스를 추가할 때의 매개 변수 값과 같습니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 WPF와 <xref:System.Collections.IDictionary> <xref:System.Windows.ResourceDictionary>같은 구현인 부모 개체의 자식 개체는 일반적으로 `x:Key` 특성을 포함해야 하며 키 값은 해당 사전 내에서 고유해야 합니다. 두 가지 주목할 만한 예외가 있습니다.  
  
- 일부 WPF 형식은 사전 사용에 대한 암시적 키를 선언합니다. 예를 들어 <xref:System.Windows.Style> <xref:System.Windows.Style.TargetType%2A>a 또는 a와 <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.DataType%2A>함께 있는 a는 에 <xref:System.Windows.ResourceDictionary> 있을 수 있으며 암시적 키를 사용할 수 있습니다.  
  
- WPF는 병합된 리소스 사전 개념을 지원합니다. 병합된 사전 간에 키를 공유할 수 있으며 을 사용하여 <xref:System.Windows.FrameworkContentElement.FindResource%2A>공유 키 동작에 액세스할 수 있습니다. 자세한 내용은 [병합된 리소스 사전](../../framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
 전체 WPF XAML 구현 및 응용 프로그램 모델에서 키 고유성은 XAML 태그 컴파일러에서 검사되지 않습니다. 대신 누락되었거나 `x:Key` 고유하지 않은 값이 로드 타임 XAML 파서 오류를 일으킵니다. 그러나 WPF용 사전의 Visual Studio 처리는 설계 단계에서 이러한 오류를 기록할 수 있습니다.  
  
 표시된 구문에서 <xref:System.Windows.ResourceDictionary> 개체는 WPF XAML 프로세서가 컬렉션을 채우는 컬렉션을 생성하는 방법에 <xref:System.Windows.FrameworkElement.Resources%2A> 암시적입니다. A는 <xref:System.Windows.ResourceDictionary> 일반적으로 태그의 요소로 명시적으로 제공되지 않지만 명확성을 원한다면 경우에 따라 제공될 수 <xref:System.Windows.FrameworkElement.Resources%2A> 있습니다(속성 요소와 사전을 채우는 항목 사이의 컬렉션 개체 요소일 수 있음). 컬렉션 개체가 거의 항상 태그의 암시적 요소인 이유에 대한 자세한 내용은 [XAML 구문 세부 정보를](../../framework/wpf/advanced/xaml-syntax-in-detail.md)참조하십시오.  
  
 WPF XAML 구현에서 리소스 사전 키에 대한 <xref:System.Windows.ResourceKey> 처리는 추상 클래스에 의해 정의됩니다. 그러나 WPF XAML 프로세서는 사용량에 따라 키에 대해 다른 기본 확장 유형을 생성합니다. 예를 들어 a <xref:System.Windows.DataTemplate> 또는 파생 클래스의 키는 별도로 처리되고 고유한 <xref:System.Windows.DataTemplateKey> 개체를 생성합니다.  
  
 키와 이름은 기본 XAML`x:Key` 정의에서 서로 다른 지시문 및 언어 요소(대)를 `x:Name`사용합니다. 키와 이름은 WPF 정의 및 이러한 개념의 응용 프로그램에 의해 다른 상황에서사용된다. 자세한 내용은 [WPF XAML 네임스코프 를](../../framework/wpf/advanced/wpf-xaml-namescopes.md)참조하십시오.  
  
 앞에서 설명한 것처럼 키 값은 태그 확장을 통해 제공될 수 있으며 문자열 값이 아닌 다른 값일 수 있습니다. WPF 시나리오의 예는 의 `x:Key` 값이 [ComponentResourceKey](../../framework/wpf/advanced/componentresourcekey-markup-extension.md). 특정 컨트롤은 스타일을 완전히 대체하지 않고 해당 컨트롤의 모양과 동작의 일부에 영향을 주는 사용자 지정 스타일 리소스에 대해 해당 유형의 스타일 키를 노출합니다. 이러한 키의 예는 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.  
  
 WPF 병합 사전 기능은 키 고유성 및 키 조회 동작에 대한 추가 고려 사항을 소개합니다. 자세한 내용은 [병합된 리소스 사전](../../framework/wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009는 `x:Key` 항상 특성 형태로 제공되는 제한을 완화합니다.  
  
 WPF에서는 XAML 2009 기능을 사용할 수 있지만 마크업 컴파일되지 않은 XAML에만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
 XAML 2009에서 다음 `x:Key` 사용을 통해 요소를 지정할 수 있습니다.  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 요소 사용(XAML 2009에만)  
  
```xaml  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`keyObject`|특수 사전에서 제공된 `object` 개체의 키로 사용되는 개체에 대한 개체 요소입니다.|  
  
- 이러한 종류의 사용에 대한 컨테이너/부모는 여기에 표시되지 않습니다. `object`는 특수 사전 구현을 나타내는 개체 요소의 자식으로 예상됩니다. `keyObject`는 특정 특수 사전 구현의 키로 적합한 개체 인스턴스(또는 값 형식의 값)가 될 것으로 예상됩니다.  
  
- WPF는 이 사용이 필요한 사전을 구현하지 않습니다. 개체 키는 XAML 언어의 일반적인 기능으로 XAML에서 사전을 만드는 것이 바람직한 특정 사용자 지정 사전 시나리오에 유용할 수 있습니다. 리소스에 비 문자열 키를 사용하는 암시적 스타일과 같은 WPF 기능의 경우 키를 설정하거나 지정하는 다른 기술이 있으므로 개체 키를 사용할 필요가 없습니다.  
  
- `keyObject`또한 직접 개체 인스턴스가 아닌 개체 요소 형식의 태그 확장 사용일 수도 있습니다.  
  
## <a name="silverlight-usage-notes"></a>실버라이트 사용 노트  
 `x:Key`실버라이트에 대한 설명은 별도로 문서화되어 있습니다. 자세한 내용은 [XAML 네임스페이스(x:)를 참조하십시오. 언어 기능 (실버 라이트)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>참조

- [XAML 리소스](../fundamentals/xaml-resources-define.md)
- [리소스 및 코드](../../framework/wpf/advanced/resources-and-code.md)
- [StaticResource 태그 확장](../../framework/wpf/advanced/staticresource-markup-extension.md)
