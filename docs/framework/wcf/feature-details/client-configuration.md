---
title: 클라이언트 구성
description: WCF 클라이언트 구성을 사용 하 여 서비스에 연결 하는 데 사용 되는 끝점에 대 한 주소, 바인딩, 동작 및 계약을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: c3e3d4904bad39e951e8ba69013ac95894130489
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245377"
---
# <a name="client-configuration"></a><span data-ttu-id="9336a-103">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9336a-103">Client Configuration</span></span>
<span data-ttu-id="9336a-104">WCF (Windows Communication Foundation) 클라이언트 구성을 사용 하 여 클라이언트가 서비스 끝점에 연결 하는 데 사용 하는 클라이언트 끝점의 "ABC" 속성인 주소, 바인딩, 동작 및 계약을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-104">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="9336a-105">요소에는 [\<client>](../../configure-apps/file-schema/wcf/client.md) [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) 끝점 abcs를 구성 하는 데 사용 되는 특성이 포함 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-105">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="9336a-106">이러한 특성에 대해서는 [끝점 구성](#configuring-endpoints) 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-106">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="9336a-107">요소에는 [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) 메타 데이터 가져오기 및 내보내기에 대 한 설정을 지정 하는 데 사용 되는 요소, [\<headers>](../../configure-apps/file-schema/wcf/headers.md) 사용자 지정 주소 헤더의 컬렉션을 포함 하는 요소 및 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 다른 끝점에서 끝점을 인증할 수 있도록 하는 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-107">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="9336a-108">[\<headers>](../../configure-apps/file-schema/wcf/headers.md)및 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 요소는의 일부 이며 <xref:System.ServiceModel.EndpointAddress> [주소](endpoint-addresses.md) 문서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-108">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](endpoint-addresses.md) article.</span></span> <span data-ttu-id="9336a-109">메타 데이터 확장 사용에 대해 설명 하는 항목에 대 한 링크는 [메타 데이터 구성](#configuring-metadata) 섹션에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-109">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="9336a-110">엔드포인트 구성</span><span class="sxs-lookup"><span data-stu-id="9336a-110">Configuring Endpoints</span></span>  
 <span data-ttu-id="9336a-111">클라이언트 구성은 클라이언트에서 끝점을 [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) 구성 하는 데 사용할 클라이언트 구성의 및 요소를 참조 하는 각각 고유한 이름, 주소 및 계약을 사용 하 여 하나 이상의 끝점을 지정할 수 있도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-111">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="9336a-112">클라이언트 구성 파일은 WCF 런타임에서 예상 하는 이름이 기 때문에 "App.config"로 이름이 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-112">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="9336a-113">다음 예제에서는 클라이언트 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-113">The following example shows a client configuration file.</span></span>  
  
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
  
 <span data-ttu-id="9336a-114">선택적 `name` 특성은 지정된 계약의 엔드포인트를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-114">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="9336a-115">이 특성은 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 또는 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A>가 서비스에 대한 채널을 만들 때 로드해야 하는 대상 엔드포인트를 클라이언트 구성에서 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-115">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="9336a-116">와일드 카드 끝점 구성 이름 " \* "을 (를) 사용할 수 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 있으며 메서드에 끝점 구성을 로드 해야 함을 나타냅니다 .이 이름은 정확히 한 번 사용 가능한 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-116">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="9336a-117">이 특성을 생략하면 해당하는 엔드포인트가 지정된 계약 형식과 연결된 기본 엔드포인트로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-117">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="9336a-118">`name` 특성의 기본값은 다른 이름과 마찬가지로 일치되는 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-118">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="9336a-119">모든 엔드포인트에는 해당 엔드포인트를 찾아서 식별할 수 있는 연결된 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-119">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="9336a-120">ph x="1" /&gt; 특성을 사용하면 엔드포인트의 위치를 제공하는 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-120">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="9336a-121">URI(Uniform Resource Identifier)를 만든 다음 <xref:System.ServiceModel.ServiceHost> 메서드 중 하나를 사용하여 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>에 추가하여 서비스 엔드포인트의 주소를 코드로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-121">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="9336a-122">자세한 내용은 [Addresses](endpoint-addresses.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9336a-122">For more information, see [Addresses](endpoint-addresses.md).</span></span> <span data-ttu-id="9336a-123">소개와 같이 [\<headers>](../../configure-apps/file-schema/wcf/headers.md) 및 [\<identity>](../../configure-apps/file-schema/wcf/identity.md) 요소는의 일부 이며 <xref:System.ServiceModel.EndpointAddress> [Addresses](endpoint-addresses.md) 항목에도 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-123">As the introduction indicates, the [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="9336a-124">ph x="1" /&gt; 특성은 서비스에 연결할 때 사용할 엔드포인트 바인딩 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-124">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="9336a-125">형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-125">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="9336a-126">앞의 예제에서이 [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) 섹션은 끝점이를 사용 함을 나타냅니다 <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="9336a-126">In the previous example, this is the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="9336a-127">그러나 엔드포인트에서 사용할 수 있는 지정된 형식의 바인딩이 여러 개 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-127">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="9336a-128">이러한 각에는 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) (바인딩) 형식 요소 내에 고유한 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-128">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="9336a-129">`bindingconfiguration` 특성은 동일한 형식의 바인딩을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-129">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="9336a-130">해당 값은 `name` 요소의 특성과 일치 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-130">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="9336a-131">구성을 사용 하 여 클라이언트 바인딩을 구성 하는 방법에 대 한 자세한 내용은 [방법: 구성에서 클라이언트 바인딩 지정](../how-to-specify-a-client-binding-in-configuration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9336a-131">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="9336a-132">`behaviorConfiguration`특성은 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) 끝점에서 사용 해야 하는를 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-132">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="9336a-133">해당 값은 `name` 요소의 특성과 일치 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-133">Its value is matched with the `name` attribute of the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="9336a-134">구성을 사용 하 여 클라이언트 동작을 지정 하는 예제는 [클라이언트 동작 구성](../configuring-client-behaviors.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9336a-134">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="9336a-135">ph x="1" /&gt; 특성은 엔드포인트가 공개하는 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-135">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="9336a-136">이 값은 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A>의 <xref:System.ServiceModel.ServiceContractAttribute>에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-136">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="9336a-137">기본값은 서비스를 구현하는 클래스의 전체 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-137">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="9336a-138">메타데이터 구성</span><span class="sxs-lookup"><span data-stu-id="9336a-138">Configuring Metadata</span></span>  
 <span data-ttu-id="9336a-139">[\<metadata>](../../configure-apps/file-schema/wcf/metadata.md)요소는 메타 데이터 가져오기 확장을 등록 하는 데 사용 되는 설정을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9336a-139">The [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="9336a-140">메타 데이터 시스템 확장에 대 한 자세한 내용은 [메타 데이터 시스템 확장](../extending/extending-the-metadata-system.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9336a-140">For more information about extending the metadata system, see [Extending the Metadata System](../extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9336a-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9336a-141">See also</span></span>

- [<span data-ttu-id="9336a-142">엔드포인트: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="9336a-142">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="9336a-143">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="9336a-143">Configuring Client Behaviors</span></span>](../configuring-client-behaviors.md)
