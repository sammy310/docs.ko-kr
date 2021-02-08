---
description: '자세히 알아보기: 표준 끝점'
title: 표준 엔드포인트
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: 5879bab5dff4dee8ac574bad1c4452a60cf7c323
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793443"
---
# <a name="standard-endpoints"></a>표준 엔드포인트

엔드포인트는 주소, 바인딩 및 계약을 지정하여 정의됩니다. 이외에도 엔드포인트에 설정할 수 있는 매개 변수에는 동작 구성, 헤더 및 수신 대기 URI가 있습니다.  일부 엔드포인트 유형의 경우 이러한 값이 변경되지 않습니다. 예를 들어 메타데이터 교환 엔드포인트는 항상 <xref:System.ServiceModel.Description.IMetadataExchange> 계약을 사용합니다. <xref:System.ServiceModel.Description.WebHttpEndpoint>와 같은 다른 엔드포인트에는 항상 지정된 엔드포인트 동작이 필요합니다. 일반적으로 사용되는 엔드포인트 속성을 기본값으로 적용하면 엔드포인트의 유용성이 향상될 수 있습니다. 개발자는 표준 엔드포인트를 사용하여 기본값을 갖거나 하나 이상의 엔드포인트 속성이 변경되지 않는 엔드포인트를 정의할 수 있습니다.  이러한 엔드포인트를 사용하면 정적 상태에 대한 정보를 지정하지 않고도 엔드포인트를 사용할 수 있습니다. 표준 엔드포인트는 인프라 및 애플리케이션 엔드포인트로 사용될 수 있습니다.  
  
## <a name="infrastructure-endpoints"></a>인프라 엔드포인트  

 서비스에서는 서비스 작성자가 명시적으로 구현하지 않은 일부 속성이 있는 엔드포인트를 노출할 수 있습니다. 예를 들어 메타데이터 교환 엔드포인트에서 <xref:System.ServiceModel.Description.IMetadataExchange> 계약을 노출하지만 해당 인프라가 서비스 작성자가 아닌 WCF에 의해 구현됩니다. 이러한 인프라는 하나 이상의 엔드포인트 속성에 대해 기본값을 가지며, 이러한 속성의 일부는 변경할 수 없습니다. 메타데이터 교환 엔드포인트의 <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> 속성은 <xref:System.ServiceModel.Description.IMetadataExchange>이어야 하는 반면 바인딩과 같은 다른 속성은 개발자가 제공할 수 있습니다. 인프라 엔드포인트는 <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> 속성을 `true`로 설정하여 식별됩니다.  
  
## <a name="application-endpoints"></a>애플리케이션 엔드포인트  

 애플리케이션 개발자는 주소, 바인딩 또는 계약에 대해 기본값을 지정하는 고유한 표준 엔드포인트를 정의할 수 있습니다. 표준 엔드포인트는 <xref:System.ServiceModel.Description.ServiceEndpoint>에서 클래스를 파생시킨 후 적절한 엔드포인트 속성을 설정하여 정의합니다. 속성에 변경 가능한 기본값을 제공할 수 있지만 일부 다른 속성은 변경할 수 없는 정적 값을 갖습니다. 다음 예제에서는 표준 엔드포인트를 구현하는 방법을 보여 줍니다.  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 구성 파일에서 사용자 정의 사용자 지정 끝점을 사용 하려면에서 클래스를 파생 하 <xref:System.ServiceModel.Configuration.StandardEndpointElement> 고에서 클래스를 파생 시킨 <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> 다음 app.config 또는 machine.config의 extensions 섹션에 새 표준 끝점을 등록 해야 합니다.  는 <xref:System.ServiceModel.Configuration.StandardEndpointElement> 다음 예제와 같이 표준 끝점에 대 한 구성을 지원 합니다.  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 는 <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> `standardEndpoints` 표준 끝점에 대 한 구성의 <> 섹션 아래에 표시 되는 컬렉션에 대 한 지원 형식을 제공 합니다.  다음 예제에서는 이 클래스를 구현하는 방법을 보여 줍니다.  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

다음 예제에서는 확장 섹션에 표준 엔드포인트를 등록하는 방법을 보여 줍니다.

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
      </standardEndpointExtensions>
</extensions>  
```  
  
## <a name="configuring-a-standard-endpoint"></a>표준 엔드포인트 구성  

 표준 엔드포인트는 코드나 구성에 추가할 수 있습니다.  코드에 표준 엔드포인트를 추가하려면 다음 예제와 같이 적절한 표준 엔드포인트 형식을 인스턴스화하고 이를 서비스 호스트에 추가합니다.  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 구성에서 표준 끝점을 추가 하려면 `endpoint` <> 요소에 <> 요소를 추가 하 `service` 고 <> 요소에 필요한 구성 설정을 추가 `standardEndpoints` 합니다. 다음 예제에서는 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>와 함께 제공되는 표준 엔드포인트 중 하나인 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]를 추가하는 방법을 보여 줍니다.  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 표준 끝점의 형식은 <> 요소의 kind 특성을 사용 하 여 지정 됩니다 `endpoint` . 끝점은 <> 요소 내에서 구성 됩니다 `standardEndpoints` . 위의 예제에서는 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 엔드포인트를 추가하고 구성했습니다. <`udpDiscoveryEndpoint`> 요소는 `standardEndpoint` 의 속성을 설정 하는 <>를 포함 합니다 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> .  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a>.NET Framework와 함께 제공되는 표준 엔드포인트  

 다음 표에서는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]와 함께 제공되는 표준 엔드포인트를 보여 줍니다.  
  
 `Mex Endpoint`  
 서비스 메타데이터를 노출하는 데 사용되는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 서비스에서 알림 메시지를 보내는 데 사용되는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 서비스에서 검색 메시지를 보내는 데 사용되는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 UDP 멀티캐스트 바인딩을 통한 검색 작업에 대해 미리 구성된 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 서비스에서 UDP 바인딩을 통해 알림 메시지를 보내는 데 사용되는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 런타임에 WS-Discovery를 사용하여 엔드포인트 주소를 동적으로 찾는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 메타데이터 교환을 위한 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.WebHttpBinding> 동작을 자동으로 추가하는 <xref:System.ServiceModel.Description.WebHttpBehavior> 바인딩이 있는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.WebHttpBinding> 동작을 자동으로 추가하는 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> 바인딩이 있는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <xref:System.ServiceModel.WebHttpBinding> 바인딩이 있는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 워크플로 인스턴스에서 제어 작업을 호출하는 데 사용할 수 있는 표준 엔드포인트입니다.  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 워크플로 생성 및 책갈피 다시 시작을 지원하는 표준 엔드포인트입니다.
