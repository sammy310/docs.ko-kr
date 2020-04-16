---
title: XAML의 제네릭
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432961"
---
# <a name="generics-in-xaml"></a>XAML의 제네릭

구현된 <xref:System.Xaml?displayProperty=fullName> .NET XAML 서비스는 제네릭 CLR 형식을 사용할 수 있는 지원을 제공합니다. 이 지원에는 제네릭의 제약 조건을 형식 인수로 지정하고 제네릭 컬렉션 사례에 적합한 `Add` 메서드를 호출하여 제약 조건을 적용하는 것이 포함됩니다. 이 항목에서는 XAML에서 제네릭 형식을 사용하고 참조하는 측면에 대해 설명합니다.

## <a name="xtypearguments"></a>x:타자 인수

`x:TypeArguments`은 XAML 언어로 정의된 지시문입니다. 제네릭 형식에 의해 지원되는 XAML 형식의 멤버로 `x:TypeArguments` 사용되는 경우 제네릭의 제한 형식 인수를 백업 생성자로 전달합니다. 구문 예제를 포함하는 .NET XAML 서비스 사용과 `x:TypeArguments`관련된 참조 구문은 [x:TypeArguments 지시문을](xtypearguments-directive.md)참조하십시오.

문자열을 사용 하 고 형식 변환기 백업을 사용 하기 때문에 `x:TypeArguments` 일반적으로 XAML 사용에서 특성으로 선언 됩니다.

XAML 노드 스트림에서, 선언된 `x:TypeArguments` 정보는 노드 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 스트림의 `StartObject` 위치에서 얻을 수 있다. 반환 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> 값은 <xref:System.Xaml.XamlType> 값 목록입니다. XAML 형식이 제네릭 형식을 나타내는지 여부를 <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>결정하는 것은 을 호출하여 만들 수 있습니다.

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a>XAML의 제네릭에 대한 규칙 및 구문 규칙

XAML에서 제네릭 형식은 항상 제한된 제네릭으로 표시되어야 합니다. 제한되지 않은 제네릭은 XAML 형식 시스템 또는 XAML 노드 스트림에 존재하지 않으며 XAML 태그에 나타낼 수 없습니다. 제네릭은 에 의해 `x:TypeArguments`참조되는 제네릭의 중첩 형식 제약 조건인 경우 또는 제네릭 `x:Type` 형식에 대한 CLR 형식 참조를 제공하는 경우에 대해 XAML 특성 구문 내에서 참조할 수 있습니다. 제네릭 참조는 .NET <xref:System.Xaml.Schema.XamlTypeTypeConverter> XAML 서비스에서 정의한 클래스를 통해 지원됩니다.

제네릭의 형식 및 제약 <xref:System.Xaml.Schema.XamlTypeTypeConverter> 조건에 대해 각도 대괄호를 사용하는 일반적인 MSIL/CLR 구문 규칙을 변경하고 대신 제약 조건 컨테이너에 대한 괄호를 대체하는 XAML 특성 구문 양식입니다. 예를 들어 [x:TypeArguments 지시문을](xtypearguments-directive.md)참조하십시오.

## <a name="generics-and-xaml-2009-features"></a>제네릭 및 XAML 2009 기능

CLR 기본 형식을 매핑하는 대신 XAML 2009를 사용하여 공통 언어 기본 항목에 대한 XAML 형식을 가져오는 경우 [XAML 2009 기본](types-for-primitives.md) 제공 형식을 정보 항목으로 사용할 수 `x:TypeArguments`있습니다. 예를 들어 다음을 선언할 수 있습니다(접두사 `x` 매핑은 표시되지 않지만 XAML 2009의 XAML 언어 XAML 네임스페이스는).

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a>WPF의 제네릭 지원

WPF를 구체적으로 대상으로 삼을 때 XAML 2006 사용의 경우 `x:TypeArguments` [x:Class도](xclass-directive.md) 와 동일한 요소에 제공되어야 하며 해당 요소는 XAML 문서의 루트 요소여야 합니다. 루트 요소는 하나 이상의 형식 인수를 가진 제네릭 형식에 매핑되어야 합니다. 예제는 <xref:System.Windows.Navigation.PageFunction%601>입니다.

제네릭 사용을 지원하는 가능한 해결 방법으로는 제네릭 형식을 반환할 수 있는 사용자 지정 태그 확장 정의 또는 제네릭 형식에서 파생되지만 자체 클래스 정의에서 제네릭 제약 조건을 병합하는 래핑 클래스 정의 제공등이 있습니다.

WPF에서는 XAML 2009 기능을 함께 `x:TypeArguments`사용할 수 있지만 느슨한 XAML(마크업 컴파일되지 않은 XAML)에만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.

.NET Framework 3.5에 대한 Windows 워크플로 재단의 사용자 지정 워크플로는 일반 XAML 사용을 지원하지 않습니다.

## <a name="see-also"></a>참조

- [x:TypeArguments 지시문](xtypearguments-directive.md)
- [x:Class 지시문](xclass-directive.md)
- [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](types-for-primitives.md)
