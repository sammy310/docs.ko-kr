---
title: 코드로 WCF 서비스 구성
description: 자체 호스팅 서비스와 웹 호스팅 서비스 모두에 대해 구성 파일 대신 코드를 사용 하 여 WCF 서비스를 구성 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: d28115236a4582fe251adf1537b9e8b3e996d611
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245416"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="81150-103">코드로 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="81150-103">Configuring WCF Services in Code</span></span>
<span data-ttu-id="81150-104">WCF (Windows Communication Foundation)를 사용 하면 개발자가 구성 파일 또는 코드를 사용 하 여 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-104">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="81150-105">구성 파일은 배포 후 서비스를 구성해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="81150-105">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="81150-106">구성 파일을 사용할 경우 IT 전문가가 구성 파일을 업데이트하기만 하면 되고 다시 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-106">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="81150-107">하지만 구성 파일은 관리하기가 복잡하고 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-107">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="81150-108">구성 파일 디버깅은 지원되지 않으며 구성 요소는 이름으로 참조되므로 구성 파일을 작성하기가 어렵고 오류가 발생하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-108">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="81150-109">WCF를 사용 하면 코드에서 서비스를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-109">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="81150-110">이전 버전의 WCF (4.0 및 이전 버전)에서 코드의 서비스 구성은 자체 호스팅 시나리오에서 쉽기 때문에 클래스를 통해 <xref:System.ServiceModel.ServiceHost> ServiceHost를 호출 하기 전에 끝점과 동작을 구성할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-110">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="81150-111">그러나 웹 호스팅 시나리오에서는 <xref:System.ServiceModel.ServiceHost> 클래스에 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-111">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="81150-112">웹 호스팅 서비스를 구성하려면 `System.ServiceModel.ServiceHostFactory`를 만들고 필요한 구성을 수행하는 <xref:System.ServiceModel.Activation.ServiceHostFactory>를 만들어야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-112">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="81150-113">.NET 4.5부터 WCF는 자체 호스팅 서비스와 웹 호스팅 서비스를 코드에서 더 쉽게 구성 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="81150-113">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="81150-114">Configure 메서드</span><span class="sxs-lookup"><span data-stu-id="81150-114">The Configure method</span></span>  
 <span data-ttu-id="81150-115">서비스 구현 클래스에서 다음 서명으로 `Configure`라는 공용 정적 메서드를 정의하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81150-115">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="81150-116">Configure 메서드는 개발자가 엔드포인트 및 동작을 추가할 수 있도록 해 주는 <xref:System.ServiceModel.ServiceConfiguration> 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81150-116">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="81150-117">이 메서드는 서비스 호스트가 열리기 전에 WCF에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81150-117">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="81150-118">정의할 때 app.config 또는 web.config 파일에 지정된 서비스 구성 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="81150-118">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="81150-119">다음 코드 조각은 `Configure` 메서드를 정의하는 방법과 서비스 엔드포인트, 엔드포인트 동작 및 서비스 동작을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81150-119">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return $"You entered: {value}";
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="81150-120">서비스에 https와 같은 프로토콜을 사용하려면 프로토콜을 사용하는 엔드포인트를 명시적으로 추가하거나 프로토콜 및 정의된 각 서비스 계약과 호환되는 각 기본 주소에 엔드포인트를 추가하는 ServiceConfiguration.EnableProtocol(Binding)을 호출하여 엔드포인트를 자동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-120">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="81150-121">다음 코드에서는 ServiceConfiguration.EnableProtocol 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81150-121">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1
{
    public string GetData(int value);
    public static void Configure(ServiceConfiguration config)
    {
        // Enable "Add Service Reference" support
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });
       // set up support for http, https, net.tcp, net.pipe
       config.EnableProtocol(new BasicHttpBinding());
       config.EnableProtocol(new BasicHttpsBinding());
       config.EnableProtocol(new NetTcpBinding());
       config.EnableProtocol(new NetNamedPipeBinding());
       // add an extra BasicHttpBinding endpoint at http:///basic
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");
    }
}
```  
  
 <span data-ttu-id="81150-122"><> 섹션의 설정은 `protocolMappings` 프로그래밍 방식으로에 응용 프로그램 끝점을 추가 하지 않은 경우에만 사용 됩니다 <xref:System.ServiceModel.ServiceConfiguration> . 필요에 따라를 호출 하 여 기본 응용 프로그램 구성 파일에서 서비스 구성을 로드 <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> 한 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-122">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="81150-123"><xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> 클래스를 사용하면 중앙 집중식 구성에서 구성을 로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81150-123">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="81150-124">다음 코드에서는 이를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81150-124">The following code illustrates how to implement this:</span></span>  
  
```csharp
public class Service1 : IService1
{
    public void DoWork();
    public static void Configure(ServiceConfiguration config)
    {
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));
    }
}  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="81150-125">는 <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> `host` <>의 <> 태그 내에서 <> 설정을 무시 `service` `system.serviceModel` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81150-125">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="81150-126">개념적으로 <`host`>는 서비스 구성이 아니라 호스트 구성에 대 한 것 이며, 구성 메서드가 실행 되기 전에 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81150-126">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81150-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81150-127">See also</span></span>

- [<span data-ttu-id="81150-128">구성 파일을 사용하여 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="81150-128">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="81150-129">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="81150-129">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
- [<span data-ttu-id="81150-130">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="81150-130">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="81150-131">구성</span><span class="sxs-lookup"><span data-stu-id="81150-131">Configuration</span></span>](./samples/configuration-sample.md)
- [<span data-ttu-id="81150-132">IIS 및 WAS에서 구성 기반 활성화</span><span class="sxs-lookup"><span data-stu-id="81150-132">Configuration-Based Activation in IIS and WAS</span></span>](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="81150-133">구성 및 메타데이터 지원</span><span class="sxs-lookup"><span data-stu-id="81150-133">Configuration and Metadata Support</span></span>](./extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="81150-134">구성</span><span class="sxs-lookup"><span data-stu-id="81150-134">Configuration</span></span>](./diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="81150-135">방법: 구성에서 서비스 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="81150-135">How to: Specify a Service Binding in Configuration</span></span>](how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="81150-136">방법: 구성에서 서비스 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="81150-136">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="81150-137">방법: 구성 파일을 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="81150-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="81150-138">방법: 구성에서 클라이언트 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="81150-138">How to: Specify a Client Binding in Configuration</span></span>](how-to-specify-a-client-binding-in-configuration.md)
