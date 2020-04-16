---
title: XAML의 xml:space 처리
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432703"
---
# <a name="xmlspace-handling-in-xaml"></a>XAML의 xml:space 처리

특성은 `xml:space` 개체 요소 내에서 중요한 공백 처리 동작을 선언하는 XML 정의 특성입니다. 이 동작은 선언된 `xml:space` 요소 내에 포함된 모든 콘텐츠(내부 텍스트)와 관련이 있으며 자식 요소의 범위도 지정합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object xml:space="preserve" />
```

 \- 또는-

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>설명

두 가지 `xml:space` 가능한 값을 포함하여 XAML의 특성에 `xml:space` 대한 정의는 XML에 대한 W3C 사양에 의해 "특수 특성"으로 정의된 대로 파생됩니다.

`xml:space` 특성의 기본값은 리터럴 값입니다. `"default"` 값의 `"default"`경우 또는 `xml:space` 전혀 표시되지 않는 경우 [XAML의 공백 처리](white-space-processing.md)항목에 정의된 대로 중요한 공백 구문 분석의 동작이 기본 처리입니다.

개체 요소 콘텐츠 내에서 공백을 `xml:space="preserve"` 유지하려면 해당 오브젝트 요소를 지정합니다.

대부분의 해석에서 `xml:space` 특성 효과와 특성값은 자식 요소로 범위가 조정됩니다.

XAML의 공백 처리에 대한 자세한 내용은 [XAML의 공백 처리를](white-space-processing.md)참조하십시오.

## <a name="see-also"></a>참조

- [XAML의 공백 처리](white-space-processing.md)
- [XAML 개요(WPF)](../fundamentals/xaml.md)
