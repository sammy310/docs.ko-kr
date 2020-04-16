---
title: '{}이스케이프 시퀀스 - 마크업 확장'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432967"
---
# <a name="-escape-sequence--markup-extension"></a>{}이스케이프 시퀀스/마크업 확장

특성 값에 대한 XAML 이스케이프 시퀀스를 제공합니다. 이스케이프 시퀀스를 사용하면 특성의 후속 값을 리터럴로 해석할 수 있습니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a>XAML 속성 요소 사용

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|*리터럴 밸류값*|이스케이프 시퀀스를 따르는 리터럴 문자열입니다. 일반적으로 이 문자열에는 열려 있거나 가까운 중괄호({ 또는 })가 포함되어 있습니다.|

## <a name="remarks"></a>설명

이스케이프{}시퀀스 ()는 열린 중괄호({)를 XAML에서 리터럴 문자로 사용할 수 있도록 사용됩니다.

XAML 판독기는 일반적으로 열린 중괄호({)를 사용하여 태그 확장의 진입점을 나타내지만 먼저 다음 문자를 확인하여 닫는 중괄호(})인지 확인합니다. 두 중괄호()가{}인접한 경우에만 이스케이프 시퀀스로 간주됩니다.

이스케이프 시퀀스가 발생하면 XAML 판독기는 문자열의 나머지 부분을 문자열로 처리해야 합니다. 그러나 이스케이프 시퀀스가 형식 변환기가 있는 멤버에 적용된 경우 XAML 작성자가 해석할 때 문자열이 형식 변환을 거칠 수 있습니다.

이스케이프 시퀀스는 태그 확장이 아니며 클래스에서 백업되지 않습니다. 그러나 XAML 판독기(사용자 지정 XAML 판독기 포함)를 준수해야 하는 규칙입니다.

따옴표(")는 이러한 방식으로 이스케이프 시퀀스로 사용할 수 없습니다. 비콘텐츠 속성에 대한 속성 값으로 따옴표를 설정해야 하는 경우 속성 요소 구문을 사용하고 따옴표를 속성 요소 내부에 문자열로 배치하거나 XML 문자 엔터티를 사용합니다. 콘텐츠 속성의 경우 따옴표는 전체 콘텐츠일 수 있습니다.

이스케이프{}시퀀스 () 는 XAML 태그 확장이 나타날 수 있는 위치에 네임스페이스 한정자를 포함해야 하는 XML 형식을 지정할 때 자주 필요합니다. 이 위치에는 XAML 특성 값의 시작과 등호(=) 직후의 태그 확장이 포함됩니다. 다음 예제에서는 XAML 특성 값의 시작 부분에 나타나는 XML 네임스페이스에 대한 이스케이프 시퀀스를 보여 주며, 이스케이프 시퀀스입니다.

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a>참조

- [XAML을 위한 형식 변환기 및 태그 확장](type-converters-and-markup-extensions.md)
- [XML 문자 엔터티 및 XAML](xml-character-entities.md)
