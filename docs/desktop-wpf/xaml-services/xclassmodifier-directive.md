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
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544819"
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier 지시문
가 제공 되는 경우 XAML 컴파일 동작 `x:Class` 을 수정 합니다. 특히 `class` `Public` 액세스 수준이 있는 부분 (기본값)을 만드는 대신 제공 된 `x:Class` 이 `NotPublic` 액세스 수준으로 만들어집니다. 이 동작은 생성 된 어셈블리의 클래스에 대 한 액세스 수준에 영향을 줍니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|*NotPublic*|를 사용 하 여 지정 하기 위해 전달할 정확한 문자열은 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 하는 코드 지향 프로그래밍 언어에 따라 달라 집니다. 설명 부분을 참조하세요.|

## <a name="dependencies"></a>종속성

또한 같은 요소에 [x:Class](xclass-directive.md) 를 제공 해야 하며,이 요소는 페이지의 루트 요소 여야 합니다. 자세한 내용은 [ \[ \] 4.3.1.8 섹션](/previous-versions/msp-n-p/ff650760(v=pandp.10))을 참조 하세요.

## <a name="remarks"></a>설명

`x:ClassModifier`.NET XAML 서비스 사용의 값은 프로그래밍 언어에 따라 달라 집니다. 사용할 문자열은 각 언어에서 및 <xref:System.CodeDom.Compiler.CodeDomProvider> 에 대 한 의미를 정의 하기 위해 반환 하는 형식 변환기와 해당 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 언어가 대/소문자를 구분 하는지 여부에 따라 달라 집니다.

- C #의 경우를 지정 하기 위해 전달할 문자열 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 은 `internal` 입니다.

- Microsoft Visual Basic .NET의 경우를 지정 하기 위해 전달할 문자열 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 은 `Friend` 입니다.

- C + +/CLI의 경우 XAML 컴파일을 지 원하는 대상이 없습니다. 따라서 전달할 값이 지정 되지 않습니다.

<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>( `public` C #에서는) Visual Basic를 지정할 수도 있습니다. `Public` 그러나 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 가 이미 기본 동작 이므로를 지정 하는 것은 거의 수행 되지 않습니다.

C #의 경우와 같이 동등한 사용자 코드 액세스 수준 제한이 있는 다른 값 `private` 은 `x:ClassModifier` XAML에서 중첩 된 클래스 참조가 지원 되지 않기 때문에와 관련이 없습니다. 따라서 한정자는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 동일한 효과를 가집니다.

## <a name="security-notes"></a>보안 정보

에 선언 된 액세스 수준에 `x:ClassModifier` 는 여전히 특정 프레임 워크 및 해당 기능에 대 한 해석이 적용 됩니다. WPF에는를 로드 하 고 인스턴스화할 수 있는 기능이 포함 되어 있습니다. 여기서는 `x:ClassModifier` `internal` 해당 클래스가 pack URI 참조를 통해 WPF 리소스에서 참조 되는 경우입니다. 이러한 경우와 다른 프레임 워크에서 구현 하는 것과 같은 다른 사용자에 게는에만 의존 `x:ClassModifier` 하 여 가능한 모든 인스턴스화 시도를 차단 합니다.

## <a name="see-also"></a>참조

- [x:Class 지시문](xclass-directive.md)
- [WPF의 코드 숨김 및 XAML](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [x:FieldModifier 지시문](xfieldmodifier-directive.md)
- [보안(WPF)](/dotnet/desktop/wpf/security-wpf)
- [WPF에서 System.Xaml로 마이그레이션된 형식](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
