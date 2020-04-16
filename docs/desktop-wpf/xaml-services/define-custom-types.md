---
title: .NET XAML 서비스에서 사용할 사용자 지정 형식 정의
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: ff7e4229450e801a6d618c5141efde8cdcbef03d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433075"
---
# <a name="define-custom-types-for-use-with-net-xaml-services"></a>.NET XAML 서비스에서 사용할 사용자 지정 유형 정의

비즈니스 개체이거나 특정 프레임워크에 대한 종속성이 없는 형식인 사용자 지정 형식을 정의하는 경우 수행할 수 있는 XAML에 대한 특정 모범 사례가 있습니다. 이러한 방법을 따르는 경우 .NET XAML 서비스 및 XAML 판독기 및 XAML 작성기는 형식의 XAML 특성을 검색하고 XAML 형식 시스템을 사용하여 XAML 노드 스트림에서 적절한 표현을 제공할 수 있습니다. 이 항목에서는 형식 정의, 멤버 정의 및 형식 또는 멤버의 CLR 귀속에 대한 모범 사례에 대해 설명합니다.

## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>XAML에 대한 생성자 패턴 및 형식 정의

XAML에서 개체 요소로 인스턴스화하려면 사용자 지정 클래스가 다음 요구 사항을 충족해야 합니다.

- 사용자 지정 클래스는 공용이어야 하며 매개 변수없는 공용 생성자가 노출되어야 합니다. 구조체에 대한 자세한 내용은 다음 섹션을 참조하세요.

- 사용자 지정 클래스는 중첩된 클래스여야 합니다. 전체 이름 경로의 추가 "점"은 클래스 네임스페이스 분할을 모호하게 만들고 연결된 속성과 같은 다른 XAML 기능을 방해합니다.
개체를 개체 요소로 인스턴스화할 수 있는 경우 생성된 개체는 개체를 기본 형식으로 간주하는 모든 속성의 속성 요소 양식을 채울 수 있습니다.

값 변환기를 사용하도록 설정하는 경우에도 이러한 조건을 충족하지 않는 형식에 대한 개체 값을 제공할 수 있습니다. 자세한 내용은 [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md)합니다.

### <a name="structures"></a>구조체

구조는 항상 CLR 정의에 의해 XAML에서 구성할 수 있습니다. 이는 CLR 컴파일러가 구조에 대한 매개 변수 없는 생성자를 암시적으로 생성하기 때문입니다. 이 생성자는 모든 속성 값을 기본값으로 초기화합니다.

경우에 따라 구조물의 기본 구성 동작이 바람직하지 않습니다. 구조체가 개념적으로 값과 함수를 공용 구조체로 채우기 위한 것일 수 있습니다. 공용 구조로 포함된 값은 상호 배타적인 해석을 가질 수 있으므로 해당 속성은 설정할 수 없습니다. WPF 어휘에서 이러한 구조의 예는 <xref:System.Windows.GridLength>. 이러한 구조는 구조값값의 다른 해석 또는 모드를 만드는 문자열 규칙을 사용하여 값을 특성 형식으로 표현할 수 있도록 형식 변환기를 구현해야 합니다. 또한 구조는 비매개 변수 생성자에서 코드 생성에 대해 유사한 동작을 노출해야 합니다.

### <a name="interfaces"></a>인터페이스

인터페이스는 기본 멤버 유형으로 사용할 수 있습니다. XAML 형식 시스템은 할당 가능한 목록을 검사하고 값으로 제공되는 개체를 인터페이스에 할당할 수 있기를 기대합니다. 관련 할당 가능한 형식이 XAML 구성 요구 사항을 지원하는 한 인터페이스를 XAML 유형으로 표시해야 하는 방법에 대한 개념은 없습니다.

### <a name="factory-methods"></a>공장 방법

팩토리 방법은 XAML 2009 기능입니다. 개체에 매개 변수 없는 생성자가 있어야 하는 XAML 원칙을 수정합니다. 팩터리 메서드는 이 문서에서 설명하지 않습니다. [참조 x:FactoryMethod 지시문](xfactorymethod-directive.md).

## <a name="enumerations"></a>열거형

열거형에는 XAML 네이티브 형식 변환 동작이 있습니다. XAML에 지정된 열거 상 이름은 기본 열거형 유형에 대해 확인되고 열거 형 값을 XAML 개체 작성기에 반환합니다.

XAML은 <xref:System.FlagsAttribute> 적용된 열거형에 대한 플래그 스타일 사용을 지원합니다. 자세한 내용은 [XAML 구문 세부 정보를](../../framework/wpf/advanced/xaml-syntax-in-detail.md)참조하십시오. [(XAML 구문 세부 정보는](../../framework/wpf/advanced/xaml-syntax-in-detail.md) WPF 대상을 위해 작성되지만 해당 항목의 대부분의 정보는 특정 구현 프레임워크와 관련이 없는 XAML과 관련이 있습니다.)

## <a name="member-definitions"></a>멤버 정의

형식은 XAML 사용에 대한 멤버를 정의할 수 있습니다. 형식은 특정 형식이 XAML에서 사용할 수 없는 경우에도 XAML에서 사용할 수 있는 멤버를 정의할 수 있습니다. 이는 CLR 상속으로 인해 가능합니다. 멤버를 상속하는 일부 형식이 XAML 사용을 유형으로 지원하고 멤버가 기본 형식에 대한 XAML 사용을 지원하거나 사용 가능한 네이티브 XAML 구문을 가지고 있는 한 해당 멤버는 XAML에서 사용할 수 있습니다.

### <a name="properties"></a>속성

일반적인 CLR `get` 및 접근자 패턴 및 `set` 언어에 적합한 키워드를 사용하여 속성을 공용 CLR 속성으로 정의하는 경우 XAML 형식 시스템은 <xref:System.Xaml.XamlMember> 속성에 <xref:System.Xaml.XamlMember.IsReadPublic%2A> 대해 <xref:System.Xaml.XamlMember.IsWritePublic%2A>제공된 적절한 정보를 사용하여 속성을 멤버로 보고할 수 있습니다.

특정 속성은 을 적용하여 텍스트 <xref:System.ComponentModel.TypeConverterAttribute>구문을 활성화할 수 있습니다. 자세한 내용은 [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md)합니다.

텍스트 구문이나 네이티브 XAML 변환이 없고 태그 확장 사용과 같은 추가 간접이 없는 경우 XAML 형식 시스템에서 속성 유형은<xref:System.Xaml.XamlMember.TargetType%2A> 대상 형식을 CLR 형식으로 처리하여 XAML 개체 작성기에 인스턴스를 반환할 수 있어야 합니다.

XAML 2009를 사용하는 경우 [x:참조 마크업 확장을](xreference-markup-extension.md) 사용하여 이전 고려 사항이 충족되지 않는 경우 값을 제공할 수 있습니다. 그러나 형식 정의 문제 보다 사용 문제 보다 더 많은 사용 문제입니다.

### <a name="events"></a>이벤트

이벤트를 공용 CLR 이벤트로 정의하는 경우 XAML 형식 시스템은 이벤트를 <xref:System.Xaml.XamlMember.IsEvent%2A> `true`로 멤버로 보고할 수 있습니다. 이벤트 처리기 배선은 .NET XAML 서비스 기능의 범위에 속하지 않습니다. 배선은 특정 프레임 워크 및 구현에 남아 있습니다.

### <a name="methods"></a>메서드

메서드에 대한 인라인 코드는 기본 XAML 기능이 아닙니다. 대부분의 경우 XAML에서 메서드 멤버를 직접 참조하지 않으며 XAML에서 메서드의 역할은 특정 XAML 패턴에 대한 지원을 제공하는 것입니다. [x:FactoryMethod 지시문은](xfactorymethod-directive.md) 예외입니다.

### <a name="fields"></a>필드

CLR 설계 지침은 비정적 필드를 억제합니다. 정적 필드의 경우 [x:정적 마크업 확장을](xstatic-markup-extension.md)통해서만 정적 필드 값에 액세스할 수 있습니다. 이 경우 clR 정의에서 [x:Static](xstatic-markup-extension.md) 사용에 대한 필드를 노출하기 위해 특별한 작업을 수행하지 않습니다.

## <a name="attachable-members"></a>연결 가능한 멤버

연결할 수 있는 멤버는 정의 형식의 접근자 메서드 패턴을 통해 XAML에 노출됩니다. 정의 형식 자체는 XAML을 개체로 사용할 수 있어야 할 필요가 없습니다. 실제로 일반적인 패턴은 첨부 가능한 멤버를 소유하고 관련 동작을 구현하지만 UI 표현과 같은 다른 함수를 제공하지 않는 역할을 하는 서비스 클래스를 선언하는 것입니다. 다음 섹션의 경우 자리 표시자 *PropertyName은* 연결 가능한 멤버의 이름을 나타냅니다. 해당 이름은 [XamlName 문법에서](xamlname-grammar.md)유효해야 합니다.

이러한 패턴과 형식의 다른 메서드 간의 이름 충돌에 주의해야 합니다. 패턴 중 하나와 일치하는 멤버가 있는 경우 의도하지 않은 경우에도 XAML 프로세서에서 연결할 수 있는 멤버 사용 경로로 해석할 수 있습니다.

#### <a name="the-getpropertyname-accessor"></a>GetPropertyName 접근자

접근자의 `GetPropertyName` 서명은 다음과 같은 여야 합니다.

`public static object GetPropertyName(object target)`

- 구현에서 보다 구체적인 형식으로 `target` 개체를 지정할 수 있습니다. 이 것을 사용하여 연결 가능한 멤버의 사용 범위를 넓을 수 있습니다. 의도한 범위를 벗어난 사용은 잘못된 캐스트 예외를 throw한 다음 XAML 구문 분석 오류로 인해 표시됩니다. 매개 변수 `target` 이름은 요구 사항이 아니지만 `target` 대부분의 구현에서 규칙에 의해 이름이 지정됩니다.

- 구현에서 보다 구체적인 형식으로 반환 값을 지정할 수 있습니다.

첨부 가능한 <xref:System.ComponentModel.TypeConverter> 멤버의 특성 사용에 대해 활성화된 텍스트 <xref:System.ComponentModel.TypeConverterAttribute> 구문을 지원하려면 `GetPropertyName` 접근자에 적용합니다. `get` 대신에 적용하는 것은 `set` 직관적이지 않은 것처럼 보일 수 있습니다. 그러나 이 규칙은 디자이너 시나리오에서 유용한 직렬화할 수 있는 읽기 전용 연결 가능한 멤버의 개념을 지원할 수 있습니다.

#### <a name="the-setpropertyname-accessor"></a>SetPropertyName 접근자

접근자의 `SetPropertyName` 서명은 다음과 같은 여야 합니다.

`public static void SetPropertyName(object target, object value)`

- 개체는 `target` 구현에서 보다 구체적인 유형으로 지정할 수 있으며 이전 섹션에서 설명한 것과 동일한 논리 및 결과를 사용할 수 있습니다.

- 구현에서 보다 구체적인 형식으로 `value` 개체를 지정할 수 있습니다.

이 메서드의 값은 일반적으로 특성 양식인 XAML 사용에서 들어오는 입력입니다. 특성 양식에서 텍스트 구문에 대한 값 변환기 지원이 있어야 `GetPropertyName`하며 s 접근자에 대한 특성이 있어야 합니다.

### <a name="attachable-member-stores"></a>연결 가능한 멤버 저장소

접근자 메서드는 일반적으로 연결 가능한 멤버 값을 개체 그래프에 배치하거나 개체 그래프에서 값을 검색하고 올바르게 직렬화하는 수단을 제공하기에는 충분하지 않습니다. 이 기능을 제공하려면 `target` 이전 접근자 서명의 개체가 값을 저장할 수 있어야 합니다. 저장소 메커니즘은 연결 가능한 멤버가 멤버 목록에 없는 대상에 멤버를 연결할 수 있다는 연결 가능한 멤버 원칙과 일치해야 합니다. .NET XAML 서비스는 API <xref:System.Xaml.IAttachedPropertyStore> 및 <xref:System.Xaml.AttachablePropertyServices>을 통해 연결할 수 있는 멤버 저장소에 대한 구현 기술을 제공합니다. <xref:System.Xaml.IAttachedPropertyStore>XAML 작성자가 저장소 구현을 검색하는 데 사용되며 접근자의 형식에 `target` 구현되어야 합니다. 정적 <xref:System.Xaml.AttachablePropertyServices> API는 접근자 본문 내에서 사용되며 연결 가능한 멤버를 에 <xref:System.Xaml.AttachableMemberIdentifier>의해 참조합니다.

## <a name="xaml-related-clr-attributes"></a>XAML 관련 CLR 속성

유형, 멤버 및 어셈블리를 올바르게 어트리뷰션하는 것은 XAML 형식 시스템 정보를 .NET XAML 서비스에 보고하는 데 중요합니다. 다음 중 하나가 적용되는 경우 XAML 유형 시스템 정보를 보고하는 것이 관련이 있습니다.

- .NET XAML 서비스 XAML 판독기 및 XAML 기록기를 직접 기반으로 하는 XAML 시스템에서 사용할 수 있습니다.
- 이러한 XAML 판독기 및 XAML 기록기를 기반으로 하는 XAML 활용 프레임워크를 정의하거나 사용합니다.

사용자 지정 형식의 XAML 지원과 관련된 각 XAML 관련 특성목록은 [사용자 지정 유형 및 라이브러리에 대한 XAML 관련 CLR 특성을](clr-attributes-with-custom-types-and-libraries.md)참조하십시오.

## <a name="usage"></a>사용

사용자 지정 형식을 사용하려면 태그 작성자가 사용자 지정 형식을 포함하는 어셈블리 및 CLR 네임스페이스에 대한 접두사를 매핑해야 합니다. 이 절차는 이 항목에 설명되어 있지 않습니다.

## <a name="access-level"></a>액세스 수준

XAML은 `internal` 액세스 수준이 있는 형식을 로드하고 인스턴스화하는 수단을 제공합니다. 이 기능은 사용자 코드가 자체 형식을 정의한 다음 동일한 사용자 코드 범위의 일부인 태그에서 해당 클래스를 인스턴스화할 수 있도록 제공됩니다.

WPF의 예는 사용자 코드가 UI <xref:System.Windows.Controls.UserControl> 동작을 리팩터링하는 방법으로 의도된 사용자를 정의할 때마다 이지만 `public` 액세스 수준으로 지원 클래스를 선언하여 암시할 수 있는 가능한 확장 메커니즘의 일부가 아닙니다. 백업 <xref:System.Windows.Controls.UserControl> 코드가 XAML 유형으로 `internal` 참조되는 동일한 어셈블리로 컴파일되는 경우 이러한 액세스로 선언할 수 있습니다.

완전 신뢰하에 XAML을 로드하고 <xref:System.Xaml.XamlObjectWriter>사용하는 응용 `internal` 프로그램의 경우 액세스 수준이 있는 클래스로드가 항상 활성화됩니다.

부분 신뢰하에 XAML을 로드하는 응용 프로그램의 경우 API를 <xref:System.Xaml.Permissions.XamlAccessLevel> 사용하여 액세스 수준 특성을 제어할 수 있습니다. 또한 지연 메커니즘(예: WPF 템플릿 시스템)은 액세스 수준 권한을 전파하고 최종 런타임 평가를 위해 보존할 수 있어야 합니다. 이 정보는 전달하여 내부적으로 <xref:System.Xaml.Permissions.XamlAccessLevel> 처리됩니다.

### <a name="wpf-implementation"></a>WPF 구현

WPF XAML은 BAML이 부분 신뢰하에 로드되는 부분 신뢰 액세스 <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> 모델을 사용하여 BAML 원본인 어셈블리에 대한 액세스가 제한됩니다. 지연의 경우 WPF는 액세스 수준 정보를 전달하기 위한 메커니즘으로 사용합니다. <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType>

WPF XAML 용어에서 *내부 형식은* 참조 XAML을 포함하는 동일한 어셈블리에 의해 정의된 형식입니다. 이러한 형식은 XAML 네임스페이스를 통해 매핑될 수 있으며, 이 경우 어셈블리= 매핑 부분(예: `xmlns:local="clr-namespace:WPFApplication1"`)을 의도적으로 생략할 수 있습니다. BAML이 내부 형식을 참조하고 `internal` 해당 형식에 액세스 `GeneratedInternalTypeHelper` 수준이 있는 경우 어셈블리에 대한 클래스가 생성됩니다. 을 사용하지 `GeneratedInternalTypeHelper`않으려면 액세스 수준을 `public` 사용하거나 관련 클래스를 별도의 어셈블리에 팩터링하고 해당 어셈블리를 종속으로 만들어야 합니다.

## <a name="see-also"></a>참조

- [사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성](clr-attributes-with-custom-types-and-libraries.md)
- [XAML 서비스](../../../api/index.md)
