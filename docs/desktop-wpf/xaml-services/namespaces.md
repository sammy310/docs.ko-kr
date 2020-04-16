---
title: .NET XAML 서비스를 위한 XAML 네임스페이스
ms.date: 03/30/2017
ms.assetid: e4f15f13-c420-4c1e-aeab-9b6f50212047
ms.openlocfilehash: 2ae57d08fade85c59fea2a54b653a2f775b57415
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433063"
---
# <a name="xaml-namespaces-for-net-xaml-services"></a>.NET XAML 서비스를 위한 XAML 네임스페이스
XAML 네임스페이스는 XML 네임스페이스의 정의를 확장하는 개념입니다. XML 네임스페이스와 마찬가지로 태그의 특성을 사용하여 XAML 네임스페이스를 `xmlns` 정의할 수 있습니다. XAML 네임스페이스는 XAML 노드 스트림 및 기타 XAML 서비스 API에도 표시됩니다. 이 항목에서는 XAML 네임스페이스 개념을 정의하고 XAML 네임스페이스를 정의하고 XAML 스키마 컨텍스트 및 .NET XAML 서비스의 다른 측면에서 사용하는 방법을 설명합니다.  
  
## <a name="xml-namespace-and-xaml-namespace"></a>XML 네임스페이스 및 XAML 네임스페이스  
 XAML 네임스페이스는 XAML이 XML의 특수 한 형태이며 마크업에 기본 XML 양식을 사용하는 것처럼 특수한 XML 네임스페이스입니다. 태그에서 요소에 적용 된 `xmlns` 특성을 통해 XAML 네임스페이스 및 매핑을 선언 합니다. 선언은 `xmlns` XAML 네임스페이스가 선언된 것과 동일한 요소에 대해 만들 수 있습니다. 요소에 대한 XAML 네임스페이스 선언은 해당 요소, 해당 요소의 모든 특성 및 해당 요소의 모든 자식에 대해 유효합니다. 특성 자체가 태그에서 특성 이름의 일부로 접두사를 참조하는 한 특성이 포함된 요소와 같지 않은 XAML 네임스페이스를 사용할 수 있습니다.  
  
 XAML 네임스페이스와 XML 네임스페이스의 차이점은 XML 네임스페이스를 스키마를 참조하거나 단순히 엔터티를 구별하는 데 사용될 수 있다는 것입니다. XAML의 경우 XAML에 사용되는 형식과 멤버는 궁극적으로 백업 유형으로 해결되어야 하며 XML 스키마 개념은 이 기능에 잘 적용되지 않습니다. XAML 네임스페이스에는 이 형식 매핑을 수행하기 위해 XAML 스키마 컨텍스트에서 사용할 수 있어야 하는 정보가 포함되어 있습니다.  
  
## <a name="xaml-namespace-components"></a>XAML 네임스페이스 구성요소  
 XAML 네임스페이스 정의에는 접두사와 식별자라는 두 가지 구성 요소가 있습니다. 이러한 각 구성 요소는 XAML 네임스페이스가 태그로 선언되거나 XAML 형식 시스템에 정의될 때 존재합니다.  
  
 접두사는 [XML 1.0 사양의 W3C 네임스페이스에서](https://www.w3.org/TR/REC-xml-names/)허용하는 모든 문자열일 수 있습니다. 일반적으로 접두사는 일반적인 태그 파일에서 여러 번 반복되기 때문에 일반적으로 짧은 문자열입니다. 여러 XAML 구현에서 사용하려는 특정 XAML 네임스페이스는 특정 기존 접두사를 사용합니다. 예를 들어 XAML 언어 XAML 네임스페이스는 일반적으로 `x`접두사를 사용하여 매핑됩니다. 접두사가 정의에 제공되지 않지만 XAML 서비스 API에 정의되거나 쿼리된 경우 빈 문자열로 표시되는 기본 XAML 네임스페이스를 정의할 수 by.NET 있습니다. 일반적으로 기본 XAML 네임스페이스는 XAML 구현 기술과 해당 시나리오 및 어휘에 의해 접두사 생략 태그의 최대양을 촉진하기 위해 의도적으로 선택됩니다.  
  
 식별자는 [XML 1.0 사양의 W3C 네임스페이스에서](https://www.w3.org/TR/REC-xml-names/)허용하는 모든 문자열일 수 있습니다. 규칙에 따라 XML 네임스페이스 또는 XAML 네임스페이스에 대한 식별자는 일반적으로 프로토콜 자격을 갖춘 절대 URI로 URI 형식으로 제공되는 경우가 많습니다. 특정 XAML 어휘를 정의하는 버전 정보는 경로 문자열의 일부로 암시되는 경우가 많습니다. XAML 네임스페이스는 XML URI 규칙 외에 추가 식별자 규칙을 추가합니다. XAML 네임스페이스의 경우 식별자는 XAML 네임스페이스 아래의 요소로 지정된 형식을 확인하거나 멤버에 대한 특성을 해결하기 위해 XAML 스키마 컨텍스트에 필요한 정보를 전달합니다.  
  
 XAML 스키마 컨텍스트에 정보를 전달하기 위해 XAML 네임스페이스의 식별자는 여전히 URI 양식에 있을 수 있습니다. 그러나 이 경우 URI는 특정 어셈블리 또는 어셈블리 목록에서 일치하는 식별자로 선언됩니다. 이 작업은 어셈블리를 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>로 어셈블리에 어트리뷰트하여 수행합니다. XAML 네임스페이스를 식별하고 특성 화된 어셈블리에서 CLR 기반 형식 확인 동작을 지원하는 이 방법은 .NET XAML 서비스의 기본 XAML 스키마 컨텍스트에서 지원됩니다. 일반적으로 이 규칙은 XAML 스키마 컨텍스트가 CLR을 통합하거나 CLR 어셈블리에서 CLR 특성을 읽는 데 필요한 기본 XAML 스키마 컨텍스트를 기반으로 하는 경우에 사용할 수 있습니다.  
  
 XAML 네임스페이스는 CLR 네임스페이스와 형식 정의 어셈블리를 통신하는 규칙으로 식별할 수도 있습니다. 이 규칙은 형식을 포함하는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 어셈블리에 기여가 없는 경우에 사용됩니다. 이 규칙은 URI 규칙보다 더 복잡할 수 있으며 어셈블리를 참조하는 여러 가지 방법이 있기 때문에 모호성과 중복될 가능성도 있습니다.  
  
 CLR 네임스페이스 및 어셈블리 규칙을 사용하는 식별자의 가장 기본적인 형식은 다음과 같습니다.  
  
 `clr-namespace:clrnsName; assembly=assemblyShortName`
  
 `clr-namespace:`구문의 `; assembly=` 리터럴 구성 요소입니다.  
  
 *clrnsName은* CLR 네임스페이스를 식별하는 문자열 이름입니다. 이 문자열 이름에는 CLR 네임스페이스및 다른 CLR 네임스페이스와의 관계에 대한 힌트를 제공하는 내부 점 문자(.)가 포함됩니다.
  
 *assemblyShortNameXML에서* 유용한 형식을 정의하는 어셈블리의 문자열 이름입니다. 선언된 XAML 네임스페이스를 통해 액세스할 형식은 어셈블리에 의해 정의되고 *clrnsName에*의해 지정된 CLR 네임스페이스 내에서 선언될 것으로 예상됩니다. 이 문자열 이름은 일반적으로 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>에서 보고한 정보와 평행합니다.  
  
 CLR 네임스페이스 및 어셈블리 규칙에 대한 보다 완전한 정의는 다음과 같습니다.  
  
 `clr-namespace:clrnsName; assembly=assemblyName`
  
 *assemblyName은* 입력으로 합법적인 모든 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 문자열을 나타냅니다. 이 문자열에는 문화권, 공개 키 또는 버전 정보가 포함될 수 있습니다(이러한 <xref:System.Reflection.Assembly>개념의 정의는 참조 항목에 정의되어 있습니다). COFF 형식 및 증거(다른 오버로드에서 사용되는 <xref:System.Reflection.Assembly.Load%2A>경우)는 XAML 어셈블리 로드 목적과 관련이 없습니다. 모든 로드 정보를 문자열로 표시해야 합니다.  
  
 어셈블리에 대한 공개 키를 지정하는 것은 XAML 보안또는 어셈블리를 간단한 이름으로 로드하거나 캐시 또는 응용 프로그램 도메인에 미리 존재하는 경우 존재할 수 있는 가능한 모호성을 제거하는 데 유용한 기술입니다. 자세한 내용은 [XAML 보안 고려 사항을](security-considerations.md)참조하십시오.  
  
## <a name="xaml-namespace-declarations-in-the-xaml-services-api"></a>XAML 서비스 API의 XAML 네임스페이스 선언  
 XAML 서비스 API에서 XAML 네임스페이스 선언은 <xref:System.Xaml.NamespaceDeclaration> 개체로 표시됩니다. 코드에서 XAML 네임스페이스를 선언하는 경우 <xref:System.Xaml.NamespaceDeclaration.%23ctor%28System.String%2CSystem.String%29> 생성자호출합니다. `ns` 및 `prefix` 매개 변수는 문자열로 지정되며 이러한 매개 변수에 대해 제공하는 입력은 이 항목에서 이전에 제공한 XAML 네임스페이스 식별자 및 XAML 네임스페이스 접두사 정의에 해당합니다.  
  
 XAML 노드 스트림의 일부로 또는 XAML 형식 시스템에 대한 다른 액세스를 통해 XAML 네임스페이스 정보를 검사하는 경우 XAML 네임스페이스 식별자를 <xref:System.Xaml.NamespaceDeclaration.Namespace%2A?displayProperty=nameWithType> 보고하고 <xref:System.Xaml.NamespaceDeclaration.Prefix%2A?displayProperty=nameWithType> XAML 네임스페이스 접두사를 보고합니다.  
  
 XAML 노드 스트림에서 XAML 네임스페이스 정보는 적용되는 엔터티 앞에 오는 XAML 노드로 나타날 수 있습니다. 여기에는 XAML 네임스페이스 정보가 XAML 루트 `StartObject` 요소앞에 있는 경우가 포함됩니다. 자세한 내용은 [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md)을 참조하십시오.  
  
 .NET XAML 서비스 API를 사용하는 많은 시나리오의 경우 하나 이상의 XAML 네임스페이스 선언이 존재할 것으로 예상되며 선언에는 XAML 스키마 컨텍스트에 필요한 정보가 포함되거나 참조되어야 합니다. XAML 네임스페이스는 로드할 어셈블리를 지정하거나 XAML 스키마 컨텍스트에서 이미 로드되거나 알려진 네임스페이스 및 어셈블리 내에서 특정 형식을 해결하는 데 도움을 주어야 합니다.  
  
 XAML 노드 스트림을 생성하려면 XAML 스키마 컨텍스트를 통해 XAML 형식 정보를 사용할 수 있어야 합니다. XAML 형식 정보는 각 노드가 만들 관련 XAML 네임스페이스를 먼저 결정하지 않고는 확인할 수 없습니다. 이 시점에서 형식의 인스턴스는 아직 만들어지지 않지만 XAML 스키마 컨텍스트는 정의 어셈블리 및 백업 형식에서 정보를 조회해야 할 수 있습니다. 예를 `<Party><PartyFavor/></Party>`들어 태그를 처리하려면 XAML 스키마 컨텍스트가 `ContentProperty` `Party`의 이름과 형식을 확인할 수 있어야 하므로 `Party` `PartyFavor`에 대한 XAML 네임스페이스 정보도 알고 있어야 합니다. 기본 XAML 스키마 컨텍스트의 경우 정적 반사는 노드 스트림에서 XAML 형식 노드를 생성하는 데 필요한 많은 XAML 형식 시스템 정보를 보고합니다.  
  
 XAML 노드 스트림에서 개체 그래프를 생성하려면 XAML 네임스페이스 선언이 원래 태그에 사용되고 XAML 노드 스트림에 기록된 각 XAML 접두사에 대해 존재해야 합니다. 이 시점에서 인스턴스가 만들어지고 실제 형식 매핑 동작이 발생합니다.  
  
 XAML 네임스페이스 정보를 미리 채워야 하는 경우 XAML 스키마 컨텍스트를 사용하려는 XAML 네임스페이스가 태그에 정의되지 않은 경우 <xref:System.Xml.XmlParserContext> <xref:System.Xml.XmlReader>에 대해 XML 네임스페이스 선언을 선언하는 것이 사용할 수 있습니다. 그런 다음 <xref:System.Xml.XmlReader> XAML 판독기 생성자 또는 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29?displayProperty=nameWithType>에 대한 입력으로 사용합니다.  
  
 .NET XAML 서비스에서 XAML 네임스페이스 처리와 관련된 두 개의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> <xref:System.Windows.Markup.XmlnsPrefixAttribute>다른 API는 특성 및 . 이러한 특성은 어셈블리에 적용됩니다. <xref:System.Windows.Markup.XmlnsDefinitionAttribute>는 Uri를 포함하는 모든 XAML 네임스페이스 선언을 해석하기 위해 XAML 스키마 컨텍스트에서 사용됩니다. <xref:System.Windows.Markup.XmlnsPrefixAttribute>XAML을 내포하는 도구에서 특정 XAML 네임스페이스를 예측 가능한 접두사로 직렬화할 수 있습니다. 자세한 내용은 [사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성을](clr-attributes-with-custom-types-and-libraries.md)참조하십시오.  
  
## <a name="see-also"></a>참조

- [XAML 노드 스트림 구조 및 개념 이해](understanding-xaml-node-stream-structures-and-concepts.md)
