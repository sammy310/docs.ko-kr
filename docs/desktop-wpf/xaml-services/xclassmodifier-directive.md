---
title: x:ClassModifier 지시문
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433273"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 지시문
XAML 컴파일 동작도 제공된 `x:Class` 경우 수정합니다. `class` 특히 `Public` 액세스 수준(기본값)이 있는 부분을 만드는 대신 `x:Class` 제공된 `NotPublic` 액세스 수준이 생성됩니다. 이 동작은 생성된 어셈블리의 클래스에 대한 액세스 수준에 영향을 줍니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|*비공개 아님*|지정할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 정확한 문자열과 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 지정하는 문자열은 사용하는 코드 숨김 프로그래밍 언어에 따라 다릅니다. 설명 부분을 참조하세요.|

## <a name="dependencies"></a>종속성

[x:Class는](xclass-directive.md) 동일한 요소에도 제공되어야 하며 해당 요소는 페이지의 루트 요소여야 합니다. 자세한 내용은 [ \[MS-XAML\] 섹션 4.3.1.8을](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))참조하십시오.

## <a name="remarks"></a>설명

.NET `x:ClassModifier` XAML 서비스 사용의 가치는 프로그래밍 언어에 따라 다릅니다. 사용할 문자열은 각 언어가 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 언어를 구현하는 방법과 해당 언어가 반환하는 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>형식 변환기의 의미를 정의하고 해당 언어가 대/소문자를 구분하는지 여부에 따라 달라집니다.

- C#의 경우 지정할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 문자열은 `internal`입니다.

- Microsoft Visual Basic .NET의 경우 지정할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 문자열은 `Friend`.

- C++/CLI의 경우 XAML 컴파일을 지원하는 대상이 없습니다. 따라서 전달할 값은 지정되지 않습니다.

(C#에서 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public` `Public` 시각적 기본)을 지정할 수도 있습니다. 그러나 이미 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 기본 동작이기 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 때문에 지정하는 작업은 자주 수행되지 않습니다.

C#과 같이 `private` 동일한 사용자 코드 액세스 수준 제한이 있는 다른 `x:ClassModifier` 값은 중첩된 클래스 참조가 XAML에서 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 지원되지 않으므로 수정자는 동일한 효과를 가지므로 관련이 없습니다.

## <a name="security-notes"></a>보안 정보

에 `x:ClassModifier` 선언된 액세스 수준은 여전히 특정 프레임워크 및 해당 기능에 의해 해석될 수 있습니다. WPF에는 해당 클래스가 WPF 리소스에서 `internal`팩 URI 참조를 통해 참조되는 경우 형식을 `x:ClassModifier` 로드하고 인스턴스화하는 기능이 포함되어 있습니다. 이 사례와 다른 프레임워크에서 구현한 것과 같은 잠재적으로 다른 작업의 결과로 `x:ClassModifier` 가능한 모든 인스턴스화 시도를 차단하는 데만 의존하지 마십시오.

## <a name="see-also"></a>참조

- [x:Class 지시문](xclass-directive.md)
- [WPF의 코드 숨김 및 XAML](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:FieldModifier 지시문](xfieldmodifier-directive.md)
- [보안(WPF)](../../framework/wpf/security-wpf.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
