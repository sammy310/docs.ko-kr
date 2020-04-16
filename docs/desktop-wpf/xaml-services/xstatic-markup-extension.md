---
title: x:Static 태그 확장
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433267"
---
# <a name="xstatic-markup-extension"></a>x:Static 태그 확장

공통 언어 사양(CLS)-규격 방식으로 정의된 모든 정적 부가가치 코드 엔터티를 참조합니다. 참조되는 정적 속성을 사용하여 XAML에서 속성값을 제공할 수 있습니다.

## <a name="xaml-attribute-usage"></a>XAML 특성 사용

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a>XAML 값

| | |
|-|-|
|`prefix`|(선택 사항) 매핑된 기본이 아닌 XAML 네임스페이스를 참조하는 접두사입니다. `prefix`기본 XAML 네임스페이스에서 오는 정적 속성을 거의 참조하지 않으므로 사용법에 명시적으로 표시됩니다. 설명 부분을 참조하세요.|
|`typeName`|필수 사항입니다. 원하는 정적 멤버를 정의하는 형식의 이름입니다.|
|`staticMemberName`|필수 사항입니다. 원하는 정적 값 멤버의 이름(상수, 정적 속성, 필드 또는 열거형 값).|

## <a name="remarks"></a>설명

참조되는 코드 엔터티는 다음 중 하나여야 합니다.

- 상수
- 정적 속성
- 필드
- 열거형 값

비정적 속성과 같은 다른 코드 엔터티를 지정하면 XAML이 태그컴파일된 경우 컴파일 타임 오류가 발생하거나 XAML 로드 타임구문 분석 예외가 발생합니다.

현재 XAML 문서의 기본 XAML 네임스페이스에 없는 정적 필드 또는 속성에 대한 참조를 만들 `x:Static` 수 있습니다. 그러나 이렇게 하려면 접두사 매핑이 필요합니다. XAML 네임스페이스는 거의 항상 XAML 문서의 루트 요소에 정의됩니다.

정적 속성에 대한 조회 작업은 기본 XAML 스키마 컨텍스트로 실행되는 경우 .NET XAML 서비스 및 XAML 판독기 및 XAML 작성기에서 수행할 수 있습니다. 이 XAML 스키마 컨텍스트는 CLR 리플렉션을 사용하여 개체 그래프 생성에 필요한 정적 값을 제공할 수 있습니다. 기본 `typeName` XAML 스키마 컨텍스트를 사용하거나 모든 기존 CLR 기반 XAML 구현 프레임워크를 사용할 때 는 기본적으로 동일한 이름이지만 지정한 것은 실제로 CLR 형식 이름이 아니라 XAML 형식 이름입니다.

속성 값의 `x:Static` 유형이 아닌 참조를 만들 때는 주의해야 합니다. XAML 처리 시퀀스에서 태그 확장에서 제공된 값은 추가 값 변환을 호출하지 않습니다. `x:Static` 참조가 텍스트 문자열을 만드는 경우에도 마찬가지이며 텍스트 문자열을 기반으로 하는 특성 값 변환은 일반적으로 해당 특정 멤버 또는 return 형식의 멤버 값에 대해 발생합니다.

특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `x:Static` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.StaticExtension.Member%2A> 확장명 클래스의 <xref:System.Windows.Markup.StaticExtension> 값으로 할당됩니다.

기술적으로 가능한 두 가지 다른 XAML 사용법이 있습니다. 그러나 이러한 사용법은 불필요하게 자세한 내용이기 때문에 덜 일반적입니다.

01. 개체 요소 구문입니다.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. 초기화 문자열에 대 한 명시적 Member 속성 특성 구문입니다.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

.NET XAML 서비스 구현에서 이 태그 확장에 대한 <xref:System.Windows.Markup.StaticExtension> 처리는 클래스에 의해 정의됩니다.

`x:Static`은 태그 확장입니다. XAML의 모든 태그 확장은 `{` `}` 해당 특성 구문의 및 문자를 사용합니다. 태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](markup-extensions-overview.md)를 참조하세요.

## <a name="wpf-usage-notes"></a>WPF 사용 정보

WPF 프로그래밍에 사용하는 기본 XAML 네임스페이스에는 많은 유용한 정적 속성이 포함되어 있지 않으며 대부분의 유용한 정적 속성에는 필요 `{x:Static}` 없이 사용을 용이하게 하는 형식 변환기와 같은 지원이 있습니다. 정적 속성의 경우 다음 중 하나가 true인 경우 XAML 네임스페이스에 대한 접두사를 매핑해야 합니다.

- WPF에 있지만 WPF()에`http://schemas.microsoft.com/winfx/2006/xaml/presentation`대한 기본 XAML 네임스페이스의 일부가 아닌 형식을 참조하는 것입니다. 이 시나리오는 을 사용하는 `x:Static`데 매우 일반적인 시나리오입니다. 예를 들어 클래스의 `x:Static` 정적 속성을 참조하기 위해 <xref:System> CLR 네임스페이스 및 mscorlib 어셈블리에 대한 <xref:System.Environment> XAML 네임스페이스 매핑이 있는 참조를 사용할 수 있습니다.

- 사용자 지정 어셈블리에서 형식을 참조하는 것입니다.

- WPF 어셈블리에 있지만 해당 형식은 WPF 기본 XAML 네임스페이스의 일부로 매핑되지 않은 CLR 네임스페이스 내에 있는 형식을 참조합니다. ClR 네임스페이스를 WPF의 기본 XAML 네임스페이스에 매핑하는 것은 다양한 WPF 어셈블리의 정의에 의해 수행됩니다(이 개념에 대한 자세한 내용은 [XAML 네임스페이스 및 WPF XAML에 대한 네임스페이스 매핑](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)참조). 매핑되지 않은 CLR 네임스페이스는 CLR 네임스페이스가 일반적으로 XAML을 위한 것이 아닌 클래스 <xref:System.Windows.Threading>정의(예: )로 구성된 클래스 정의로 구성된 경우 존재할 수 있습니다.

WPF에 접두사와 XAML 네임스페이스를 사용하는 방법에 대한 자세한 내용은 [WPF XAML에 대한 XAML 네임스페이스 및 네임스페이스 매핑을](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)참조하십시오.

## <a name="see-also"></a>참조

- [x:Type 태그 확장](xtype-markup-extension.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
