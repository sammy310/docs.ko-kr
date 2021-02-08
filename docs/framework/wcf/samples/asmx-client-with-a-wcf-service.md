---
description: '자세히 알아보기: WCF 서비스를 사용 하는 ASMX 클라이언트'
title: WCF 서비스를 사용한 ASMX 클라이언트
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: b9f561f6651c591556f821478c4c4bfd7d7da23d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778921"
---
# <a name="asmx-client-with-a-wcf-service"></a><span data-ttu-id="313b0-103">WCF 서비스를 사용한 ASMX 클라이언트</span><span class="sxs-lookup"><span data-stu-id="313b0-103">ASMX Client with a WCF Service</span></span>

<span data-ttu-id="313b0-104">이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 서비스를 만든 다음 ASMX 클라이언트와 같은 WCF가 아닌 클라이언트에서 서비스에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-104">This sample demonstrates how to create a service using Windows Communication Foundation (WCF) and then access the service from a non-WCF client, such as an ASMX client.</span></span>

> [!NOTE]
> <span data-ttu-id="313b0-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="313b0-106">이 샘플은 IIS(인터넷 정보 서비스)에 의해 호스트되는 클라이언트 콘솔 프로그램(.exe) 및 서비스 라이브러리(.dll)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="313b0-107">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-107">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="313b0-108">계약은 수학 연산(`ICalculator`, `Add`, `Subtract` 및 `Multiply`)을 노출하는 `Divide` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-108">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="313b0-109">ASMX 클라이언트에서 수학 작업을 동기적으로 요청하면 서비스에서 결과로 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-109">The ASMX client makes synchronous requests to a math operation and the service replies with the result.</span></span>

<span data-ttu-id="313b0-110">서비스는 다음 코드에 정의된 대로 `ICalculator` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-110">The service implements an `ICalculator` contract as defined in the following code.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="313b0-111"><xref:System.Runtime.Serialization.DataContractSerializer> 및 <xref:System.Xml.Serialization.XmlSerializer>는 CLR 형식을 XML 표현에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-111">The <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Xml.Serialization.XmlSerializer> map CLR types to an XML representation.</span></span> <span data-ttu-id="313b0-112"><xref:System.Runtime.Serialization.DataContractSerializer>에서는 일부 XML 표현을 XmlSerializer와 다르게 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-112">The <xref:System.Runtime.Serialization.DataContractSerializer> interprets some XML representations differently than XmlSerializer.</span></span> <span data-ttu-id="313b0-113">Wsdl.exe와 같은 WCF가 아닌 프록시 생성기는 XmlSerializer를 사용 하는 경우 더 사용할 수 있는 인터페이스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-113">Non-WCF proxy generators, such as Wsdl.exe, generate a more usable interface when the XmlSerializer is being used.</span></span> <span data-ttu-id="313b0-114">는 <xref:System.ServiceModel.XmlSerializerFormatAttribute> `ICalculator` CLR 형식을 XML에 매핑하는 데 XmlSerializer를 사용 하도록 인터페이스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-114">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> is applied to the `ICalculator` interface, to ensure that the XmlSerializer is used for mapping CLR types to XML.</span></span> <span data-ttu-id="313b0-115">이 서비스 구현에서는 해당 결과를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-115">The service implementation calculates and returns the appropriate result.</span></span>

<span data-ttu-id="313b0-116">서비스는 구성 파일(Web.config)을 사용하여 서비스와 통신하기 위한 단일 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-116">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="313b0-117">엔드포인트는 하나의 주소, 바인딩 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="313b0-118">서비스에서는 IIS(인터넷 정보 서비스) 호스트에서 제공되는 기본 주소에서 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-118">The service exposes the endpoint at the base address provided by the Internet Information Services (IIS) host.</span></span> <span data-ttu-id="313b0-119">`binding` 특성은 다음 샘플 구성에 표시된 것과 같이 WS-I BasicProfile 1.1과 호환되는 SOAP 1.1을 사용하는 HTTP 통신을 제공하는 basicHttpBinding으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-119">The `binding` attribute is set to basicHttpBinding that provides HTTP communications using SOAP 1.1, which is compliant with WS-I BasicProfile 1.1 as shown in the following sample configuration.</span></span>

```xml
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->
    <endpoint address=""
              binding="basicHttpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
</services>
```

<span data-ttu-id="313b0-120">ASMX 클라이언트는 WSDL (웹 서비스 기술 언어) 유틸리티 (Wsdl.exe)에서 생성 된 형식화 된 프록시를 사용 하 여 WCF 서비스와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-120">The ASMX client communicates with the WCF service using a typed proxy that is generated by the Web Services Description Language (WSDL) utility (Wsdl.exe).</span></span> <span data-ttu-id="313b0-121">형식이 지정된 프록시는 generatedClient.cs 파일에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-121">The typed proxy is contained in the file generatedClient.cs.</span></span> <span data-ttu-id="313b0-122">WSDL 유틸리티는 지정된 서비스의 메타데이터를 검색하여 통신할 클라이언트에서 사용되는, 형식이 지정된 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-122">The WSDL utility retrieves metadata for the specified service and generates a typed proxy for use by a client to communicate.</span></span> <span data-ttu-id="313b0-123">기본적으로 프레임워크에서는 메타데이터를 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-123">By default, the framework does not expose any metadata.</span></span> <span data-ttu-id="313b0-124">프록시를 생성 하는 데 필요한 메타 데이터를 노출 하려면 [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) `httpGetEnabled` `True` 다음 구성에 표시 된 것 처럼를 추가 하 고 특성을로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-124">To expose the metadata required to generate the proxy, you must add a [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) and set its `httpGetEnabled` attribute to `True` as shown in the following configuration.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <!-- Setting httpGetEnabled to True on the serviceMetadata
           behavior exposes the service's wsdl at <base address>?wsdl :
           http://localhost/servicemodelsamples/service.svc?wsdl -->
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="313b0-125">클라이언트 디렉터리의 명령 프롬프트에서 다음 명령을 실행하여 형식화된 프록시를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-125">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>

```console
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl
```

<span data-ttu-id="313b0-126">생성된, 형식이 지정된 프록시를 사용하면 클라이언트에서 적절한 주소를 구성하여 지정된 서비스 엔드포인트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-126">By using the generated typed proxy, the client can access a given service endpoint by configuring the appropriate address.</span></span> <span data-ttu-id="313b0-127">클라이언트에서는 구성 파일(App.config)을 사용하여 통신할 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-127">The client uses a configuration file (App.config) to specify the endpoint to communicate with.</span></span>

```xml
<appSettings>
  <add key="CalculatorServiceAddress"
       value="http://localhost/ServiceModelSamples/service.svc"/>
</appSettings>
```

<span data-ttu-id="313b0-128">클라이언트 구현에서는 형식이 지정된 프록시의 인스턴스를 구성하여 서비스와의 통신을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-128">The client implementation constructs an instance of the typed proxy to begin communicating with the service.</span></span>

```csharp
// Create a client to the CalculatorService.
using (CalculatorService client = new CalculatorService())
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

    // Call the Subtract service operation.
    value1 = 145.00D;
    value2 = 76.54D;
    result = client.Subtract(value1, value2);
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

    // Call the Multiply service operation.
    value1 = 9.00D;
    value2 = 81.25D;
    result = client.Multiply(value1, value2);
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

    // Call the Divide service operation.
    value1 = 22.00D;
    value2 = 7.00D;
    result = client.Divide(value1, value2);
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

}

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

<span data-ttu-id="313b0-129">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-129">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="313b0-130">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-130">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="313b0-131">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="313b0-131">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="313b0-132">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="313b0-133">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="313b0-134">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="313b0-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="313b0-135">복합 데이터 형식을 전달 하 고 반환 하는 방법에 대 한 자세한 내용은 [Windows Forms 클라이언트의 데이터 바인딩](data-binding-in-a-windows-forms-client.md), [Windows Presentation Foundation 클라이언트의 데이터 바인딩](data-binding-in-a-wpf-client.md)및 [ASP.NET 클라이언트의 데이터](data-binding-in-an-aspnet-client.md) 바인딩을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="313b0-135">For more information about passing and returning complex data types see: [Data Binding in a Windows Forms Client](data-binding-in-a-windows-forms-client.md), [Data Binding in a Windows Presentation Foundation Client](data-binding-in-a-wpf-client.md), and [Data Binding in an ASP.NET Client](data-binding-in-an-aspnet-client.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="313b0-136">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="313b0-137">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="313b0-137">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="313b0-138">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="313b0-139">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="313b0-139">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`
