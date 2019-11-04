---
title: Binding 태그 확장
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: d0a437e756da16db978d8074c4355fd83d211b67
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453607"
---
# <a name="binding-markup-extension"></a>Binding 태그 확장
속성 값을 데이터 바인딩된 값으로 지연 하 여 중간 식 개체를 만들고 런타임에 요소 및 바인딩에 적용 되는 데이터 컨텍스트를 해석 합니다.  
  
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
  
## <a name="syntax-notes"></a>구문 정보  
 이러한 구문에서 `[]` 및 `*`는 리터럴이 아닙니다. 이러한 값은 0 개 이상의 *bindprop*`=`*값* 쌍을 사용할 수 있음을 나타내는 표기법의 일부 이며, 그 사이에는 `,` 구분 기호와 이전 *bindprop*`=`*값* 쌍이 있습니다.  
  
 "바인딩 확장을 사용 하 여 설정할 수 있는 바인딩 속성" 섹션에 나열 된 모든 속성은 <xref:System.Windows.Data.Binding> object 요소의 특성을 사용 하 여 설정할 수 있습니다. 그러나 <xref:System.Windows.Data.Binding>의 태그 확장 사용은 아닙니다 .이는 CLR <xref:System.Windows.Data.Binding> 클래스의 속성을 설정 하는 특성의 일반적인 XAML 처리 일 뿐입니다. 즉, `<Binding` *bindProp1*`="`*Value1*`"[` *Bindpropn*`="`*valueen*`"]*/>`는 <xref:System.Windows.Data.Binding> 식 사용 대신 `Binding` 개체 요소 사용의 특성에 해당 하는 구문입니다. <xref:System.Windows.Data.Binding>의 특정 속성에 대 한 XAML 특성 사용에 대 한 자세한 내용은 .NET Framework 클래스 라이브러리에서 <xref:System.Windows.Data.Binding> 관련 속성의 "XAML 특성 사용" 섹션을 참조 하세요.  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|설정할 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.BindingBase> 속성의 이름입니다. `Binding` 확장을 사용 하 여 모든 <xref:System.Windows.Data.Binding> 속성을 설정할 수 있는 것은 아니고, 추가 중첩 된 태그 확장을 사용 해야만 `Binding` 식 내에서 일부 속성을 설정할 수 있습니다. "바인딩 확장을 사용 하 여 설정할 수 있는 바인딩 속성" 섹션을 참조 하세요.|  
|`value1, valueN`|속성을 설정할 값. 특성 값의 처리는 궁극적으로 설정 되는 특정 <xref:System.Windows.Data.Binding> 속성의 형식 및 논리와 관련이 있습니다.|  
|`path`|암시적 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 속성을 설정 하는 경로 문자열입니다. [XAML 구문 PropertyPath](propertypath-xaml-syntax.md)도 참조 하세요.|  
  
## <a name="unqualified-binding"></a>정규화 되지 않은 {Binding}  
 "바인딩 식 사용"에 표시 된 `{Binding}` 사용은 기본값을 사용 하 여 `null`의 초기 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>를 포함 하는 <xref:System.Windows.Data.Binding> 개체를 만듭니다. 이는 생성 된 <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>와 같은 키 데이터 바인딩 속성과 런타임 데이터 컨텍스트에서 설정 되는 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>를 사용할 수 있기 때문에 대부분의 시나리오에서 유용 합니다. 데이터 컨텍스트 개념에 대 한 자세한 내용은 [데이터 바인딩](../data/data-binding-wpf.md)을 참조 하세요.  
  
## <a name="implicit-path"></a>암시적 경로  
 `Binding` 태그 확장은 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>를 개념 "기본 속성"으로 사용 합니다 .이 경우 `Path=` 식에 나타날 필요가 없습니다. 암시적 경로를 사용 하 여 `Binding` 식을 지정 하는 경우 이름으로 <xref:System.Windows.Data.Binding> 속성이 지정 된 다른 `bindProp`=`value` 쌍 보다 먼저 암시적 경로가 식에 표시 되어야 합니다. 예: `{Binding PathString}`. 여기서 `PathString`는 태그 확장 사용으로 만든 <xref:System.Windows.Data.Binding>의 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 값으로 평가 되는 문자열입니다. 쉼표 구분 기호 뒤에 다른 명명 된 속성을 사용 하 여 암시적 경로를 추가할 수 있습니다 (예: `{Binding LastName, Mode=TwoWay}`).  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>바인딩 확장을 사용 하 여 설정할 수 있는 바인딩 속성  
 이 항목에 표시 된 구문에서는 <xref:System.Windows.Data.Binding> 태그 확장/식 구문을 통해 설정할 수 있는 <xref:System.Windows.Data.BindingBase> 또는 `Binding`의 읽기/쓰기 속성이 많기 때문에 제네릭 `bindProp`=`value` 근사값을 사용 합니다. 암시적 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>를 제외 하 고 순서에 관계 없이 설정할 수 있습니다. `Path=`를 명시적으로 지정 하는 옵션을 사용할 수 있으며,이 경우 임의의 순서로 설정할 수 있습니다. 기본적으로 아래 목록에서 0 개 이상의 속성을 설정 하 고 쉼표로 구분 된 `bindProp`=`value` 쌍을 사용할 수 있습니다.  
  
 이러한 속성 값 중 일부에는 XAML의 텍스트 구문에서 네이티브 형식 변환을 지원 하지 않으므로 특성 값으로 설정 하기 위해 태그 확장이 필요한 개체 형식이 필요 합니다. 자세한 내용은 각 속성에 대 한 .NET Framework 클래스 라이브러리의 XAML 특성 사용 섹션을 참조 하세요. 추가 태그 확장 사용 여부와 상관 없이 XAML 특성 구문에 사용 되는 문자열은 기본적으로 `Binding` 식에서 지정 하는 값과 동일 합니다. 단,에서는 각 `bindProp`=`value`에 따옴표를 넣지 않습니다. `Binding` 식입니다.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: 가능한 바인딩 그룹을 식별 하는 문자열입니다. 이는 비교적 고급 바인딩 개념입니다. <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>참조 페이지를 참조 하세요.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: 식에서 `bindProp`=`value` 문자열로 설정할 수 있지만 이렇게 하려면 [StaticResource 태그 확장과](staticresource-markup-extension.md)같은 값에 대 한 개체 참조가 필요 합니다. 이 경우 값은 사용자 지정 변환기 클래스의 인스턴스입니다.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: 표준 기반 식별자로 식에서 설정 가능 합니다. <xref:System.Windows.Data.Binding.ConverterCulture%2A>에 대 한 참조 항목을 참조 하세요.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: 식에서 `bindProp`=`value` 문자열로 설정할 수 있지만이는 전달 되는 매개 변수의 유형에 따라 달라 집니다. 값에 대 한 참조 형식을 전달 하는 경우이 사용에는 중첩 된 [StaticResource 태그 확장과](staticresource-markup-extension.md)같은 개체 참조가 필요 합니다.  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: 함께 사용할 수 없는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>; 이러한 각 바인딩 속성은 특정 바인딩 방법을 나타냅니다. [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조 하세요.  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: 식에서 `bindProp`=`value` 문자열로 설정할 수 있지만이는 전달 되는 값의 형식에 따라 달라 집니다. 참조 형식을 전달 하는 경우에는 중첩 된 [StaticResource 태그 확장과](staticresource-markup-extension.md)같은 개체 참조가 필요 합니다.  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *값* 은 <xref:System.Windows.Data.BindingMode> 열거형의 상수 이름입니다. 예를 들어 `{Binding Mode=OneWay}`과 같은 형식입니다.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: 데이터 개체 또는 일반 개체 모델에 대 한 경로를 설명 하는 문자열입니다. 형식은이 항목에서 적절 하 게 설명할 수 없는 개체 모델을 트래버스하는 여러 가지 규칙을 제공 합니다. [PROPERTYPATH XAML 구문](propertypath-xaml-syntax.md)을 참조 하세요.  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: 함께 사용할 수 없고 <xref:System.Windows.Data.Binding.ElementName%2A> 및 <xref:System.Windows.Data.Binding.Source%2A>와 함께 사용할 수 없습니다. 이러한 각 바인딩 속성은 특정 바인딩 방법을 나타냅니다. [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조 하세요. 값을 지정 하려면 중첩 된 [RelativeSource MarkupExtension](relativesource-markupextension.md) 사용이 필요 합니다.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: 함께 사용할 수 없는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 및 <xref:System.Windows.Data.Binding.ElementName%2A>; 이러한 각 바인딩 속성은 특정 바인딩 방법을 나타냅니다. [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조 하세요. 에는 중첩 된 확장 사용이 필요 합니다. 일반적으로 키가 지정 된 리소스 사전의 개체 데이터 소스를 참조 하는 [StaticResource 태그 확장이](staticresource-markup-extension.md) 필요 합니다.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: 바인딩된 데이터의 문자열 형식 규칙을 설명 하는 문자열입니다. 이는 비교적 고급 바인딩 개념입니다. <xref:System.Windows.Data.BindingBase.StringFormat%2A>참조 페이지를 참조 하세요.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: 식에서 `bindProp`=`value` 문자열로 설정할 수 있지만이는 전달 되는 매개 변수의 유형에 따라 달라 집니다. 값에 대 한 참조 형식을 전달 하는 경우에는 중첩 된 [StaticResource 태그 확장과](staticresource-markup-extension.md)같은 개체 참조가 필요 합니다.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *값* 은 <xref:System.Windows.Data.UpdateSourceTrigger> 열거형의 상수 이름입니다. 예를 들어 `{Binding UpdateSourceTrigger=LostFocus}`과 같은 형식입니다. 특정 컨트롤에는이 바인딩 속성에 대 한 기본값이 다를 수 있습니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하세요.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean은 `true` 또는 `false`수 있습니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: XML 데이터 소스의 XMLDOM에 대 한 경로를 설명 하는 문자열입니다. [XMLDataProvider 및 XPath 쿼리를 사용 하 여 XML 데이터에 바인딩을](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)참조 하세요.  
  
 다음은 `Binding` 태그 확장/`{Binding}` 식 형태를 사용 하 여 설정할 수 없는 <xref:System.Windows.Data.Binding> 속성입니다.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>:이 속성에는 콜백 구현에 대 한 참조가 필요 합니다. 이벤트 처리기 이외의 콜백/메서드는 XAML 구문에서 참조할 수 없습니다.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: 속성은 <xref:System.Windows.Controls.ValidationRule> 개체의 제네릭 컬렉션을 사용 합니다. 이는 <xref:System.Windows.Data.Binding> object 요소의 속성 요소로 표시 될 수 있지만 `Binding` 식에서 사용 하기 위한 특성 구문 분석 기술은 바로 사용할 수 없습니다. <xref:System.Windows.Data.Binding.ValidationRules%2A>에 대 한 참조 항목을 참조 하세요.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>주의  
  
> [!IMPORTANT]
> 종속성 속성의 우선 순위를 기준으로 `Binding` 식은 로컬로 설정 된 값과 동일 합니다. 이전에 `Binding` 식이 있던 속성의 로컬 값을 설정 하면 `Binding` 완전히 제거 됩니다. 자세한 내용은 [종속성 속성 값 우선 순위](dependency-property-value-precedence.md)를 참조하세요.  
  
 기본 수준에서 데이터 바인딩을 설명 하는 방법은이 항목에서 다루지 않습니다. [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조 하세요.  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding>는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 확장 구문을 지원 하지 않습니다. 대신 속성 요소를 사용 합니다. <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding>에 대 한 참조 항목을 참조 하세요.  
  
 XAML에 대 한 부울 값은 대/소문자를 구분 하지 않습니다. 예를 들어 `{Binding NotifyOnValidationError=true}` 또는 `{Binding NotifyOnValidationError=True}`를 지정할 수 있습니다.  
  
 데이터 유효성 검사와 관련 된 바인딩은 일반적으로 `{Binding ...}` 식이 아니라 명시적 `Binding` 요소로 지정 되며 식에 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 또는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>를 설정 하는 것은 일반적이 지 않습니다. 이는 동반 속성 <xref:System.Windows.Data.Binding.ValidationRules%2A>를 식 폼에서 쉽게 설정할 수 없기 때문입니다. 자세한 내용은 [바인딩 유효성 검사 구현](../data/how-to-implement-binding-validation.md)을 참조 하세요.  
  
 `Binding`은 태그 확장입니다. 태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값으로 이스케이프 해야 하는 요구 사항이 있는 경우 일반적으로 구현 되며, 요구 사항은 특정 형식 또는 속성에 대 한 특성이 있는 형식 변환기 보다 더 전역적입니다. XAML의 모든 태그 확장은 특성 구문에서 `{` 및 `}` 문자를 사용 합니다 .이는 XAML 프로세서가 태그 확장에서 문자열 내용을 처리 해야 함을 인식 하는 데 사용 되는 규칙입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
 `Binding`는 WPF의 XAML 구현에 대 한 확장 기능을 구현 하는 <xref:System.Windows.Data.Binding> 클래스가 XAML과 관련이 없는 몇 가지 다른 메서드와 속성을 구현 하는 경우에는 이례적인 태그 확장입니다. 다른 멤버는 XAML 태그 확장으로 작동 하는 것 외에도 많은 데이터 바인딩 시나리오를 처리할 수 있는 보다 다양 하 고 자체 포함 클래스를 <xref:System.Windows.Data.Binding> 하기 위한 것입니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Data.Binding>
- [데이터 바인딩 개요](../data/data-binding-overview.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
