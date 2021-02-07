---
description: '자세히 알아보기: 표준 끝점 사용'
title: 표준 엔드포인트 사용
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 804fdd84d3f6ff6f961aed81e8bd14cf8c43063c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685415"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="66be0-103">표준 엔드포인트 사용</span><span class="sxs-lookup"><span data-stu-id="66be0-103">Usage of Standard Endpoints</span></span>

<span data-ttu-id="66be0-104">이 샘플에서는 서비스 구성 파일에서 표준 엔드포인트를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-104">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="66be0-105">표준 엔드포인트를 사용하면 사용자는 주소, 바인딩 및 계약 조합을 설명하는 단일 속성과 엔드포인트에 관련된 추가 속성을 사용하여 엔드포인트 정의를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-105">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="66be0-106">이 샘플에서는 사용자 지정 표준 엔드포인트를 정의 및 구현하는 방법과 엔드포인트의 특정 속성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-106">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="66be0-107">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="66be0-107">Sample Details</span></span>

<span data-ttu-id="66be0-108">서비스 엔드포인트는 주소, 바인딩 및 계약의 세 매개 변수를 제공하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-108">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="66be0-109">제공할 수 있는 다른 매개 변수로는 동작 구성, 헤더 및 수신 대기 URI 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-109">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="66be0-110">일부 경우에는 주소, 바인딩 및 계약의 일부 또는 모두에 변경할 수 없는 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-110">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="66be0-111">이러한 이유로 표준 엔드포인트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-111">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="66be0-112">이러한 엔드포인트의 몇 가지 예로는 메타데이터 교환 엔드포인트와 검색 엔드포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-112">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="66be0-113">표준 엔드포인트를 사용하면 고정 특성의 정보를 제공하거나 고유한 표준 엔드포인트를 만들 필요 없이 서비스 엔드포인트의 구성을 그대로 사용하여 유용성을 향상시킬 수도 있습니다. 예를 들어 적절한 기본값 집합을 제공하여 구성 파일의 복잡성을 줄임으로써 유용성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-113">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="66be0-114">이 샘플은 두 개의 표준 엔드포인트를 정의하는 서비스 및 이 서비스와 통신하는 클라이언트의 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-114">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="66be0-115">구성 파일에서 서비스에 대한 표준 엔드포인트가 정의되는 방법은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-115">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="66be0-116">서비스에 대해 정의되는 첫 번째 엔드포인트는 `customEndpoint` 종류로, `<standardEndpoints>` 섹션에서 해당 정의를 볼 수 있으며 `property` 속성 값은 `true`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-116">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="66be0-117">이 엔드포인트는 새 속성으로 사용자 지정된 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-117">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="66be0-118">두 번째 엔드포인트는 주소, 바인딩 및 계약의 값이 고정된 메타데이터 엔드포인트에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-118">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="66be0-119">표준 엔드포인트 요소를 정의하려면 `StandardEndpointElement`에서 파생된 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-119">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="66be0-120">이 샘플에서는 `CustomEndpointElement`가 다음 예제와 같이 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-120">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

<span data-ttu-id="66be0-121">`CreateServiceEndpoint` 함수에서는 `CustomEndpoint` 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-121">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="66be0-122">해당 정의는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-122">Its definition is shown in the following example:</span></span>

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 <span data-ttu-id="66be0-123">서비스와 클라이언트 간의 통신을 수행하기 위해 서비스에 대한 서비스 참조가 클라이언트에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-123">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="66be0-124">샘플이 빌드되어 실행되면 서비스가 실행되고 클라이언트가 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-124">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="66be0-125">서비스 참조는 서비스에 변경 사항이 있을 때마다 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-125">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="66be0-126">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="66be0-126">To use this sample</span></span>

1. <span data-ttu-id="66be0-127">Visual Studio 2012을 사용 하 여 StandardEndpoints .sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-127">Using Visual Studio 2012, open the StandardEndpoints.sln file.</span></span>

2. <span data-ttu-id="66be0-128">여러 개의 프로젝트가 시작되도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-128">Enable multiple projects to start up.</span></span>

    1. <span data-ttu-id="66be0-129">**솔루션 탐색기** 에서 표준 끝점 솔루션을 마우스 오른쪽 단추로 클릭 한 다음 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-129">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2. <span data-ttu-id="66be0-130">**공용 속성** 에서 **시작 프로젝트** 를 선택한 다음 **여러 개의 시작 프로젝트** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-130">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3. <span data-ttu-id="66be0-131">서비스 프로젝트를 목록의 시작 부분으로 이동 하 고 **작업** 을 **시작** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-131">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4. <span data-ttu-id="66be0-132">서비스 프로젝트를 실행 하 고 **작업** 을 **시작** 으로 설정 하 여 클라이언트 프로젝트를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-132">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="66be0-133">이렇게 하면 Client 프로젝트가 Service 프로젝트 다음에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-133">This specifies that the Client project is executed after the Service project.</span></span>

3. <span data-ttu-id="66be0-134">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-134">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="66be0-135">이러한 단계가 작동 하지 않는 경우 다음 단계를 사용 하 여 환경이 올바르게 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-135">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="66be0-136">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="66be0-137">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="66be0-137">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="66be0-138">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="66be0-138">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66be0-139">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="66be0-140">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="66be0-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="66be0-141">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-141">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="66be0-142">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66be0-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
