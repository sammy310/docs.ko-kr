---
title: Binding 태그 확장
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 3455c7ccdedb432fc05c7dc9e80f0f7509f4fa0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170315"
---
# <a name="binding-markup-extension"></a>Binding 태그 확장
데이터 바인딩된 값을 중간 식 개체를 만들고 요소 및 해당 런타임 바인딩에 적용 되는 데이터 컨텍스트를 해석 하기 위해 속성 값을 연기 합니다.  
  
## <a name="binding-expression-usage"></a>바인딩 식 사용  
  
```  
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
 이러한 구문에는 `[]` 고 `*` 리터럴이 아닌 합니다. 나타내는 표기법의 일부인 0 개 이상의 *과*`=`*값* 쌍을 사용할 수 있습니다 사용 하 여를 `,` 들 앞 사이 구분 기호 *과*  `=` *값* 쌍입니다.  
  
 "바인딩 속성은 수 수 설정 된 바인딩 확장" 섹션에 나열 된 속성 대신 설정할 수의 특성을 사용 하는 <xref:System.Windows.Data.Binding> 개체 요소입니다. 그러나 없는 실제로 태그 확장 사용 <xref:System.Windows.Data.Binding>,이 CLR의 속성을 설정 하는 특성의 일반 XAML 처리만 <xref:System.Windows.Data.Binding> 클래스입니다. 다시 말해 `<Binding` *bindProp1*`="`*value1* `"[` *bindPropN*`="`*값* `"]*/>` 의 특성에 대 한 해당 구문은 <xref:System.Windows.Data.Binding> 개체 대신 요소 사용을 `Binding` 식 사용 합니다. 특정 속성의 XAML 특성 사용에 대해 자세히 알아보려면 <xref:System.Windows.Data.Binding>, 관련 속성의 "XAML 특성 사용" 섹션을 참조 <xref:System.Windows.Data.Binding> .NET Framework 클래스 라이브러리에서.  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|이름을 합니다 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.BindingBase> 속성을 설정 합니다. 일부 <xref:System.Windows.Data.Binding> 속성을 사용 하 여 설정할 수 있습니다 합니다 `Binding` 확장과 일부 속성 내에서 설정할 수는 `Binding` 추가로 사용 하 여 식 중첩 태그 확장 합니다. "바인딩 속성은 수 수 설정 된 바인딩 확장" 섹션을 참조 하세요.|  
|`value1, valueN`|속성을 설정할 값입니다. 특성 값의 처리는 궁극적으로 유형 및 특정 논리를 <xref:System.Windows.Data.Binding> 설정 되는 속성입니다.|  
|`path`|암시적으로 설정 하는 경로 문자열 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 속성입니다. 참고 항목 [PropertyPath XAML 구문](propertypath-xaml-syntax.md)합니다.|  
  
## <a name="unqualified-binding"></a>정규화 되지 않은 {Binding}  
 합니다 `{Binding}` "바인딩 식 사용"에 표시 된 사용량을 만듭니다는 <xref:System.Windows.Data.Binding> 초기값을 포함 하는 기본값을 사용 하 여 개체 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 의 `null`합니다. 대부분의 시나리오에서는 여전히 유용 하기 때문에 만들어진 <xref:System.Windows.Data.Binding> 와 같은 주요 데이터 바인딩 속성을 사용할 수도 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 런타임 데이터 컨텍스트에서 설정 합니다. 데이터 컨텍스트의 개념에 대 한 자세한 내용은 참조 하세요. [데이터 바인딩](../data/data-binding-wpf.md)합니다.  
  
## <a name="implicit-path"></a>암시적 경로  
 합니다 `Binding` 태그 확장 사용 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 개념적으로 "기본 속성" 여기서 `Path=` 식에 표시할 필요가 없습니다. 지정 하는 경우는 `Binding` 암시적 경로 사용 하 여 식에 암시적 경로가 다른 이전 식에서 첫 번째로 나타나야 합니다 `bindProp` = `value` 쌍을 <xref:System.Windows.Data.Binding> 속성 이름으로 지정 됩니다. 예를 들어: `{Binding PathString}`여기서 `PathString` 의 값으로 평가 되는 문자열인 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> 에 <xref:System.Windows.Data.Binding> 태그 확장 사용 하 여 생성 합니다. 예를 들어 쉼표 구분 기호 뒤 다른 명명 된 속성을 사용 하 여 암시적 경로 추가할 수 있습니다 `{Binding LastName, Mode=TwoWay}`합니다.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>바인딩 확장을 사용 하 여 설정할 수 있는 바인딩 속성  
 이 항목에 표시 된 구문에서는 제네릭 `bindProp` = `value` 근사치의 많은 읽기/쓰기 속성 이므로 <xref:System.Windows.Data.BindingBase> 또는 <xref:System.Windows.Data.Binding> 통해 설정할 수 있습니다는 `Binding` 태그 확장 / 식 구문입니다. 순서에 관계 없이 암시적인를 제외 하 고 설정할 수 있습니다 <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>합니다. (명시적으로 지정 하는 옵션을 사용 하도록 필요가 `Path=`,이 경우 순서에 관계 없이 설정할 수 있습니다). 기본적으로 설정할 수 있습니다 0 개 이상의 속성을 아래 목록에서 사용 하 여 `bindProp` = `value` 쌍은 쉼표로 구분 합니다.  
  
 이러한 속성 값의 몇 가지 XAML을 텍스트 구문에서 네이티브 형식 변환을 지원 하지 않으며 따라서 태그 확장이 특성 값으로 설정 하려면 필요 여부를 지정 하는 개체 유형이 필요 합니다. 자세한 내용은 각 속성에 대 한.NET Framework 클래스 라이브러리의 XAML 특성 사용 섹션 확인 XAML 특성 구문을 사용 하 여 사용 하는 문자열 또는 태그 확장을 추가 하지 않고 사용 기본적으로 동일한에서 지정한 값으로는 `Binding` 식을 각 주위에 따옴표를 배치 하지 마십시오 예외 `bindProp` = `value` 에 `Binding` 식입니다.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: 바인딩 가능한 그룹을 식별 하는 문자열입니다. 이 비교적 고급 바인딩 개념입니다. 참조 페이지를 참조 하십시오 <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>합니다.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>:으로 설정할 수는 `bindProp` = `value` 문자열 식에 있지만 그러려면 참조가 필요 합니다. 개체 값에 대해 같은 [StaticResource 태그 확장](staticresource-markup-extension.md)합니다. 이 경우 값은 사용자 지정 변환기 클래스의 인스턴스입니다.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: 표준 기반 식별자가 식에서 설정할 수 있음 에 대 한 참조 항목을 참조 <xref:System.Windows.Data.Binding.ConverterCulture%2A>합니다.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>:으로 설정할 수는 `bindProp` = `value` 식에 있지만이 문자열은 전달 된 매개 변수의 형식에 따라 달라 집니다. 이 사용량 같은 중첩 된 개체 참조가 필요 합니다. 값에 대 한 참조 형식에 전달 하는 경우 [StaticResource 태그 확장](staticresource-markup-extension.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>:와 함께 사용할 수 없습니다 <xref:System.Windows.Data.Binding.RelativeSource%2A> 고 <xref:System.Windows.Data.Binding.Source%2A>각 이러한 특정 바인딩 방법론을 나타내는 바인딩 속성입니다. 참조 [데이터 바인딩 개요](../data/data-binding-overview.md)합니다.  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>:으로 설정할 수는 `bindProp` = `value` 식에 있지만이 문자열은 전달 되는 값의 유형에 따라 달라 집니다. 중첩 된 같은 개체 참조가 필요 합니다. 참조 형식을 전달 하는 경우 [StaticResource 태그 확장](staticresource-markup-extension.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *값* 에서 이름인 상수는 <xref:System.Windows.Data.BindingMode> 열거형입니다. 예를 들어, `{Binding Mode=OneWay}`을 입력합니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: 데이터 개체 또는 일반 개체 모델에 대 한 경로 설명 하는 문자열입니다. 형식은이 항목의 적절 하 게 설명할 수 없는 개체 모델을 탐색 하는 데 다른 여러 규칙을 제공 합니다. 참조 [PropertyPath XAML 구문](propertypath-xaml-syntax.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: 비교와 함께 <xref:System.Windows.Data.Binding.ElementName%2A> 고 <xref:System.Windows.Data.Binding.Source%2A>각 이러한 특정 바인딩 방법론을 나타내는 바인딩 속성입니다. 참조 [데이터 바인딩 개요](../data/data-binding-overview.md)합니다. 중첩 된 필요 [RelativeSource 태그 확장](relativesource-markupextension.md) 사용량 값을 지정 합니다.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>:와 함께 사용할 수 없습니다 <xref:System.Windows.Data.Binding.RelativeSource%2A> 고 <xref:System.Windows.Data.Binding.ElementName%2A>각 이러한 특정 바인딩 방법론을 나타내는 바인딩 속성입니다. 참조 [데이터 바인딩 개요](../data/data-binding-overview.md)합니다. 일반적으로는 중첩 된 확장 사용 필요를 [StaticResource 태그 확장](staticresource-markup-extension.md) 키가 지정 된 리소스 사전에서 개체 데이터 소스를 나타내는입니다.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: 바인딩된 데이터에 대 한 문자열 형식 규칙을 설명 하는 문자열입니다. 이 비교적 고급 바인딩 개념입니다. 참조 페이지를 참조 하십시오 <xref:System.Windows.Data.BindingBase.StringFormat%2A>합니다.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>:으로 설정할 수는 `bindProp` = `value` 식에 있지만이 문자열은 전달 된 매개 변수의 형식에 따라 달라 집니다. 중첩 된 같은 개체 참조가 필요 합니다. 참조 형식을 값으로 전달 하는 경우 [StaticResource 태그 확장](staticresource-markup-extension.md)합니다.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *값* 에서 이름인 상수는 <xref:System.Windows.Data.UpdateSourceTrigger> 열거형입니다. 예를 들어, `{Binding UpdateSourceTrigger=LostFocus}`을 입력합니다. 특정 컨트롤에는 잠재적으로 서로 다른 기본 값이 바인딩 속성의 경우 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>을 참조하세요.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: 부울 일 수 있습니다 `true` 또는 `false`합니다. 기본값은 `false`입니다. 설명 부분을 참조하세요.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: XML 데이터 원본의 XMLDOM에 경로 설명 하는 문자열입니다. 참조 [XMLDataProvider 및 XPath 쿼리를 사용 하 여 XML 데이터를 바인딩할](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)합니다.  
  
 다음의 속성은 <xref:System.Windows.Data.Binding> 를 사용 하 여 설정할 수 없는 합니다 `Binding` 태그 확장 /`{Binding}` 식 형식입니다.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>:이 속성에 콜백 구현에 대 한 참조를 사용 해야 합니다. XAML 구문에서 콜백을/이벤트 처리기 이외의 메서드를 참조할 수 없습니다.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: 속성의 제네릭 컬렉션을 가져와서 <xref:System.Windows.Controls.ValidationRule> 개체입니다. 속성 요소로 표현할 수는 <xref:System.Windows.Data.Binding> 사용량에 대 한 즉시 사용할 수 없는 특성 구문 분석 기술이 되었지만 요소 개체를 `Binding` 식입니다. 참조 항목을 참조 <xref:System.Windows.Data.Binding.ValidationRules%2A>합니다.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  종속성 속성 우선 순위 측면에서 `Binding` 식 로컬로 설정에 해당 하는 값입니다. 이전에 있던 속성에 대 한 로컬 값을 설정 하는 경우는 `Binding` 식의 `Binding` 완전히 제거 됩니다. 자세한 내용은 [종속성 속성 값 우선 순위](dependency-property-value-precedence.md)를 참조하세요.  
  
 기본 수준에서 데이터 바인딩을 설명 하는이 항목에서 다루지 않습니다. 참조 [데이터 바인딩 개요](../data/data-binding-overview.md)합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> 및 <xref:System.Windows.Data.PriorityBinding> 지원 하지 않습니다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 확장 구문입니다. 대신 속성 요소를 사용할 수 있습니다. 참조 항목을 참조 하세요 <xref:System.Windows.Data.MultiBinding> 고 <xref:System.Windows.Data.PriorityBinding>입니다.  
  
 XAML에 대 한 부울 값은 대/소문자 구분입니다. 예를 들어 하거나 지정할 수 있습니다 `{Binding NotifyOnValidationError=true}` 또는 `{Binding NotifyOnValidationError=True}`합니다.  
  
 데이터 유효성 검사와 관련 된 바인딩은 일반적으로 명시적으로 지정 `Binding` 요소 아니라는 `{Binding ...}` 식 및 설정은 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 또는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 식에는 흔하지 않습니다. 왜냐하면 도우미 속성 <xref:System.Windows.Data.Binding.ValidationRules%2A> 식 형식에서 쉽게 설정할 수 없습니다. 자세한 내용은 [구현 바인딩 유효성 검사](../data/how-to-implement-binding-validation.md)합니다.  
  
 `Binding` 태그 확장입니다. 태그 확장 되도록 아닌 리터럴 값 또는 처리기 이름을 특성 값을 이스케이프 하는 요구 사항은 되며 이러한 요구 사항은 특정 형식 또는 속성에 특성을 사용 하는 형식 변환기 보다 더 많은 글로벌 하는 경우에 일반적으로 구현 됩니다. XAML 사용의 모든 태그 확장을 `{` 고 `}` XAML 프로세서는 태그 확장에 문자열 내용을 처리 해야 한다는 것을 인식 하는 규칙은 특성 구문에서 문자입니다. 자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.  
  
 `Binding` 비정상적 태그 확장인는 <xref:System.Windows.Data.Binding> WPF의 XAML 구현에 대 한 확장 기능을 구현 하는 클래스도 여러 다른 메서드 및 XAML에 관련 되지 않은 속성을 구현 합니다. 다른 멤버를 확인 하려는 <xref:System.Windows.Data.Binding> XAML 태그 확장으로 작동 하는 것 외에도 여러 데이터 바인딩 시나리오를 해결할 수 있는 더 다양 하 고 자체 포함 된 클래스입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.Binding>
- [데이터 바인딩 개요](../data/data-binding-overview.md)
- [XAML 개요(WPF)](xaml-overview-wpf.md)
- [태그 확장명 및 WPF XAML](markup-extensions-and-wpf-xaml.md)
