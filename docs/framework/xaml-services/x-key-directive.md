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
ms.openlocfilehash: 4ffd7a2922c7f3ba35ccb9ac7ce29a6a00cd99af
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837209"
---
# <a name="xkey-directive"></a>x:Key 지시문
XAML 정의된 사전에서 만들어지고 참조되는 요소를 고유하게 식별합니다. `x:Key` 값을 XAML 개체 요소를 추가하는 것은 WPF <xref:System.Windows.ResourceDictionary>에서처럼 리소스 사전에서 리소스를 식별하는 일반적인 방법입니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 특성 사용(WPF 특정)  
  
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
|`stringKeyValue`|키로 사용할 텍스트 문자열입니다. 텍스트 문자열은 [XamlName 문법을](xamlname-grammar.md)준수 해야 합니다.|  
|`markupExtensionUsage`|태그 확장 구분 기호 내에서 키로 사용할 개체를 제공 하는 태그 확장 사용 {}입니다. 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>주의  
 `x:Key`는 XAML 리소스 사전 개념을 지원합니다. 언어로서의 XAML은 리소스 사전 구현을 정의하지 않으며, 이러한 구현은 특정 UI 프레임워크에서 해결해야 합니다. WPF에서 XAML 리소스 사전을 구현 하는 방법에 대해 자세히 알아보려면 [Xaml 리소스](../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조 하세요.  
  
 XAML 2006 및 WPF에서 `x:Key`은 특성으로 제공 되어야 합니다. 문자열이 아닌 키는 여전히 사용할 수 있지만 특성 양식에서 문자열이 아닌 값을 제공하려면 이 태그 확장을 사용해야 합니다. XAML 2009를 사용 하는 경우 태그 확장 중간을 요구 하지 않고 문자열 이외의 개체 형식으로 키가 지정 된 사전을 명시적으로 지원 하기 위해 `x:Key`를 요소로 지정할 수 있습니다. 이 항목의 "XAML 2009" 섹션을 참조 하세요. 설명 섹션의 나머지 부분은 XAML 2006 구현에만 적용 됩니다.  
  
 `x:Key`의 특성 값은 [XamlName 문법](xamlname-grammar.md) 에 정의 된 문자열이 될 수도 있고 태그 확장을 통해 계산 되는 개체 일 수도 있습니다. WPF의 예제는 "WPF 사용 정보"를 참조하십시오.  
  
 <xref:System.Collections.IDictionary> 구현인 부모 요소의 자식 요소는 일반적으로 해당 사전 내에서 고유한 키 값을 지정하는 `x:Key` 특성을 포함해야 합니다. 프레임워크는 특정 형식의 `x:Key`에 대해 별칭이 지정된 키 속성을 구현할 수 있습니다. 이러한 속성을 정의하는 형식은 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>로 특성을 지정해야 합니다.  
  
 코드에서 `x:Key`를 지정하는 것과 동일한 기능을 하는 것은 기본 <xref:System.Collections.IDictionary>용 키를 사용하는 것입니다. 예를 들어 WPF에서 리소스에 대해 태그에서 적용된 `x:Key`는 코드에서 리소스를 WPF <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>에 추가할 때 지정하는 <xref:System.Windows.ResourceDictionary>의 `key` 매개 변수 값과 동일합니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 WPF <xref:System.Collections.IDictionary>와 같이 <xref:System.Windows.ResourceDictionary> 구현인 부모 개체의 자식 개체는 일반적으로 `x:Key` 특성을 포함해야 하며 키 값은 해당 사전 내에서 고유해야 합니다. 두 가지 중요한 예외가 있습니다.  
  
- 일부 WPF 형식은 사전 사용을 위한 암시적 키를 선언합니다. 예를 들어, <xref:System.Windows.Style>이 있는 <xref:System.Windows.Style.TargetType%2A> 또는 <xref:System.Windows.DataTemplate>이 있는 <xref:System.Windows.DataTemplate.DataType%2A>를 <xref:System.Windows.ResourceDictionary>에 배치할 수 있고 암시적 키를 사용합니다.  
  
- WPF는 병합된 리소스 사전 개념을 지원합니다. 키는 병합된 사전 간에 공유될 수 있으며 공유 키 동작은 <xref:System.Windows.FrameworkContentElement.FindResource%2A>를 사용하여 액세스할 수 있습니다. 자세한 내용은 [병합된 리소스 사전](../wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
 전체적인 WPF XAML 구현 및 응용 프로그램 모델에서 XAML 태그 컴파일러는 키 고유성을 확인하지 않습니다. 대신, `x:Key` 값이 없거나 고유하지 않으면 로드할 때 XAML 구문 분석기 오류가 발생합니다. 그러나 WPF 용 사전의 Visual Studio 처리는 디자인 단계에서 이러한 오류를 종종 확인할 수 있습니다.  
  
 표시된 구문에서 <xref:System.Windows.ResourceDictionary> 개체는 WPF XAML 프로세서가 컬렉션을 생성하여 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션을 채우는 방법을 암시적으로 지정합니다. <xref:System.Windows.ResourceDictionary>는 태그에 명시적으로 요소로 제공되지 않는 것이 일반적입니다. 단, 필요한 경우 명확성을 높이기 위해 명시적으로 제공할 수 있으며 이 경우 <xref:System.Windows.FrameworkElement.Resources%2A> 속성 요소와 사전을 채우는 항목 사이의 컬렉션 개체 요소로 제공됩니다. 컬렉션 개체가 거의 항상 태그의 암시적 요소인 이유에 대 한 자세한 내용은 [XAML 구문](../wpf/advanced/xaml-syntax-in-detail.md)정보를 참조 하세요.  
  
 WPF XAML 구현에서 리소스 사전 키의 처리는 <xref:System.Windows.ResourceKey> 추상 클래스를 통해 정의됩니다. 하지만 WPF XAML 프로세서는 키 용도에 따라 키에 대해 서로 다른 기본 확장 형식을 생성합니다. 예를 들어 <xref:System.Windows.DataTemplate> 또는 파생 클래스에 대한 키는 별도로 처리되어 별개의 <xref:System.Windows.DataTemplateKey> 개체를 생성합니다.  
  
 키와 이름은 기본 XAML 정의에서 다른 지시문 및 언어 요소(`x:Key` 및 `x:Name`)를 사용합니다. 키와 이름은 이러한 개념의 WPF 정의 및 응용 프로그램에 의해 다른 상황에서도 사용됩니다. 자세한 내용은 참조 하세요 [WPF XAML 이름 범위](../wpf/advanced/wpf-xaml-namescopes.md)합니다.  
  
 앞에서 설명한 것처럼 키 값은 문자열 값 이외에 태그 확장을 통해 제공될 수 있습니다. 예제 WPF 시나리오는 `x:Key` 값이 [ComponentResourceKey](../wpf/advanced/componentresourcekey-markup-extension.md)수 있다는 것입니다. 특정 컨트롤은 스타일을 완전히 바꾸지 않고 해당 컨트롤의 모양과 동작에 영향을 주는 사용자 지정 스타일 리소스에 대해 해당 형식의 스타일 키를 노출합니다. 이러한 키로는 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>가 있습니다.  
  
 WPF 병합된 사전 기능은 키 고유성 및 키 조회 동작에 대한 추가 고려 사항을 소개합니다. 자세한 내용은 [병합된 리소스 사전](../wpf/advanced/merged-resource-dictionaries.md)을 참조하세요.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009은 `x:Key` 항상 특성 형식으로 제공 되는 제한을 완화 합니다.  
  
 WPF에서 XAML 2009 기능을 사용할 수 있지만 태그 컴파일되지 않은 XAML에만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
 XAML 2009에서는 다음을 사용 하 여 `x:Key` 요소를 지정할 수 있습니다.  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 요소 사용(XAML 2009만 해당)  
  
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
|`keyObject`|특수 사전에서 주어진 `object`에 대한 키로 사용되는 개체의 개체 요소입니다.|  
  
- 이러한 종류의 사용에 대한 컨테이너/부모는 여기에 표시되지 않습니다. `object`는 특수 사전 구현을 나타내는 개체 요소의 자식입니다. `keyObject`는 특정 특수 사전 구현을 위한 키로 적합한 개체 인스턴스(또는 값 형식의 값)로 예상됩니다.  
  
- WPF는 이 사용에 필요한 사전을 구현하지 않습니다. 개체 키는 XAML 언어의 보다 일반적인 기능이며 XAML에서 사전을 만드는 것이 바람직할 때 특정한 사용자 지정 사전 시나리오에 유용할 수 있습니다. 리소스에 대해 문자열이 아닌 키를 사용하는 암시적 스타일 같은 WPF 기능의 경우 키를 설정하거나 지정하는 다른 방법이 있으므로 개체 키를 사용할 필요가 없습니다.  
  
- *keyObject* 는 직접 개체 인스턴스가 아닌 개체 요소 형식에서 태그 확장 사용이 될 수도 있습니다.  
  
## <a name="silverlight-usage-notes"></a>Silverlight 사용 정보  
 Silverlight용 `x:Key`는 별도로 문서화되어 있습니다. 자세한 내용은 [XAML 네임 스페이스 (x:)를 참조 하세요. 언어 기능 (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>참조

- [XAML 리소스](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [리소스 및 코드](../wpf/advanced/resources-and-code.md)
- [StaticResource 태그 확장](../wpf/advanced/staticresource-markup-extension.md)
