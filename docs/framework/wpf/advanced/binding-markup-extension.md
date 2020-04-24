---
title: Binding 태그 확장
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: c6a424e085c7499db08d0a7e6b652f45fb2cdd70
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644076"
---
# <a name="binding-markup-extension"></a>Binding 태그 확장
속성 값을 데이터 바인딩 값으로 연기하여 중간 식 개체를 만들고 런타임에 요소 및 해당 바인딩에 적용되는 데이터 컨텍스트를 해석합니다.  
  
## <a name="binding-expression-usage"></a>바인딩 식 사용  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>구문 노트  
 이러한 구문에서는 `[]` `*` 리터럴이 아닙니다. 이러한 표현법의 일부로, 0개 이상의 *bindProp*`=`*값* 쌍을 사용할 수 `,` 있으며, 그 중 구분 기호와 이전 *bindProp*`=`*값* 쌍이 있습니다.  
  
 "바인딩 확장으로 설정할 수 있는 바인딩 속성" 섹션에 나열 된 모든 속성 대신 <xref:System.Windows.Data.Binding> 개체 요소의 특성을 사용 하 여 설정할 수 있습니다. 그러나 실제로 는 CLR <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.Binding> 클래스의 속성을 설정 하는 특성의 일반적인 XAML 처리의 태그 확장 사용 이 아닙니다. `<Binding` 즉, *bindProp1*`="`*value1* `"[` *bindPropN valueN은*`="`*valueN* `"]*/>` <xref:System.Windows.Data.Binding> `Binding` 식 사용 대신 개체 요소 사용의 특성에 대해 동등한 구문입니다. 의 특정 속성에 <xref:System.Windows.Data.Binding>대한 XAML 특성 사용에 대한 자세한 내용은 .NET Framework 클래스 <xref:System.Windows.Data.Binding> 라이브러리의 관련 속성의 "XAML 특성 사용" 섹션을 참조하십시오.  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|설정할 <xref:System.Windows.Data.Binding> 속성 또는 <xref:System.Windows.Data.BindingBase> 속성의 이름입니다. 확장으로 <xref:System.Windows.Data.Binding> `Binding` 모든 속성을 설정할 수 있는 것은 아니며 일부 `Binding` 속성은 추가 중첩된 태그 확장을 사용하여 표현식 내에서 설정할 수 있습니다. "바인딩 확장을 통해 설정할 수 있는 바인딩 속성" 절을 참조하십시오.|  
|`value1, valueN`|속성을 설정할 값. 특성 값의 처리는 궁극적으로 설정되는 특정 <xref:System.Windows.Data.Binding> 속성의 형식 및 논리에 따라 다릅니다.|  
|`path`|암시적 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 속성을 설정하는 경로 문자열입니다. 또한 [PropertyPath XAML 구문 참조.](propertypath-xaml-syntax.md)|  
  
## <a name="unqualified-binding"></a>정규화되지 않은 {바인딩}  
 "바인딩 식 사용"에 표시된 `{Binding}` <xref:System.Windows.Data.Binding> 사용법은 `null`의 이니셜을 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 포함하는 기본값을 가진 개체를 만듭니다. 생성된 <xref:System.Windows.Data.Binding> 속성이 런타임 데이터 컨텍스트에서 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 설정되고 있는 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 것과 같은 키 데이터 바인딩 속성에 의존할 수 있기 때문에 많은 시나리오에서 여전히 유용합니다. 데이터 컨텍스트의 개념에 대한 자세한 내용은 [데이터 바인딩](../../../desktop-wpf/data/data-binding-overview.md)을 참조하십시오.  
  
## <a name="implicit-path"></a>암시적 경로  
 태그 `Binding` 확장은 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 식에 표시할 필요가 없는 개념적 "기본 속성"으로 `Path=` 사용합니다. 암시적 경로가 있는 `Binding` 식을 지정하는 경우 속성이 이름으로 지정된 다른 `bindProp` = `value` 쌍보다 <xref:System.Windows.Data.Binding> 먼저 암시적 경로가 식에 먼저 나타나야 합니다. 예를 `{Binding PathString}`들어, `PathString` markup 확장 사용에 의해 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> <xref:System.Windows.Data.Binding> 생성된 값으로 평가되는 문자열은 여기서입니다. 예를 들어 쉼표 구분 기호 다음의 다른 명명된 속성으로 암시적 `{Binding LastName, Mode=TwoWay}`경로를 추가할 수 있습니다.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>바인딩 확장으로 설정할 수 있는 바인딩 속성  
 이 항목에 표시된 구문은 많은 `bindProp` = `value` 읽기/쓰기 속성이 <xref:System.Windows.Data.BindingBase> 있거나 <xref:System.Windows.Data.Binding> 태그 확장/식 구문을 통해 설정할 `Binding` 수 있기 때문에 제네릭 근사치를 사용합니다. 암시적 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>을 제외한 모든 순서로 설정할 수 있습니다. (명시적으로 지정하는 `Path=`옵션이 있습니다.이 경우 임의의 순서로 설정할 수 있습니다.) 기본적으로 쉼표로 구분된 쌍을 사용하여 `bindProp` = `value` 아래 목록에서 0 개 이상의 속성을 설정할 수 있습니다.  
  
 이러한 속성 값 중 일부는 XAML의 텍스트 구문에서 네이티브 형식 변환을 지원하지 않는 개체 형식이 필요하므로 특성 값으로 설정하려면 태그 확장이 필요합니다. 자세한 내용은 각 속성에 대한 .NET Framework 클래스 라이브러리의 XAML 특성 사용 섹션을 확인합니다. 추가 태그 확장 사용 여부에 관계없이 XAML 특성 구문에 사용하는 문자열은 `Binding` 기본적으로 식의 각 `bindProp` = `value` `Binding` 값 주위에 따옴표를 배치하지 않는 경우를 제외하고 식에서 지정한 값과 동일합니다.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: 가능한 바인딩 그룹을 식별하는 문자열입니다. 이는 비교적 진보된 바인딩 개념입니다. 에 대한 <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>참조 페이지를 참조하십시오.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: 식에서 `bindProp` = `value` 문자열로 설정할 수 있지만 이렇게 하려면 [StaticResource 마크업 확장과](staticresource-markup-extension.md)같은 값에 대한 개체 참조가 필요합니다. 이 경우 값은 사용자 지정 변환기 클래스의 인스턴스입니다.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: 표준 기반 식별자로 식에서 설정할 수 있습니다. 에 대한 <xref:System.Windows.Data.Binding.ConverterCulture%2A>참조 항목을 참조하십시오.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: 식에서 `bindProp` = `value` 문자열로 설정할 수 있지만 전달되는 매개 변수의 형식에 따라 다릅니다. 값에 대한 참조 형식을 전달하는 경우 이 사용에는 중첩된 [StaticResource Markup 확장과](staticresource-markup-extension.md)같은 개체 참조가 필요합니다.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: 상호 배타적 대 <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>; 이러한 각 바인딩 속성은 특정 바인딩 방법론을 나타냅니다. [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오.  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: 식에서 `bindProp` = `value` 문자열로 설정할 수 있지만 전달되는 값의 형식에 따라 다릅니다. 참조 형식을 전달하는 경우 중첩된 [StaticResource 마크업 확장과](staticresource-markup-extension.md)같은 개체 참조가 필요합니다.  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *값은* <xref:System.Windows.Data.BindingMode> 열거형의 상수 이름입니다. 예: `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: 데이터 개체 또는 일반 개체 모델에 대한 경로를 설명하는 문자열입니다. 형식은 이 항목에서 적절하게 설명할 수 없는 개체 모델을 탐색하기 위한 여러 가지 규칙을 제공합니다. [PropertyPath XAML 구문](propertypath-xaml-syntax.md)을 참조하십시오.  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: 상호 배타적 <xref:System.Windows.Data.Binding.Source%2A>대 및; <xref:System.Windows.Data.Binding.ElementName%2A> 이러한 각 바인딩 속성은 특정 바인딩 방법론을 나타냅니다. [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오. 값을 지정하려면 중첩된 [상대 소스 마크업확장](relativesource-markupextension.md) 사용이 필요합니다.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: 상호 배타적 대 <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.ElementName%2A>; 이러한 각 바인딩 속성은 특정 바인딩 방법론을 나타냅니다. [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오. 중첩된 확장 사용(일반적으로 키리소스 사전의 개체 데이터 원본을 참조하는 [StaticResource Markup 확장)이](staticresource-markup-extension.md) 필요합니다.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: 바인딩된 데이터에 대한 문자열 형식 규칙을 설명하는 문자열입니다. 이는 비교적 진보된 바인딩 개념입니다. 에 대한 <xref:System.Windows.Data.BindingBase.StringFormat%2A>참조 페이지를 참조하십시오.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: 식에서 `bindProp` = `value` 문자열로 설정할 수 있지만 전달되는 매개 변수의 형식에 따라 다릅니다. 값에 대한 참조 형식을 전달하는 경우 중첩된 [StaticResource 마크업 확장과](staticresource-markup-extension.md)같은 개체 참조가 필요합니다.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *값은* <xref:System.Windows.Data.UpdateSourceTrigger> 열거형의 상수 이름입니다. 예: `{Binding UpdateSourceTrigger=LostFocus}`. 특정 컨트롤은 이 바인딩 속성에 대해 서로 다른 기본값을 가질 수 있습니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>을 참조하세요.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: 부울, 중 `true` `false`하나 또는 할 수 있습니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: XML 데이터 원본의 XMLDOM에 대한 경로를 설명하는 문자열입니다. [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩을](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)참조하십시오.  
  
 다음은 <xref:System.Windows.Data.Binding> `Binding` 태그 확장/`{Binding}` 식 양식을 사용하여 설정할 수 없는 속성입니다.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: 이 속성은 콜백 구현에 대한 참조를 기대합니다. 이벤트 처리기 이외의 콜백/메서드는 XAML 구문에서 참조할 수 없습니다.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: 속성은 개체의 <xref:System.Windows.Controls.ValidationRule> 일반 컬렉션을 수행합니다. 이 개체 요소에서 속성 요소로 표현할 수 있지만 <xref:System.Windows.Data.Binding> `Binding` 식에서 사용하기 위해 쉽게 사용할 수 있는 특성 구문 분석 기술이 없습니다. 에 대한 <xref:System.Windows.Data.Binding.ValidationRules%2A>참조 항목을 참조하십시오.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
> 종속성 속성 우선 순위 측면에서 `Binding` 식은 로컬로 설정된 값과 같습니다. 이전에 `Binding` 식이 있었던 속성에 대한 로컬 값을 설정하면 이 `Binding` 값이 완전히 제거됩니다. 자세한 내용은 [종속성 속성 값 우선 순위](dependency-property-value-precedence.md)를 참조하세요.  
  
 기본 수준에서 데이터 바인딩을 설명하는 것은 이 항목에서 다루지 않습니다. [데이터 바인딩 개요를](../../../desktop-wpf/data/data-binding-overview.md)참조하십시오.  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 <xref:System.Windows.Data.PriorityBinding> 확장 구문을 지원하지 않습니다. 대신 속성 요소를 사용합니다. 및 <xref:System.Windows.Data.PriorityBinding>에 <xref:System.Windows.Data.MultiBinding> 대한 참조 항목을 참조하십시오.  
  
 XAML에 대한 부울 값은 대/소문자를 구분하지 않습니다. 예를 들어 `{Binding NotifyOnValidationError=true}` 또는 `{Binding NotifyOnValidationError=True}`을 지정할 수 있습니다.  
  
 데이터 유효성 검사를 포함하는 바인딩은 일반적으로 `Binding` `{Binding ...}` 표현식이 아닌 명시적 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 요소에 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 의해 지정되며 설정또는 식에서 드문 경우입니다. 이는 식 양식에서 <xref:System.Windows.Data.Binding.ValidationRules%2A> companion 속성을 쉽게 설정할 수 없기 때문입니다. 자세한 내용은 [바인딩 유효성 검사 구현을](../data/how-to-implement-binding-validation.md)참조하십시오.  
  
 `Binding`은 태그 확장입니다. 태그 확장은 일반적으로 리터럴 값 이나 처리기 이름 이외의 특성 값을 이스케이프 해야 하는 경우 구현 되 고 요구 사항은 특정 형식 또는 속성에 특성 형식 변환기 보다 더 전역. XAML의 모든 태그 확장은 `{` `}` 해당 특성 구문의 및 문자를 사용합니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
 `Binding`WPF의 XAML 구현에 <xref:System.Windows.Data.Binding> 대 한 확장 기능을 구현 하는 클래스는 또한 XAML관련 되지 않은 몇 가지 다른 메서드 및 속성을 구현 하는 점에서 비정형 태그 확장입니다. 다른 멤버는 XAML 태그 확장으로 작동하는 것 외에도 많은 데이터 바인딩 시나리오를 해결할 수 있는 보다 다재다능하고 독립적인 클래스를 만들기 <xref:System.Windows.Data.Binding> 위한 것입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Data.Binding>
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
