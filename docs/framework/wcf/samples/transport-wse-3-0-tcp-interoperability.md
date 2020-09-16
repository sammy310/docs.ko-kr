---
title: '전송: WSE 3.0 TCP 상호 운용성'
ms.date: 03/30/2017
ms.assetid: 5f7c3708-acad-4eb3-acb9-d232c77d1486
ms.openlocfilehash: f61d5037af0be6579d5110152ca070bec586fe87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558968"
---
# <a name="transport-wse-30-tcp-interoperability"></a><span data-ttu-id="2cf99-102">전송: WSE 3.0 TCP 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="2cf99-102">Transport: WSE 3.0 TCP Interoperability</span></span>
<span data-ttu-id="2cf99-103">WSE 3.0 TCP 상호 운용성 전송 샘플에서는 TCP 이중 세션을 WCF (사용자 지정 Windows Communication Foundation) 전송으로 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-103">The WSE 3.0 TCP Interoperability Transport sample demonstrates how to implement a TCP duplex session as a custom Windows Communication Foundation (WCF) transport.</span></span> <span data-ttu-id="2cf99-104">또한 채널 계층의 확장성을 사용하여 연결을 통해 기존에 배포된 시스템과 상호 작용할 수 있는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-104">It also demonstrates how you can use the extensibility of the channel layer to interface over the wire with existing deployed systems.</span></span> <span data-ttu-id="2cf99-105">다음 단계에서는이 사용자 지정 WCF 전송을 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-105">The following steps show how to build this custom WCF transport:</span></span>  
  
1. <span data-ttu-id="2cf99-106">TCP 소켓에서 시작하여 DIME 프레이밍을 사용하여 메시지 경계를 나타내는 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>의 클라이언트 및 서버 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-106">Starting with a TCP socket, create client and server implementations of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> that use DIME Framing to delineate message boundaries.</span></span>  
  
2. <span data-ttu-id="2cf99-107">WSE TCP 서비스에 연결되고 클라이언트 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>을 통해 프레임 메시지를 보내는 채널 팩터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-107">Create a channel factory that connects to a WSE TCP service and sends framed messages over the client <xref:System.ServiceModel.Channels.IDuplexSessionChannel>s.</span></span>  
  
3. <span data-ttu-id="2cf99-108">들어오는 TCP 연결을 수락하고 해당하는 채널을 생성하도록 채널 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-108">Create a channel listener to accept incoming TCP connections and produce corresponding channels.</span></span>  
  
4. <span data-ttu-id="2cf99-109">네트워크 관련 예외가 <xref:System.ServiceModel.CommunicationException>의 적절한 파생 클래스로 정규화되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-109">Ensure that any network-specific exceptions are normalized to the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
5. <span data-ttu-id="2cf99-110">사용자 지정 전송을 채널 스택에 추가하는 바인딩 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-110">Add a binding element that adds the custom transport to a channel stack.</span></span> <span data-ttu-id="2cf99-111">자세한 내용은 [바인딩 요소 추가]를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf99-111">For more information, see [Adding a Binding Element].</span></span>  
  
## <a name="creating-iduplexsessionchannel"></a><span data-ttu-id="2cf99-112">IDuplexSessionChannel 만들기</span><span class="sxs-lookup"><span data-stu-id="2cf99-112">Creating IDuplexSessionChannel</span></span>  
 <span data-ttu-id="2cf99-113">WSE 3.0 TCP 상호 운용성 전송을 작성하는 첫 번째 단계는 <xref:System.ServiceModel.Channels.IDuplexSessionChannel> 위에 <xref:System.Net.Sockets.Socket>의 구현을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-113">The first step in writing the WSE 3.0 TCP Interoperability Transport is to create an implementation of <xref:System.ServiceModel.Channels.IDuplexSessionChannel> on top of a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="2cf99-114">`WseTcpDuplexSessionChannel`은 <xref:System.ServiceModel.Channels.ChannelBase>로부터 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-114">`WseTcpDuplexSessionChannel` derives from <xref:System.ServiceModel.Channels.ChannelBase>.</span></span> <span data-ttu-id="2cf99-115">메시지를 보내는 논리는 (1) 메시지를 바이트로 인코딩한 다음 (2) 이러한 바이트를 프레이밍하여 연결을 통해 보내는 두 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-115">The logic of sending a message consists of two main pieces: (1) Encoding the message into bytes, and (2) framing those bytes and sending them on the wire.</span></span>  
  
 `ArraySegment<byte> encodedBytes = EncodeMessage(message);`  
  
 `WriteData(encodedBytes);`  
  
 <span data-ttu-id="2cf99-116">또한 Send() 호출이 IDuplexSessionChannel을 순서대로 유지하고 기본 소켓에 대한 호출이 올바르게 동기화되도록 잠금을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-116">In addition, a lock is taken so that the Send() calls preserve the IDuplexSessionChannel in-order guarantee, and so that calls to the underlying socket are synchronized correctly.</span></span>  
  
 <span data-ttu-id="2cf99-117">`WseTcpDuplexSessionChannel`은 <xref:System.ServiceModel.Channels.MessageEncoder>와 byte[] 간의 변환에 <xref:System.ServiceModel.Channels.Message>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-117">`WseTcpDuplexSessionChannel` uses a <xref:System.ServiceModel.Channels.MessageEncoder> for translating a <xref:System.ServiceModel.Channels.Message> to and from byte[].</span></span> <span data-ttu-id="2cf99-118">이는 전송이기 때문에 `WseTcpDuplexSessionChannel`은 채널이 구성된 원격 주소를 적용하는 작업도 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-118">Because it is a transport, `WseTcpDuplexSessionChannel` is also responsible for applying the remote address that the channel was configured with.</span></span> <span data-ttu-id="2cf99-119">`EncodeMessage`는 이 변환을 위한 논리를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-119">`EncodeMessage` encapsulates the logic for this conversion.</span></span>  
  
 `this.RemoteAddress.ApplyTo(message);`  
  
 `return encoder.WriteMessage(message, maxBufferSize, bufferManager);`  
  
 <span data-ttu-id="2cf99-120"><xref:System.ServiceModel.Channels.Message>를 바이트로 인코딩한 다음에는 연결을 통해 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-120">Once the <xref:System.ServiceModel.Channels.Message> is encoded into bytes, it must be transmitted on the wire.</span></span> <span data-ttu-id="2cf99-121">이렇게 하려면 메시지 경계를 정의하기 위한 시스템이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-121">This requires a system for defining message boundaries.</span></span> <span data-ttu-id="2cf99-122">WSE 3.0에서는 프레이밍 프로토콜로 [DIME](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-122">WSE 3.0 uses a version of [DIME](/archive/msdn-magazine/2002/december/sending-files-attachments-and-soap-messages-via-dime) as its framing protocol.</span></span> <span data-ttu-id="2cf99-123">`WriteData`는 프레이밍 논리를 캡슐화하여 byte[]를 DIME 레코드의 집합으로 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-123">`WriteData` encapsulates the framing logic to wrap a byte[] into a set of DIME records.</span></span>  
  
 <span data-ttu-id="2cf99-124">메시지를 수신 하는 논리는 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-124">The logic for receiving messages is similar.</span></span> <span data-ttu-id="2cf99-125">주요 복잡성은 소켓 읽기가 요청 된 것 보다 더 짧은 바이트를 반환할 수 있다는 사실을 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-125">The main complexity is handling the fact that a socket read can return fewer bytes than were requested.</span></span> <span data-ttu-id="2cf99-126">메시지를 수신하기 위해 `WseTcpDuplexSessionChannel`은 연결이 끊긴 상태에서 바이트를 읽고 DIME 프레이밍을 디코딩한 다음 byte[]를 <xref:System.ServiceModel.Channels.MessageEncoder>로 변환하는 데 <xref:System.ServiceModel.Channels.Message>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-126">To receive a message, `WseTcpDuplexSessionChannel` reads bytes off the wire, decodes the DIME framing, and then uses the <xref:System.ServiceModel.Channels.MessageEncoder> for turning the byte[] into a <xref:System.ServiceModel.Channels.Message>.</span></span>  
  
 <span data-ttu-id="2cf99-127">기본 `WseTcpDuplexSessionChannel`은 연결된 소켓을 수신하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-127">The base `WseTcpDuplexSessionChannel` assumes that it receives a connected socket.</span></span> <span data-ttu-id="2cf99-128">기본 클래스는 소켓 종료를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-128">The base class handles socket shutdown.</span></span> <span data-ttu-id="2cf99-129">소켓 닫기를 처리하는 세 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-129">There are three places that interface with socket closure:</span></span>  
  
- <span data-ttu-id="2cf99-130">OnAbort -- 소켓을 강제로 닫습니다(강제 닫기).</span><span class="sxs-lookup"><span data-stu-id="2cf99-130">OnAbort -- close the socket ungracefully (hard close).</span></span>  
  
- <span data-ttu-id="2cf99-131">On[Begin]Close -- 소켓을 정상적으로 닫습니다(정상 닫기).</span><span class="sxs-lookup"><span data-stu-id="2cf99-131">On[Begin]Close -- close the socket gracefully (soft close).</span></span>  
  
- <span data-ttu-id="2cf99-132">세션별. CloseOutputSession--아웃 바운드 데이터 스트림 (절반 닫기)을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-132">session.CloseOutputSession -- shut down the outbound data stream (half close).</span></span>  
  
## <a name="channel-factory"></a><span data-ttu-id="2cf99-133">채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="2cf99-133">Channel Factory</span></span>  
 <span data-ttu-id="2cf99-134">TCP 전송을 작성하는 다음 단계는 클라이언트 채널을 위한 <xref:System.ServiceModel.Channels.IChannelFactory>의 구현을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-134">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels.</span></span>  
  
- <span data-ttu-id="2cf99-135">`WseTcpChannelFactory`에서 파생 <xref:System.ServiceModel.Channels.ChannelFactoryBase> \<IDuplexSessionChannel> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-135">`WseTcpChannelFactory` derives from <xref:System.ServiceModel.Channels.ChannelFactoryBase>\<IDuplexSessionChannel>.</span></span> <span data-ttu-id="2cf99-136">이는 `OnCreateChannel`을 재정의하여 클라이언트 채널을 생성하는 팩터리입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-136">It is a factory that overrides `OnCreateChannel` to produce client channels.</span></span>  
  
 `protected override IDuplexSessionChannel OnCreateChannel(EndpointAddress remoteAddress, Uri via)`  
  
 `{`  
  
 `return new ClientWseTcpDuplexSessionChannel(encoderFactory, bufferManager, remoteAddress, via, this);`  
  
 `}`  
  
- <span data-ttu-id="2cf99-137">`ClientWseTcpDuplexSessionChannel` 기본에 논리를 추가 `WseTcpDuplexSessionChannel` 하 여 시간에 TCP 서버에 연결 `channel.Open` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-137">`ClientWseTcpDuplexSessionChannel` adds logic to the base `WseTcpDuplexSessionChannel` to connect to a TCP server at `channel.Open` time.</span></span> <span data-ttu-id="2cf99-138">다음 코드에 나온 것처럼 먼저 호스트 이름이 IP 주소로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-138">First the hostname is resolved to an IP address, as shown in the following code.</span></span>  
  
 `hostEntry = Dns.GetHostEntry(Via.Host);`  
  
- <span data-ttu-id="2cf99-139">그런 다음에는 다음 코드에 나온 것처럼 호스트 이름이 루프의 사용 가능한 첫 번째 IP 주소에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-139">Then the hostname is connected to the first available IP address in a loop, as shown in the following code.</span></span>  
  
 `IPAddress address = hostEntry.AddressList[i];`  
  
 `socket = new Socket(address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `socket.Connect(new IPEndPoint(address, port));`  
  
- <span data-ttu-id="2cf99-140">채널 계약의 일부로 도메인 관련 예외를 래핑합니다(예: `SocketException`의 <xref:System.ServiceModel.CommunicationException>).</span><span class="sxs-lookup"><span data-stu-id="2cf99-140">As part of the channel contract, any domain-specific exceptions are wrapped, such as `SocketException` in <xref:System.ServiceModel.CommunicationException>.</span></span>  
  
## <a name="channel-listener"></a><span data-ttu-id="2cf99-141">채널 수신기</span><span class="sxs-lookup"><span data-stu-id="2cf99-141">Channel Listener</span></span>  
 <span data-ttu-id="2cf99-142">TCP 전송을 작성하는 다음 단계는 서버 채널을 수락하기 위한 <xref:System.ServiceModel.Channels.IChannelListener>의 구현을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-142">The next step in writing the TCP transport is to create an implementation of <xref:System.ServiceModel.Channels.IChannelListener> for accepting server channels.</span></span>  
  
- <span data-ttu-id="2cf99-143">`WseTcpChannelListener`에서 파생 되 <xref:System.ServiceModel.Channels.ChannelListenerBase> \<IDuplexSessionChannel> 고 [Begin] Open 및 On [Begin] Close에서를 재정의 하 여 수신 소켓의 수명을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-143">`WseTcpChannelListener` derives from <xref:System.ServiceModel.Channels.ChannelListenerBase>\<IDuplexSessionChannel> and overrides On[Begin]Open and On[Begin]Close to control the lifetime of its listen socket.</span></span> <span data-ttu-id="2cf99-144">OnOpen에서는 IP_ANY를 수신 대기하는 소켓이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-144">In OnOpen, a socket is created to listen on IP_ANY.</span></span> <span data-ttu-id="2cf99-145">더 고급 구현에서는 IPv6을 수신 대기하는 두 번째 소켓도 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-145">More advanced implementations can create a second socket to listen on IPv6 as well.</span></span> <span data-ttu-id="2cf99-146">또한 호스트 이름에 IP 주소를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-146">They can also allow the IP address to be specified in the hostname.</span></span>  
  
 `IPEndPoint localEndpoint = new IPEndPoint(IPAddress.Any, uri.Port);`  
  
 `this.listenSocket = new Socket(localEndpoint.AddressFamily, SocketType.Stream, ProtocolType.Tcp);`  
  
 `this.listenSocket.Bind(localEndpoint);`  
  
 `this.listenSocket.Listen(10);`  
  
 <span data-ttu-id="2cf99-147">새 소켓을 수락하면 이 소켓으로 서버 채널이 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-147">When a new socket is accepted, a server channel is initialized with this socket.</span></span> <span data-ttu-id="2cf99-148">모든 입력 및 출력은 기본 클래스에서 이미 구현되었으므로 이 채널은 소켓의 초기화를 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-148">All the input and output is already implemented in the base class, so this channel is responsible for initializing the socket.</span></span>  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="2cf99-149">바인딩 요소 추가</span><span class="sxs-lookup"><span data-stu-id="2cf99-149">Adding a Binding Element</span></span>  
 <span data-ttu-id="2cf99-150">팩터리와 채널이 빌드되었으므로 이제 바인딩을 통해 ServiceModel 런타임에 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-150">Now that the factories and channels are built, they must be exposed to the ServiceModel runtime through a binding.</span></span> <span data-ttu-id="2cf99-151">바인딩은 서비스 주소와 연결된 통신 스택을 나타내는 바인딩 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-151">A binding is a collection of binding elements that represents the communication stack associated with a service address.</span></span> <span data-ttu-id="2cf99-152">스택의 각 요소는 바인딩 요소로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-152">Each element in the stack is represented by a binding element.</span></span>  
  
 <span data-ttu-id="2cf99-153">이 샘플에서 바인딩 요소는 `WseTcpTransportBindingElement`에서 파생된 <xref:System.ServiceModel.Channels.TransportBindingElement>로,</span><span class="sxs-lookup"><span data-stu-id="2cf99-153">In the sample, the binding element is `WseTcpTransportBindingElement`, which derives from <xref:System.ServiceModel.Channels.TransportBindingElement>.</span></span> <span data-ttu-id="2cf99-154"><xref:System.ServiceModel.Channels.IDuplexSessionChannel>을 지원하고 다음 메서드를 재정의하여 바인딩과 연결된 팩터리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-154">It supports <xref:System.ServiceModel.Channels.IDuplexSessionChannel> and overrides the following methods to build the factories associated with our binding.</span></span>  
  
 `public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelFactory<TChannel>)(object)new WseTcpChannelFactory(this, context);`  
  
 `}`  
  
 `public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)`  
  
 `{`  
  
 `return (IChannelListener<TChannel>)(object)new WseTcpChannelListener(this, context);`  
  
 `}`  
  
 <span data-ttu-id="2cf99-155">또한 `BindingElement`를 복제하고 체계(wse.tcp)를 반환하기 위한 멤버를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-155">It also contains members for cloning the `BindingElement` and returning our scheme (wse.tcp).</span></span>  
  
## <a name="the-wse-tcp-test-console"></a><span data-ttu-id="2cf99-156">WSE TCP 테스트 콘솔</span><span class="sxs-lookup"><span data-stu-id="2cf99-156">The WSE TCP Test Console</span></span>  
 <span data-ttu-id="2cf99-157">이 샘플 전송을 사용하기 위한 테스트 코드는 TestCode.cs에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-157">Test code for using this sample transport is available in TestCode.cs.</span></span> <span data-ttu-id="2cf99-158">다음 지침은 WSE `TcpSyncStockService` 샘플을 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-158">The following instructions show how to set up the WSE `TcpSyncStockService` sample.</span></span>  
  
 <span data-ttu-id="2cf99-159">이 테스트 코드는 인코딩으로 MTOM을 사용하고 전송으로 `WseTcpTransport`를 사용하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-159">The test code creates a custom binding that uses MTOM as the encoding and `WseTcpTransport` as the transport.</span></span> <span data-ttu-id="2cf99-160">또한 다음 코드에 나온 것처럼 WSE 3.0을 준수하도록 AddressingVersion을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-160">It also sets up the AddressingVersion to be conformant with WSE 3.0, as shown in the following code.</span></span>  
  
 `CustomBinding binding = new CustomBinding();`  
  
 `MtomMessageEncodingBindingElement mtomBindingElement = new MtomMessageEncodingBindingElement();`  
  
 `mtomBindingElement.MessageVersion = MessageVersion.Soap11WSAddressingAugust2004;`  
  
 `binding.Elements.Add(mtomBindingElement);`  
  
 `binding.Elements.Add(new WseTcpTransportBindingElement());`  
  
 <span data-ttu-id="2cf99-161">이 테스트 코드는 두 개의 테스트로 구성됩니다. 첫 번째 테스트에서는 WSE 3.0 WSDL에서 생성된 코드를 사용하여 형식화된 클라이언트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-161">It consists of two tests—one test sets up a typed client using code generated from the WSE 3.0 WSDL.</span></span> <span data-ttu-id="2cf99-162">두 번째 테스트는 채널 Api 위에서 직접 메시지를 전송 하 여 WCF를 클라이언트와 서버로 모두 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-162">The second test uses WCF as both the client and the server by sending messages directly on top of the channel APIs.</span></span>  
  
 <span data-ttu-id="2cf99-163">샘플을 실행할 경우의 예상 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-163">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="2cf99-164">클라이언트:</span><span class="sxs-lookup"><span data-stu-id="2cf99-164">Client:</span></span>  
  
```console  
Calling soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Symbol: FABRIKAM  
        Name: Fabrikam, Inc.  
        Last Price: 120  
  
Symbol: CONTOSO  
        Name: Contoso Corp.  
        Last Price: 50.07  
Press enter.  
  
Received Action: http://SayHello  
Received Body: to you.  
Hello to you.  
Press enter.  
  
Received Action: http://NotHello  
Received Body: to me.  
Press enter.  
```  
  
 <span data-ttu-id="2cf99-165">서버:</span><span class="sxs-lookup"><span data-stu-id="2cf99-165">Server:</span></span>  
  
```console  
Listening for messages at soap://stockservice.contoso.com/wse/samples/2003/06/TcpSyncStockService  
  
Press any key to exit when done...  
  
Request received.  
Symbols:  
        FABRIKAM  
        CONTOSO  
```  
  
## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="2cf99-166">샘플 설정, 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="2cf99-166">Set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2cf99-167">이 샘플을 실행 하려면 Microsoft .NET 및 WSE 샘플 [에 대 한 wse (웹 서비스 향상) 3.0](https://www.microsoft.com/download/details.aspx?id=14089) 이 설치 되어 있어야 합니다 `TcpSyncStockService` .</span><span class="sxs-lookup"><span data-stu-id="2cf99-167">To run this sample, you must have [Web Services Enhancements (WSE) 3.0 for Microsoft .NET](https://www.microsoft.com/download/details.aspx?id=14089) and the WSE `TcpSyncStockService` sample installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2cf99-168">WSE 3.0은 Windows Server 2008에서 지원 되지 않으므로 `TcpSyncStockService` 해당 운영 체제에서 예제를 설치 하거나 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-168">Because WSE 3.0 is not supported on Windows Server 2008, you cannot install or run the `TcpSyncStockService` sample on that operating system.</span></span>  
  
1. <span data-ttu-id="2cf99-169">`TcpSyncStockService` 샘플을 설치했으면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-169">Once you install the `TcpSyncStockService` sample, do the following:</span></span>  
  
    1. <span data-ttu-id="2cf99-170">`TcpSyncStockService`Visual Studio에서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-170">Open the `TcpSyncStockService` in Visual Studio.</span></span> <span data-ttu-id="2cf99-171">TcpSyncStockService 샘플은 WSE 3.0와 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-171">(The TcpSyncStockService sample is installed with WSE 3.0.</span></span> <span data-ttu-id="2cf99-172">이 샘플 코드에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-172">It is not part of this sample's code.)</span></span>  
  
    2. <span data-ttu-id="2cf99-173">StockService 프로젝트를 시작 프로젝트로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-173">Set the StockService project as the start-up project.</span></span>  
  
    3. <span data-ttu-id="2cf99-174">StockService 프로젝트에서 StockService.cs를 열고 `StockService` 클래스의 [Policy] 특성을 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-174">Open StockService.cs in the StockService project and comment out the [Policy] attribute on the `StockService` class.</span></span> <span data-ttu-id="2cf99-175">이렇게 하면 샘플에서 보안을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-175">This disables security from the sample.</span></span> <span data-ttu-id="2cf99-176">WCF는 WSE 3.0 보안 끝점과 상호 운용할 수 있지만 보안을 사용 하지 않도록 설정 하 여이 샘플이 사용자 지정 TCP 전송에 집중 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-176">While WCF can interoperate with WSE 3.0 secure endpoints, security is disabled to keep this sample focused on the custom TCP transport.</span></span>  
  
    4. <span data-ttu-id="2cf99-177">F5 키를 눌러 `TcpSyncStockService`를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-177">Press F5 to start the `TcpSyncStockService`.</span></span> <span data-ttu-id="2cf99-178">새 콘솔 창에서 서비스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-178">The service starts in a new console window.</span></span>  
  
    5. <span data-ttu-id="2cf99-179">Visual Studio에서 이 TCP 전송 샘플을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-179">Open this TCP transport sample in Visual Studio.</span></span>  
  
    6. <span data-ttu-id="2cf99-180">`TcpSyncStockService`를 실행하는 컴퓨터 이름과 일치하도록 TestCode.cs의 "hostname" 변수를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-180">Update the "hostname" variable in TestCode.cs to match the machine name running the `TcpSyncStockService`.</span></span>  
  
    7. <span data-ttu-id="2cf99-181">F5 키를 눌러 TCP 전송 샘플을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-181">Press F5 to start the TCP transport sample.</span></span>  
  
    8. <span data-ttu-id="2cf99-182">TCP 전송 테스트 클라이언트가 새 콘솔에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-182">The TCP transport test client starts in a new console.</span></span> <span data-ttu-id="2cf99-183">클라이언트는 서비스에서 스톡 할당량을 요청한 다음 콘솔 창에 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf99-183">The client requests stock quotes from the service and then displays the results in its console window.</span></span>
