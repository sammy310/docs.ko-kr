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
ms.openlocfilehash: 3da2f6afc7e7ecf20c91f0badca38bc26083d3ae
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295712"
---
# <a name="xstatic-markup-extension"></a>x:Static 태그 확장
에 정의 된 모든 값으로 정적 코드 엔터티 참조는 [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– 호환 방식으로 합니다. 참조 되는 정적 속성 XAML에서 속성 값을 제공 하기 사용할 수 있습니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
| | |  
|-|-|  
|`prefix`|선택 사항입니다. 매핑된, 기본이 아닌 XAML 네임 스페이스를 참조 하는 접두사입니다. `prefix` 명시적으로 표시 사용의 기본 XAML 네임 스페이스에서 제공 하는 정적 속성을 거의 참조 하지 않기 때문입니다. 설명 부분을 참조하세요.|  
|`typeName`|필수 요소. 원하는 정적 멤버를 정의 하는 형식의 이름입니다.|  
|`staticMemberName`|필수 요소. 원하는 정적 값 멤버 (상수, 정적 속성, 필드 또는 열거형 값)의 이름입니다.|  
  
## <a name="remarks"></a>설명  

참조 되는 코드 엔터티 중 하나 여야 합니다.  
  
-   상수  
-   정적 속성  
-   필드  
-   열거형 값

비정적 속성을 같은 기타 코드 엔터티를 지정 하면 인지는 XAML 태그 컴파일된 XAML 로드 타임 구문 분석 예외를 컴파일 타임 오류가 발생 합니다.  

하지만 가능 `x:Static` 정적 필드 또는 현재 XAML 문서에 대 한 기본 XAML 네임 스페이스에 없는 속성에 대 한 참조에이 접두사 매핑이 필요 합니다. XAML 네임 스페이스는 거의 항상 XAML 문서의 루트 요소에 정의 됩니다.  

기본 XAML 스키마 컨텍스트를 사용 하 여 실행 될 때.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기에서 정적 속성에 대 한 조회 작업을 수행할 수 있습니다. 이 XAML 스키마 컨텍스트 CLR 리플렉션을 사용 개체 그래프 생성에 대 한 필요한 정적 값을 제공할 수 있습니다. `typeName` 지정은 실제로 XAML 형식, CLR 형식 이름이 아니라 기본 XAML 스키마 컨텍스트를 사용 하는 경우 또는 모든 기존 CLR 기반 XAML 구현 프레임 워크를 사용 하는 경우이 기본적으로 동일한 이름입니다.  

주의 해야 할 때 사용 하 여 `x:Static` 참조 된 속성의 값의 형식입니다. XAML에서 태그 확장에서 값을 제공 하는 시퀀스를 처리는 가치를 더하는 변환을 호출 하지 마십시오. 이것이 사실이 경우에 프로그램 `x:Static` 참조 텍스트 문자열을 만들고 반환 형식의 모든 멤버 값 또는 해당 특정 멤버에 대해 일반적으로 텍스트 문자열을 기반으로 특성 값에 대 한 값 변환 발생 합니다.  

특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다. `x:Static` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.StaticExtension.Member%2A> 확장 클래스의 <xref:System.Windows.Markup.StaticExtension> 값으로 할당됩니다.  

두 개의 다른 XAML 용도 기술적으로 가능 있습니다. 그러나 이러한 사용 가지 번거롭습니다 이기 때문에 일반적이 지 않습니다.  

1. 개체 요소 구문입니다.

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. 초기화 문자열에 대 한 명시적 멤버 속성으로 구문을 특성입니다.

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

이 태그 확장에 대 한 처리 정의한.NET Framework XAML 서비스 구현에서의 <xref:System.Windows.Markup.StaticExtension> 클래스입니다.  

`x:Static` 태그 확장입니다. XAML 사용의 모든 태그 확장을 `{` 고 `}` XAML 프로세서는 태그 확장 값을 입력 해야 한다는 인식 하는 규칙은 특성 구문에서 문자입니다. 태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md)를 참조하세요.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 WPF 프로그래밍에 사용할 기본 XAML 네임 스페이스에는 많은 유용한 정적 속성이 있고 유용한 정적 속성 중 대부분 필요 없이 쉽게 사용할 수 있는 형식 변환기와 같은 지원 `{x:Static}` 합니다. 정적 속성에 대 한 중 하나가 참인 경우 XAML 네임 스페이스에 대 한 접두사를 매핑되어야 합니다.  
  
-   Wpf에서 존재 하지만 WPF 기본 XAML 네임 스페이스의 일부가 아닌 형식을 참조 하는 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]). 이 사용 하는 매우 일반적인 시나리오는 `x:Static`합니다. 예를 들어 사용할 수 있습니다는 `x:Static` XAML 네임 스페이스 매핑 사용 하 여 참조를 <xref:System> 의 정적 속성을 참조 하기 위해 CLR 네임 스페이스 및 mscorlib 어셈블리는 <xref:System.Environment> 클래스입니다.  
  
-   사용자 지정 어셈블리에서 형식을 참조 합니다.  
  
-   WPF 기본 XAML 네임 스페이스의 일부가 되려면 매핑되지 않은 CLR 네임 스페이스 내에서 형식이 없는 WPF 어셈블리에 존재 하는 형식을 참조입니다. WPF에 대 한 기본 XAML 네임 스페이스를 CLR 네임 스페이스의 매핑을 다양 한 WPF 어셈블리에 정의 하 여 수행 됩니다 (이 개념에 대 한 자세한 내용은 참조 하세요. [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑을 Namespace](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)). 매핑되지 않은 CLR 네임 스페이스는 해당 CLR 네임 스페이스 클래스 정의 되지 않는 일반적으로 XAML에 대 한 같은 대부분의 구성 된 경우 있습니다 <xref:System.Windows.Threading>합니다.  
  
 WPF에 대 한 접두사와 XAML 네임 스페이스를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [XAML 네임 스페이스 및 WPF XAML에 대 한 매핑 Namespace](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [x:Type 태그 확장](x-type-markup-extension.md)
- [WPF에서 System.Xaml로 마이그레이션된 형식](types-migrated-from-wpf-to-system-xaml.md)
