---
title: x:Null 태그 확장명
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432697"
---
# <a name="xnull-markup-extension"></a>x:Null 태그 확장명

XAML `null` 멤버에 대한 값으로 지정합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a>설명

C# 및 C++에서 null 참조의 키워드는 null입니다. null 참조에 대한 Microsoft Visual `Nothing`Basic 키워드는 `{x:Null}` , 항상 XAML과 연관된 코드 숨바귀 언어에 관계없이 XAML 사용법으로 사용합니다.

`x:Null` 태그 확장에는 설정 가능한 속성이 없습니다.

null 사용은 종종 CLR <xref:System.Nullable%601> 값의 XAML 멤버 노출과 관련이 있습니다.

모든 `x:Null` XAML 태그 확장과 마찬가지로 태그 확장은 문자`{,}`값 처리를 리터럴 또는 이벤트 처리기 참조 가 아닌 다른 것으로 이스케이프하기 위해 중괄호()를 사용합니다. 특성 구문은 이 태그 확장에 가장 자주 사용되는 구문입니다. 개체 요소 구문은 `<x:Null />` 기술적으로 가능하지만 `x:Null` 태그 확장에 위치 매개 변수 또는 구성 인수가 없기 때문에 거의 사용되지 않습니다.

마크업 확장에 대한 자세한 내용은 [마크업 확장 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하십시오.

.NET XAML 서비스에서 이 태그 확장에 대한 처리는 클래스에 <xref:System.Windows.Markup.NullExtension> 의해 정의됩니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

`null` 참조 형식 종속성 속성의 초기 설정 되지 않은 값은 아닙니다. 초기 기본값은 각 종속성 속성에 따라 다를 수 있으며 속성별 메타데이터를 기반으로 할 수 있습니다. 많은 종속성 속성은 `null` 유효성 검사 콜백 구현으로 인해 태그 또는 코드를 통해 값으로 허용하지 않습니다. 종속성 속성에 대한 자세한 내용은 [종속성 속성 개요를](../../framework/wpf/advanced/dependency-properties-overview.md)참조하십시오.

## <a name="see-also"></a>참조

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [XAML 개요(WPF)](../fundamentals/xaml.md)
- [태그 확장명 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
