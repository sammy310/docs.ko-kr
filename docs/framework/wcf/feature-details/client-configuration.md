---
title: 클라이언트 구성
description: WCF 클라이언트 구성을 사용 하 여 서비스에 연결 하는 데 사용 되는 끝점에 대 한 주소, 바인딩, 동작 및 계약을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: af9101be0067311fb1a3c0e6e575f186e8ccf161
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265975"
---
# <a name="client-configuration"></a>클라이언트 구성

WCF (Windows Communication Foundation) 클라이언트 구성을 사용 하 여 클라이언트가 서비스 끝점에 연결 하는 데 사용 하는 클라이언트 끝점의 "ABC" 속성인 주소, 바인딩, 동작 및 계약을 지정할 수 있습니다. 요소에는 [\<client>](../../configure-apps/file-schema/wcf/client.md) [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) 끝점 abcs를 구성 하는 데 사용 되는 특성이 포함 된 요소가 있습니다. 이러한 특성에 대해서는 [끝점 구성](#configuring-endpoints) 섹션에서 설명 합니다.  
  
 요소에는 [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) 메타 데이터 가져오기 및 내보내기에 대 한 설정을 지정 하는 데 사용 되는 요소, [\<headers>](../../configure-apps/file-schema/wcf/headers.md) 사용자 지정 주소 헤더의 컬렉션을 포함 하는 요소 및 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 다른 끝점에서 끝점을 인증할 수 있도록 하는 요소가 포함 되어 있습니다. [\<headers>](../../configure-apps/file-schema/wcf/headers.md)및 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 요소는의 일부 이며 <xref:System.ServiceModel.EndpointAddress> [주소](endpoint-addresses.md) 문서에 설명 되어 있습니다. 메타 데이터 확장 사용에 대해 설명 하는 항목에 대 한 링크는 [메타 데이터 구성](#configuring-metadata) 섹션에 제공 됩니다.  
  
## <a name="configuring-endpoints"></a>엔드포인트 구성  

 클라이언트 구성은 클라이언트에서 끝점을 [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) 구성 하는 데 사용할 클라이언트 구성의 및 요소를 참조 하는 각각 고유한 이름, 주소 및 계약을 사용 하 여 하나 이상의 끝점을 지정할 수 있도록 디자인 되었습니다. 클라이언트 구성 파일은 WCF 런타임에서 예상 하는 이름이 기 때문에 "App.config"로 이름이 지정 되어야 합니다. 다음 예제에서는 클라이언트 구성 파일을 보여 줍니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
            <!-- Add another endpoint by adding another <endpoint> element. -->
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
          <!-- Configure this binding here. -->  
        </binding>  
          </wsHttpBinding>  
     </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 선택적 `name` 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다. 이 특성은 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 또는 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A>가 서비스에 대한 채널을 만들 때 로드해야 하는 대상 엔드포인트를 클라이언트 구성에서 지정하는 데 사용됩니다. 와일드 카드 끝점 구성 이름 " \* "을 (를) 사용할 수 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 있으며 메서드에 끝점 구성을 로드 해야 함을 나타냅니다 .이 이름은 정확히 한 번 사용 가능한 경우 예외를 throw 합니다. 이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다. `name` 특성의 기본값은 다른 이름과 마찬가지로 일치되는 빈 문자열입니다.  
  
 모든 엔드포인트에는 해당 엔드포인트를 찾아서 식별할 수 있는 연결된 주소가 있어야 합니다. ph x="1" /&gt; 특성을 사용하면 엔드포인트의 위치를 제공하는 URL을 지정할 수 있습니다. URI(Uniform Resource Identifier)를 만든 다음 <xref:System.ServiceModel.ServiceHost> 메서드 중 하나를 사용하여 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>에 추가하여 서비스 엔드포인트의 주소를 코드로 지정할 수도 있습니다. 자세한 내용은 [Addresses](endpoint-addresses.md)를 참조 하세요. 소개와 같이 [\<headers>](../../configure-apps/file-schema/wcf/headers.md) 및 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 요소는의 일부 이며 <xref:System.ServiceModel.EndpointAddress> [Addresses](endpoint-addresses.md) 항목에도 설명 되어 있습니다.  
  
 ph x="1" /&gt; 특성은 서비스에 연결할 때 사용할 엔드포인트 바인딩 형식을 나타냅니다. 형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다. 앞의 예제에서이 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 섹션은 끝점이를 사용 함을 나타냅니다 <xref:System.ServiceModel.WSHttpBinding> . 그러나 엔드포인트에서 사용할 수 있는 지정된 형식의 바인딩이 여러 개 있을 수도 있습니다. 이러한 각에는 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) (바인딩) 형식 요소 내에 고유한 요소가 있습니다. `bindingconfiguration` 특성은 동일한 형식의 바인딩을 구분하는 데 사용됩니다. 해당 값은 `name` 요소의 특성과 일치 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 합니다. 구성을 사용 하 여 클라이언트 바인딩을 구성 하는 방법에 대 한 자세한 내용은 [방법: 구성에서 클라이언트 바인딩 지정](../how-to-specify-a-client-binding-in-configuration.md)을 참조 하세요.  
  
 `behaviorConfiguration`특성은 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) 끝점에서 사용 해야 하는를 지정 하는 데 사용 됩니다. 해당 값은 `name` 요소의 특성과 일치 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 합니다. 구성을 사용 하 여 클라이언트 동작을 지정 하는 예제는 [클라이언트 동작 구성](../configuring-client-behaviors.md)을 참조 하세요.  
  
 ph x="1" /&gt; 특성은 엔드포인트가 공개하는 계약을 지정합니다. 이 값은 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A>의 <xref:System.ServiceModel.ServiceContractAttribute>에 매핑됩니다. 기본값은 서비스를 구현하는 클래스의 전체 형식 이름입니다.  
  
### <a name="configuring-metadata"></a>메타데이터 구성  

 [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md)요소는 메타 데이터 가져오기 확장을 등록 하는 데 사용 되는 설정을 지정 하는 데 사용 됩니다. 메타 데이터 시스템 확장에 대 한 자세한 내용은 [메타 데이터 시스템 확장](../extending/extending-the-metadata-system.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [엔드포인트: 주소, 바인딩 및 계약](endpoints-addresses-bindings-and-contracts.md)
- [클라이언트 동작 구성](../configuring-client-behaviors.md)
