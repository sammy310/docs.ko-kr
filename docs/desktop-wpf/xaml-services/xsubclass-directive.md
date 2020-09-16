---
title: x:Subclass 지시문
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540721"
---
# <a name="xsubclass-directive"></a>x:Subclass 지시문

가 제공 될 때 XAML 태그 컴파일 동작 `x:Class` 을 수정 합니다. 을 기반으로 하는 partial 클래스를 만드는 대신 `x:Class` 제공 된 `x:Class` 가 중간 클래스로 생성 된 다음 제공 된 파생 클래스의 기반이 될 것으로 예상 됩니다 `x:Class` .

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`namespace`|선택 사항입니다. 가 포함 된 CLR 네임 스페이스를 지정 합니다 `classname` . 을 `namespace` 지정 하면 점 (.)은 및를 `namespace` 구분 `classname` 합니다.|
|`classname`|필수 요소. 해당 XAML에 대해 로드 된 XAML 및 코드 숨김이 연결 되는 partial 클래스의 CLR 이름을 지정 합니다. 설명 부분을 참조하세요.|
|`subclassNamespace`|선택 사항입니다. `namespace`각 네임 스페이스에서 다른를 확인할 수 있는 경우와 다를 수 있습니다. 가 포함 된 CLR 네임 스페이스를 지정 합니다 `subclassName` . 을 `subclassName` 지정 하면 점 (.)은 및를 `subclassNamespace` 구분 `subclassName` 합니다.|
|`subclassName`|필수 요소. 서브 클래스의 CLR 이름을 지정 합니다.|

## <a name="dependencies"></a>종속성

[X:Class 지시문](xclass-directive.md) 도 동일한 개체에서 제공 해야 하며, 해당 개체는 XAML 프로덕션의 루트 요소 여야 합니다.

## <a name="remarks"></a>설명

`x:Subclass` 사용은 주로 partial 클래스 선언을 지원 하지 않는 언어를 위한 것입니다.

로 사용 되는 클래스는 `x:Subclass` 중첩 된 클래스가 될 수 없으며 `x:Subclass` "종속성" 섹션에 설명 된 대로 루트 개체를 참조 해야 합니다.

그렇지 않은 경우의 개념 의미는 `x:Subclass` .NET XAML 서비스 구현에서 정의 되지 않습니다. .NET XAML 서비스 동작은 XAML 태그 및 백업 코드가 연결 되는 전체 프로그래밍 모델을 지정 하지 않기 때문입니다. 및와 관련 된 추가 개념의 구현은 `x:Class` `x:Subclass` XAML 태그, 컴파일된 태그 및 CLR 기반 코드를 연결 하는 방법을 정의 하기 위해 프로그래밍 모델 또는 응용 프로그램 모델을 사용 하는 특정 프레임 워크에 의해 수행 됩니다. 각 프레임 워크에는 일부 동작이 나 빌드 환경에 포함 되어야 하는 특정 구성 요소를 사용할 수 있도록 하는 고유한 빌드 작업이 있을 수 있습니다. 프레임 워크 내에서 빌드 작업은 코드 숨김으로 사용 되는 특정 CLR 언어에 따라 달라질 수도 있습니다.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

`x:Subclass` 는 <xref:System.Windows.Application> 이미 있는 응용 프로그램 정의의 루트 또는 페이지 루트에 있을 수 있습니다 `x:Class` . `x:Subclass`페이지나 응용 프로그램 루트 이외의 요소에 선언 하거나 존재 하지 않는 요소를 지정 하면 `x:Class` 컴파일 시간 오류가 발생 합니다.

시나리오에서 제대로 작동 하는 파생 클래스를 만드는 `x:Subclass` 것은 매우 복잡 합니다. .Xaml 파일 이름을 포함 하는 이름을 사용 하 여 태그 컴파일로 프로젝트의 obj 폴더에 생성 된 중간 파일 (. g 파일)을 검사 해야 할 수도 있습니다. 이러한 중간 파일은 컴파일된 응용 프로그램에서 조인 된 partial 클래스의 특정 프로그래밍 구문에 대 한 원본을 결정 하는 데 도움이 될 수 있습니다.

`internal override` `Friend Overrides` 컴파일 중에 중간 클래스에서 만든 처리기의 스텁을 재정의 하려면 파생 클래스의 이벤트 처리기가 (Microsoft Visual Basic) 여야 합니다. 그렇지 않으면 파생 클래스 구현에서 중간 클래스 구현을 숨기고 중간 클래스 처리기가 호출 되지 않습니다.

및를 둘 다 정의 하는 경우 `x:Class` `x:Subclass` 에서 참조 하는 클래스에 대 한 구현을 제공할 필요가 없습니다 `x:Class` . `x:Class`컴파일러가 중간 파일에 만드는 클래스에 대 한 몇 가지 지침을 포함 하도록 특성을 통해 이름을 지정 하기만 하면 됩니다. 컴파일러는이 경우 기본 이름을 선택 하지 않습니다. 클래스에 구현을 제공할 수 있지만 `x:Class` 및를 모두 사용 하는 일반적인 시나리오는 아닙니다. `x:Class` `x:Subclass`

## <a name="see-also"></a>참조

- [x:Class 지시문](xclass-directive.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
