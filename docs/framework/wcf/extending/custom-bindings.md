---
description: '자세한 정보: 사용자 지정 바인딩'
title: 사용자 지정 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: ced0f9ada7238b43216a246d75dd391aa6eb3f2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735350"
---
# <a name="custom-bindings"></a><span data-ttu-id="5258e-103">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5258e-103">Custom Bindings</span></span>

<span data-ttu-id="5258e-104">시스템에서 제공하는 바인딩 중 하나가 사용자의 서비스 요구 사항을 충족하지 않을 때 <xref:System.ServiceModel.Channels.CustomBinding> 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-104">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="5258e-105">모든 바인딩은 정렬된 바인딩 요소 집합으로부터 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-105">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="5258e-106">사용자 지정 바인딩은 시스템 제공 바인딩 요소로부터 만들거나 사용자 정의 사용자 지정 바인딩 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-106">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="5258e-107">예를 들어 사용자 지정 바인딩 요소를 사용하여 서비스 엔드포인트에서 새 전송 또는 새 인코더를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-107">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="5258e-108">작업 예제는 [사용자 지정 바인딩 샘플](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5258e-108">For working examples, see [Custom Binding Samples](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span></span> <span data-ttu-id="5258e-109">자세한 내용은 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)을(를) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5258e-109">For more information, see [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>

## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="5258e-110">사용자 지정 바인딩 생성</span><span class="sxs-lookup"><span data-stu-id="5258e-110">Construction of a Custom Binding</span></span>

<span data-ttu-id="5258e-111">사용자 지정 바인딩은 특정 순서로 "스택"되는 바인딩 요소 컬렉션에서 <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> 생성자를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-111">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="5258e-112">맨 위에는 트랜잭션 이동을 허용하는 선택적 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-112">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>

- <span data-ttu-id="5258e-113">다음에는 WS-ReliableMessaging 사양에서 정의된 세션 및 순서 지정 메커니즘을 제공하는 선택적 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-113">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="5258e-114">세션은 SOAP 매개자 및 전송 매개자에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-114">A session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="5258e-115">다음에는 권한 부여, 인증, 보호, 기밀성과 같은 보안 기능을 제공하는 선택적 <xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-115">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>

- <span data-ttu-id="5258e-116">다음에는 기본적으로 이중 통신을 지원하지 않는 전송 프로토콜(예: HTTP)을 사용하여 양방향 이중 통신을 수행하는 기능을 제공하는 선택적 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-116">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>

- <span data-ttu-id="5258e-117">다음에는 단방향 통신을 제공하는 <xref:System.ServiceModel.Channels.OneWayBindingElement>) 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-117">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>

- <span data-ttu-id="5258e-118">다음에는 아래와 같은 선택적 스트림 보안 바인딩 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-118">Next is an optional stream security binding element which can be one of the following.</span></span>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="5258e-119">다음은 필수 메시지 인코딩 바인딩 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-119">Next is a required message encoding binding element.</span></span> <span data-ttu-id="5258e-120">고유의 메시지 인코더를 사용하거나 다음 세 가지 메시지 인코딩 바인딩 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-120">You can use your own message encoder or one of the three message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

<span data-ttu-id="5258e-121">맨 아래에는 필수 전송 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-121">At the bottom is a required transport element.</span></span> <span data-ttu-id="5258e-122">사용자 고유의 전송 또는 WCF (전송 바인딩 요소 Windows Communication Foundation) 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-122">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

<span data-ttu-id="5258e-123">다음 표에서는 각 계층에 대 한 옵션을 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-123">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="5258e-124">계층</span><span class="sxs-lookup"><span data-stu-id="5258e-124">Layer</span></span>|<span data-ttu-id="5258e-125">옵션</span><span class="sxs-lookup"><span data-stu-id="5258e-125">Options</span></span>|<span data-ttu-id="5258e-126">필수</span><span class="sxs-lookup"><span data-stu-id="5258e-126">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="5258e-127">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="5258e-127">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="5258e-128">No</span><span class="sxs-lookup"><span data-stu-id="5258e-128">No</span></span>|
|<span data-ttu-id="5258e-129">안정성</span><span class="sxs-lookup"><span data-stu-id="5258e-129">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="5258e-130">No</span><span class="sxs-lookup"><span data-stu-id="5258e-130">No</span></span>|
|<span data-ttu-id="5258e-131">보안</span><span class="sxs-lookup"><span data-stu-id="5258e-131">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="5258e-132">No</span><span class="sxs-lookup"><span data-stu-id="5258e-132">No</span></span>|
|<span data-ttu-id="5258e-133">Encoding</span><span class="sxs-lookup"><span data-stu-id="5258e-133">Encoding</span></span>|<span data-ttu-id="5258e-134">텍스트, 이진, MTOM(Message Transmission Optimization Mechanism), 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5258e-134">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="5258e-135">Yes</span><span class="sxs-lookup"><span data-stu-id="5258e-135">Yes</span></span>|
|<span data-ttu-id="5258e-136">전송</span><span class="sxs-lookup"><span data-stu-id="5258e-136">Transport</span></span>|<span data-ttu-id="5258e-137">TCP, HTTP, HTTPS, 명명된 파이프(IPC), P2P(Peer-to-Peer), 메시지 큐(MSMQ), 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5258e-137">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="5258e-138">Yes</span><span class="sxs-lookup"><span data-stu-id="5258e-138">Yes</span></span>|

<span data-ttu-id="5258e-139">또한 사용자 고유의 바인딩 요소를 정의 하 고 앞에서 정의한 계층 사이에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5258e-139">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

## <a name="see-also"></a><span data-ttu-id="5258e-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5258e-140">See also</span></span>

- [<span data-ttu-id="5258e-141">엔드포인트 만들기 개요</span><span class="sxs-lookup"><span data-stu-id="5258e-141">Endpoint Creation Overview</span></span>](../endpoint-creation-overview.md)
- [<span data-ttu-id="5258e-142">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5258e-142">Using Bindings to Configure Services and Clients</span></span>](../using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5258e-143">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="5258e-143">System-Provided Bindings</span></span>](../system-provided-bindings.md)
- [<span data-ttu-id="5258e-144">방법: 시스템 제공 바인딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5258e-144">How to: Customize a System-Provided Binding</span></span>](how-to-customize-a-system-provided-binding.md)
- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="5258e-145">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5258e-145">Custom Binding</span></span>](../samples/custom-binding.md)
