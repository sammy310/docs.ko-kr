---
title: '방법: 구성에서 서비스 엔드포인트 만들기'
description: 상대 주소와 절대 주소를 모두 포함 하는 구성 파일을 사용 하 여 WCF 서비스에 대 한 끝점을 추가 하는 방법을 알아봅니다.
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: 184bcb5f7f3e83f12608757b55bbb4d57be58f7d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247067"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="0ffa7-103">방법: 구성에서 서비스 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="0ffa7-103">How to: Create a Service Endpoint in Configuration</span></span>
<span data-ttu-id="0ffa7-104">끝점은 WCF (Windows Communication Foundation) 서비스에서 제공 하는 기능에 대 한 액세스를 클라이언트에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-104">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="0ffa7-105">상대 및 절대 엔드포인트 주소 조합을 사용하여 엔드포인트를 하나 이상 정의할 수 있으며, 서비스 엔드포인트를 정의하지 않는 경우에는 런타임이 기본적으로 일부 엔드포인트를 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-105">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="0ffa7-106">이 항목에서는 상대 주소와 절대 주소를 모두 포함하는 구성 파일을 사용해 엔드포인트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-106">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ffa7-107">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-107">Example</span></span>  
 <span data-ttu-id="0ffa7-108">다음 서비스 구성에는 기본 주소와 5개의 엔드포인트가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-108">The following service configuration specifies a base address and five endpoints.</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced in .NET Framework 4. -->  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="0ffa7-109">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-109">Example</span></span>  
 <span data-ttu-id="0ffa7-110">기본 주소는 다음 샘플에서처럼 service/host/baseAddresses 아래 `add` 요소를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-110">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="0ffa7-111">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-111">Example</span></span>  
 <span data-ttu-id="0ffa7-112">다음 샘플에서처럼 첫 번째 엔드포인트 정의는 엔드포인트 주소가 기본 주소와 URI(Uniform Resource Identifier) 컴퍼지션 다음에 오는 상대 주소의 조합인 상대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-112">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="0ffa7-113">상대 주소가 비어 있으므로("") 엔드포인트 주소는 기본 주소와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-113">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="0ffa7-114">실제 끝점 주소는 `http://localhost:8000/servicemodelsamples/service` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-114">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="0ffa7-115">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-115">Example</span></span>  
 <span data-ttu-id="0ffa7-116">두 번째 엔드포인트 정의도 다음 샘플 구성에서처럼 상대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-116">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="0ffa7-117">상대 주소 "test"가 기본 주소에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-117">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="0ffa7-118">실제 끝점 주소는 `http://localhost:8000/servicemodelsamples/service/test` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-118">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="0ffa7-119">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-119">Example</span></span>  
 <span data-ttu-id="0ffa7-120">세 번째 엔드포인트 정의는 다음 샘플 구성에서처럼 절대 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-120">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="0ffa7-121">주소에서 기본 주소는 아무런 역할도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-121">The base address plays no role in the address.</span></span> <span data-ttu-id="0ffa7-122">실제 끝점 주소는 `http://localhost:8001/hello/servicemodelsamples` 입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-122">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="0ffa7-123">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-123">Example</span></span>  
 <span data-ttu-id="0ffa7-124">네 번째 엔드포인트 주소는 절대 주소 및 다른 전송(TCP)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-124">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="0ffa7-125">주소에서 기본 주소는 아무런 역할도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-125">The base address plays no role in the address.</span></span> <span data-ttu-id="0ffa7-126">실제 엔드포인트 주소는 net.tcp://localhost:9000/servicemodelsamples/service입니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-126">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="0ffa7-127">예제</span><span class="sxs-lookup"><span data-stu-id="0ffa7-127">Example</span></span>  
 <span data-ttu-id="0ffa7-128">런타임에서 제공하는 기본 엔드포인트를 사용하려면 코드나 구성 파일에 서비스 엔드포인트를 지정하지 않으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-128">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="0ffa7-129">이 예제에서는 서비스를 열 때 런타임이 기본 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-129">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="0ffa7-130">기본 엔드포인트, 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../samples/simplified-configuration-for-wcf-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-130">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
