---
title: 사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 80127bae06a90dccd204b0f2a4baef10732ade76
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58039472"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
이 항목에서는.NET Framework XAML 서비스에 정의 된 공용 언어 런타임 (CLR) 특성을 설명 합니다. 또한 응용 프로그램 어셈블리 또는 형식에 대 한 XAML 관련 시나리오는.NET Framework에 정의 된 CLR 특성 다른 설명 합니다. 이러한 CLR 특성을 사용 하 여 어셈블리, 형식 또는 멤버를 설정 하면 해당 형식과 관련 된 XAML 형식 시스템 정보를 제공 합니다. 정보는 XAML 노드 스트림에서 직접 처리 하거나 전용된 XAML 판독기 및 XAML 작성기를 통해.NET Framework XAML 서비스를 사용 하는 모든 XAML 소비자에 게 제공 됩니다.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>사용자 지정 형식 및 사용자 지정 멤버에 대 한 XAML 관련 CLR 특성  
 CLR 특성을 사용 하는 형식을 정의 하는 전체 CLR을 사용 하는, 이러한 특성을 사용할 수이 고, 그렇지 수반 합니다. CLR을 사용 하 여 백업 하는 형식을 정의 하는 경우.NET Framework XAML 서비스 XAML 작성기에서 사용 하는 기본 XAML 스키마 컨텍스트 백업 어셈블리에 대해 리플렉션을 통해 CLR 특성을 읽을 수 있습니다.  
  
 다음 섹션에서는 사용자 지정 형식 또는 사용자 지정 멤버에 적용할 수 있는 XAML 관련 특성을 설명 합니다. 각 CLR 특성 XAML 형식 시스템에 관련 된 정보를 전달 합니다. 로드 경로 정보를 특성 사용된 하는 데 도움이 XAML 판독기가 유효한 XAML 노드 스트림을 형성 또는 XAML 작성기가 유효한 개체 그래프를 생성할 수 있도록 합니다. 파일에서 경로, XAML 형식 시스템 정보를 다시 구성 하는 유효한 XAML 노드 스트림을 형성 된 XAML 판독기를 사용 하면 하나 특성 사용된 정보 또는 serialization 힌트 또는 XAML 작성기 또는 기타 XAML 소비자에 대 한 요구 사항을 선언 하는 것입니다.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **적용 대상:** 클래스, 속성 또는 `get` 접근자 멤버 연결 가능한 속성을 지원 합니다.  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.AmbientAttribute> 이 속성이 나 특성 사용된 형식을 사용 하는 모든 속성 XAML의 앰비언트 속성 개념에 따라 해석 되어야 함을 나타냅니다. 앰비언트 개념은 XAML 프로세서가 멤버의 형식 소유자를 결정하는 방법과 관련됩니다. 앰비언트 속성 값을 예상 하 하지만 일반적인 형식 멤버 조회가 바로 XAML 노드 집합을 만드는 대 한 일시 중단 되는 개체 그래프를 만들 때 파서 컨텍스트에서 사용할 수 있는 속성이입니다.  
  
 앰비언트 개념은 CLR 특성을 정의 하는 방법 측면에서 속성으로 표현 되지 않는 연결 가능한 멤버에 적용할 수 있습니다 <xref:System.AttributeTargets>합니다. 메서드 특성 사용만의 경우 적용할는 `get` 사용을 지 원하는 연결 가능한 XAML에 대 한 접근자입니다.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 단일 생성자 인수를 일치 하는 속성의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> 기본이 아닌 생성자 구문을 사용 하 여 개체를 초기화할 수 있습니다 및 지정 된 이름의 속성이 생성 정보를 제공을 지정 합니다. 이 정보는 주로 XAML serialization용입니다. 자세한 내용은 <xref:System.Windows.Markup.ConstructorArgumentAttribute>을 참조하세요.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성 사용된 형식 멤버의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> 속성 인수에 의해 명명 해야 해당 형식에 대 한 XAML 콘텐츠 속성으로 사용 될 있음을 나타냅니다. XAML 콘텐츠 속성 정의 정의 하는 형식에 할당할 수 있는 모든 파생된 형식에 상속 됩니다. 특정 파생된 형식에서 정의 적용 하 여 재정의할 수 있습니다 <xref:System.Windows.Markup.ContentPropertyAttribute> 특정 파생 형식입니다.  
  
 XAML 콘텐츠 속성으로 사용 되는 속성에 대 한 XAML 사용량에서 속성에 대 한 태그를 지정 하는 속성 요소를 생략할 수 있습니다. 일반적으로 포함 하 고 콘텐츠 모델에 대해 간소화 된 XAML 마크업을 승격 하는 XAML 콘텐츠 속성을 지정 합니다. XAML 콘텐츠 속성으로 한 명의 멤버만 지정할 수 있습니다, 되므로 경우에 따라 옵션이 있습니다 디자인 되도록는 여러 컨테이너에 대 한 형식의 속성을 XAML 콘텐츠 속성으로 지정 해야 합니다. 다른 컨테이너 속성은 명시적 속성 요소와 함께 사용 되어야 합니다.  
  
 XAML 노드 스트림의 XAML 콘텐츠 속성 여전히 생성 `StartMember` 하 고 `EndMember` 에 대 한 속성의 이름을 사용 하 여 노드를 <xref:System.Xaml.XamlMember>입니다. 멤버를 XAML 콘텐츠 속성 인지 여부를 확인 하려면 합니다 <xref:System.Xaml.XamlType> 에서 값을 `StartObject` 배치 하 고 값을 가져올 <xref:System.Xaml.XamlType.ContentProperty%2A>합니다.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **적용 대상:** 클래스, 특히 컬렉션 형식입니다.  
  
 **인수:** <xref:System.Type> 외래 콘텐츠에 대 한 콘텐츠 래퍼 형식으로 사용할 형식을 지정 하는 합니다.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> 외부 콘텐츠를 래핑할 사용 될 연결 된 컬렉션 형식에 하나 이상의 형식을 지정 합니다. 외부 콘텐츠를 콘텐츠 속성의 형식에 형식 시스템 제약 조건이 캡처하지 않으면 소유 하는 형식에 대 한 XAML 사용은 지원 가능한 콘텐츠 사례의 모든 사례를 가리킵니다. 특정 유형의 콘텐츠를 강력한 형식의 일반에서 문자열을 지원할 수 있습니다에 대 한이 XAML이 지원 되는 예를 들어 <xref:System.Collections.ObjectModel.Collection%601>합니다. 콘텐츠 래퍼는 할당 가능한 값 컬렉션의 경우 텍스트 관련 콘텐츠 모델을 마이그레이션하는 등의 XAML의 개념에 기존의 태그 규칙을 마이그레이션에 유용 합니다.  
  
 둘 이상의 콘텐츠 래퍼 형식을 지정 하려면 특성을 여러 번 적용 합니다.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **적용 대상:** 속성  
  
 **인수:** 특성 사용된 형식이 다른 멤버의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> 특성 사용된 속성이 다른 속성의 값에 따라 달라 집니다 나타냅니다. 속성 정의에이 특성을 적용 하면 종속 속성 XAML 개체에에서 먼저 처리 됩니다. 사용법 <xref:System.Windows.Markup.DependsOnAttribute> 유효한 개체 만들기에 대 한 구문 분석 하는 특정 순서를 야 합니다. 여기서 형식에서 속성의 예외적인 경우를 지정 합니다.  
  
 여러를 적용할 수 있습니다 <xref:System.Windows.Markup.DependsOnAttribute> 속성 정의 사례입니다.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **적용 대상:** 되도록 예상 되는 클래스는 <xref:System.Windows.Markup.MarkupExtension> 파생 형식입니다.  
  
 **인수:** <xref:System.Type> 로 예상 가장 정확한 형식을 지정 하는 `ProvideValue` 특성 사용의 결과 <xref:System.Windows.Markup.MarkupExtension>합니다.  
  
 자세한 내용은 [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md)합니다.  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 두 가지 형태의 attribution 지원합니다.  
  
-   특성 사용된 형식이 속성의 이름을 지정 하는 문자열입니다.  
  
-   속성의 이름을 지정 하는 문자열 및 <xref:System.Type> 명명된 된 속성을 정의 하는 형식에 대 한 합니다. 이 형식은 XAML 이름 범위 속성으로 연결 가능한 멤버를 지정 합니다.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> 특성 사용된 클래스에 대 한 XAML 이름 범위 값을 제공 하는 속성을 지정 합니다. XAML 이름 범위 속성을 구현 하는 개체를 참조 해야 합니다. <xref:System.Windows.Markup.INameScope> 실제 XAML 이름 범위, 해당 저장소 및 해당 동작을 보유 하 고 있습니다.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성 사용된 형식이 런타임 이름 속성의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> XAML에 매핑되는 특성이 지정 된 형식의 속성을 보고 [X:name 지시문](x-name-directive.md)합니다. 속성 형식 이어야 합니다 <xref:System.String> 읽기/쓰기 여야 합니다.  
  
 정의 정의 하는 형식에 할당할 수 있는 모든 파생된 형식에 상속 됩니다. 특정 파생된 형식에서 정의 적용 하 여 재정의할 수 있습니다 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 특정 파생 형식입니다.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **적용 대상:** 유형  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> 공백이 중요 한 콘텐츠 내에서 자식 요소로 표시 될 수 있는 특정 형식에 적용 됩니다 (포함 된 컬렉션에 포함 된 콘텐츠 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> 저장에 주로 관련이, 하지만 사용할 수 있는 경로가 로드 경로에서 XAML 형식 시스템에서 검사 하 여 <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>입니다. 자세한 내용은 [공백 XAML 처리](whitespace-processing-in-xaml.md)합니다.  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **참조 설명서:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **적용 대상:** 클래스, 속성, 메서드 (경우에 유효한 XAML 메서드 사례는는 `get` 연결 가능한 멤버를 지 원하는 접근자).  
  
 **인수:** <xref:System.Type>의 <xref:System.ComponentModel.TypeConverter>입니다.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> XAML 상황에 맞는 사용자 지정 참조 <xref:System.ComponentModel.TypeConverter>합니다. 이 <xref:System.ComponentModel.TypeConverter> 사용자 지정 형식 또는 해당 형식의 멤버에 대 한 형식 변환 동작을 제공 합니다.  
  
 적용 하는 <xref:System.ComponentModel.TypeConverterAttribute> 특성을 형식에 형식 변환기 구현을 참조 합니다. 클래스, 구조체 또는 인터페이스에서 XAML에 대 한 형식 변환기를 정의할 수 있습니다. 변환을 고유 하 게 사용할 수 있도록 열거형에 대 한 형식 변환을 제공할 필요가 없습니다.  
  
 형식 변환기를 사용 하 여 원하는 대상 형식에 특성 또는 초기화 텍스트 태그에 사용 되는 문자열에서 변환할 수 있어야 합니다. 자세한 내용은 [Typeconverter 및 XAML](../wpf/advanced/typeconverters-and-xaml.md)합니다.  
  
 형식의 모든 값에 적용 하는 대신 XAML에 대 한 형식 변환기 동작 특정 속성에 설정할 수도 있습니다. 적용 하는 예에서 <xref:System.ComponentModel.TypeConverterAttribute> 속성 정의에 (외부 정의 특정 없습니다 `get` 및 `set` 정의).  
  
 사용자 지정 연결 가능한 멤버의 XAML 사용에 대 한 형식 변환기 동작을 적용 하 여 할당할 수 있습니다 <xref:System.ComponentModel.TypeConverterAttribute> 에 `get` XAML 사용을 지 원하는 메서드 접근자입니다.  
  
 비슷합니다 <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> XAML 도입 되기 전에.NET Framework의 존재 및 형식 변환기 모델 기타 목적을 위해 제공 합니다. 참조 하 고 사용 하기 위해 <xref:System.ComponentModel.TypeConverterAttribute>를 완전히 정규화 하거나 제공 해야 합니다는 `using` 방침 <xref:System.ComponentModel>합니다. 프로젝트에서 시스템 어셈블리를 포함 해야 합니다.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 관련 속성 이름으로 참조 하는 문자열입니다.  
  
 별칭을 지정 하는 클래스의 CLR 속성을 나타내는 합니다 [X:uid 지시문](x-uid-directive.md)합니다.  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 부울입니다. 특성의 용도 사용 하는 경우 항상 지정 해야으로 `true`입니다.  
  
 이 형식이 XAML 개체 그래프를 만드는 동안 하향식으로 빌드되는지 여부를 나타냅니다. 고급 개념, 프로그래밍 모델의 정의 아마도 밀접 한 관련이 있는 경우 자세한 내용은 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>을 참조하세요.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **적용 대상:** 클래스, 속성, 메서드 (경우에 유효한 XAML 메서드 사례는는 `get` 연결 가능한 멤버를 지 원하는 접근자).  
  
 **인수:** <xref:System.Type> 특성이 지정 된 형식의 모든 속성을 직렬화 할 때 사용 하는 값 serializer 지원 클래스를 지정 하는 또는 특정 특성 속성을 사용 합니다.  
  
 <xref:System.Windows.Markup.ValueSerializer> 자세한 상태 및 컨텍스트를 필요로 하는 값 serialization 클래스 지정을 <xref:System.ComponentModel.TypeConverter> 않습니다. <xref:System.Windows.Markup.ValueSerializer> 적용 하 여 연결 가능한 멤버를 사용 하 여 연결할 수는 <xref:System.Windows.Markup.ValueSerializerAttribute> 정적 특성 `get` 연결 가능한 멤버에 대 한 접근자 메서드. 값 serialization도 적용 됩니다. 대리자 아니라 열거형, 인터페이스 및 구조체에 대 한 합니다.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **적용 대상:** 클래스, 특히 개체 요소 주위의 공백을 UI 표현에 중요할 수 있는 혼합된 콘텐츠를 호스트에 예상 되는 컬렉션 형식입니다.  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 컬렉션 형식을 컬렉션 내에서 XAML 노드 스트림의 값 노드 생성에 영향을 줍니다는 XAML 프로세서에서 중요 한 흰 공간으로 처리 되어야 한다는 것을 나타냅니다. 자세한 내용은 [공백 XAML 처리](whitespace-processing-in-xaml.md)합니다.  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **적용 대상:** 클래스 속성입니다.  
  
 **인수:** 지 원하는 두 가지 특성 형식을 문자열로, forms 또는 형식을로 <xref:System.Type>합니다. <xref:System.Windows.Markup.XamlDeferLoadAttribute>을 참조하세요.  
  
 클래스 또는 속성에 XAML에 대 한 지연 된 로드 사용법 (예: 템플릿 동작의 경우) 및 지연 동작 및 해당 대상/콘텐츠 형식을 지 원하는 클래스를 보고를 나타냅니다.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 콜백을 이름을 지정 합니다.  
  
 클래스 속성을 하나 이상에 대 한 값을 제공 하는 태그 확장을 사용할 수 있음을 나타내고 XAML 작성기 클래스의 모든 속성에 태그 확장 설정 작업을 수행 하기 전에 호출 해야 하는 처리기를 참조 합니다.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 콜백을 이름을 지정 합니다.  
  
 클래스 속성을 하나 이상에 대 한 값을 제공 하는 형식 변환기를 사용할 수 있음을 나타내고 XAML 작성기 클래스의 모든 속성에 형식 변환기 설정 작업을 수행 하기 전에 호출 해야 하는 처리기를 참조 합니다.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 속성 별칭의 이름을 지정 하는 문자열 `xml:lang` 특성 사용된 형식에 있습니다.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> XML에 매핑되는 특성이 지정 된 형식의 속성을 보고 `lang` 지시문입니다. 속성은 반드시 형식이 아닙니다 <xref:System.String>, 있지만 (가능 특정 속성 또는 속성의 형식과 형식 변환기를 연결 하 여) 문자열에서 할당 되어야 합니다. 속성은 읽기/쓰기 여야 합니다.  
  
 매핑 시나리오 `xml:lang` XMLDOM을 사용 하 여 특별히 처리 하지 않고는 런타임 개체 모델은 XML에서 지정한 언어 정보에 액세스할 수 있도록 합니다.  
  
 정의 정의 하는 형식에 할당할 수 있는 모든 파생된 형식에 상속 됩니다. 특정 파생된 형식에서 정의 적용 하 여 재정의할 수 있습니다 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 는 일반적인 시나리오는 파생 형식에 특정 합니다.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>어셈블리 수준에서 XAML 관련 CLR 특성  
 다음 섹션에서는 XAML 관련 형식 또는 멤버 정의에 적용 되지 않습니다 하지만 대신 어셈블리에 적용 되는 특성을 설명 합니다. 이러한 특성은 XAML에서 사용 하 여 사용자 지정 형식을 포함 하는 라이브러리를 정의 하는 전반적인 목표와 관련이 있습니다. 특성의 일부 반드시 영향을 XAML 노드 스트림에서 직접 있지만 다른 소비자가 사용할 노드 스트림에서 전달 됩니다. 정보에 대 한 소비자는 디자인 환경이 나 XAML 네임 스페이스 정보가 필요 하 고 접두사 정보를 연결 하는 serialization 프로세스를 포함 합니다. XAML 스키마 컨텍스트 (.NET Framework XAML 서비스 기본 포함)도이 정보를 사용 합니다.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **인수:**  
  
-   되더라도 XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.  
  
-   이전 인수에서 XAML 네임 스페이스를 포함할 수 있는 XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> 다른 XAML 네임 스페이스는 XAML 네임 스페이스 포함 될 수 있는지를 지정 합니다. 일반적으로 포함하는 XAML 네임스페이스는 미리 정의된 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>에 표시됩니다. 이 기술은 라이브러리 및 이전 버전의 어휘에 대해 이전에 정의 된 태그와 호환 되도록 XAML 어휘 버전 관리에 사용 합니다.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **인수:**  
  
-   XAML 네임 스페이스 정의의 식별자를 지정 하는 문자열입니다.  
  
-   CLR 네임 스페이스의 이름을 지정 하는 문자열입니다. CLR 네임 스페이스, 어셈블리의 public 형식 정의 해야 하 고 XAML 사용에 대 한 사용 해야 하는 CLR 네임 스페이스 형식 중 하나 이상이 있습니다.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 네임 스페이스 및 XAML 개체 작성기 또는 XAML 스키마 컨텍스트에서 형식 확인에 사용 되는 CLR 네임 스페이스 간 어셈블리별에 매핑을 지정 합니다.  
  
 둘 이상의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 어셈블리에 적용할 수 있습니다. 다음과 같은 이유로 모든 조합에 대해이 작업을 수행할 수 있습니다.  
  
-   런타임 API 액세스;의 논리적 구성에 대 한 여러 CLR 네임 스페이스를 포함 하는 라이브러리 디자인 그러나 동일한 XAML 네임 스페이스를 참조 하 여 XAML에서 사용할 수 있으려면 해당 네임 스페이스의 모든 형식을 해야 합니다. 이 경우, 적용 여러 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 동일한를 사용 하 여 특성 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 다른 값 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> 값입니다. 일반적으로 기본 XAML 네임 스페이스를 프레임 워크 또는 응용 프로그램 의도 XAML 네임 스페이스에 대 한 매핑을 정의 하는 경우 특히 유용 합니다.  
  
-   여러 CLR 네임 스페이스를 포함 하는 라이브러리 디자인 하 고 해당 CLR 네임 스페이스의 형식 사용 간에 의도적인 XAML 네임 스페이스 분리 하려는 키를 누릅니다.  
  
-   어셈블리의 CLR 네임 스페이스를 정의 하 고 둘 이상의 XAML 네임 스페이스를 통해 액세스할 수 있도록 하려는 키를 누릅니다. 이 시나리오는 동일한 코드 베이스를 사용 하 여 여러 개의 어휘를 지 원하는 경우에 발생 합니다.  
  
-   XAML 언어 지원 하나 이상의 CLR 네임 스페이스를 정의합니다. 이러한 경우는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값 이어야 합니다 `http://schemas.microsoft.com/winfx/2006/xaml`합니다.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **인수:**  
  
-   XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.  
  
-   권장 되는 접두사를 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 네임 스페이스는 데 권장 되는 접두사를 지정 합니다. .NET Framework XAML 서비스에서 serialize 되는 XAML 파일의 특성과 해당 요소를 작성할 때 접두사 유용 <xref:System.Xaml.XamlXmlWriter>, XAML 구현 라이브러리 XAML 디자인 환경과 상호 작용 하는 경우 편집 기능 또는 합니다.  
  
 둘 이상의 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 어셈블리에 적용할 수 있습니다. 다음과 같은 이유로 모든 조합에 대해이 작업을 수행할 수 있습니다.  
  
-   어셈블리에 둘 이상의 XAML 네임 스페이스에 대 한 형식을 정의합니다. 이 경우 각 XAML 네임 스페이스에 대 한 서로 다른 접두사 값을 정의 해야 합니다.  
  
-   여러 개의 어휘를 지 원하는 및 서로 다른 접두사를 사용 하 여 각 어휘 및 XAML 네임 스페이스에 대 한 합니다.  
  
-   XAML 언어 지원 어셈블리에서 정의 하 고 있는 한 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 에 대 한 `http://schemas.microsoft.com/winfx/2006/xaml`합니다. 이 경우 일반적으로 승격 해야 접두사 `x`합니다.  
  
> [!NOTE]
>  .NET framework XAML 서비스 XAML 관련 특성 정의 <xref:System.Windows.Markup.RootNamespaceAttribute>합니다. 이 특성은 프로젝트 시스템 지원에 대 한 어셈블리 수준 특성 및 관련이 없는 XAML 사용자 지정 형식에 대 한 합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Attribute>
- [.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의](defining-custom-types-for-use-with-net-framework-xaml-services.md)
