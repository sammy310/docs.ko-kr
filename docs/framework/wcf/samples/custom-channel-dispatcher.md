---
description: '자세한 정보: 사용자 지정 채널 디스패처'
title: 사용자 지정 채널 디스패처
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: cb56c21b540f359d78e71d8769e9f2d9ccf65a63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732594"
---
# <a name="custom-channel-dispatcher"></a><span data-ttu-id="089da-103">사용자 지정 채널 디스패처</span><span class="sxs-lookup"><span data-stu-id="089da-103">Custom Channel Dispatcher</span></span>

<span data-ttu-id="089da-104">이 샘플에서는 <xref:System.ServiceModel.ServiceHostBase>를 직접 구현하여 사용자 지정 방식으로 채널 스택을 빌드하는 방법과 웹 호스트 환경에서 사용자 지정 채널 디스패처를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="089da-104">This sample demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span> <span data-ttu-id="089da-105">채널 디스패처에서는 <xref:System.ServiceModel.Channels.IChannelListener>와 상호 작용하여 채널을 수락하고 채널 스택에서 메시지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-105">The channel dispatcher interacts with <xref:System.ServiceModel.Channels.IChannelListener> to accept channels and retrieves messages from the channel stack.</span></span> <span data-ttu-id="089da-106">또한 이 샘플에서는 <xref:System.ServiceModel.Activation.VirtualPathExtension>을 사용하여 웹 호스트 환경에서 채널 스택을 빌드하는 방법을 보여 주는 기본 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-106">This sample also provides a basic sample to show how to build a channel stack in a Web host environment by using <xref:System.ServiceModel.Activation.VirtualPathExtension>.</span></span>  
  
## <a name="custom-servicehostbase"></a><span data-ttu-id="089da-107">사용자 지정 ServiceHostBase</span><span class="sxs-lookup"><span data-stu-id="089da-107">Custom ServiceHostBase</span></span>  

 <span data-ttu-id="089da-108">이 샘플 <xref:System.ServiceModel.ServiceHostBase> <xref:System.ServiceModel.ServiceHost> 에서는 WCF (Windows Communication Foundation) 스택 구현을 채널 스택 맨 위에 있는 사용자 지정 메시지 처리 계층으로 바꾸는 방법을 보여 주기 위해 대신 기본 형식을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-108">This sample implements the base type <xref:System.ServiceModel.ServiceHostBase> instead of <xref:System.ServiceModel.ServiceHost> to demonstrate how to replace the Windows Communication Foundation (WCF) stack implementation with a custom message handling layer on top of the channel stack.</span></span> <span data-ttu-id="089da-109">가상 메서드 <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A>을 재정의하여 채널 수신기 및 채널 디스패처를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-109">You override the virtual method <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> to build channel listeners and the channel dispatcher.</span></span>  
  
 <span data-ttu-id="089da-110">웹 호스트 서비스를 구현하려면 전송 계층에서 호스트 환경 설정, 즉 IIS(인터넷 정보 서비스)/WAS(Windows Process Activation Service) 설정을 기반으로 채널 수신기를 구성하는 방법을 알 수 있도록 <xref:System.ServiceModel.Activation.VirtualPathExtension> 컬렉션에서 서비스 확장명 <xref:System.ServiceModel.ServiceHostBase.Extensions%2A>을 가져와 <xref:System.ServiceModel.Channels.BindingParameterCollection>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-110">To implement a Web-hosted service, get the service extension <xref:System.ServiceModel.Activation.VirtualPathExtension> from the <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> collection and add it to the <xref:System.ServiceModel.Channels.BindingParameterCollection> so that the transport layer knows how to configure the channel listener based on the hosting environment settings, that is, the Internet Information Services (IIS)/Windows Process Activation Service (WAS) settings.</span></span>  
  
## <a name="custom-channel-dispatcher"></a><span data-ttu-id="089da-111">사용자 지정 채널 디스패처</span><span class="sxs-lookup"><span data-stu-id="089da-111">Custom Channel Dispatcher</span></span>  

 <span data-ttu-id="089da-112">사용자 지정 채널 디스패처에서는 <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase> 형식을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-112">The custom channel dispatcher extends the type <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>.</span></span> <span data-ttu-id="089da-113">이 형식은 채널 계층 프로그래밍 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-113">This type implements the channel-layer programming logic.</span></span> <span data-ttu-id="089da-114">이 샘플에서는 요청-회신 메시지 교환 패턴에 <xref:System.ServiceModel.Channels.IReplyChannel>만 지원되지만 사용자 지정 채널 디스패처를 다른 채널 형식으로 손쉽게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-114">In this sample, only <xref:System.ServiceModel.Channels.IReplyChannel> is supported for request-reply message exchange pattern, but the custom channel dispatcher can be easily extended to other channel types.</span></span>  
  
 <span data-ttu-id="089da-115">디스패처에서는 먼저 채널 수신기를 연 다음 singleton 회신 채널을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-115">The dispatcher first opens the channel listener and then accepts the singleton reply channel.</span></span> <span data-ttu-id="089da-116">그런 다음 이 채널을 사용하여 무한 루프에 메시지(요청)를 보내기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-116">With the channel, it starts to send messages (requests) in an infinite loop.</span></span> <span data-ttu-id="089da-117">또한 각 요청에 대해 회신 메시지를 만들고 이를 다시 클라이언트에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="089da-117">For each request, it creates a reply message and sends it back to the client.</span></span>  
  
## <a name="creating-a-response-message"></a><span data-ttu-id="089da-118">응답 메시지 만들기</span><span class="sxs-lookup"><span data-stu-id="089da-118">Creating a Response Message</span></span>  

 <span data-ttu-id="089da-119">메시지 처리는 `MyServiceManager` 형식에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="089da-119">The message processing is implemented in the type `MyServiceManager`.</span></span> <span data-ttu-id="089da-120">`HandleRequest` 메서드에서는 메시지의 `Action` 헤더를 먼저 검사하여 요청이 지원되는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-120">In the `HandleRequest` method, the `Action` header of the message is first checked to see whether the request is supported.</span></span> <span data-ttu-id="089da-121">미리 정의 된 SOAP 동작 " http://tempuri.org/HelloWorld/Hello "가 메시지 필터링을 제공 하도록 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-121">A predefined SOAP action "http://tempuri.org/HelloWorld/Hello" is defined to provide message filtering.</span></span> <span data-ttu-id="089da-122">이는의 WCF 구현에서 서비스 계약 개념과 유사 합니다 <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="089da-122">This is similar to the service contract concept in the WCF implementation of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="089da-123">올바른 SOAP 동작의 경우 샘플에서는 요청된 메시지 데이터를 검색하고 <xref:System.ServiceModel.ServiceHost>의 경우와 비슷하게 요청에 해당하는 응답을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-123">For the correct SOAP action case, the sample retrieves the requested message data and generates a corresponding response to the request similar to what is seen in the <xref:System.ServiceModel.ServiceHost> case.</span></span>  
  
 <span data-ttu-id="089da-124">이 경우 브라우저에서 서비스를 찾아 올바르게 컴파일되었는지 확인할 수 있도록 사용자 지정 HTML 메시지를 반환하여 HTTP-GET 동사를 특별하게 처리했습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-124">You specially handled the HTTP-GET verb by returning a custom HTML message, in this, case so that you can browse the service from a browser to see that it is compiled correctly.</span></span> <span data-ttu-id="089da-125">SOAP 동작이 일치하지 않는 경우에는 요청이 지원되지 않음을 나타내는 오류 메시지를 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="089da-125">If the SOAP action does not match, send a fault message back to indicate that the request is not supported.</span></span>  
  
 <span data-ttu-id="089da-126">이 샘플의 클라이언트는 서비스에서 어떤 것도 가정 하지 않는 일반적인 WCF 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="089da-126">The client of this sample is a normal WCF client that does not assume anything from the service.</span></span> <span data-ttu-id="089da-127">따라서 서비스는 일반적인 WCF 구현에서 가져온 것과 일치 하도록 특별 하 게 설계 되었습니다 <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="089da-127">So, the service is specially designed to match what you get from a normal WCF<xref:System.ServiceModel.ServiceHost> implementation.</span></span> <span data-ttu-id="089da-128">결과적으로 클라이언트에는 서비스 계약만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-128">As a result, only a service contract is required on the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="089da-129">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="089da-129">Using the sample</span></span>  

 <span data-ttu-id="089da-130">클라이언트 애플리케이션을 직접 실행하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="089da-130">Running the client application directly produces the following output.</span></span>  
  
```output  
Client is talking to a request/reply WCF service.
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 <span data-ttu-id="089da-131">HTTP-GET 메시지가 서버에서 처리될 수 있도록 브라우저에서 서비스를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-131">You can also browse the service from a browser so that an HTTP-GET message gets processed on the server.</span></span> <span data-ttu-id="089da-132">이렇게 하면 제대로 구성된 HTML 텍스트를 다시 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-132">This gets you well-formatted HTML text back.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="089da-133">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="089da-134">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="089da-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="089da-135">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="089da-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="089da-136">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="089da-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
