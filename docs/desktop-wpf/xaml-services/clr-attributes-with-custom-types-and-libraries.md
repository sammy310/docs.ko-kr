---
title: 사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432985"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성

이 항목에서는 .NET XAML 서비스에서 정의하는 CLR(공통 언어 런타임) 특성에 대해 설명합니다. 또한 어셈블리 또는 형식에 대한 응용 프로그램에 대한 XAML 관련 시나리오가 있는 .NET에 정의된 다른 CLR 특성에 대해서도 설명합니다. 이러한 CLR 특성을 사용하여 어셈블리, 형식 또는 멤버를 어트리뷰션하면 형식과 관련된 XAML 형식 시스템 정보를 제공합니다. 정보는 직접 또는 전용 XAML 판독기 및 XAML 기록기를 통해 XAML 노드 스트림을 처리하기 위해 .NET XAML 서비스를 사용하는 모든 XAML 소비자에게 제공됩니다.

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>사용자 지정 형식 및 사용자 지정 멤버에 대한 XAML 관련 CLR 특성

CLR 특성을 사용하면 전체 CLR을 사용하여 형식을 정의하는 것이 수반되며 그렇지 않으면 이러한 특성을 사용할 수 없습니다. CLR을 사용하여 형식 백업을 정의하는 경우 .NET XAML 서비스 XAML 작성자가 사용하는 기본 XAML 스키마 컨텍스트는 백업 어셈블리에 대한 리플렉션을 통해 CLR 기여도를 읽을 수 있습니다.

다음 섹션에서는 사용자 지정 형식 또는 사용자 지정 멤버에 적용할 수 있는 XAML 관련 특성에 대해 설명합니다. 각 CLR 특성은 XAML 형식 시스템과 관련된 정보를 전달합니다. 로드 경로에서 특성정보는 XAML 판독기가 유효한 XAML 노드 스트림을 형성하는 데 도움이 되거나 XAML 작성기가 유효한 개체 그래프를 생성하는 데 도움이 됩니다. 저장 경로에서 특성 정보는 XAML 판독기가 XAML 형식 시스템 정보를 재구성하는 유효한 XAML 노드 스트림을 형성하는 데 도움이 됩니다. 또는 XAML 기록기 또는 기타 XAML 소비자에 대한 직렬화 힌트 또는 요구 사항을 선언합니다.

### <a name="ambientattribute"></a>앰비언트 특성

**참조 문서:**<xref:System.Windows.Markup.AmbientAttribute>

**다음에 적용됩니다.** 첨부 가능한 속성을 `get` 지원하는 클래스, 속성 또는 접근자 멤버입니다.

**인수:** 없음

<xref:System.Windows.Markup.AmbientAttribute>는 속성 또는 특성 형식을 취하는 모든 속성이 XAML의 주변 속성 개념에 따라 해석되어야 음을 나타냅니다. 앰비언트 개념은 XAML 프로세서가 멤버의 형식 소유자를 결정하는 방법과 관련됩니다. 앰비언트 속성은 개체 그래프를 만들 때 파서 컨텍스트에서 값을 사용할 수 있어야 하지만 생성되는 즉시 XAML 노드 집합에 대해 일반적인 형식 멤버 조회가 일시 중단되는 속성입니다.

주변 개념은 CLR 기여가 정의하는 방식에서 속성으로 표현되지 않는 연결 가능한 멤버에 적용할 <xref:System.AttributeTargets>수 있습니다. 메서드 기여 사용은 XAML에 대한 첨부 `get` 가능한 사용을 지원하는 접근자에 대해서만 적용되어야 합니다.

### <a name="constructorargumentattribute"></a>생성자 인수 특성

**참조 문서:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 단일 생성자 인수와 일치하는 속성의 이름을 지정하는 문자열입니다.

<xref:System.Windows.Markup.ConstructorArgumentAttribute>매개 변수가 없는 생성자 구문을 사용하여 개체를 초기화할 수 있고 지정된 이름의 속성이 구성 정보를 제공한다고 지정합니다. 이 정보는 주로 XAML serialization용입니다. 자세한 내용은 <xref:System.Windows.Markup.ConstructorArgumentAttribute>를 참조하세요.

### <a name="contentpropertyattribute"></a>콘텐츠속성 속성

**참조 문서:**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 특성이 있는 형식의 멤버 이름을 지정하는 문자열입니다.

<xref:System.Windows.Markup.ContentPropertyAttribute>는 인수에 의해 명명 된 속성이 해당 형식에 대한 XAML 콘텐츠 속성으로 제공되어야 한다는 것을 나타냅니다. XAML 콘텐츠 속성 정의 정의 형식에 할당할 수 있는 모든 파생 된 형식에 상속 합니다. 특정 파생 형식에 적용하여 <xref:System.Windows.Markup.ContentPropertyAttribute> 특정 파생 형식에 대한 정의를 재정의할 수 있습니다.

XAML 콘텐츠 속성 역할을 하는 속성의 경우 속성에 대한 속성 요소 태그 지정은 XAML 사용에서 생략할 수 있습니다. 일반적으로 콘텐츠 및 제약 모델에 대해 간소화된 XAML 태그를 승격하는 XAML 콘텐츠 속성을 지정합니다. 한 멤버만 XAML 콘텐츠 속성으로 지정할 수 있으므로 형식의 여러 컨테이너 속성 중 어떤 것을 XAML 콘텐츠 속성으로 지정해야 하는지 에 대해 선택할 수 있는 디자인이 있는 경우가 있습니다. 다른 컨테이너 속성은 명시적 속성 요소와 함께 사용해야 합니다.

XAML 노드 스트림에서 XAML 콘텐츠 `StartMember` 속성은 여전히 에 대한 속성 의 이름을 사용하여 생성 및 `EndMember` 노드를 <xref:System.Xaml.XamlMember>생성합니다. 멤버가 XAML 콘텐츠 속성인지 여부를 확인하려면 <xref:System.Xaml.XamlType> `StartObject` 위치에서 값을 검사하고 <xref:System.Xaml.XamlType.ContentProperty%2A>의 값을 가져옵니다.

### <a name="contentwrapperattribute"></a>콘텐츠래퍼속성

**참조 문서:**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**다음에 적용됩니다.** 클래스, 특히 컬렉션 형식입니다.

**인수:** 외부 <xref:System.Type> 콘텐츠의 콘텐츠 래퍼 유형으로 사용할 형식을 지정하는 A입니다.

<xref:System.Windows.Markup.ContentWrapperAttribute>외부 콘텐츠를 래핑하는 데 사용할 관련 컬렉션 형식에 하나 이상의 형식을 지정합니다. 외부 콘텐츠는 콘텐츠 속성형식에 대한 형식 시스템 제약 조건이 소유 형식에 대한 XAML 사용이 지원하는 가능한 모든 콘텐츠 사례를 캡처하지 않는 경우를 말합니다. 예를 들어 특정 형식의 콘텐츠에 대한 XAML 지원은 강력하게 <xref:System.Collections.ObjectModel.Collection%601>형식이 있는 제네릭의 문자열을 지원할 수 있습니다. 콘텐츠 래퍼는 텍스트 관련 콘텐츠 모델 마이그레이션과 같은 컬렉션에 할당 가능한 값의 XAML 개념으로 기존 태그 규칙을 마이그레이션하는 데 유용합니다.

두 개 이상의 콘텐츠 래퍼 유형을 지정하려면 특성을 여러 번 적용합니다.

### <a name="dependsonattribute"></a>종속 속성

**참조 문서:**  <xref:System.Windows.Markup.DependsOnAttribute>

**다음에 적용됩니다.** 속성

**인수:** 특성이 있는 형식의 다른 멤버의 이름을 지정하는 문자열입니다.

<xref:System.Windows.Markup.DependsOnAttribute>는 특성 속성이 다른 속성의 값에 종속되어 있음을 나타냅니다. 속성 정의에 이 특성을 적용하면 종속 속성이 XAML 개체 쓰기에서 먼저 처리됩니다. 유효한 개체 <xref:System.Windows.Markup.DependsOnAttribute> 를 만들기 위해 특정 구문 분석 순서를 따라야 하는 형식에 속성의 예외적인 경우를 지정 하는 사용 법입니다.

속성 정의에 <xref:System.Windows.Markup.DependsOnAttribute> 여러 사례를 적용할 수 있습니다.

### <a name="markupextensionreturntypeattribute"></a>마크업익스텐션리턴트특성

**참조 문서:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**다음에 적용됩니다.** <xref:System.Windows.Markup.MarkupExtension> 파생 된 형식이 될 것으로 예상 되는 클래스입니다.

**인수:** 특성의 <xref:System.Type> `ProvideValue` 결과로 기대할 수 있는 가장 정확한 형식을 지정하는 <xref:System.Windows.Markup.MarkupExtension>A.

자세한 내용은 [XAML 개요에 대한 마크업 확장을](markup-extensions-overview.md)참조하십시오.

### <a name="namescopepropertyattribute"></a>네임스코프속성속성

**참조 문서:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 두 가지 형태의 기여를 지원합니다.

- 특성형식의 속성 이름을 지정하는 문자열입니다.

- 속성의 이름을 지정하는 문자열과 명명된 <xref:System.Type> 속성을 정의하는 형식에 대한 문자열입니다. 이 양식은 연결할 수 있는 멤버를 XAML 네임스코프 속성으로 지정하기 위한 것입니다.

<xref:System.Windows.Markup.NameScopePropertyAttribute>특성이 있는 클래스에 대한 XAML 네임스코프 값을 제공하는 속성을 지정합니다. XAML namescope 속성은 실제 XAML <xref:System.Windows.Markup.INameScope> 네임스코프, 해당 저장소 및 해당 동작을 구현하고 보유하는 개체를 참조해야 합니다.

### <a name="runtimenamepropertyattribute"></a>런타임네임속성속성

**참조 문서:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 특성형식의 런타임 name 속성의 이름을 지정하는 문자열입니다.

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>XAML [x:Name 지시문에](xname-directive.md)매핑되는 특성 형식의 속성을 보고합니다. 속성은 형식이어야 <xref:System.String> 하며 읽기/쓰기여야 합니다.

정의는 정의 형식에 할당할 수 있는 모든 파생 된 형식에 상속 됩니다. 특정 파생 형식에 적용하여 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 특정 파생 형식에 대한 정의를 재정의할 수 있습니다.

### <a name="trimsurroundingwhitespaceattribute"></a>트림주변화이트스페이스속성

**참조 문서:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**다음에 적용됩니다.** 형식

**인수:** 없음.

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>공백 중요한 콘텐츠(컬렉션이 보유한 콘텐츠) 내에서 자식 요소로 나타날 수 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>있는 특정 형식에 적용됩니다. <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>저장 경로와 주로 관련이 있지만 로드 경로의 XAML 형식 시스템에서 <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>검사하여 사용할 수 있습니다. 자세한 내용은 [XAML의 공백 처리를](white-space-processing.md)참조하십시오.

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**참조 문서:**  <xref:System.ComponentModel.TypeConverterAttribute>

**다음에 적용됩니다.** 클래스, 속성, 메서드(유일한 XAML 유효한 메서드 `get` 사례는 연결 가능한 멤버를 지원하는 접근자).

**인수:** 의 <xref:System.Type> <xref:System.ComponentModel.TypeConverter>의

<xref:System.ComponentModel.TypeConverterAttribute>XAML 컨텍스트에서 사용자 <xref:System.ComponentModel.TypeConverter>지정 을 참조합니다. 이렇게 <xref:System.ComponentModel.TypeConverter> 하면 사용자 지정 형식 또는 해당 형식의 멤버에 대한 형식 변환 동작이 제공됩니다.

형식 <xref:System.ComponentModel.TypeConverterAttribute> 변환기 구현을 참조하여 형식에 특성을 적용합니다. 클래스, 구조 또는 인터페이스에서 XAML에 대한 형식 변환기를 정의할 수 있습니다. 열거형에 대한 형식 변환을 제공할 필요가 없으며 해당 변환은 기본적으로 활성화됩니다.

형식 변환기는 태그의 특성 또는 초기화 텍스트에 사용되는 문자열에서 의도한 대상 유형으로 변환할 수 있어야 합니다. 자세한 내용은 [TypeConverters 및 XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)을 참조하십시오.

형식의 모든 값에 적용하는 대신 XAML에 대한 형식 변환기 동작을 특정 속성에 설정할 수도 있습니다. 이 경우 속성 <xref:System.ComponentModel.TypeConverterAttribute> 정의(특정 `get` 정의 및 `set` 정의가 아닌 외부 정의)에 적용됩니다.

사용자 지정 연결 가능한 멤버의 XAML 사용에 대 한 형식 <xref:System.ComponentModel.TypeConverterAttribute> 변환기 동작 XAML 사용을 지 원하는 `get` 메서드 접근자에 적용 하 여 할당할 수 있습니다.

와 <xref:System.ComponentModel.TypeConverter>유사합니다 .NET <xref:System.ComponentModel.TypeConverterAttribute> XAML이 존재 하기 전에 존재 하 고 형식 변환기 모델 다른 목적을 제공 했습니다. 을 참조하고 사용하려면 <xref:System.ComponentModel.TypeConverterAttribute>완전히 자격을 갖추거나 `using` 에 <xref:System.ComponentModel>대한 설명서를 제공해야 합니다. 또한 프로젝트에 시스템 어셈블리를 포함합니다.

### <a name="uidpropertyattribute"></a>UidProperty속성

**참조 문서:**  <xref:System.Windows.Markup.UidPropertyAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 이름으로 관련 속성을 참조 하는 문자열입니다.

[x:Uid 지시문을](xuid-directive.md)별칭으로 하는 클래스의 CLR 속성을 나타냅니다.

### <a name="usableduringinitializationattribute"></a>사용 가능한 초기화특성 동안

**참조 문서:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 부울. 특성의 의도된 용도에 사용되는 경우 값을 로 `true`설정해야 합니다.

XAML 개체 그래프 를 만드는 동안 형식이 하향식으로 빌드되는지 여부를 나타냅니다. 이 개념은 프로그래밍 모델의 정의와 밀접한 관련이 있는 고급 개념입니다. 자세한 내용은 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>를 참조하세요.

### <a name="valueserializerattribute"></a>값 직렬화기특성

**참조 문서:**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**다음에 적용됩니다.** 클래스, 속성, 메서드(유일한 XAML 유효한 메서드 `get` 사례는 연결 가능한 멤버를 지원하는 접근자).

**인수:** 특성이 있는 형식 또는 특정 특성 속성의 모든 속성을 직렬화할 때 사용할 값 serializer 지원 클래스를 지정하는 A입니다. <xref:System.Type>

<xref:System.Windows.Markup.ValueSerializer>는 보다 더 많은 상태 및 컨텍스트를 필요로 <xref:System.ComponentModel.TypeConverter> 하는 값 직렬화 클래스를 지정 합니다. <xref:System.Windows.Markup.ValueSerializer>연결 가능한 멤버에 대한 정적 <xref:System.Windows.Markup.ValueSerializerAttribute> `get` 접근자 메서드에 특성을 적용하여 연결할 수 있는 멤버와 연결할 수 있습니다. 값 직렬화는 열거형, 인터페이스 및 구조에도 적용되지만 대리자에는 적용되지 않습니다.

### <a name="whitespacesignificantcollectionattribute"></a>화이트스페이스하한컬렉션속성

**참조 문서:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**다음에 적용됩니다.** 개체 요소 주위의 공백이 UI 표현에 중요할 수 있는 혼합 콘텐츠를 호스트할 것으로 예상되는 클래스, 특히 컬렉션 형식입니다.

**인수:** 없음.

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>는 컬렉션 형식이 XAML 프로세서에 의해 중요한 공백으로 처리되어야 하며, 이는 컬렉션 내에서 XAML 노드 스트림의 값 노드 구성에 영향을 미칩니다. 자세한 내용은 [XAML의 공백 처리를](white-space-processing.md)참조하십시오.

### <a name="xamldeferloadattribute"></a>XamlDefer로드특성

**참조 문서:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**다음에 적용됩니다.** 클래스, 속성입니다.

**인수:** 두 어트리뷰트 폼 형식을 문자열로 지원하거나 <xref:System.Type>. <xref:System.Windows.Markup.XamlDeferLoadAttribute>을 참조하세요.

클래스 또는 속성에 XAML에 대한 지연된 로드 사용(예: 템플릿 동작)이 있음을 나타내고 지연 동작 및 해당 대상/콘텐츠 형식을 사용하도록 설정하는 클래스를 보고합니다.

### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkup확장특성

**참조 문서:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 콜백 이름을 지정합니다.

클래스가 태그 확장을 사용하여 하나 이상의 속성에 대한 값을 제공할 수 있음을 나타내고 클래스의 모든 속성에서 태그 확장 집합 작업을 수행하기 전에 XAML 작성자가 호출해야 하는 처리기를 참조합니다.

### <a name="xamlsettypeconverterattribute"></a>XamlSetType변환기속성

**참조 문서:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 콜백 이름을 지정합니다.

클래스는 형식 변환기를 사용하여 하나 이상의 속성에 대한 값을 제공할 수 있음을 나타내고 클래스의 모든 속성에서 형식 변환기 집합 작업을 수행하기 전에 XAML 작성자가 호출해야 하는 처리기를 참조합니다.

### <a name="xmllangpropertyattribute"></a>XmlLang속성

**참조 문서:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**다음에 적용됩니다.** 클래스

**인수:** 속성 이름을 특성식에 별칭으로 지정하는 `xml:lang` 문자열입니다.

<xref:System.Windows.Markup.XmlLangPropertyAttribute>은 XML `lang` 지시문에 매핑되는 특성 형식의 속성을 보고합니다. 속성은 반드시 형식이 <xref:System.String> 아니지만 문자열에서 할당할 수 있어야 합니다(형식 변환기를 속성의 형식 또는 특정 속성과 연결하여 할당할 수 있음). 속성은 읽기/쓰기여야 합니다.

매핑 `xml:lang` 시나리오는 런타임 개체 모델이 XMLDOM을 사용하여 특별히 처리하지 않고 XML 지정 언어 정보에 액세스할 수 있도록 하는 것입니다.

정의는 정의 형식에 할당할 수 있는 모든 파생 된 형식에 상속 됩니다. 드문 시나리오이지만 특정 파생 형식에 적용하여 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 특정 파생 형식에 대한 정의를 재정의할 수 있습니다.

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>어셈블리 수준에서의 XAML 관련 CLR 특성

다음 섹션에서는 형식 또는 멤버 정의에 적용되지 않고 어셈블리에 적용되는 XAML 관련 특성에 대해 설명합니다. 이러한 특성은 XAML에서 사용할 사용자 지정 형식을 포함하는 라이브러리를 정의하는 전반적인 목표와 관련이 있습니다. 일부 특성이 반드시 XAML 노드 스트림에 직접 영향을 줄 필요는 없지만 다른 소비자가 사용할 수 있도록 노드 스트림에 전달됩니다. 정보에 대한 소비자는 XAML 네임스페이스 정보 및 관련 접두사 정보가 필요한 설계 환경 또는 직렬화 프로세스를 포함합니다. XAML 스키마 컨텍스트(.NET XAML 서비스 기본값 포함)도 이 정보를 사용합니다.

### <a name="xmlnscompatiblewithattribute"></a>Xmlns호환속성

**참조 문서:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**인수:**

- XAML 네임스페이스의 식별자를 subsume로 지정하는 문자열입니다.

- 이전 인수에서 XAML 네임스페이스를 subsume할 수 있는 XAML 네임스페이스의 식별자를 지정하는 문자열입니다.

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>XAML 네임스페이스를 다른 XAML 네임스페이스에 의해 subsumed할 수 있음을 지정합니다. 일반적으로 포함하는 XAML 네임스페이스는 미리 정의된 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>에 표시됩니다. 이 기술은 라이브러리에서 XAML 어휘를 버전화하고 이전 버전의 어휘에 대해 이전에 정의된 태그와 호환되도록 하는 데 사용할 수 있습니다.

### <a name="xmlnsdefinitionattribute"></a>Xmlns정의속성

**참조 문서:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**인수:**

- 정의할 XAML 네임스페이스의 식별자를 지정하는 문자열입니다.

- CLR 네임스페이스의 이름을 지정하는 문자열입니다. CLR 네임스페이스는 어셈블리에서 공용 형식을 정의해야 하며, CLR 네임스페이스 유형 중 하나 이상이 XAML 사용을 위해 사용되어야 합니다.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 네임스페이스와 CLR 네임스페이스 사이의 어셈블리별로 매핑을 지정한 다음 XAML 개체 작성기 또는 XAML 스키마 컨텍스트에서 형식 확인에 사용됩니다.

  어셈블리에 두 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 개 이상 적용할 수 있습니다. 이 작업은 다음과 같은 이유로 인해 수행될 수 있습니다.

- 라이브러리 디자인에는 런타임 API 액세스의 논리적 조직을 위한 여러 CLR 네임스페이스가 포함되어 있습니다. 그러나 동일한 XAML 네임스페이스를 참조하여 해당 네임스페이스의 모든 형식을 XAML로 사용할 수 있습니다. 이 경우 동일한 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값이지만 다른 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> 값을 사용하여 여러 특성을 적용합니다. 이 기능은 프레임워크 또는 응용 프로그램이 일반적인 사용에서 기본 XAML 네임스페이스로 의도하는 XAML 네임스페이스에 대한 매핑을 정의하는 경우에 특히 유용합니다.

- 라이브러리 디자인에는 여러 CLR 네임스페이스가 포함되어 있으며 해당 CLR 네임스페이스에서 형식의 사용 법 간에 의도적으로 XAML 네임스페이스를 분리할 수 있습니다.

- 어셈블리에서 CLR 네임스페이스를 정의하고 두 개 이상의 XAML 네임스페이스를 통해 액세스할 수 있도록 하려고 합니다. 이 시나리오는 동일한 코드베이스를 통해 여러 어휘를 지원할 때 발생합니다.

- 하나 이상의 CLR 네임스페이스에서 XAML 언어 지원을 정의합니다. 이 경우 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값은 이어야 `http://schemas.microsoft.com/winfx/2006/xaml`합니다.

### <a name="xmlnsprefixattribute"></a>Xmlns사전수정속성

**참조 문서:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**인수:**

- XAML 네임스페이스의 식별자를 지정하는 문자열입니다.

- 권장 접두사를 지정하는 문자열입니다.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>XAML 네임스페이스에 사용할 권장 접두사를 지정합니다. 접두사는 .NET XAML 서비스에서 <xref:System.Xaml.XamlXmlWriter>직렬화된 XAML 파일의 요소 및 특성을 작성하거나 XAML 구현 라이브러리가 XAML 편집 기능이 있는 디자인 환경과 상호 작용할 때 유용합니다.

  어셈블리에 두 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 개 이상 적용할 수 있습니다. 이 작업은 다음과 같은 이유로 인해 수행될 수 있습니다.

- 어셈블리는 두 개 이상의 XAML 네임스페이스에 대한 형식을 정의합니다. 이 경우 각 XAML 네임스페이스에 대해 서로 다른 접두사 값을 정의합니다.

- 여러 어휘를 지원하고 있으며 각 어휘와 XAML 네임스페이스에 대해 서로 다른 접두사를 사용합니다.

- 어셈블리에서 XAML 언어 지원을 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 정의하고 에 대해 `http://schemas.microsoft.com/winfx/2006/xaml` 이 경우 일반적으로 접두사를 `x`승격해야 합니다.

> [!NOTE]
> .NET XAML 서비스는 XAML 관련 특성도 <xref:System.Windows.Markup.RootNamespaceAttribute>정의합니다. 이 특성은 프로젝트 시스템 지원에 대한 어셈블리 수준 특성이며 XAML 사용자 지정 형식과는 관련이 없습니다.

## <a name="see-also"></a>참조

- <xref:System.Attribute>
- [.NET XAML 서비스에서 사용할 사용자 지정 형식 정의](define-custom-types.md)
