---
title: x:Code 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432805"
---
# <a name="xcode-intrinsic-xaml-type"></a>x:Code 내장 XAML 형식
XAML 프로덕션 내에서 코드를 배치할 수 있습니다. 이러한 코드는 XAML을 컴파일하는 모든 XAML 프로세서 구현에서 컴파일하거나 런타임에 의한 해석과 같은 나중에 사용하기 위해 XAML 프로덕션에 남아 있을 수 있습니다.

## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a>설명

XAML `x:Code` 지시문 요소 내의 코드는 여전히 일반적인 XML 네임스페이스 및 제공된 XAML 네임스페이스 내에서 해석됩니다. 따라서 일반적으로 `x:Code` `CDATA` 세그먼트 내부에 사용되는 코드를 동봉해야 합니다.

`x:Code`XAML 프로덕션의 가능한 모든 배포 메커니즘에 대해 허용되지 않습니다. 특정 프레임워크(예: WPF)에서는 코드를 컴파일해야 합니다. 다른 프레임워크에서는 `x:Code` 일반적으로 사용이 허용되지 않을 수 있습니다.

관리되는 `x:Code` 콘텐츠를 허용하는 프레임워크의 경우 콘텐츠에 `x:Code` 사용할 올바른 언어 컴파일러는 응용 프로그램을 컴파일하는 데 사용되는 포함 프로젝트의 설정 및 대상에 의해 결정됩니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

WPF내에서 `x:Code` 선언된 코드에는 다음과 같은 몇 가지 주목할 만한 제한 사항이 있습니다.

- `x:Code` 지시문 요소는 XAML 프로덕션의 루트 요소의 즉각적인 자식 요소여야 합니다.

- [x:Class 지시문은](xclass-directive.md) 부모 루트 요소에 제공되어야 합니다.

- 내에 `x:Code` 배치된 코드는 컴파일에 의해 해당 XAML 페이지에 대해 이미 생성중인 부분 클래스의 범위 내에 있도록 처리됩니다. 따라서 정의하는 모든 코드는 해당 부분 클래스의 멤버 또는 변수여야 합니다.

- 부분 클래스 내에 클래스를 중첩하는 것 외에는 추가 클래스를 정의할 수 없습니다(중첩은 허용되지만 XAML에서 중첩된 클래스를 참조할 수 없기 때문에 일반적이지는 않습니다). 기존 부분 클래스에 사용되는 네임스페이스 이외의 CLR 네임스페이스는 정의하거나 추가할 수 없습니다.

- 부분 클래스 CLR 네임스페이스 외부의 코드 엔터티에 대한 참조는 모두 정규화되어야 합니다. 선언되는 멤버가 부분 클래스 재정의 가능한 멤버에 재정의되는 경우 언어별 재정의 키워드로 지정해야 합니다. XAML에서 `x:Code` 만든 부분 클래스의 멤버와 범위 충돌에서 선언된 멤버가 컴파일러가 충돌을 보고하는 방식으로 XAML 파일을 컴파일하거나 로드할 수 없습니다.

## <a name="see-also"></a>참조

- [x:Class 지시문](xclass-directive.md)
- [WPF의 코드 숨김 및 XAML](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [XAML 개요(WPF)](../fundamentals/xaml.md)
