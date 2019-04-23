---
title: .NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의
ms.date: 03/30/2017
helpviewer_keywords:
- defining custom types [XAML Services]
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
ms.openlocfilehash: be9c0e26574a15279ce89af2c7862abaa8713360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164439"
---
# <a name="defining-custom-types-for-use-with-net-framework-xaml-services"></a>.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의
비즈니스 개체는 사용자 지정 형식을 정의 하거나 특정 프레임 워크에서 종속성을 갖지 않는 형식은 따르면 XAML에 대 한 몇 가지 최상의 방법이 있습니다. 이러한 사례를 따르는 경우.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기 수 형식의 XAML 특성을 검색 하 고 XAML 노드 스트림의 XAML 형식 시스템을 사용 하 여 적절 한 표현 합니다. 이 항목에서는 형식 정의 멤버 정의 및 CLR 형식 또는 멤버의 특성에 대 한 모범 사례를 설명 합니다.  
  
## <a name="constructor-patterns-and-type-definitions-for-xaml"></a>XAML에 대 한 형식 정의와 생성자 패턴  
 XAML에서 개체 요소로 인스턴스화하려면 사용자 지정 클래스에는 다음 요구 사항을 충족 해야 합니다.  
  
-   사용자 지정 클래스는 public 이어야 하며 기본 (매개 변수가 없는) public 생성자를 노출 해야 합니다. 구조체에 대한 자세한 내용은 다음 섹션을 참조하세요.  
  
-   사용자 지정 클래스에는 중첩된 클래스가 아니어야 합니다. "점" 전체 이름 경로에 추가 클래스 네임 스페이스 나누기 모호 하 고 연결 된 속성과 같은 기타 XAML 기능을 방해 합니다.  
  
 개체 요소로 개체를 인스턴스화할 수 있습니다, 하는 경우 생성된 된 개체 수 속성 요소 형식의 기본 형식으로 개체를 사용 하는 모든 속성을 입력 합니다.  
  
 값 변환기를 사용 하는 경우 이러한 기준을 충족 하지 않는 형식에 대 한 개체 값을 계속 제공할 수 있습니다. 자세한 내용은 [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md)합니다.  
  
### <a name="structures"></a>구조체  
 구조는 항상 XAML에서 CLR 정의 의해 생성 될 수 있습니다. 즉, CLR 컴파일러는 구조에 대 한 기본 생성자를 암시적으로 만듭니다. 이 생성자는 모든 속성 값을 기본값으로 초기화합니다.  
  
 일부 경우에는 구조에 대 한 기본 생성 동작 바람직하지 않습니다. 구조 개념적으로 공용 구조체의 값 및 함수를 채우는 것 때문일 수 있습니다. 공용 구조체의 경우 포함 된 값을 상호 배타적인 해석을 하며 따라서 해당 속성은 설정할 수 있습니다. WPF 어휘의 이러한 구조체의 예로 <xref:System.Windows.GridLength>합니다. 이러한 구조체는 값 서로 다른 해석 이나 모드는 구조체의 값을 만드는 문자열 규칙을 사용 하 여 특성 형식으로 표현할 수 있도록 형식 변환기를 구현 해야 합니다. 이러한 구조체는 기본값이 아닌 생성자를 통해 코드를 생성하는 경우에도 이와 유사한 동작을 노출해야 합니다.  
  
### <a name="interfaces"></a>인터페이스  
 인터페이스 멤버의 기본 형식으로 사용할 수 있습니다. 할당 가능한 목록을 검사 하 고 값으로 제공 되는 개체 인터페이스에 할당 될 수는 예상 하는 XAML 형식 시스템. 어떻게 인터페이스 표시 되어야 하는 XAML 형식으로 할당할 수 있는 관련 형식 XAML 생성 요구 사항을 지 원하는 개념은 있습니다.  
  
### <a name="factory-methods"></a>팩터리 메서드  
 팩터리 메서드는 XAML 2009 기능. 개체에 기본 생성자가 있어야 하는 XAML 원칙을 수정 합니다. 팩터리 메서드는이 항목에서 설명 되지 않습니다. 참조 [X:factorymethod 지시문](x-factorymethod-directive.md)합니다.  
  
## <a name="enumerations"></a>열거형  
 열거형에는 XAML 네이티브 형식 변환 작동 합니다. XAML에 지정 된 열거형 상수 이름을 기본 열거형 형식에 대해 확인 되며 및 XAML 개체 작성기에 열거 값을 반환 합니다.  
  
 XAML 사용 하 여 열거형에 대 한 플래그 스타일 사용 지원 <xref:System.FlagsAttribute> 적용 합니다. 자세한 내용은 [XAML 구문 정보](../wpf/advanced/xaml-syntax-in-detail.md)합니다. ([XAML 구문 정보](../wpf/advanced/xaml-syntax-in-detail.md) WPF 대상 작성 되지만 해당 항목의 정보는 대부분은 특정 프레임 워크 구현에 한정 되지 않은 XAML에 대 한 관련.)  
  
## <a name="member-definitions"></a>멤버 정의  
 형식은은 XAML 사용에 대 한 멤버를 정의할 수 있습니다. XAML에서 사용할 수 없는 형식이 해당 하는 경우에 XAML에서 사용할 수 있는 멤버를 정의 하는 형식에 대 한 것 같습니다. 이것이 가능한 것은 CLR 상속 때문입니다. 있도록 멤버를 상속 하는 일부 형식을 형식으로 XAML 사용을 지원 하 고 구성원 해당 기본 형식에 대 한 XAML 사용을 지원 하거나 사용할 수 있는 기본 XAML 구문에 해당 멤버는 XAML에서 사용할 수 있습니다.  
  
### <a name="properties"></a>속성  
 일반적인 CLR을 사용 하 여 공용 CLR 속성으로 속성을 정의 하는 경우 `get` 고 `set` 접근자 패턴 및 언어에 적합 한 키워드는 XAML 형식 시스템에 대 한 적절 한 정보를 사용 하 여 멤버 속성을 제공 보고할 수 <xref:System.Xaml.XamlMember> 속성을 같은 <xref:System.Xaml.XamlMember.IsReadPublic%2A> 고 <xref:System.Xaml.XamlMember.IsWritePublic%2A>입니다.  
  
 특정 속성을 적용 하 여 텍스트 구문 가능 <xref:System.ComponentModel.TypeConverterAttribute>합니다. 자세한 내용은 [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md)합니다.  
  
 텍스트 구문 또는 네이티브 XAML 변환에 추가 간접 참조를 태그 확장 사용에는 속성의 형식 예: 없는 경우 (<xref:System.Xaml.XamlMember.TargetType%2A> 는 XAML의 형식 시스템) t를 처리 하 여 XAML 개체 작성기에 인스턴스를 반환할 수 있어야 합니다 CLR 형식으로 arget 형식입니다.  
  
 그러나 XAML 2009를 사용 하는 경우 [X:reference 태그 확장명](x-reference-markup-extension.md) 위의 고려 사항은 충족 되지 않으면 값을 제공 하기 사용할 수 있습니다. 즉 형식 정의 문제를 보다 사용 문제를 더 합니다.  
  
### <a name="events"></a>이벤트  
 공용 CLR 이벤트로 이벤트를 정의 하는 경우 XAML 형식 시스템 멤버로 사용 하 여 이벤트를 보고할 수 있습니다 <xref:System.Xaml.XamlMember.IsEvent%2A> 으로 `true`입니다. .NET Framework XAML 서비스 기능의; 범위 내에서 없으면 이벤트 처리기를 연결 합니다. 이 구현에서는 특정 프레임 워크를 그대로 사용 합니다.  
  
### <a name="methods"></a>메서드  
 메서드에 대 한 인라인 코드는 기본 XAML 기능이 아닙니다. 대부분의 경우에서 직접 참조 하지 메서드 멤버를 XAML에서 및 XAML의 메서드는 역할은 특정 XAML 패턴에 대 한 지원을 제공 하기 위해서만 합니다. [X:factorymethod 지시문](x-factorymethod-directive.md) 예외가 있습니다.  
  
### <a name="fields"></a>필드  
 CLR 디자인 지침 비정적 필드를 억제 합니다. 정적 필드에 대 한 정적 필드 값에 액세스할 수 있습니다 통해서만 [X:static 태그 확장](x-static-markup-extension.md);이 경우에 수행 하지 않습니다에 대 한 필드를 노출 하기 위해 CLR 정의에서 특별히 [X:static](x-static-markup-extension.md) 사용 합니다.  
  
## <a name="attachable-members"></a>연결 가능한 멤버  
 연결 가능한 멤버 XAML 정의 형식에 대 한 접근자 메서드 패턴을 통해 노출 됩니다. 정의 형식 자체 XAML에서 사용 가능한 개체로 될 필요가 없습니다. 역할이 서비스 클래스를 선언 하려면 일반적인 패턴은 실제로 연결 가능한 멤버를 소유 하 고 관련된 동작을 구현 하지만 UI 표현 같은 없는 다른 기능을 제공 합니다. 다음 섹션에서는 자리 표시자에 대 한 *PropertyName* 연결 가능한 멤버의 이름을 나타냅니다. 해당 이름에서 유효 해야 합니다 [XamlName 문법](xamlname-grammar.md)합니다.  
  
 이러한 패턴 및 기타 메서드에 형식 간의 이름 충돌 주의 해야 합니다. 패턴 중 하 나와 일치 하는 멤버가 있으면 해석 될 수는 연결 가능한 멤버 사용 경로를 XAML 프로세서에서 의도 된 경우에 합니다.  
  
#### <a name="the-getpropertyname-accessor"></a>GetPropertyName 접근자  
 `Get`*PropertyName* 접근자에 대한 서명은 다음과 같아야 합니다.  
  
 `public static object Get`*PropertyName* `(object`  `target` `)`  
  
-   구현에서 보다 구체적인 형식으로 `target` 개체를 지정할 수 있습니다. 범위에 연결 가능 멤버를 사용 하는 데 사용할 수 있습니다. 원하는 범위를 벗어나는 사용량에는 XAML 구문 분석 오류가 발생 한 후 표시 되는 잘못 된 캐스팅 예외가 throw 됩니다. 매개 변수 이름을 `target` 요구 되지 않지만 라는 `target` 대부분의 구현에서 규칙에 따라 합니다.  
  
-   구현에서 보다 구체적인 형식으로 반환 값을 지정할 수 있습니다.  
  
 지원에 <xref:System.ComponentModel.TypeConverter> 연결 가능한 멤버의 특성 사용에 대 한 사용 가능한 텍스트 구문을 적용 <xref:System.ComponentModel.TypeConverterAttribute> 에 `Get` *PropertyName* 접근자 합니다. 적용 합니다 `get` 대신는 `set` 임의의; 보일 수 있습니다이 규칙 개념을 지원할 수 있지만 직렬화 할 수 있는 읽기 전용 연결 가능한 멤버에는 디자이너 시나리오에서 유용 합니다.  
  
#### <a name="the-setpropertyname-accessor"></a>SetPropertyName 접근자  
 집합에 대 한 서명을*PropertyName* 접근자 이어야 합니다.  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   `target` 이전 섹션에 설명 된 대로 동일한 논리와 결과 사용 하 여 구현에서 보다 구체적인 형식으로 개체를 지정할 수 있습니다.  
  
-   구현에서 보다 구체적인 형식으로 `value` 개체를 지정할 수 있습니다.  
  
 이 메서드에 대 한 값이 XAML 사용 특성 양식에서 일반적으로 입력 해야 합니다. 특성 및 특성 양식에서 값 변환기 지원이 있어야 텍스트 구문에 대 한 합니다 `Get` *PropertyName* 접근자입니다.  
  
### <a name="attachable-member-stores"></a>연결 가능한 멤버 저장소  
 접근자 메서드는 일반적으로 아닙니다 연결 가능한 멤버 값을 개체 그래프를 배치할 또는 개체 그래프에서 값을 검색 하 고 제대로 serialize 할 수 있는 방법을 제공 합니다. 이 기능을 제공 하는 `target` 이전 접근자 서명에서 개체 값을 저장할 수 있어야 합니다. 저장소 메커니즘 연결 가능한 멤버 있지 않은 멤버 목록에서 대상에 연결할 수 있는 멤버는 연결 가능한 멤버 원칙와 일치 해야 합니다. 연결 가능한 멤버 저장소 Api를 통해.NET framework XAML 서비스 제공 구현 하는 기법 <xref:System.Xaml.IAttachedPropertyStore> 고 <xref:System.Xaml.AttachablePropertyServices>입니다. <xref:System.Xaml.IAttachedPropertyStore> XAML 작성기를 사용 하 여 저장소 구현을 검색 하는 데 사용 되 고 형식을에 구현 해야 합니다 `target` 접근자입니다. 정적 <xref:System.Xaml.AttachablePropertyServices> Api는 접근자의 본문 내에서 사용 되 고에서 연결 가능한 멤버를 참조 해당 <xref:System.Xaml.AttachableMemberIdentifier>합니다.  
  
## <a name="xaml-related-clr-attributes"></a>XAML 관련 CLR 특성  
 올바르게 프로그램 형식, 멤버 및 어셈블리 특성을 지정 하는 것은.NET Framework XAML 서비스 XAML 형식 시스템의 정보를 보고 하기 위해 중요 합니다. 이 형식을 기반으로 하는 직접.NET Framework XAML 서비스 XAML 판독기 및 XAML 작성기는 XAML 시스템 사용 하려는 경우 또는 정의 하거나 해당 XAML 판독기 및 XAML 작성기를 기반으로 하는 XAML을 활용 하 여 프레임 워크를 사용 하는 경우에 관련이 있습니다.  
  
 사용자 지정 형식 XAML 지원에 대 한 관련 된 각 XAML 관련 특성의 나열을 참조 하세요 [사용자 지정 형식 및 라이브러리에 대 한 CLR 특성 XAML-Related](xaml-related-clr-attributes-for-custom-types-and-libraries.md)합니다.  
  
## <a name="usage"></a>사용법  
 사용자 지정 형식 사용 해야 태그 작성자가 사용자 지정 형식을 포함 하는 어셈블리 및 CLR 네임 스페이스에 대 한 접두사를 매핑해야 합니다. 이 절차는이 항목에서 설명 하지 않습니다.  
  
## <a name="access-level"></a>액세스 수준  
 XAML을 로드 하는 형식을 인스턴스화하는 방법을 제공는 `internal` 액세스 수준입니다. 이 기능은 사용자 코드는 고유한 형식을 정의 하 고 다음 동일한 사용자 코드 범위에 포함 되는 태그에서 해당 클래스를 인스턴스화할 수 있도록 제공 됩니다.  
  
 WPF의 예제는 사용자 코드에서 정의 될 때마다를 <xref:System.Windows.Controls.UserControl> UI 동작을 리팩터링 하는 방법으로 사용 하 여 지원 클래스를 선언 하 여 사용 권한에 포함 된 수는 모든 가능한 확장 메커니즘의 일부가 아니라 것 `public` 액세스 수준입니다. 이러한를 <xref:System.Windows.Controls.UserControl> 으로 선언 될 수 있습니다 `internal` 백업 코드를 XAML 형식으로 참조 되는 동일한 어셈블리로 컴파일되는 경우에 액세스 합니다.  
  
 완전 신뢰 수준에서 XAML을 로드 하 고 사용 하는 응용 프로그램에 대 한 <xref:System.Xaml.XamlObjectWriter>, 클래스 로드 `internal` 액세스 수준을 항상 사용 됩니다.  
  
 부분 신뢰 환경에서 XAML을 로드 하는 응용 프로그램에 대 한 액세스 수준 특성을 사용 하 여 제어할 수 있습니다는 <xref:System.Xaml.Permissions.XamlAccessLevel> API. 또한 지연 메커니즘 (예: WPF 서식 파일 시스템)를 액세스 수준 권한을 전파 하 여 최종 실행된 시간 평가판;에 대 한 보존 수 있어야 이 값은 전달 하 여 내부적으로 처리 되는 <xref:System.Xaml.Permissions.XamlAccessLevel> 정보입니다.  
  
### <a name="wpf-implementation"></a>WPF 구현  
 WPF XAML 모델을 사용 하는 부분 신뢰 액세스 BAML 부분 신뢰 환경에서 로드 되 면 액세스 인 제한 <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A> BAML 소스는 어셈블리에 대 한 합니다. WPF는 지연을 위해 다음을 사용 합니다. <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=nameWithType> 액세스 수준 정보를 전달 하기 위한 메커니즘으로 합니다.  
  
 WPF XAML 용어에서는 *내부 형식* 도 참조 XAML을 포함 하는 동일한 어셈블리에 의해 정의 된 형식입니다. 이러한 형식의 어셈블리를 의도적으로 생략 하는 XAML 네임 스페이스를 통해 매핑될 수 = 매핑, 예를 들어, 부분 `xmlns:local="clr-namespace:WPFApplication1"`합니다.  BAML 내부 형식을 참조 하는 경우 및 형식에 있는지 `internal` 액세스 수준이 생성을 `GeneratedInternalTypeHelper` 어셈블리에 대 한 클래스입니다. 방지 하려는 경우 `GeneratedInternalTypeHelper`를 사용 하거나 `public` 액세스 수준이 또는 관련 클래스를 별도 어셈블리로 팩터링 하 고 확인 해야 해당 어셈블리가 종속입니다.  
  
## <a name="see-also"></a>참고자료

- [사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성](xaml-related-clr-attributes-for-custom-types-and-libraries.md)
- [XAML 서비스](index.md)
