---
description: '자세한 정보: 사용자 지정 메시지 인터셉터'
title: 사용자 지정 메시지 인터셉터
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 916e608e9f5bee66c5d2b56304af0255ace5b827
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752472"
---
# <a name="custom-message-interceptor"></a><span data-ttu-id="246dd-103">사용자 지정 메시지 인터셉터</span><span class="sxs-lookup"><span data-stu-id="246dd-103">Custom Message Interceptor</span></span>

<span data-ttu-id="246dd-104">이 샘플에서는 채널 확장성 모델의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-104">This sample demonstrates the use of the channel extensibility model.</span></span> <span data-ttu-id="246dd-105">특히 채널 팩터리 및 채널 수신기를 만드는 사용자 지정 바인딩 요소를 구현하여 런타임 스택의 특정 지점에서 들어오고 보내는 모든 메시지를 가로채는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-105">In particular, it shows how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span> <span data-ttu-id="246dd-106">또한 이 샘플에는 이 사용자 지정 팩터리의 사용을 보여 주는 클라이언트와 서버도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-106">The sample also includes a client and server that demonstrate the use of these custom factories.</span></span>  
  
 <span data-ttu-id="246dd-107">이 샘플에서는 클라이언트와 서비스 모두가 콘솔 프로그램(.exe)입니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-107">In this sample, both the client and the service are console programs (.exe).</span></span> <span data-ttu-id="246dd-108">클라이언트와 서비스 모두 사용자 지정 바인딩 요소 및 관련 런타임 개체를 포함하는 공용 라이브러리(.dll)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-108">The client and service both make use of a common library (.dll) that contains the custom binding element and its associated run-time objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="246dd-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="246dd-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="246dd-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="246dd-111">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="246dd-112">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="246dd-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-113">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 <span data-ttu-id="246dd-114">이 샘플에서는 채널 프레임 워크 및 WCF 모범 사례를 사용 하 여 WCF (Windows Communication Foundation)에서 사용자 지정 계층화 된 채널을 만드는 권장 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-114">The sample describes the recommended procedure for creating a custom layered channel in Windows Communication Foundation (WCF), by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="246dd-115">사용자 지정 계층화된 채널을 만드는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-115">The steps to create a custom layered channel are as follows:</span></span>  
  
1. <span data-ttu-id="246dd-116">채널 팩터리 및 채널 수신기에서 지원할 채널 셰이프를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-116">Decide which of the channel shapes your channel factory and channel listener will support.</span></span>  
  
2. <span data-ttu-id="246dd-117">채널 셰이프를 지원하는 채널 팩터리 및 채널 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-117">Create a channel factory and a channel listener that support your channel shapes.</span></span>  
  
3. <span data-ttu-id="246dd-118">사용자 지정 계층화된 채널을 채널 스택에 추가하는 바인딩 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-118">Add a binding element that adds the custom layered channel to a channel stack.</span></span>  
  
4. <span data-ttu-id="246dd-119">새 바인딩 요소가 구성 시스템에 노출되도록 바인딩 요소 확장명 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-119">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
## <a name="channel-shapes"></a><span data-ttu-id="246dd-120">채널 셰이프</span><span class="sxs-lookup"><span data-stu-id="246dd-120">Channel Shapes</span></span>  

 <span data-ttu-id="246dd-121">사용자 지정 계층화된 채널을 작성하는 첫 번째 단계는 채널에 필요한 셰이프를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-121">The first step in writing a custom layered channel is to decide which shapes are required for the channel.</span></span> <span data-ttu-id="246dd-122">메시지 검사자를 위해 아래의 계층이 지원하는 모든 셰이프를 지원합니다. 예를 들어, 아래의 계층이 <xref:System.ServiceModel.Channels.IOutputChannel> 및 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>을 빌드할 수 있는 경우 <xref:System.ServiceModel.Channels.IOutputChannel> 및 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>도 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-122">For our message inspector, we support any shape that the layer below us supports (for example, if the layer below us can build <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, then we also expose <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span></span>  
  
## <a name="channel-factory-and-listener-factory"></a><span data-ttu-id="246dd-123">채널 팩터리 및 수신기 팩터리</span><span class="sxs-lookup"><span data-stu-id="246dd-123">Channel Factory and Listener Factory</span></span>  

 <span data-ttu-id="246dd-124">사용자 지정 계층화된 채널을 작성하는 두 번째 단계는 클라이언트 채널을 위한 <xref:System.ServiceModel.Channels.IChannelFactory> 구현 및 서비스 채널을 위한 <xref:System.ServiceModel.Channels.IChannelListener> 구현을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-124">The next step in writing a custom layered channel is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span>  
  
 <span data-ttu-id="246dd-125">이 클래스는 내부 팩터리 및 수신기를 받고 `OnCreateChannel` 및 `OnAcceptChannel` 호출을 제외한 모두를 내부 팩터리 및 수신기에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-125">These classes take an inner factory and listener, and delegate all but the `OnCreateChannel` and `OnAcceptChannel` calls to the inner factory and listener.</span></span>  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{
    //...
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="246dd-126">바인딩 요소 추가</span><span class="sxs-lookup"><span data-stu-id="246dd-126">Adding a Binding Element</span></span>  

 <span data-ttu-id="246dd-127">이 샘플에서는 사용자 지정 바인딩 요소인 `InterceptingBindingElement`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-127">The sample defines a custom binding element: `InterceptingBindingElement`.</span></span> <span data-ttu-id="246dd-128">`InterceptingBindingElement` 는를 `ChannelMessageInterceptor` 입력으로 사용 하 고이를 `ChannelMessageInterceptor` 통해 전달 되는 메시지를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-128">`InterceptingBindingElement` takes a `ChannelMessageInterceptor` as an input, and uses this `ChannelMessageInterceptor` to manipulate messages that pass through it.</span></span> <span data-ttu-id="246dd-129">이는 public이어야 하는 유일한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-129">This is the only class that must be public.</span></span> <span data-ttu-id="246dd-130">팩터리, 수신기 및 채널 모두 public 런타임 인터페이스의 내부 구현이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-130">The factory, listener, and channels can all be internal implementations of the public run-time interfaces.</span></span>  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="246dd-131">구성 지원 추가</span><span class="sxs-lookup"><span data-stu-id="246dd-131">Adding Configuration Support</span></span>  

 <span data-ttu-id="246dd-132">바인딩 구성과 통합하기 위해 라이브러리에서는 구성 섹션 처리기를 바인딩 요소 확장 섹션으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-132">To integrate with binding configuration, the library defines a configuration section handler as a binding element extension section.</span></span> <span data-ttu-id="246dd-133">클라이언트 및 서버 구성 파일은 구성 시스템에 바인딩 요소 확장을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-133">The client and server configuration files must register the binding element extension with the configuration system.</span></span> <span data-ttu-id="246dd-134">구성 시스템에 바인딩 요소를 노출하려는 구현자는 이 클래스에서 파생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-134">Implementers that want to expose their binding element to the configuration system can derive from this class.</span></span>  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement
{
    //...
}
```  
  
## <a name="adding-policy"></a><span data-ttu-id="246dd-135">정책 추가</span><span class="sxs-lookup"><span data-stu-id="246dd-135">Adding Policy</span></span>  

 <span data-ttu-id="246dd-136">정책 시스템과 통합하기 위해 `InterceptingBindingElement`는 IPolicyExportExtension을 구현하여 정책 생성에 참여해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-136">To integrate with our policy system, `InterceptingBindingElement` implements IPolicyExportExtension to signal that we should participate in generating policy.</span></span> <span data-ttu-id="246dd-137">생성된 클라이언트에 정책을 가져오는 것을 지원하기 위해 사용자는 `InterceptingBindingElementImporter`의 파생 클래스를 등록하고 해당 정책을 사용하는 `CreateMessageInterceptor` 클래스를 생성하도록 `ChannelMessageInterceptor`()를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-137">To support importing policy on a generated client, the user can register a derived class of `InterceptingBindingElementImporter` and override `CreateMessageInterceptor`() to generate their policy-enabled `ChannelMessageInterceptor` class.</span></span>  
  
## <a name="example-droppable-message-inspector"></a><span data-ttu-id="246dd-138">예제: 삭제 가능한 메시지 검사자</span><span class="sxs-lookup"><span data-stu-id="246dd-138">Example: Droppable Message Inspector</span></span>  

 <span data-ttu-id="246dd-139">메시지를 삭제하는 `ChannelMessageInspector`의 구현 예제가 샘플에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-139">Included in the sample is an example implementation of `ChannelMessageInspector` which drops messages.</span></span>  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 <span data-ttu-id="246dd-140">다음과 같이 구성에서 이 예제에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-140">You can access it from configuration as follows:</span></span>  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="246dd-141">클라이언트와 서버 모두 이 새로 생성된 구성 섹션을 사용하여 런타임 채널 스택의 최하위(전송 수준 위)에 사용자 지정 팩터리를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-141">The client and server both use this newly created configuration section to insert the custom factories into the lowest-level of their run-time channel stacks (above the transport level).</span></span>  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="246dd-142">클라이언트에서는 `MessageInterceptor` 라이브러리를 사용하여 사용자 지정 헤더를 짝수 번호의 메시지에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-142">The client uses the `MessageInterceptor` library to add a custom header to even numbered messages.</span></span> <span data-ttu-id="246dd-143">한편 서비스는 `MessageInterceptor` 라이브러리를 사용하여 이 특수 헤더가 없는 메시지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-143">The service on the other hand uses `MessageInterceptor` library to drop any messages that do not have this special header.</span></span>  
  
 <span data-ttu-id="246dd-144">서비스와 클라이언트를 차례로 실행한 후 다음과 같은 클라이언트 출력이 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-144">You should see the following client output after running the service and then the client.</span></span>  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 <span data-ttu-id="246dd-145">클라이언트가 서로 다른 10가지 풍속을 서비스에 보고하지만, 그 중 절반에만 특수 헤더를 태그합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-145">The client reports 10 different wind speeds to the service, but only tags half of them with the special header.</span></span>  
  
 <span data-ttu-id="246dd-146">서비스에서는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-146">On the service, you should see the following output:</span></span>  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="246dd-147">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="246dd-147">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="246dd-148">다음 명령을 사용 하 여 ASP.NET 4.0을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-148">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="246dd-149">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-149">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="246dd-150">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="246dd-150">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="246dd-151">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="246dd-151">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="246dd-152">먼저 Service.exe를 실행한 다음 Client.exe를 실행하고 두 콘솔 창의 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="246dd-152">Run Service.exe first then run Client.exe and watch both console windows for output.</span></span>  
