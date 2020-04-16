---
title: x:Reference 태그 확장
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432655"
---
# <a name="xreference-markup-extension"></a>x:Reference 태그 확장

XAML 태그의 다른 위치에 선언된 인스턴스를 참조합니다. 참조는 요소의 을 `x:Name`참조합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`instancexName`|참조된 인스턴스의 `x:Name` 값(또는 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified 속성의 값)입니다.|

## <a name="remarks"></a>설명

`x:Reference`는 WPF와 같은 특정 프레임워크에서 구현된 요소 참조 개념에 대한 XAML 언어 수준 지원을 제공합니다.

## <a name="xreference-and-wpf"></a>x:참조 및 WPF

WPF 및 XAML 2006에서 요소 참조는 바인딩의 <xref:System.Windows.Data.Binding.ElementName%2A> 프레임워크 수준 기능에 의해 해결됩니다. 대부분의 WPF 응용 프로그램 <xref:System.Windows.Data.Binding.ElementName%2A> 및 시나리오에서 바인딩은 계속 사용해야 합니다. 이 일반 지침의 예외에는 데이터 바인딩을 비실용적으로 만드는 데이터 컨텍스트 또는 기타 범위 지정 고려 사항이 있는 경우와 태그 컴파일이 포함되지 않은 경우가 포함될 수 있습니다.

`x:Reference`는 XAML 2009에 정의된 구문입니다. WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일된 XAML에만 사용할 수 있습니다. 태그 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.
