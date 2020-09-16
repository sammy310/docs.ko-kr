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
ms.openlocfilehash: 7e4e9cbded01297818f9f01df01e95e94d7dc4af
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548275"
---
# <a name="xkey-directive"></a>x:Key 지시문
XAML 정의 사전에서 만들어지고 참조 되는 요소를 고유 하 게 식별 합니다. `x:Key`XAML 개체 요소에 값을 추가 하는 것은 WPF에서와 같이 리소스 사전에서 리소스를 식별 하는 가장 일반적인 방법입니다 <xref:System.Windows.ResourceDictionary> .  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a>XAML 특성 사용 (WPF 관련)  
  
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
|`markupExtensionUsage`|태그 확장 구분 기호 내에서 {} 키로 사용할 개체를 제공 하는 태그 확장 사용입니다. 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 `x:Key` XAML 리소스 사전 개념을 지원 합니다. 언어별 XAML은 특정 UI 프레임 워크로 남은 리소스 사전 구현을 정의 하지 않습니다. WPF에서 XAML 리소스 사전을 구현 하는 방법에 대해 자세히 알아보려면 [Xaml 리소스](../fundamentals/xaml-resources-define.md)를 참조 하세요.  
  
 XAML 2006 및 WPF에서는 `x:Key` 특성으로 제공 되어야 합니다. 여전히 문자열이 아닌 키를 사용할 수 있지만 특성 형식에서 문자열이 아닌 값을 제공 하기 위해 태그 확장 사용이 필요 합니다. XAML 2009를 사용 하는 경우를 `x:Key` 요소로 지정 하 여 태그 확장 중간을 요구 하지 않고 문자열 이외의 개체 형식으로 키가 지정 된 사전을 명시적으로 지원할 수 있습니다. 이 항목의 "XAML 2009" 섹션을 참조 하세요. 설명 섹션의 나머지 부분은 XAML 2006 구현에만 적용 됩니다.  
  
 의 특성 값은 `x:Key` [XamlName 문법](xamlname-grammar.md) 에 정의 된 문자열 일 수도 있고 태그 확장을 통해 계산 되는 개체 일 수도 있습니다. WPF의 예제는 "WPF 사용 정보"를 참조 하세요.  
  
 구현 되는 부모 요소의 자식 요소 <xref:System.Collections.IDictionary> 는 일반적으로 `x:Key` 해당 사전 내에서 고유한 키 값을 지정 하는 특성을 포함 해야 합니다. 프레임 워크는 별칭 키 속성을 구현 하 여 특정 형식에서를 대체할 수 있습니다. `x:Key` 이러한 속성을 정의 하는 형식은로 특성화 되어야 합니다 <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute> .  
  
 를 지정 하는 것과 동일한 코드는 `x:Key` 내부에 사용 되는 키입니다 <xref:System.Collections.IDictionary> . 예를 들어 `x:Key` wpf에서 리소스에 대 한 태그에 적용 되는는 `key` <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 코드에서 wpf에 리소스를 추가할 때의 매개 변수 값과 동일 합니다 <xref:System.Windows.ResourceDictionary> .  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 WPF와 같은 구현인 부모 개체의 자식 개체는 <xref:System.Collections.IDictionary> <xref:System.Windows.ResourceDictionary> 일반적으로 `x:Key` 특성을 포함 해야 하며 키 값은 해당 사전 내에서 고유 해야 합니다. 다음과 같은 두 가지 주목할 만한 예외가 있습니다.  
  
- 일부 WPF 형식은 사전 사용에 대 한 암시적 키를 선언 합니다. 예를 들어, 또는가 있는는에 <xref:System.Windows.Style> <xref:System.Windows.Style.TargetType%2A> <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.DataType%2A> 있을 수 있으며 <xref:System.Windows.ResourceDictionary> 암시적 키를 사용할 수 있습니다.  
  
- WPF는 병합 된 리소스 사전 개념을 지원 합니다. 병합 된 사전 간에 키를 공유할 수 있으며을 사용 하 여 공유 키 동작에 액세스할 수 있습니다 <xref:System.Windows.FrameworkContentElement.FindResource%2A> . 자세한 내용은 [병합 된 리소스 사전](/dotnet/desktop/wpf/advanced/merged-resource-dictionaries)을 참조 하세요.  
  
 전반적인 WPF XAML 구현 및 응용 프로그램 모델에서 키 고유성이 XAML 태그 컴파일러에 의해 검사 되지 않습니다. 대신, 값이 없거나 고유 하지 않으면 `x:Key` 로드 시간 XAML 파서 오류가 발생 합니다. 그러나 WPF 용 사전의 Visual Studio 처리는 디자인 단계에서 이러한 오류를 종종 확인할 수 있습니다.  
  
 표시 된 구문에서 <xref:System.Windows.ResourceDictionary> 개체는 WPF XAML 프로세서가 컬렉션을 만드는 방법에 대해 암시적입니다 <xref:System.Windows.FrameworkElement.Resources%2A> . 는 <xref:System.Windows.ResourceDictionary> 일반적으로 태그에서 요소로 명시적으로 제공 되지 않습니다. 그러나 명확 하 게 하기 위해 ( <xref:System.Windows.FrameworkElement.Resources%2A> 속성 요소와 사전을 채우는 내의 항목 사이에 컬렉션 개체 요소가 될 수 있음) 컬렉션 개체가 거의 항상 태그의 암시적 요소인 이유에 대 한 자세한 내용은 [XAML 구문](/dotnet/desktop/wpf/advanced/xaml-syntax-in-detail)정보를 참조 하세요.  
  
 WPF XAML 구현에서 리소스 사전 키에 대 한 처리는 추상 클래스에 의해 정의 됩니다 <xref:System.Windows.ResourceKey> . 그러나 WPF XAML 프로세서는 용도에 따라 키에 대해 서로 다른 기본 확장 형식을 생성 합니다. 예를 들어 또는 파생 클래스에 대 한 키는 <xref:System.Windows.DataTemplate> 별도로 처리 되 고 고유 개체를 생성 <xref:System.Windows.DataTemplateKey> 합니다.  
  
 키와 이름은 `x:Key` 기본 XAML 정의에서 다른 지시문 및 언어 요소 (vs)를 사용 `x:Name` 합니다. 키와 이름은 WPF 정의 및 이러한 개념의 응용 프로그램에서 다양 한 상황에도 사용 됩니다. 자세한 내용은 [WPF XAML 이름 범위](/dotnet/desktop/wpf/advanced/wpf-xaml-namescopes)를 참조 하세요.  
  
 앞에서 설명한 것 처럼 키 값은 태그 확장을 통해 제공 될 수 있으며 문자열 값이 아닌 다른 값이 될 수 있습니다. 예제 WPF 시나리오는의 값이 ComponentResourceKey 수 있다는 것입니다 `x:Key` . [ComponentResourceKey](/dotnet/desktop/wpf/advanced/componentresourcekey-markup-extension) 특정 컨트롤은 스타일을 완전히 바꾸지 않고 해당 컨트롤의 모양과 동작의 일부에 영향을 주는 사용자 지정 스타일 리소스에 대해 해당 형식의 스타일 키를 노출 합니다. 이러한 키의 예는 <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A> 입니다.  
  
 WPF 병합 사전 기능에서는 키 고유성 및 키 조회 동작에 대 한 추가 고려 사항을 소개 합니다. 자세한 내용은 [병합 된 리소스 사전](/dotnet/desktop/wpf/advanced/merged-resource-dictionaries)을 참조 하세요.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009은 `x:Key` 항상 특성 형식으로 제공 되는 제한을 완화 합니다.  
  
 WPF에서 XAML 2009 기능을 사용할 수 있지만 태그 컴파일되지 않은 XAML에만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
 XAML 2009에서는 다음을 사용 하 여 요소를 지정할 수 있습니다 `x:Key` .  
  
### <a name="xaml-element-usage-xaml-2009-only"></a>XAML 요소 사용 (XAML 2009에만 해당)  
  
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
|`keyObject`|특수화 된 사전에서 지정 된의 키로 사용 되는 개체의 개체 요소입니다 `object` .|  
  
- 이러한 종류의 용도에 대 한 컨테이너/부모는 여기에 표시 되지 않습니다. `object` 는 특수 사전 구현을 나타내는 개체 요소의 자식 이어야 합니다. `keyObject` 는 특정 특수 사전 구현에 대 한 키로 적합 한 개체 인스턴스 (또는 값 형식의 값) 여야 합니다.  
  
- WPF는 이러한 사용법이 필요한 사전을 구현 하지 않습니다. 개체 키는 XAML 언어의 일반적인 기능입니다. XAML로 사전을 만드는 것이 바람직한 특정 사용자 지정 사전 시나리오에 유용할 수 있습니다. 리소스에 대해 문자열이 아닌 키를 사용 하는 암시적 스타일과 같은 WPF 기능의 경우 키를 설정 하거나 지정 하는 다른 기술 들이 존재 하므로 개체 키를 사용 하지 않아도 됩니다.  
  
- `keyObject` 는 직접 개체 인스턴스가 아닌 개체 요소 형식에서 태그 확장 사용이 될 수도 있습니다.  
  
## <a name="silverlight-usage-notes"></a>Silverlight 사용 메모  
 `x:Key` Silverlight의는 별도로 설명 됩니다. 자세한 내용은 [XAML 네임 스페이스 (x:)를 참조 하세요. 언어 기능 (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>참조

- [XAML 리소스](../fundamentals/xaml-resources-define.md)
- [리소스 및 코드](/dotnet/desktop/wpf/advanced/resources-and-code)
- [StaticResource 태그 확장](/dotnet/desktop/wpf/advanced/staticresource-markup-extension)
