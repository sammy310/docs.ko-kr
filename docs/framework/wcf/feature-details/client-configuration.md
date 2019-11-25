---
title: 클라이언트 구성
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 6a5cbf5d536af8649b0b8bb93600e94a48c507c1
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141774"
---
# <a name="client-configuration"></a><span data-ttu-id="10ae6-102">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="10ae6-102">Client Configuration</span></span>
<span data-ttu-id="10ae6-103">WCF (Windows Communication Foundation) 클라이언트 구성을 사용 하 여 클라이언트가 서비스 끝점에 연결 하는 데 사용 하는 클라이언트 끝점의 "ABC" 속성인 주소, 바인딩, 동작 및 계약을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="10ae6-104">[\<client >](../../configure-apps/file-schema/wcf/client.md) 요소에는 끝점 abcs를 구성 하는 데 사용 되는 특성을 가진 [\<끝점 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-104">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="10ae6-105">이러한 특성에 대해서는 [끝점 구성](#configuring-endpoints) 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-105">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="10ae6-106">[\<끝점 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) 요소에는 메타 데이터 가져오기 및 내보내기에 대 한 설정을 지정 하는 데 사용 되는 [\<메타 데이터 >](../../configure-apps/file-schema/wcf/metadata.md) 요소, 사용자 지정 주소 헤더의 컬렉션을 포함 하는\<[헤더 >](../../configure-apps/file-schema/wcf/headers.md) 요소와 메시지를 교환할 다른 끝점에서 끝점을 인증할 수 있도록 하는 [\<identity >](../../configure-apps/file-schema/wcf/identity.md) 요소도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-106">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="10ae6-107">[\<헤더 >](../../configure-apps/file-schema/wcf/headers.md) 및 [\<id >](../../configure-apps/file-schema/wcf/identity.md) 요소는 <xref:System.ServiceModel.EndpointAddress>의 일부 이며 [주소](../../wcf/feature-details/endpoint-addresses.md) 문서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-107">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../wcf/feature-details/endpoint-addresses.md) article.</span></span> <span data-ttu-id="10ae6-108">메타 데이터 확장 사용에 대해 설명 하는 항목에 대 한 링크는 [메타 데이터 구성](#configuring-metadata) 섹션에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-108">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="10ae6-109">엔드포인트 구성</span><span class="sxs-lookup"><span data-stu-id="10ae6-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="10ae6-110">클라이언트 구성은 클라이언트에서 하나 이상의 끝점을 지정할 수 있도록 디자인 되었습니다. 각 끝점은 고유한 이름, 주소 및 계약을 사용 하 여 각 끝점을 구성 하는 데 사용 되는 [\<바인딩을 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 하 고 [\<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="10ae6-111">클라이언트 구성 파일의 이름은 WCF 런타임에서 예상 하는 이름 이므로 "App.config"로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="10ae6-112">다음 예제에서는 클라이언트 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-112">The following example shows a client configuration file.</span></span>  
  
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
// Add another endpoint by adding another <endpoint> element.  
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
        //Configure this binding here.  
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
  
 <span data-ttu-id="10ae6-113">선택적 `name` 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="10ae6-114">이 특성은 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 또는 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A>가 서비스에 대한 채널을 만들 때 로드해야 하는 대상 엔드포인트를 클라이언트 구성에서 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="10ae6-115">와일드 카드 끝점 구성 이름 "\*"을 사용할 수 있으며, 사용 가능한 것이 있는 경우 파일에 끝점 구성을 로드 해야 하 고 그렇지 않으면 예외를 throw 하는 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 메서드에 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="10ae6-116">이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="10ae6-117">`name` 특성의 기본값은 다른 이름과 마찬가지로 일치되는 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="10ae6-118">모든 엔드포인트에는 해당 엔드포인트를 찾아서 식별할 수 있는 연결된 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="10ae6-119">ph x="1" /&gt; 특성을 사용하면 엔드포인트의 위치를 제공하는 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="10ae6-120">URI(Uniform Resource Identifier)를 만든 다음 <xref:System.ServiceModel.ServiceHost> 메서드 중 하나를 사용하여 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>에 추가하여 서비스 엔드포인트의 주소를 코드로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="10ae6-121">자세한 내용은 [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10ae6-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="10ae6-122">소개로 설명 된 것 처럼 [\<헤더 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) 및 [\<id >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 요소는 <xref:System.ServiceModel.EndpointAddress>의 일부 이며 [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) 항목에도 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="10ae6-123">ph x="1" /&gt; 특성은 서비스에 연결할 때 사용할 엔드포인트 바인딩 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="10ae6-124">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="10ae6-125">이전 예제에서이는 끝점에서 <xref:System.ServiceModel.WSHttpBinding>를 사용 함을 나타내는 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="10ae6-126">그러나 엔드포인트에서 사용할 수 있는 지정된 형식의 바인딩이 여러 개 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="10ae6-127">이러한 각에는 (바인딩) 형식 요소 내에서 고유한 [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-127">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="10ae6-128">`bindingconfiguration` 특성은 동일한 형식의 바인딩을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="10ae6-129">해당 값은 [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) 요소의 `name` 특성과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-129">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="10ae6-130">구성을 사용 하 여 클라이언트 바인딩을 구성 하는 방법에 대 한 자세한 내용은 [방법: 구성에서 클라이언트 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10ae6-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="10ae6-131">`behaviorConfiguration` 특성은 끝점에서 사용 해야 하는 [\<> endpointbehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) [\<동작](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="10ae6-132">해당 값은 [\<behavior >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소의 `name` 특성과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="10ae6-133">구성을 사용 하 여 클라이언트 동작을 지정 하는 예제는 [클라이언트 동작 구성](../../../../docs/framework/wcf/configuring-client-behaviors.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10ae6-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="10ae6-134">ph x="1" /&gt; 특성은 엔드포인트가 공개하는 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="10ae6-135">이 값은 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A>의 <xref:System.ServiceModel.ServiceContractAttribute>에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="10ae6-136">기본값은 서비스를 구현하는 클래스의 전체 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="10ae6-137">메타데이터 구성</span><span class="sxs-lookup"><span data-stu-id="10ae6-137">Configuring Metadata</span></span>  
 <span data-ttu-id="10ae6-138">[\<metadata >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) 요소는 메타 데이터 가져오기 확장을 등록 하는 데 사용 되는 설정을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10ae6-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="10ae6-139">메타 데이터 시스템 확장에 대 한 자세한 내용은 [메타 데이터 시스템 확장](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10ae6-139">For more information about extending the metadata system, see [Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ae6-140">참조</span><span class="sxs-lookup"><span data-stu-id="10ae6-140">See also</span></span>

- [<span data-ttu-id="10ae6-141">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="10ae6-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="10ae6-142">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="10ae6-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
