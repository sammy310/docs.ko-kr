---
title: WCF 클라이언트를 사용하여 서비스 액세스
description: WCF 서비스에 대 한 WCF 클라이언트 프록시를 만드는 방법에 대해 알아봅니다. 클라이언트 응용 프로그램은 클라이언트 프록시를 사용 하 여 서비스와 통신 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 25446a89a0b5657d32d77e2d0d57f58f36bed71b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245546"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="2a658-104">WCF 클라이언트를 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="2a658-104">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="2a658-105">서비스를 만든 후 다음 단계는 WCF 클라이언트 프록시를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-105">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="2a658-106">클라이언트 응용 프로그램은 WCF 클라이언트 프록시를 사용 하 여 서비스와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-106">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="2a658-107">클라이언트 응용 프로그램은 일반적으로 서비스의 메타 데이터를 가져와 서비스를 호출 하는 데 사용할 수 있는 WCF 클라이언트 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-107">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="2a658-108">WCF 클라이언트를 만드는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-108">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="2a658-109">서비스 코드를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-109">Compile the service code.</span></span>

2. <span data-ttu-id="2a658-110">WCF 클라이언트 프록시를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-110">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="2a658-111">WCF 클라이언트 프록시를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-111">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="2a658-112">WCF 클라이언트 프록시는 서비스 모델 메타 데이터 유틸리티 도구 (SvcUtil.exe)를 사용 하 여 수동으로 생성할 수 있습니다. 자세한 내용은 [ServiceModel Metadata Utility tool (Svcutil.exe) (영문)](servicemodel-metadata-utility-tool-svcutil-exe.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a658-112">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="2a658-113">WCF 클라이언트 프록시는 **서비스 참조 추가** 기능을 사용 하 여 Visual Studio 내에서 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-113">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="2a658-114">어떤 방법으로 WCF 클라이언트 프록시를 생성하더라도 서비스가 실행되고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-114">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="2a658-115">자체 호스팅 서비스의 경우 호스트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-115">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="2a658-116">서비스가 IIS/WAS에서 호스트되는 경우에는 별도의 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-116">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="2a658-117">ServiceModel Metadata 유틸리티 도구</span><span class="sxs-lookup"><span data-stu-id="2a658-117">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="2a658-118">[ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 는 메타 데이터에서 코드를 생성 하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-118">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="2a658-119">다음 사용은 기본 Svcutil.exe 명령 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-119">The following use is an example of a basic Svcutil.exe command.</span></span>

```console
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="2a658-120">또는 Svcutil.exe에 파일 시스템의 WSDL(웹 서비스 기술 언어) 및 XSD(XML 스키마 정의 언어) 파일을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-120">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```console
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="2a658-121">결과는 클라이언트 응용 프로그램이 서비스를 호출 하는 데 사용할 수 있는 WCF 클라이언트 코드를 포함 하는 코드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-121">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="2a658-122">이 도구를 사용하여 구성 파일을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-122">You can also use the tool to generate configuration files.</span></span>

```console
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="2a658-123">파일 이름을 제공하면 해당 이름이 출력 파일의 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-123">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="2a658-124">두 개의 파일 이름을 제공하면 첫 번째 파일은 입력 구성 파일로, 해당 내용이 생성된 구성과 병합되어 두 번째 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-124">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="2a658-125">구성에 대 한 자세한 내용은 [서비스에 대 한 바인딩 구성](configuring-bindings-for-wcf-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a658-125">For more information about configuration, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a658-126">보안되지 않은 메타데이터 요청은 보안되지 않은 네트워크 요청과 동일한 방식으로 특정 위험을 노출합니다. 통신하는 엔드포인트가 실제로 주장되는 엔드포인트인지 확실하지 않을 경우 검색한 정보가 악성 서비스의 메타데이터일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-126">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="2a658-127">Visual Studio의 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="2a658-127">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="2a658-128">서비스를 실행 하는 동안 WCF 클라이언트 프록시를 포함할 프로젝트를 마우스 오른쪽 단추로 클릭 하 **Add**고  >  **서비스 참조**추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-128">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="2a658-129">**서비스 참조 추가 대화 상자**에서 호출 하려는 서비스에 대 한 URL을 입력 하 고 **이동** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-129">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="2a658-130">대화 상자에 지정한 주소에서 사용할 수 있는 서비스 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-130">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="2a658-131">서비스를 두 번 클릭 하 여 사용할 수 있는 계약 및 작업을 확인 하 고 생성 된 코드의 네임 스페이스를 지정한 다음 **확인** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-131">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="2a658-132">예제</span><span class="sxs-lookup"><span data-stu-id="2a658-132">Example</span></span>
 <span data-ttu-id="2a658-133">다음 코드 예제에서는 서비스에 대해 만들어진 서비스 계약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-133">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="2a658-134">ServiceModel Metadata 유틸리티 도구와 Visual Studio의 **서비스 참조 추가** 는 다음과 같은 WCF 클라이언트 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-134">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="2a658-135">클래스는 제네릭 <xref:System.ServiceModel.ClientBase%601> 클래스에서 상속되며 `ICalculator` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-135">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="2a658-136">또한 이 도구는 여기에 표시되지 않은 `ICalculator` 인터페이스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-136">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="2a658-137">WCF 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="2a658-137">Using the WCF Client</span></span>
 <span data-ttu-id="2a658-138">WCF 클라이언트를 사용 하려면 다음 코드에 표시 된 것 처럼 WCF 클라이언트의 인스턴스를 만들고 해당 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-138">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="2a658-139">클라이언트에서 Throw된 예외 디버깅</span><span class="sxs-lookup"><span data-stu-id="2a658-139">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="2a658-140">WCF 클라이언트에서 throw 된 많은 예외는 서비스의 예외로 인해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-140">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="2a658-141">몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-141">Some examples of this are:</span></span>

- <span data-ttu-id="2a658-142"><xref:System.Net.Sockets.SocketException>: 기존 연결이 원격 호스트에 의해 강제로 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-142"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

- <span data-ttu-id="2a658-143"><xref:System.ServiceModel.CommunicationException>: 기본 연결이 예기치 않게 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-143"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

- <span data-ttu-id="2a658-144"><xref:System.ServiceModel.CommunicationObjectAbortedException>: 소켓 연결이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-144"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="2a658-145">이는 메시지 처리 오류, 원격 호스트에 의해 초과되는 수신 제한 시간 또는 기본 네트워크 리소스 문제로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-145">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="2a658-146">이러한 형식의 예외가 발생할 때 가장 좋은 문제 해결 방법은 서비스측에 추적 기능을 설정하고 발생한 예외를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a658-146">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="2a658-147">추적에 대 한 자세한 내용은 추적 및 [사용 하 여 응용 프로그램 문제 해결](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)을 [참조 하세요.](./diagnostics/tracing/index.md)</span><span class="sxs-lookup"><span data-stu-id="2a658-147">For more information about tracing, see [Tracing](./diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a658-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a658-148">See also</span></span>

- [<span data-ttu-id="2a658-149">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="2a658-149">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="2a658-150">방법: 이중 계약을 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="2a658-150">How to: Access Services with a Duplex Contract</span></span>](./feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="2a658-151">방법: 비동기적으로 서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="2a658-151">How to: Call Service Operations Asynchronously</span></span>](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="2a658-152">방법: 단방향 및 요청-회신 계약을 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="2a658-152">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](./feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="2a658-153">방법: WSE 3.0 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="2a658-153">How to: Access a WSE 3.0 Service</span></span>](./feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="2a658-154">생성된 클라이언트 코드 이해</span><span class="sxs-lookup"><span data-stu-id="2a658-154">Understanding Generated Client Code</span></span>](./feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="2a658-155">방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상</span><span class="sxs-lookup"><span data-stu-id="2a658-155">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="2a658-156">클라이언트 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="2a658-156">Specifying Client Run-Time Behavior</span></span>](specifying-client-run-time-behavior.md)
- [<span data-ttu-id="2a658-157">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="2a658-157">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
