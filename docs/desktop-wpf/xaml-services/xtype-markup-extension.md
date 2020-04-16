---
title: x:Type 태그 확장
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432637"
---
# <a name="xtype-markup-extension"></a>x:Type 태그 확장

지정된 XAML 형식의 기본 형식인 CLR <xref:System.Type> 개체를 제공합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`prefix`|(선택 사항) 기본이 아닌 XAML 네임스페이스를 매핑하는 접두사입니다. 접두사를 지정할 필요는 없습니다. 설명 부분을 참조하세요.|
|`typeNameValue`|필수 사항입니다. 현재 기본 XAML 네임스페이스에 확인할 수 있는 형식 이름; 또는 제공된 경우 `prefix` 지정된 매핑된 접두사입니다.|

## <a name="remarks"></a>설명

`x:Type` 태그 확장은 C# 연산자 또는 Microsoft Visual Basic의 `typeof()` `GetType` 연산자와 유사한 기능을 가지고 있습니다.

태그 `x:Type` 확장 형식은 형식을 <xref:System.Type>취하는 속성에 대해 문자열 변환 동작을 제공합니다. 입력은 XAML 유형입니다. 입력 XAML 형식과 출력 <xref:System.Type> CLR 간의 관계는 <xref:System.Type> XAML 스키마 컨텍스트와 컨텍스트가 제공하는 <xref:System.Xaml.XamlType.UnderlyingType%2A> <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlType> <xref:System.Windows.Markup.IXamlTypeResolver> 서비스를 기반으로 필요한 것을 찾은 후 출력이 입력의 출력이라는 것입니다.

.NET XAML 서비스에서 이 태그 확장에 대한 처리는 클래스에 <xref:System.Windows.Markup.TypeExtension> 의해 정의됩니다.

특정 프레임워크 구현에서 값으로 <xref:System.Type> 사용할 일부 속성은 형식의 이름(형식의 `Name`문자열 값)을 직접 수락할 수 있습니다. 그러나 이 동작을 구현하는 것은 복잡한 시나리오입니다. 예제에서는 다음의 "WPF 사용 참고 사항" 섹션을 참조하세요.

특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `x:Type` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 확장명 클래스의 <xref:System.Windows.Markup.TypeExtension> 값으로 할당됩니다. CLR 형식을 기반으로 하는 .NET XAML 서비스에 대한 기본 XAML 스키마 컨텍스트에서 이 <xref:System.Reflection.MemberInfo.Name%2A> 특성의 값은 원하는 <xref:System.Reflection.MemberInfo.Name%2A> 형식의 값이거나 기본이 아닌 XAML 네임스페이스 매핑에 대한 접두사가 앞에 오는 것을 포함합니다.

태그 `x:Type` 확장은 개체 요소 구문에서 사용할 수 있습니다. 이 경우 확장을 올바르게 초기화하려면 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 속성 값을 지정해야 합니다.

`x:Type` 태그 확장을 자세한 특성으로 사용할 수도 있습니다. 그러나 이 사용은 일반적인 것이 아닙니다.`<object property="{x:Type TypeName=typeNameValue}" .../>`

## <a name="wpf-usage-notes"></a>WPF 사용 정보

### <a name="default-xaml-namespace-and-type-mapping"></a>기본 XAML 네임스페이스 및 유형 매핑

WPF 프로그래밍의 기본 XAML 네임스페이스에는 일반적인 XAML 시나리오에 필요한 대부분의 XAML 형식이 포함되어 있습니다. 따라서 XAML 형식 값을 참조할 때 접두사를 피할 수 있습니다. 사용자 지정 어셈블리에서 형식을 참조하거나 WPF 어셈블리에 있지만 기본 XAML 네임스페이스에 매핑되지 않은 CLR 네임스페이스의 형식인 경우 접두사를 매핑해야 할 수 있습니다. 접두사, XAML 네임스페이스 및 CLR 네임스페이스 매핑에 대한 자세한 내용은 [WPF XAML에 대한 XAML 네임스페이스 및 네임스페이스 매핑을](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)참조하십시오.

### <a name="type-properties-that-support-typename-as-string"></a>문자열로 형식 이름을 지원하는 형식 속성

WPF는 <xref:System.Type> `x:Type` 태그 확장 사용을 요구하지 않고 형식의 일부 속성의 값을 지정할 수 있는 기술을 지원합니다. 대신 형식을 이름을 지정하는 문자열로 값을 지정할 수 있습니다. 이 예는 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 다음과 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>같습니다. 이 동작에 대 한 지원 형식 변환기 또는 태그 확장을 통해 제공 되지 않습니다. 대신 을 통해 <xref:System.Windows.FrameworkElementFactory>구현된 지연 동작입니다.

실버라이트는 유사한 규칙을 지원합니다. 실제로 Silverlight는 현재 XAML 언어 지원에서 지원하지 `{x:Type}` 않으며 `{x:Type}` WPF-Silverlight XAML 마이그레이션을 지원하기 위한 몇 가지 상황 이외에는 사용을 허용하지 않습니다. 따라서 문자열로 형식 이름 동작은 값이 <xref:System.Type> 되는 모든 Silverlight 네이티브 속성 평가에 기본 제공 됩니다.

## <a name="xaml-2009"></a>XAML 2009

XAML 2009는 제네릭 형식에 대한 추가 `x:TypeArguments` 지원을 `x:Type` 제공하고 기능 동작을 수정하고 이 지원을 제공합니다.

- `x:TypeArguments`일반 개체 인스턴스화에 대한 연결된 개체 요소는 루트가 아닌 다른 요소에 있을 수 있습니다. 자세한 내용은 [x:TypeArguments 지시문](xtypearguments-directive.md)에서 "XAML 2009" 섹션을 참조하십시오.

- XAML 2009는 태그에서 제네릭 형식의 제약 조건을 지정하기 위한 구문을 지원합니다. 이 기능은 `x:TypeArguments`에서 `x:Type`또는 두 기능을 조합하여 사용할 수 있습니다.

- 부하에 대한 XAML 2009를 처리할 때 WPF XAML 구현은 형식을 <xref:System.Type>사용하는 특정 프레임워크 속성에 대한 암시적 형식 변환 동작에 이 기능을 추가합니다.

WPF에서는 XAML 2009 기능을 사용할 수 있지만 느슨한 XAML(마크업 컴파일되지 않은 XAML)에만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Style>
- [스타일 지정 및 템플릿](../fundamentals/styles-templates-overview.md)
- [XAML 개요(WPF)](../fundamentals/xaml.md)
- [태그 확장명 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
