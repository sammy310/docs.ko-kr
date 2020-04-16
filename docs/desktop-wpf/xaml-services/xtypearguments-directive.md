---
title: x:TypeArguments 지시문
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432631"
---
# <a name="xtypearguments-directive"></a>x:TypeArguments 지시문

제네릭의 형식 인수를 제네릭 형식의 생성자에게 전달합니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`object`|CLR 제네릭 형식에 의해 뒷받침되는 XAML 형식의 개체 요소 선언입니다. 기본 `object` XAML 네임스페이스에 없는 XAML 형식을 참조하는 경우 XAML 네임스페이스가 `object` 있는 위치를 나타내는 접두사가 `object` 필요합니다.|
|`typeString`|하나 이상의 XAML 형식 이름을 문자열로 선언하는 문자열로, CLR 제네릭 형식에 대한 형식 인수를 제공합니다. 추가 구문 메모는 비고를 참조하십시오.|

## <a name="remarks"></a>설명

대부분의 경우 `typeString` 문자열의 정보 항목으로 사용되는 XAML 형식은 접두사입니다. 일반적인 유형의 CLR 제네릭 <xref:System.Int32> 제약 <xref:System.String>조건(예: 및)은 CLR 기본 클래스 라이브러리에서 제공됩니다. 이러한 라이브러리는 일반적인 프레임워크별 기본 XAML 네임스페이스에 매핑되지 않으므로 XAML 사용에 대한 접두사 매핑이 필요합니다.

쉼표 구분 기호를 사용하여 두 개 이상의 XAML 형식 이름을 지정할 수 있습니다.

제네릭 제약 조건 자체가 제네릭 형식을 사용하는 경우 중첩된 제약 조건 형식 인수는 괄호()에 포함될 수 있습니다.

이 `x:TypeArguments` 정의는 .NET XAML 서비스 및 CLR 백업 사용에 만 해당합니다. 언어 수준 정의는 [ \[MS-XAML\] 섹션 5.3.11에서](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))찾을 수 있습니다.

## <a name="usage-examples"></a>사용 예제

이러한 예제에서는 다음 XAML 네임스페이스 정의가 선언된다고 가정합니다.

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a>문자열\<> 나열

`<scg:List x:TypeArguments="sys:String" ...>`을 사용하면 형식 <xref:System.Collections.Generic.List%601> 인수를 사용하여 새 인수를 인스턴스화합니다. <xref:System.String>

### <a name="dictionarystringstring"></a>사전\<문자열, 문자열>

`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`두 가지 <xref:System.String> 형식 <xref:System.Collections.Generic.Dictionary%602> 인수를 사용하여 새 인수를 인스턴스화합니다.

### <a name="queuekeyvaluepairstringstring"></a>큐<키밸류페어링\<문자열, 문자열>>

`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`내부 제약 조건 <xref:System.Collections.Generic.Queue%601> 형식 인수 및 <xref:System.Collections.Generic.KeyValuePair%602> <xref:System.String>의 제약 조건이 <xref:System.String> 있는 새 를 인스턴스화합니다.

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>XAML 2006 및 WPF 일반 XAML 사용법

XAML 2006 사용 및 WPF 응용 프로그램에 사용되는 XAML의 경우 `x:TypeArguments` 일반적으로 XAML의 일반 형식 사용에 대해 다음과 같은 제한 사항이 있습니다.

- XAML 파일의 루트 요소만 제네릭 형식을 참조하는 제네릭 XAML 사용을 지원할 수 있습니다.

- 루트 요소는 하나 이상의 형식 인수를 가진 제네릭 형식에 매핑되어야 합니다. 예제는 <xref:System.Windows.Navigation.PageFunction%601>입니다. 페이지 함수는 WPF에서 XAML 일반 사용 지원에 대 한 기본 시나리오입니다.

- 제네릭의 루트 요소 XAML 개체 요소는 을 `x:Class`사용하여 부분 클래스를 선언해야 합니다. WPF 빌드 작업을 정의하는 경우에도 마찬가지입니다.

- `x:TypeArguments`중첩된 제네릭 제약 조건을 참조할 수 없습니다.

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>WPF 3.0 또는 WPF 3.5 종속성이 없는 XAML 2009 또는 XAML 2006

XAML 2006 또는 XAML 2009에 대한 .NET XAML 서비스에서는 일반 XAML 사용에 대한 WPF 관련 제한이 완화됩니다. 백업 형식 시스템 및 개체 모델이 지원할 수 있는 XAML 태그의 모든 위치에서 일반 개체 요소를 인스턴스화할 수 있습니다.

CLR 기본 형식을 매핑하는 대신 XAML 2009를 사용하여 공통 언어 기본 항목에 대한 XAML 형식을 가져오는 경우 [공통 XAML 언어 프리미티브에 대한 기본 제공 형식을](types-for-primitives.md) 의 정보 항목으로 사용할 수 `typeString`있습니다. 예를 들어 다음을 선언할 수 있습니다(접두사 매핑은 표시되지 않지만 x는 XAML 2009의 XAML 언어 XAML 네임스페이스입니다).

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

WPF 및 .NET Framework 4 또는 .NET Core 3.0(이상)을 대상으로 할 때XAML 2009 기능을 함께 `x:TypeArguments` 사용할 수 있지만 느슨한 XAML(마크업 컴파일되지 않은 XAML)에대해서만 사용할 수 있습니다. WPF에 대한 태그로 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다. XAML을 컴파일하는 마크업이 필요한 경우 [XAML 2006 및 WPF 일반 XAML 사용](#xaml-2006-and-wpf-generic-xaml-usages) 섹션에 명시된 제한 사항에 따라 작동해야 합니다. BAML은 .NET 프레임워크에서만 지원됩니다.

## <a name="see-also"></a>참조

- [x:Class 지시문](xclass-directive.md)
- [x:Type 태그 확장](xtype-markup-extension.md)
- [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](types-for-primitives.md)
- [XAML의 제네릭](generics.md)
