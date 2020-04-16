---
title: x:Class 지시문
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: f589fa70c2ee1c56544fa0f0152990478aa3761f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433279"
---
# <a name="xclass-directive"></a>x:Class 지시문
XAML 태그 컴파일을 구성하여 태그와 코드 숨결 사이의 부분 클래스를 조인합니다. 코드 부분 클래스는 공통 언어 사양(CLS) 언어의 별도 코드 파일에 정의되는 반면 태그 부분 클래스는 일반적으로 XAML 컴파일 중에 코드 생성에 의해 만들어집니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a>XAML 값

|||
|-|-|
|`namespace`|(선택 사항) 에서 식별된 부분 클래스를 포함하는 CLR `classname`네임스페이스를 지정합니다. `namespace` 지정하면 점(.)이 `namespace` 분리되고 `classname`. 설명 부분을 참조하세요.|
|`classname`|필수 사항입니다. 로드된 XAML및 해당 XAML에 대한 코드 숨미를 연결하는 부분 클래스의 CLR 이름을 지정합니다.|

## <a name="dependencies"></a>종속성

`x:Class`XAML 프로덕션의 루트 요소에만 지정할 수 있습니다. `x:Class`XAML 프로덕션에 부모가 있는 개체에서 유효하지 않습니다. 자세한 내용은 [ \[MS-XAML\] 섹션 4.3.1.6을](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))참조하십시오.

## <a name="remarks"></a>설명

이 `namespace` 값에는 .NET 프로그래밍의 일반적인 기술인 이름 계층구조로 관련 네임스페이스를 구성하는 추가 점이 포함될 수 있습니다. 값 `x:Class` 문자열의 마지막 점만 구분으로 `namespace` 해석되고 `classname.` 사용되는 `x:Class` 클래스는 중첩 된 클래스가 될 수 없습니다. 중첩된 클래스가 허용되는 경우 문자열에 대한 `x:Class` 점의 의미를 결정하는 것은 모호하기 때문에 중첩된 클래스는 허용되지 않습니다.

을 `x:Class` `x:Class` 사용하는 기존 프로그래밍 모델에서는 코드 숨결이 없는 XAML 페이지를 사용하는 것이 전적으로 유효하다는 점에서 선택 사항입니다. 그러나 이 기능은 XAML을 사용하는 프레임워크에서 구현된 빌드 작업과 상호 작용합니다. `x:Class`기능은 또한 XAML 지정 콘텐츠의 다양한 분류가 응용 프로그램 모델 및 해당 빌드 작업에 있는 역할에 의해 영향을 받습니다. XAML에서 이벤트 처리 특성 값을 선언하거나 정의 클래스가 코드 숨결 클래스에 있는 사용자 지정 요소를 `x:Class` 인스턴스화하는 경우 코드 숨결에 적합한 클래스에 지시문 참조(또는 [x:Subclass)를](xsubclass-directive.md)제공해야 합니다.

`x:Class` 지시문 값은 클래스의 정규화된 이름을 지정하지만 어셈블리 정보(와 <xref:System.Type.FullName%2A?displayProperty=nameWithType>동일)가 없는 문자열이어야 합니다. 간단한 응용 프로그램의 경우 코드 숨김이 이러한 방식으로 구조화되어 있는 경우 CLR 네임스페이스 정보를 생략할 수 있습니다(코드 정의는 클래스 수준에서 시작).

페이지 또는 응용 프로그램 정의에 대한 코드 숨김 파일은 컴파일된 응용 프로그램을 생성하고 태그 컴파일을 포함하는 프로젝트의 일부로 포함된 코드 파일 내에 있어야 합니다. CLR 클래스의 이름 규칙을 따라야 합니다. 자세한 내용은 [프레임워크 디자인 지침을](../../../api/index.md)참조하십시오. 기본적으로 코드 숨결 클래스는 `public`다음과 같은 값입니다. 그러나 [x:ClassModifier 지시문을](xclassmodifier-directive.md)사용하여 다른 액세스 수준에서 정의할 수 있습니다.

이 `x:Class` 특성의 해석은 CLR 기반 XAML 구현, 특히 .NET XAML 서비스에만 적용됩니다. CLR을 기반으로 하지 않고 .NET XAML 서비스를 사용하지 않는 다른 XAML 구현은 XAML 태그를 연결하고 런타임 코드를 백업하기 위해 다른 해결 공식을 사용할 수 있습니다. 자세한 `x:Class`해석에 대한 자세한 내용은 [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))을 참조하십시오.

특정 수준의 아키텍처에서 의 `x:Class` 의미는 .NET XAML 서비스에서 정의되지 않습니다. 이는 .NET XAML 서비스가 XAML 태그 및 백업 코드가 연결된 프로그래밍 모델을 지정하지 않기 때문입니다. `x:Class` 지시문을 추가로 사용하면 프로그래밍 모델 또는 응용 프로그램 모델을 사용하여 XAML 태그 및 CLR 기반 코드 숨결을 연결하는 방법을 정의하는 특정 프레임워크에서 구현할 수 있습니다. 각 프레임워크에는 빌드 환경에 포함되어야 하는 동작 또는 특정 구성 요소 중 일부를 사용하도록 설정하는 자체 빌드 작업이 있을 수 있습니다. 프레임워크 내에서 빌드 작업은 코드 숨김에 사용되는 특정 CLR 언어에 따라 달라질 수 있습니다.

## <a name="xclass-in-the-wpf-programming-model"></a>x:WPF 프로그래밍 모델의 클래스

WPF 응용 프로그램 및 WPF `x:Class` 응용 프로그램 모델에서 XAML 파일의 루트이며 컴파일되는 모든 요소(XAML가 빌드 작업이 있는 `Page` WPF 응용 프로그램 프로젝트에 포함된 <xref:System.Windows.Application> 경우) 또는 컴파일된 WPF 응용 프로그램의 응용 프로그램 정의의 루트에 대한 특성으로 선언할 수 있습니다. 페이지 `x:Class` 루트 또는 응용 프로그램 루트가 아닌 다른 요소또는 컴파일되지 않은 WPF XAML 파일에 선언하면 .NET Framework 3.0 및 .NET Framework 3.5 WPF XAML 컴파일러에서 컴파일 타임 오류가 발생합니다. WPF에서 `x:Class` 처리하는 다른 측면에 대한 자세한 내용은 [WPF의 코드 숨미및 XAML을](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)참조하십시오.

## <a name="xclass-for-windows-workflow-foundation"></a>x:Windows 워크플로 파운데이션용 클래스
Windows 워크플로 `x:Class` 재단의 경우 XAML로 완전히 구성된 사용자 지정 활동의 클래스이름을 지정하거나 코드 숨김이 있는 활동 디자이너의 XAML 페이지의 일부 클래스 이름을 지정합니다.

## <a name="silverlight-usage-notes"></a>실버라이트 사용 노트

`x:Class`실버라이트에 대한 설명은 별도로 문서화되어 있습니다. 자세한 내용은 [XAML 네임스페이스(x:)를 참조하십시오. 언어 기능 (실버 라이트)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>참조

- [x:Subclass 지시문](xsubclass-directive.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [x:ClassModifier 지시문](xclassmodifier-directive.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
