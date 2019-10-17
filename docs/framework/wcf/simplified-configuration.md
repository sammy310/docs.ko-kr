---
title: 단순화된 구성
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 567f03e8f35ed72ba7e2a602bf47257158741fb3
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321163"
---
# <a name="simplified-configuration"></a><span data-ttu-id="adb94-102">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-102">Simplified Configuration</span></span>
<span data-ttu-id="adb94-103">WCF (Windows Communication Foundation) 서비스를 구성 하는 작업은 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-103">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="adb94-104">다양한 옵션이 있을 수 있고 경우에 따라 필요한 설정을 확인하는 것이 쉽지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-104">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="adb94-105">구성 파일은 WCF 서비스의 유연성을 향상 하지만 많은 문제를 찾기 위한 원본 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-105">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="adb94-106">에서는 이러한 문제를 해결하고 서비스 구성의 크기와 복잡성을 줄일 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-106">addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="adb94-107">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-107">Simplified Configuration</span></span>  
 <span data-ttu-id="adb94-108">WCF 서비스 구성 파일의 < `system.serviceModel` > 섹션에는 호스트 된 각 서비스에 대 한 < `service` > 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-108">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="adb94-109">< @No__t_0 > 요소에는 각 서비스에 대해 노출 되는 끝점과 선택적으로 서비스 동작 집합을 지정 하는 < `endpoint` > 요소의 컬렉션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-109">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="adb94-110">< @No__t_0 > 요소는 끝점에서 노출 하는 주소, 바인딩 및 계약을 지정 하 고 선택적으로 바인딩 구성과 끝점 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-110">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="adb94-111">또한 < `system.serviceModel` > 섹션에는 서비스 또는 끝점 동작을 지정할 수 있도록 하는 < `behaviors` > 요소도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-111">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="adb94-112">다음 예에서는 구성 파일의 < `system.serviceModel` > 섹션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-112">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="adb94-113">를 사용 하면 < `service` > 요소에 대 한 요구 사항을 제거 하 여 WCF 서비스를 보다 쉽게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-113">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="adb94-114">< @No__t_0 > 섹션을 추가 하지 않거나 < `service` > 섹션에서 끝점을 추가 하지 않고 서비스에서 프로그래밍 방식으로 끝점을 정의 하지 않는 경우 각 서비스 기준 주소 마다 하나씩, 기본 끝점 집합이 서비스에 자동으로 추가 됩니다. 서비스에서 구현 하는 각 계약에 대 한 및입니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-114">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="adb94-115">이러한 각 엔드포인트에서 엔드포인트 주소는 기본 주소에 해당하고, 바인딩은 기본 주소 스키마에 의해 결정되며, 계약은 서비스에 의해 구현되는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-115">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="adb94-116">엔드포인트 또는 서비스 동작을 지정하지 않아도 되거나 바인딩 설정을 변경하지 않아도 되는 경우에는 서비스 구성 파일을 지정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-116">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="adb94-117">서비스에서 두 개의 계약을 구현하고 호스트에서 HTTP 전송과 TCP 전송을 둘 다 사용하는 경우 서비스 호스트에서 각 전송을 사용하여 각 계약마다 하나씩 네 개의 기본 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-117">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="adb94-118">기본 엔드포인트를 만들려면 서비스 호스트에서 사용할 바인딩을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-118">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="adb94-119">이러한 설정은 < `system.serviceModel` > 섹션 내의 < `protocolMappings` > 섹션에서 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-119">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="adb94-120">< @No__t_0 > 섹션에는 바인딩 형식에 매핑된 전송 프로토콜 스키마의 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-120">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="adb94-121">서비스 호스트는 이 목록에 전달된 기본 주소를 사용하여 사용할 바인딩을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-121">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="adb94-122">다음 예에서는 < `protocolMappings` > 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-122">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="adb94-123">바인딩 또는 동작과 같은 기본 구성 요소를 변경하면 구성 계층 구조의 낮은 수준에서 정의된 서비스에서 이러한 기본 바인딩 및 동작을 사용할 수도 있기 때문에 해당 서비스에 영향을 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-123">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="adb94-124">따라서 기본 바인딩 및 동작을 변경하는 경우 이러한 변경이 계층 구조의 다른 서비스에 영향을 줄 수도 있다는 점을 명심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-124">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="adb94-125">IIS(인터넷 정보 서비스)나 WAS(Windows Process Activation Service)에서 호스트된 서비스는 가상 디렉터리를 기본 주소로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-125">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="adb94-126">이전 예제에서 "http" 체계로 시작하는 기본 주소를 가진 엔드포인트는 <xref:System.ServiceModel.BasicHttpBinding>을 사용하고,</span><span class="sxs-lookup"><span data-stu-id="adb94-126">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="adb94-127">"net.tcp" 체계로 시작하는 기본 주소를 가진 있는 엔드포인트는 <xref:System.ServiceModel.NetTcpBinding>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-127">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="adb94-128">로컬 App.config 또는 Web.config 파일의 설정은 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-128">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="adb94-129">< @No__t_0 > 섹션 내의 각 요소는 스키마와 바인딩을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-129">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="adb94-130">선택적으로 구성 파일의 < `bindings` > 섹션 내에서 바인딩 구성을 지정 하는 `bindingConfiguration` 특성을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-130">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="adb94-131">`bindingConfiguration`을 지정하지 않으면 해당 바인딩 형식의 익명 바인딩 구성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-131">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="adb94-132">서비스 동작은 < `serviceBehaviors` > 섹션 내에서 익명 < `behavior` > 섹션을 사용 하 여 기본 끝점에 대해 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-132">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="adb94-133">< @No__t_1 > 내의 명명 되지 않은 < `behavior` > 요소는 서비스 동작을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-133">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="adb94-134">예를 들어 다음 구성 파일은 호스트 내의 모든 서비스에 대한 서비스 메타데이터 게시를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-134">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="adb94-135">끝점 동작은 < `serviceBehaviors` > 섹션 내에서 익명 < `behavior` > 섹션을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-135">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="adb94-136">다음 예제에서는 이 항목의 시작 부분에 나온 구성 파일이 단순화된 구성 모델을 사용하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-136">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> <span data-ttu-id="adb94-137">이 기능은 클라이언트 구성이 아닌 WCF 서비스 구성에만 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-137">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="adb94-138">대부분, WCF 클라이언트 구성은 Visual Studio에서 서비스 참조를 추가하거나 svcutil.exe와 같은 도구에 의해 생성될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-138">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="adb94-139">WCF 클라이언트를 수동으로 구성 하는 경우 구성에 \<client > 요소를 추가 하 고 호출 하려는 모든 끝점을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb94-139">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb94-140">참조</span><span class="sxs-lookup"><span data-stu-id="adb94-140">See also</span></span>

- [<span data-ttu-id="adb94-141">구성 파일을 사용하여 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-141">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="adb94-142">서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-142">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="adb94-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-143">Configuring System-Provided Bindings</span></span>](./feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="adb94-144">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-144">Configuring Services</span></span>](configuring-services.md)
- [<span data-ttu-id="adb94-145">WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-145">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="adb94-146">코드로 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="adb94-146">Configuring WCF Services in Code</span></span>](configuring-wcf-services-in-code.md)
