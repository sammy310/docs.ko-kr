---
title: XAML의 공백 처리
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 05f28c9115326424164b92e1b704c52bba31cf35
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432847"
---
# <a name="white-space-processing-in-xaml"></a>XAML의 공백 처리

XAML에 대한 언어 규칙은 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현에서 중요한 공백을 처리해야 한다고 명시합니다. 이 문서에서는 이러한 XAML 언어 규칙을 문서화합니다. 또한 XAML 프로세서와 직렬화를 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 위한 XAML 기록기의 구현에 의해 정의된 추가 공백 처리를 문서화합니다.

## <a name="white-space-definition"></a>공백 정의

XML과 일치하는 공백 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 문자는 공백, 줄 바영 및 탭입니다. 유니코드 값 0020, 000A 및 0009에 각각 해당합니다.

## <a name="white-space-normalization"></a>공백 정규화

기본적으로 프로세서가 파일을 처리할 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 때 다음과 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 같은 공백 정규화가 발생합니다.

1. 동아시아 문자 사이에서 줄 바꿈 문자가 제거됩니다. 이 용어의 정의에 대해서는 이 항목의 뒷부분에서 "동아시아 문자" 섹션을 참조하세요.

2. 모든 공백 문자(공백, 줄 바영, 탭)는 공백으로 변환됩니다.

3. 모든 연속 공백은 삭제되고 공백 하나로 대체됩니다.

4. 시작 태그 바로 뒤의 공백은 삭제됩니다.

5. 종료 태그 바로 앞의 공백은 삭제됩니다.

"기본값"은 [xml:space](xml-space-handling.md) 특성의 기본값으로 나타내는 상태에 해당합니다.

## <a name="white-space-in-inner-text-and-string-primitives"></a>내부 텍스트의 공백 및 문자열 프리미티브

이전 정규화 규칙은 XAML 요소 내에 있는 내부 텍스트에 적용됩니다. 정규화 후에 다음과 같이 XAML 프로세서에서는 모든 내부 텍스트를 적절한 형식으로 변환합니다.

- 속성 형식이 컬렉션이 아니지만 직접 <xref:System.Object> 형식이 아니면 XAML 프로세서에서는 형식 변환기를 사용하여 해당 형식으로 변환하려고 합니다. 여기서 변환에 실패하면 컴파일 시간 오류가 발생합니다.

- 속성 형식이 컬렉션이고 내부 텍스트가 연속(중간 요소 태그 없음)이면 내부 텍스트가 단일 <xref:System.String>으로 구문 분석됩니다. 컬렉션 형식이 <xref:System.String>을 허용할 수 없으면 이로 인해 컴파일 시간 오류가 발생합니다.

- 속성 형식이 <xref:System.Object>이면 내부 텍스트가 단일 <xref:System.String>으로 구문 분석됩니다. <xref:System.Object> 형식이 단일 개체(<xref:System.String> 등)를 의미하기 때문에, 중간 요소 태그가 있으면 이로 인해 컴파일 시간 오류가 발생합니다.

- 속성 형식이 컬렉션이고 내부 텍스트가 연속이 아니면 첫 번째 하위 문자열이 <xref:System.String> 으로 변환되고 컬렉션 항목으로 추가되고, 중간 요소가 컬렉션 항목으로 추가되고, 마지막으로 후행 하위 문자열(있는 경우)이 컬렉션에 세 번째 <xref:System.String> 항목으로 추가됩니다.

## <a name="preserving-white-space"></a>공백 보존

프로세서 공백 정규화의 영향을 받지 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 않는 최종 프레젠테이션을 위해 소스에서 공백을 보존하는 몇 가지 기술이 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]

**xml:space="보존"**: 공백 보존이 필요한 요소 수준에서 이 특성을 지정합니다. 이를 사용하면 코드 편집 애플리케이션에 의해 "pretty-print" 맞춤 요소에 시각적으로 바로 확인되는 중첩으로 추가될 수 있는 공백이 포함된 모든 공백이 유지됩니다. 그러나 해당 공백의 렌더링 여부는 포함하는 요소의 콘텐츠 모델에서 결정됩니다. 대부분의 개체 `xml:space="preserve"` 모델은 특성을 설정하는 방법에 관계없이 공백을 중요하게 간주하지 않으므로 루트 수준에서 지정하지 마십시오. `xml:space` 를 전역으로 설정하면 일부 구현에서는 XAML 처리(특히 serialization) 성능에 영향을 미칠 수 있습니다. 문자열 내에서 공백을 렌더링하거나 공백이 중요한 컬렉션인 요소 수준에서만 특성을 설정하는 것이 좋습니다.

**엔터티 및 끊김 이없는 공백**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 텍스트 개체 모델 내에 유니코드 엔터티를 배치할 수 있습니다. 비중단 공간(&\#160; UTF-8 인코딩)과 같은 전용 엔터티를 사용할 수 있습니다. 줄 바꿈하지 않는 공백 문자를 지원하는 서식 있는 텍스트 컨트롤을 사용할 수도 있습니다. 엔터티를 사용하여 들여쓰기 등의 레이아웃 특성을 시뮬레이트하는 경우 주의해야 합니다. 이는 엔터티의 런타임 출력은 패널 및 여백의 적절한 사용과 같은 일반적인 레이아웃 시스템에서 들여쓰기 결과를 생성하는 기능보다 더 많은 요소에 따라 달라지기 때문입니다. 예를 들어 엔터티는 글꼴에 매핑되고 사용자 글꼴 선택에 따라 크기가 변경될 수 있습니다.

## <a name="east-asian-characters"></a>동아시아 문자

"동아시아 문자"는 U+20000에서 U+2FFFD, U+30000에서 U+3FFFD까지의 유니코드 문자 범위 집합으로 정의됩니다. 이 하위 집합을 "한중일 한자"라고도 합니다. 자세한 내용은 <https://www.unicode.org>를 참조하세요.

## <a name="white-space-and-text-content-models"></a>공백 및 텍스트 콘텐츠 모델

실제로 공백을 보존하는 것은 가능한 모든 콘텐츠 모델의 하위 집합에 대해서만 중요합니다. 해당 하위 집합은 몇몇 형식의 singleton <xref:System.String> 형식 또는 전용 <xref:System.String> 컬렉션을 사용하거나 <xref:System.String> 과 <xref:System.Collections.IList> 또는 <xref:System.Collections.Generic.ICollection%601> 컬렉션의 기타 형식을 혼합해서 사용할 수 있는 콘텐츠 모델로 구성됩니다.

### <a name="white-space-and-text-content-models-in-wpf"></a>WPF의 공백 및 텍스트 콘텐츠 모델

설명하기 위해 이 섹션의 나머지 부분에서는 WPF에서 정의된 특정 형식을 참조합니다. 이 문서에서 설명하는 공백 처리 기능은 .NET XAML 서비스 및 WPF 모두와 관련이 있습니다. 작동 중인 동작을 확인하기 위해 일부 WPF XAML 태그를 실험하고, 개체 그래프에서 결과를 확인하고, 다시 태그로 serialize할 수 있습니다.

문자열을 사용할 수 있는 콘텐츠 모델의 경우에도 이러한 콘텐츠 모델 내의 기본 동작은 남아 있는 공백이 중요한 것으로 처리되지 않는다는 것입니다. 예를 들어 <xref:System.Windows.Controls.ListBox> <xref:System.Collections.IList>은 을 취하지만 공백(예: 각 <xref:System.Windows.Controls.ListBoxItem>공백 간의 선 배분)은 유지되지 않고 렌더링되지 않습니다. <xref:System.Windows.Controls.ListBoxItem> 항목에 대한 문자열 사이에서 줄 바꿈을 구분 기호로 사용하려는 시도가 전혀 작동하지 않으면 줄 바꿈으로 구분된 문자열은 단일 문자열 및 단일 항목으로 처리됩니다.

공백을 중요로 처리하는 컬렉션은 일반적으로 흐름 문서 모델의 일부입니다. 공백 보존 동작을 지원하는 기본 <xref:System.Windows.Documents.InlineCollection>컬렉션은 입니다. 이 컬렉션 클래스는 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>을 통해 선언됩니다. 이 특성이 발견되면 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 컬렉션 내의 공백을 중요한 것으로 처리합니다. 표시된 컬렉션 `xml:space="preserve"` 내의 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 공백과 공백의 조합은 모든 공백이 보존되고 렌더링된다는 것입니다. 앞에서 설명한 `xml:space="default"` <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 초기 공백 정규화와 공백의 조합은 특정 위치에 하나의 공백을 남기고 해당 공백이 보존되고 렌더링됩니다. 적합한 동작은 직접 결정할 수 있고 원하는 동작을 사용하려면 선택적으로 `xml:space` 를 사용해야 합니다.

또한 흐름 문서 모델에서 줄 바선을 나타내는 특정 인라인 요소는 공백 중요한 컬렉션에서도 의도적으로 여분의 공간을 도입하지 않아야 합니다. 예를 들어 <xref:System.Windows.Documents.LineBreak> 요소는 HTML에서 \<BR/> 태그와 동일한 목적을 가지며 태그의 가독성을 위해 일반적으로 a는 <xref:System.Windows.Documents.LineBreak> 작성된 줄 피드에 의해 후속 텍스트와 분리됩니다. 후속 줄의 선행 공백이 될 수 있으므로 줄 바꿈을 정규화하면 안 됩니다. 해당 동작을 활성화하기 위해 <xref:System.Windows.Documents.LineBreak> 요소에 대한 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>클래스 정의는 를 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 적용한 다음 프로세서에서 해석하여 주변의 <xref:System.Windows.Documents.LineBreak> 공백이 항상 잘립니다.

## <a name="see-also"></a>참조

- [XAML 개요(WPF)](../fundamentals/xaml.md)
- [XML 문자 엔터티 및 XAML](xml-character-entities.md)
- [xml: XAML의 공간 처리](xml-space-handling.md)
