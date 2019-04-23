---
title: 표준 엔드포인트 사용
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 4ef0714acad12db1414e34fbb476b4ae7d1d9fb2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977082"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="a2057-102">표준 엔드포인트 사용</span><span class="sxs-lookup"><span data-stu-id="a2057-102">Usage of Standard Endpoints</span></span>

<span data-ttu-id="a2057-103">이 샘플에서는 서비스 구성 파일에서 표준 엔드포인트를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="a2057-104">표준 엔드포인트를 사용하면 사용자는 주소, 바인딩 및 계약 조합을 설명하는 단일 속성과 엔드포인트에 관련된 추가 속성을 사용하여 엔드포인트 정의를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="a2057-105">이 샘플에서는 사용자 지정 표준 엔드포인트를 정의 및 구현하는 방법과 엔드포인트의 특정 속성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="a2057-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="a2057-106">Sample Details</span></span>

<span data-ttu-id="a2057-107">서비스 엔드포인트는 주소, 바인딩 및 계약의 세 매개 변수를 제공하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="a2057-108">제공할 수 있는 다른 매개 변수로는 동작 구성, 헤더 및 수신 대기 URI 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="a2057-109">일부 경우에는 주소, 바인딩 및 계약의 일부 또는 모두에 변경할 수 없는 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="a2057-110">이러한 이유로 표준 엔드포인트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="a2057-111">이러한 엔드포인트의 몇 가지 예로는 메타데이터 교환 엔드포인트와 검색 엔드포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="a2057-112">표준 엔드포인트를 사용하면 고정 특성의 정보를 제공하거나 고유한 표준 엔드포인트를 만들 필요 없이 서비스 엔드포인트의 구성을 그대로 사용하여 유용성을 향상시킬 수도 있습니다. 예를 들어 적절한 기본값 집합을 제공하여 구성 파일의 복잡성을 줄임으로써 유용성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="a2057-113">이 샘플은 두 개의 표준 엔드포인트를 정의하는 서비스 및 이 서비스와 통신하는 클라이언트의 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="a2057-114">구성 파일에서 서비스에 대한 표준 엔드포인트가 정의되는 방법은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

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

<span data-ttu-id="a2057-115">서비스에 대해 정의되는 첫 번째 엔드포인트는 `customEndpoint` 종류로, `<standardEndpoints>` 섹션에서 해당 정의를 볼 수 있으며 `property` 속성 값은 `true`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="a2057-116">이 엔드포인트는 새 속성으로 사용자 지정된 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="a2057-117">두 번째 엔드포인트는 주소, 바인딩 및 계약의 값이 고정된 메타데이터 엔드포인트에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="a2057-118">표준 엔드포인트 요소를 정의하려면 `StandardEndpointElement`에서 파생된 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="a2057-119">이 샘플에서는 `CustomEndpointElement`가 다음 예제와 같이 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

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

<span data-ttu-id="a2057-120">`CreateServiceEndpoint` 함수에서는 `CustomEndpoint` 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="a2057-121">해당 정의 다음 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-121">Its definition is shown in the following example:</span></span>

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

 <span data-ttu-id="a2057-122">서비스와 클라이언트 간의 통신을 수행하기 위해 서비스에 대한 서비스 참조가 클라이언트에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="a2057-123">샘플이 빌드되어 실행되면 서비스가 실행되고 클라이언트가 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="a2057-124">서비스 참조는 서비스에 변경 사항이 있을 때마다 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-124">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="a2057-125">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a2057-125">To use this sample</span></span>

1. <span data-ttu-id="a2057-126">StandardEndpoints.sln 파일을 열고 Visual Studio 2012를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-126">Using Visual Studio 2012, open the StandardEndpoints.sln file.</span></span>

2. <span data-ttu-id="a2057-127">여러 개의 프로젝트가 시작되도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-127">Enable multiple projects to start up.</span></span>

    1.  <span data-ttu-id="a2057-128">**솔루션 탐색기**Standard Endpoints 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택한 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2.  <span data-ttu-id="a2057-129">**공용 속성**를 선택 **시작 프로젝트**를 클릭 하 고 **여러 개의 시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3.  <span data-ttu-id="a2057-130">서비스 프로젝트를 사용 하 여 목록의 처음으로 이동 합니다.는 **동작** 로 설정 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4.  <span data-ttu-id="a2057-131">사용 하 여 클라이언트 프로젝트를 Service 프로젝트 다음에 이동 합니다 **동작** 로 설정 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="a2057-132">이렇게 하면 Client 프로젝트가 Service 프로젝트 다음에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-132">This specifies that the Client project is executed after the Service project.</span></span>

3. <span data-ttu-id="a2057-133">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-133">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="a2057-134">이 단계 작동 하지 않으면는 사용자 환경에 올바르게 설정 되었는지, 다음 단계를 사용 하 여 있는지 확인 한 후:</span><span class="sxs-lookup"><span data-stu-id="a2057-134">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="a2057-135">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="a2057-136">지침에 따라 솔루션을 빌드하려면 [Building Windows Communication Foundation Samples](building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="a2057-137">단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침을 따릅니다 [Windows Communication Foundation 샘플 실행](running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2057-138">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a2057-139">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a2057-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a2057-140">이 디렉터리가 없으면 이동할 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="a2057-140">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a2057-141">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2057-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
