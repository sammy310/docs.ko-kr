---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: 8dba147ace7ada221b5d274cd233e4b9618835d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585132"
---
# <a name="httpcookiesession"></a><span data-ttu-id="63912-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="63912-102">HttpCookieSession</span></span>
<span data-ttu-id="63912-103">이 샘플에서는 세션 관리에 HTTP 쿠키를 사용하기 위해 사용자 지정 프로토콜 채널을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63912-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="63912-104">이 채널을 통해 Windows Communication Foundation (WCF) 서비스와 ASMX 클라이언트 간 또는 WCF 클라이언트와 ASMX 서비스 간에 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-104">This channel enables communication between Windows Communication Foundation (WCF) services and ASMX clients or between WCF clients and ASMX services.</span></span>  
  
 <span data-ttu-id="63912-105">클라이언트에서 세션 기반 ASMX 웹 서비스의 웹 메서드를 호출 하는 경우 ASP.NET 엔진은 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-105">When a client calls a Web method in an ASMX Web service that is session-based, the ASP.NET engine does the following:</span></span>  
  
- <span data-ttu-id="63912-106">고유 ID(세션 ID)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-106">Generates a unique ID (session ID).</span></span>  
  
- <span data-ttu-id="63912-107">세션 개체를 생성하여 고유 ID에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-107">Generates the session object and associates it with the unique ID.</span></span>  
  
- <span data-ttu-id="63912-108">고유 ID를 Set-Cookie HTTP 응답 헤더에 추가하여 클라이언트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="63912-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
- <span data-ttu-id="63912-109">클라이언트로 보내는 세션 ID를 기반으로 이후의 호출에서 클라이언트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="63912-110">클라이언트는 이후에 서버로 보내는 요청에 이 세션 ID를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="63912-111">서버는 클라이언트가 보낸 세션 ID를 사용하여 현재 HTTP 컨텍스트에 적절한 세션 개체를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="63912-112">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="63912-113">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="63912-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="63912-114">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="63912-115">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="63912-116">HttpCookieSession 채널 메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="63912-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  
 <span data-ttu-id="63912-117">이 샘플에서는 ASMX와 같은 시나리오에 대해 세션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="63912-118">채널 스택의 맨 아래에는 <xref:System.ServiceModel.Channels.IRequestChannel> 및 <xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 HTTP 전송이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="63912-119">채널은 채널 스택의 상위 수준에 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="63912-120">이 샘플에서는 세션을 지원하는 두 개의 채널(<xref:System.ServiceModel.Channels.IRequestSessionChannel> 및 <xref:System.ServiceModel.Channels.IReplySessionChannel>)을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="63912-121">서비스 채널</span><span class="sxs-lookup"><span data-stu-id="63912-121">Service Channel</span></span>  
 <span data-ttu-id="63912-122">이 샘플은 `HttpCookieReplySessionChannelListener` 클래스에 서비스 채널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="63912-123">이 클래스는 <xref:System.ServiceModel.Channels.IChannelListener> 인터페이스를 구현하고 채널 스택의 하위 수준에 있는 <xref:System.ServiceModel.Channels.IReplyChannel> 채널을 <xref:System.ServiceModel.Channels.IReplySessionChannel>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="63912-124">이 프로세스는 다음과 같이 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-124">This process can be divided into the following parts:</span></span>  
  
- <span data-ttu-id="63912-125">채널 수신기가 열리면 채널 수신기는 내부 수신기로부터 내부 채널을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="63912-126">내부 수신기는 데이터그램 수신기이고 받은 채널의 수명은 수신기의 수명에서 분리되므로 내부 수신기를 닫고 내부 채널만 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```csharp  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- <span data-ttu-id="63912-127">열기 프로세스가 완료되면 내부 채널에서 메시지를 받도록 메시지 루프를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```csharp  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       this.completeReceiveCallback ??= new WaitCallback(CompleteReceiveCallback);
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- <span data-ttu-id="63912-128">메시지가 도착하면 서비스 채널은 세션 식별자를 확인하고 적절한 세션 채널로 디멀티플렉싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="63912-129">채널 수신기는 세션 식별자를 세션 채널 인스턴스에 매핑하는 사전을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```csharp  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="63912-130">`HttpCookieReplySessionChannel` 클래스는 <xref:System.ServiceModel.Channels.IReplySessionChannel>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="63912-131">채널 스택의 상위 수준에서는 <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> 메서드를 호출하여 이 세션에 대한 요청을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="63912-132">각 세션 채널에는 서비스 채널에서 채우는 개인 메시지 큐가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```csharp  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="63912-133">누군가가 <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> 메서드를 호출했지만 메시지 큐에 메시지가 없는 경우 채널은 지정된 시간 동안 대기한 후에 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="63912-134">이렇게 하면 WCF가 아닌 클라이언트에 대해 만들어진 세션 채널이 정리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-134">This cleans up the session channels created for non-WCF clients.</span></span>  
  
 <span data-ttu-id="63912-135">`channelMapping`을 사용하여 `ReplySessionChannels`를 추적하며, 받은 채널이 모두 닫힐 때까지 기본 `innerChannel`을 닫지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="63912-136">이렇게 하면 `HttpCookieReplySessionChannel`이 `HttpCookieReplySessionChannelListener`의 수명보다 오래 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="63912-137">받은 채널은 `OnClosed` 콜백을 통해 수신기에 대한 참조를 유지하므로 수신기에서 수행되는 가비지 수집에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="63912-138">클라이언트 채널</span><span class="sxs-lookup"><span data-stu-id="63912-138">Client channel</span></span>  
 <span data-ttu-id="63912-139">해당 클라이언트 채널은 `HttpCookieSessionChannelFactory` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="63912-140">채널을 만드는 동안 채널 팩터리는 내부 요청 채널을 `HttpCookieRequestSessionChannel`로 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="63912-141">`HttpCookieRequestSessionChannel` 클래스는 호출을 기본 요청 채널로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="63912-142">클라이언트가 프록시를 닫으면 `HttpCookieRequestSessionChannel`은 채널이 닫히는 것을 알리는 메시지를 서비스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="63912-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="63912-143">따라서 서비스 채널 스택은 사용 중인 세션 채널을 정상적으로 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="63912-144">바인딩 및 바인딩 요소</span><span class="sxs-lookup"><span data-stu-id="63912-144">Binding and Binding Element</span></span>  
 <span data-ttu-id="63912-145">서비스 및 클라이언트 채널을 만든 후 다음 단계는 WCF 런타임에 통합 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="63912-145">After creating the service and client channels, the next step is to integrate them into the WCF runtime.</span></span> <span data-ttu-id="63912-146">채널은 바인딩 및 바인딩 요소를 통해 WCF에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-146">Channels are exposed to WCF through bindings and binding elements.</span></span> <span data-ttu-id="63912-147">이 바인딩은 하나 또는 여러 개의 바인딩 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-147">A binding consists of one or many binding elements.</span></span> <span data-ttu-id="63912-148">WCF는 여러 시스템 정의 바인딩을 제공 합니다. 예: BasicHttpBinding 또는 WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="63912-148">WCF offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="63912-149">`HttpCookieSessionBindingElement` 클래스에는 바인딩 요소의 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="63912-150">이 클래스는 채널 수신기 및 채널 팩터리 만들기 메서드를 재정의하여 필요한 채널 수신기 또는 채널 팩터리 인스턴스화를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="63912-151">이 샘플에서는 서비스 설명에 정책 어설션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="63912-152">따라서 이 샘플을 사용하면 서비스를 사용할 수 있는 다른 클라이언트에 채널 요구 사항을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="63912-153">예를 들어 이 바인딩 요소는 정책 어설션을 게시하여 세션을 지원함을 잠재적 클라이언트에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="63912-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="63912-154">이 샘플에서는 바인딩 요소 구성에서 `ExchangeTerminateMessage` 속성을 사용하도록 설정하므로 서비스가 세션 대화를 종료하기 위한 추가 메시지 교환 작업을 지원하는 것을 보여 주기 위해 필요한 어설션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="63912-155">그런 다음 클라이언트는 이 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-155">Clients can then use this action.</span></span> <span data-ttu-id="63912-156">다음 WSDL 코드는 `HttpCookieSessionBindingElement`에서 만든 정책 어설션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63912-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="63912-157">`HttpCookieSessionBinding` 클래스는 이전에 설명한 바인딩 요소를 사용하는 시스템 제공 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="63912-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="63912-158">구성 시스템에 채널 추가</span><span class="sxs-lookup"><span data-stu-id="63912-158">Adding the Channel to the Configuration System</span></span>  
 <span data-ttu-id="63912-159">이 샘플에서는 구성을 통해 샘플 채널을 노출하는 두 개의 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="63912-160">첫 번째 클래스는 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>의 `HttpCookieSessionBindingElement`입니다</span><span class="sxs-lookup"><span data-stu-id="63912-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="63912-161">대량의 구현은 `HttpCookieSessionBindingConfigurationElement`로부터 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="63912-162">`HttpCookieSessionBindingConfigurationElement`에는 `HttpCookieSessionBindingElement`의 속성에 대응하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="63912-163">바인딩 요소 확장명 섹션</span><span class="sxs-lookup"><span data-stu-id="63912-163">Binding Element Extension Section</span></span>  
 <span data-ttu-id="63912-164">`HttpCookieSessionBindingElementSection` 섹션은 구성 시스템에 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>을 노출하는 `HttpCookieSessionBindingElement`입니다.</span><span class="sxs-lookup"><span data-stu-id="63912-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="63912-165">몇 가지 재정의를 통해 구성 섹션 이름, 바인딩 요소의 형식 및 바인딩 요소를 만드는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="63912-166">그러면 다음과 같이 구성 파일의 확장 섹션을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>
    <system.serviceModel>
      <extensions>
        <bindingElementExtensions>
          <add name="httpCookieSession"
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,
                    HttpCookieSessionExtension, Version=1.0.0.0,
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>
    </system.serviceModel>
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="63912-167">테스트 코드</span><span class="sxs-lookup"><span data-stu-id="63912-167">Test Code</span></span>  
 <span data-ttu-id="63912-168">이 샘플 전송을 사용하기 위한 테스트 코드는 Client 및 Service 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63912-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="63912-169">이는 두 가지 테스트로 구성 됩니다. 즉, 한 테스트는 `allowCookies` 클라이언트에서가로 설정 된 바인딩을 사용 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="63912-170">두 번째 테스트에서는 종료 메시지 교환을 사용하여 바인딩에서 명시적인 종료를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="63912-171">샘플을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63912-171">When you run the sample, you should see the following output:</span></span>  
  
```console  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="63912-172">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="63912-172">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="63912-173">다음 명령을 사용 하 여 ASP.NET 4.0을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-173">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="63912-174">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="63912-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="63912-175">솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](building-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="63912-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="63912-176">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="63912-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
