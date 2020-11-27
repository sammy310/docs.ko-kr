---
title: '방법: 구성에서 서비스 엔드포인트 만들기'
description: 상대 주소와 절대 주소를 모두 포함 하는 구성 파일을 사용 하 여 WCF 서비스에 대 한 끝점을 추가 하는 방법을 알아봅니다.
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: aa8dce18a39b44c2c56d072a81699d1bc1e7d7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286424"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a>방법: 구성에서 서비스 엔드포인트 만들기

끝점은 WCF (Windows Communication Foundation) 서비스에서 제공 하는 기능에 대 한 액세스를 클라이언트에 제공 합니다. 상대 및 절대 엔드포인트 주소 조합을 사용하여 엔드포인트를 하나 이상 정의할 수 있으며, 서비스 엔드포인트를 정의하지 않는 경우에는 런타임이 기본적으로 일부 엔드포인트를 자동으로 제공합니다. 이 항목에서는 상대 주소와 절대 주소를 모두 포함하는 구성 파일을 사용해 엔드포인트를 추가하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  

 다음 서비스 구성에는 기본 주소와 5개의 엔드포인트가 지정됩니다.  
  
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
  
## <a name="example"></a>예제  

 기본 주소는 다음 샘플에서처럼 service/host/baseAddresses 아래 `add` 요소를 사용하여 지정합니다.  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a>예제  

 다음 샘플에서처럼 첫 번째 엔드포인트 정의는 엔드포인트 주소가 기본 주소와 URI(Uniform Resource Identifier) 컴퍼지션 다음에 오는 상대 주소의 조합인 상대 주소를 지정합니다. 상대 주소가 비어 있으므로("") 엔드포인트 주소는 기본 주소와 동일합니다. 실제 끝점 주소는 `http://localhost:8000/servicemodelsamples/service` 입니다.  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예제  

 두 번째 엔드포인트 정의도 다음 샘플 구성에서처럼 상대 주소를 지정합니다. 상대 주소 "test"가 기본 주소에 추가됩니다. 실제 끝점 주소는 `http://localhost:8000/servicemodelsamples/service/test` 입니다.  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예제  

 세 번째 엔드포인트 정의는 다음 샘플 구성에서처럼 절대 주소를 지정합니다. 주소에서 기본 주소는 아무런 역할도 하지 않습니다. 실제 끝점 주소는 `http://localhost:8001/hello/servicemodelsamples` 입니다.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예제  

 네 번째 엔드포인트 주소는 절대 주소 및 다른 전송(TCP)을 지정합니다. 주소에서 기본 주소는 아무런 역할도 하지 않습니다. 실제 엔드포인트 주소는 net.tcp://localhost:9000/servicemodelsamples/service입니다.  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예제  

 런타임에서 제공하는 기본 엔드포인트를 사용하려면 코드나 구성 파일에 서비스 엔드포인트를 지정하지 않으면 됩니다. 이 예제에서는 서비스를 열 때 런타임이 기본 엔드포인트를 만듭니다. 기본 엔드포인트, 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../samples/simplified-configuration-for-wcf-services.md)을 참조하세요.  
  
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
