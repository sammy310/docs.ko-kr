---
title: .NET Framework XAML 서비스의 XAML 네임스페이스
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 11bf5d112c64fb0b942decf7635f02b90a98bdeb
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837170"
---
# <a name="xaml-namespaces-for-net-framework-xaml-services"></a>.NET Framework XAML 서비스의 XAML 네임스페이스
XAML 네임 스페이스는 XML 네임 스페이스 정의를 확장 하는 개념입니다. XML 네임 스페이스와 마찬가지로 태그에 `xmlns` 특성을 사용 하 여 XAML 네임 스페이스를 정의할 수 있습니다. Xaml 네임 스페이스는 xaml 노드 스트림 및 기타 XAML 서비스 Api에도 표시 됩니다. 이 항목에서는 xaml 네임 스페이스 개념을 정의 하 고 xaml 네임 스페이스를 정의 하 고 xaml 스키마 컨텍스트 및 .NET Framework XAML 서비스의 다른 측면에서 사용 하는 방법을 설명 합니다.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML 네임 스페이스 및 XAML 네임 스페이스  
 Xaml 네임 스페이스는 XAML이 특수 한 형태의 XML이 고 태그에 기본 XML 형식을 사용 하는 것 처럼 특수화 된 XML 네임 스페이스입니다. 태그에서 요소에 적용 된 `xmlns` 특성을 통해 XAML 네임 스페이스 및 해당 매핑을 선언 합니다. `xmlns` 선언은 XAML 네임 스페이스가 선언 된 동일한 요소에 대해 만들 수 있습니다. 요소에 대 한 XAML 네임 스페이스 선언은 해당 요소, 해당 요소의 모든 특성 및 해당 요소의 모든 자식 요소에 대해 유효 합니다. 특성 이름 자체가 태그에서 해당 특성 이름의 일부로 접두사를 참조 하는 한 특성은 특성을 포함 하는 요소와는 다른 XAML 네임 스페이스를 사용할 수 있습니다.  
  
 XAML 네임 스페이스와 XML 네임 스페이스의 차이점은 XML 네임 스페이스를 사용 하 여 스키마를 참조 하거나 단순히 엔터티를 구별 하는 데 사용 될 수 있다는 것입니다. XAML의 경우 XAML에 사용 되는 형식 및 멤버를 궁극적으로 지원 형식으로 확인 해야 하며 XML 스키마 개념은이 기능에 잘 적용 되지 않습니다. XAML 네임 스페이스는이 형식 매핑을 수행 하기 위해 XAML 스키마 컨텍스트에서 사용할 수 있어야 하는 정보를 포함 합니다.  
  
## <a name="xaml-namespace-components"></a>XAML 네임 스페이스 구성 요소  
 XAML 네임 스페이스 정의에는 접두사와 식별자의 두 가지 구성 요소가 있습니다. 이러한 각 구성 요소는 XAML 네임 스페이스가 태그로 선언 되거나 XAML 형식 시스템에서 정의 될 때 제공 됩니다.  
  
 접두사는 [XML 1.0 사양에서 W3C 네임 스페이스에](https://www.w3.org/TR/REC-xml-names/) 의해 허용 되는 임의의 문자열일 수 있습니다. 일반적으로 접두사는 일반적인 태그 파일에서 여러 번 반복 되므로 규칙에 따라 일반적으로 매우 짧은 문자열입니다. 여러 XAML 구현에서 사용 하기 위한 특정 XAML 네임 스페이스는 특정 한 기본 접두사를 사용 합니다. 예를 들어 XAML 언어 XAML 네임 스페이스는 일반적으로 `x`접두사를 사용 하 여 매핑됩니다. 기본 XAML 네임 스페이스를 정의할 수 있습니다. 여기서 접두사는 정의에 지정 되지 않지만 by.NET Framework XAML 서비스 API를 정의 하거나 쿼리하면 빈 문자열로 표시 됩니다. 일반적으로 기본 XAML 네임 스페이스는 XAML 구현 기술과 해당 시나리오 및 어휘에 의해 최대한 많은 접두사 생략 태그를 승격 하기 위해 의도적으로 선택 됩니다.  
  
 식별자는 [XML 1.0 사양에서 W3C 네임 스페이스에](https://www.w3.org/TR/REC-xml-names/)의해 허용 되는 임의의 문자열일 수 있습니다. 규칙에 따라 XML 네임 스페이스 또는 XAML 네임 스페이스에 대 한 식별자는 일반적으로 일반적으로 프로토콜로 한정 된 절대 URI로 URI 형식으로 제공 됩니다. 특정 XAML 어휘를 정의 하는 버전 정보는 경로 문자열의 일부로 포함 되는 경우가 많습니다. XAML 네임 스페이스는 XML URI 규칙 외에 추가 식별자 규칙을 추가 합니다. Xaml 네임 스페이스의 경우 식별자는 xaml 스키마 컨텍스트에 필요한 정보를 전달 하 여 해당 XAML 네임 스페이스 아래의 요소로 지정 된 형식을 확인 하거나 특성을 멤버에 대해 확인 합니다.  
  
 Xaml 스키마 컨텍스트에 정보를 전달 하기 위해 XAML 네임 스페이스의 식별자는 URI 형식이 될 수 있습니다. 그러나이 경우 URI는 특정 어셈블리나 어셈블리 목록에서 일치 하는 식별자로도 선언 됩니다. 이 작업은 어셈블리에서 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>로 어셈블리를 사용 하 여 수행 됩니다. Xaml 네임 스페이스를 식별 하 고 특성 사용 어셈블리에서 CLR 기반 형식 확인 동작을 지 원하는이 메서드는 .NET Framework XAML 서비스의 기본 XAML 스키마 컨텍스트에서 지원 됩니다. 보다 일반적으로이 규칙은 XAML 스키마 컨텍스트가 CLR을 통합 하거나 CLR 어셈블리에서 CLR 특성을 읽는 데 필요한 기본 XAML 스키마 컨텍스트를 기반으로 하는 경우에 사용할 수 있습니다.  
  
 XAML 네임 스페이스는 CLR 네임 스페이스 및 형식 정의 어셈블리를 전달 하는 규칙으로도 식별할 수 있습니다. 이 규칙은 형식을 포함 하는 어셈블리에 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 특성이 존재 하지 않는 경우에 사용 됩니다. 이 규칙은 URI 규칙 보다 더 복잡할 수 있으며, 어셈블리를 참조 하는 여러 방법이 있으므로 모호성 및 중복이 발생할 수 있습니다.  
  
 CLR 네임 스페이스 및 어셈블리 규칙을 사용 하는 가장 기본적인 형태의 식별자는 다음과 같습니다.  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyShortName*  
  
 `clr-namespace:` 및 `; assembly=`는 구문의 리터럴 구성 요소입니다.  
  
 *Clrnsname* 은 CLR 네임 스페이스를 식별 하는 문자열 이름입니다. 이 문자열 이름에는 CLR 네임 스페이스 및 다른 CLR 네임 스페이스와의 관계에 대 한 힌트를 제공 하는 내부 점 문자 (.)가 포함 됩니다.  
  
 *assemblyShortName* 는 XAML에서 유용한 형식을 정의 하는 어셈블리의 문자열 이름입니다. 선언 된 XAML 네임 스페이스를 통해 액세스할 수 있는 형식은 어셈블리에 의해 정의 되 고 *Clrnsname*으로 지정 된 CLR 네임 스페이스 내에서 구체적으로 선언 되어야 합니다. 이 문자열 이름은 일반적으로 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>에서 보고 한 정보와 유사 합니다.  
  
 CLR 네임 스페이스 및 어셈블리 규칙의 전체 정의는 다음과 같습니다.  
  
 `clr-namespace:` *clrnsName* `; assembly=` *assemblyName*  
  
 *assemblyName* 은 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 입력으로 사용할 수 있는 모든 문자열을 나타냅니다. 이 문자열에는 문화권, 공개 키 또는 버전 정보가 포함 될 수 있습니다. 이러한 개념의 정의는 <xref:System.Reflection.Assembly>에 대 한 참조 항목에 정의 되어 있습니다. COFF 형식 및 증명 정보 (<xref:System.Reflection.Assembly.Load%2A>의 다른 오버 로드에서 사용 됨)는 XAML 어셈블리 로드와 관련이 없습니다. 모든 로드 정보는 문자열로 표시 되어야 합니다.  
  
 어셈블리에 대 한 공개 키를 지정 하는 것은 XAML 보안에 유용한 기술 이거나, 어셈블리가 단순한 이름으로 로드 되거나 캐시 또는 응용 프로그램 도메인에 미리 존재 하는 경우 발생할 수 있는 모호성을 제거 하는 것입니다. 자세한 내용은 [XAML 보안 고려 사항](xaml-security-considerations.md)을 참조 하세요.  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>Xaml 서비스 API의 XAML 네임 스페이스 선언  
 XAML 서비스 API에서 XAML 네임 스페이스 선언은 <xref:System.Xaml.NamespaceDeclaration> 개체로 표현 됩니다. 코드에서 XAML 네임 스페이스를 선언 하는 경우 <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> 생성자를 호출 합니다. `ns` 및 `prefix` 매개 변수는 문자열로 지정 되 고 이러한 매개 변수에 제공할 입력은이 항목의 앞부분에서 제공 된 xaml 네임 스페이스 식별자 및 XAML 네임 스페이스 접두사의 정의에 해당 합니다.  
  
 Xaml 노드 스트림의 일부로 또는 xaml 형식 시스템에 대 한 다른 액세스를 통해 XAML 네임 스페이스 정보를 검사 하는 경우 <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType>는 XAML 네임 스페이스 식별자를 보고 하 고 <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType>는 XAML 네임 스페이스 접두사를 보고 합니다.  
  
 Xaml 노드 스트림에서 XAML 네임 스페이스 정보는 해당 정보가 적용 되는 엔터티 앞에 나오는 XAML 노드로 표시 될 수 있습니다. 여기에는 xaml 네임 스페이스 정보가 XAML 루트 요소의 `StartObject` 앞에 오는 경우가 포함 됩니다. 자세한 내용은 [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md)을 참조하십시오.  
  
 .NET Framework XAML 서비스 API를 사용 하는 대부분의 시나리오에서는 하나 이상의 XAML 네임 스페이스 선언이 있어야 하며 선언은 XAML 스키마 컨텍스트에 필요한 정보를 포함 하거나이를 참조 해야 합니다. XAML 네임 스페이스는 로드 될 어셈블리를 지정 하거나, XAML 스키마 컨텍스트에서 이미 로드 되거나 알려진 네임 스페이스 및 어셈블리 내의 특정 형식을 확인 하는 데 도움이 되어야 합니다.  
  
 Xaml 노드 스트림을 생성 하기 위해 xaml 스키마 컨텍스트를 통해 xaml 형식 정보를 사용할 수 있어야 합니다. 만들려는 각 노드에 대 한 관련 XAML 네임 스페이스를 먼저 확인 하지 않으면 XAML 형식 정보를 확인할 수 없습니다. 이 시점에서 형식의 인스턴스는 아직 생성 되지 않지만 XAML 스키마 컨텍스트는 정의 어셈블리 및 지원 형식에서 정보를 조회 해야 할 수 있습니다. 예를 들어 `<Party><PartyFavor/></Party>`태그를 처리 하기 위해 XAML 스키마 컨텍스트는 `Party``ContentProperty`의 이름과 형식을 결정할 수 있어야 하므로 `Party` 및 `PartyFavor`에 대 한 XAML 네임 스페이스 정보를 알아야 합니다. 기본 XAML 스키마 컨텍스트의 경우 정적 리플렉션은 노드 스트림에 XAML 형식 노드를 생성 하는 데 필요한 대부분의 XAML 형식 시스템 정보를 보고 합니다.  
  
 XAML 노드 스트림에서 개체 그래프를 생성 하려면 원래 태그에 사용 되 고 XAML 노드 스트림에 기록 된 각 XAML 접두사에 대해 XAML 네임 스페이스 선언이 있어야 합니다. 이때 인스턴스가 만들어지고 진정한 형식 매핑 동작이 발생 합니다.  
  
 Xaml 네임 스페이스 정보를 미리 채워야 하는 경우 xaml 스키마 컨텍스트에서 사용할 XAML 네임 스페이스가 태그에 정의 되어 있지 않은 경우에는 <xref:System.Xml.XmlReader>에 대 한 <xref:System.Xml.XmlParserContext>에서 XML 네임 스페이스 선언을 선언 하는 방법 중 하나를 사용할 수 있습니다. 그런 다음 해당 <xref:System.Xml.XmlReader>를 XAML 판독기 생성자 또는 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>에 대 한 입력으로 사용 합니다.  
  
 .NET Framework XAML 서비스의 XAML 네임 스페이스 처리와 관련 된 두 가지 다른 API는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 및 <xref:System.Windows.Markup.XmlnsPrefixAttribute>특성입니다. 이러한 특성은 어셈블리에 적용 됩니다. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>는 URI를 포함 하는 XAML 네임 스페이스 선언을 해석 하기 위해 XAML 스키마 컨텍스트에서 사용 됩니다. <xref:System.Windows.Markup.XmlnsPrefixAttribute>은 특정 XAML 네임 스페이스를 예측 가능한 접두사로 serialize 할 수 있도록 XAML을 내보내는 도구에서 사용 됩니다. 자세한 내용은 [사용자 지정 형식 및 라이브러리에 대 한 XAML 관련 CLR 특성](xaml-related-clr-attributes-for-custom-types-and-libraries.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [XAML 노드 스트림 구조 및 개념 이해](understanding-xaml-node-stream-structures-and-concepts.md)
