---
description: '자세한 정보: Windows Communication Foundation의 전송'
title: Windows Communication Foundation의 전송
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: e80a1730de107c0433949b7d476944f38e386702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752615"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="d6d85-103">Windows Communication Foundation의 전송</span><span class="sxs-lookup"><span data-stu-id="d6d85-103">Transports in Windows Communication Foundation</span></span>

<span data-ttu-id="d6d85-104">전송 계층은 채널 스택의 최하위 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-104">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="d6d85-105">WCF (Windows Communication Foundation)에서 사용 되는 기본 전송은 HTTP, HTTPS, TCP 및 명명 된 파이프입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-105">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="d6d85-106">이 단원의 항목에서는 이러한 전송 중에서 특정 전송을 선택하여 구성하고 조정 속성을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-106">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="d6d85-107">WCF에는 추가 전송 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-107">WCF includes additional transports.</span></span> <span data-ttu-id="d6d85-108">MSMQ (메시지 큐) 전송에 대 한 자세한 내용은 [큐 및 신뢰할 수 있는 세션](queues-and-reliable-sessions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d85-108">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="d6d85-109">피어 투 피어 전송에 대 한 자세한 내용은 피어 투 [피어 네트워킹](peer-to-peer-networking.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d85-109">For information about peer-to-peer transport, see [Peer-to-Peer Networking](peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6d85-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d6d85-110">In This Section</span></span>  

 [<span data-ttu-id="d6d85-111">전송 선택</span><span class="sxs-lookup"><span data-stu-id="d6d85-111">Choosing a Transport</span></span>](choosing-a-transport.md)  
 <span data-ttu-id="d6d85-112">세 가지 기본 전송과 그 중 하나를 선택하기 위해 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-112">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="d6d85-113">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="d6d85-113">Choosing a Message Encoder</span></span>](choosing-a-message-encoder.md)  
 <span data-ttu-id="d6d85-114">메시지 인코딩 바인딩 요소를 선택할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-114">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="d6d85-115">스트리밍 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="d6d85-115">Streaming Message Transfer</span></span>](streaming-message-transfer.md)  
 <span data-ttu-id="d6d85-116">스트리밍을 수행하도록 전송 계층을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-116">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="d6d85-117">HTTP 및 HTTPS 구성</span><span class="sxs-lookup"><span data-stu-id="d6d85-117">Configuring HTTP and HTTPS</span></span>](configuring-http-and-https.md)  
 <span data-ttu-id="d6d85-118">HTTP 및 HTTPS 전송 바인딩 요소를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-118">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="d6d85-119">방법: WCF URL 예약을 제한된 예약으로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d6d85-119">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="d6d85-120">WCFURL 제한 된 예약을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-120">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="d6d85-121">전송 할당량</span><span class="sxs-lookup"><span data-stu-id="d6d85-121">Transport Quotas</span></span>](transport-quotas.md)  
 <span data-ttu-id="d6d85-122">전송 계층에 사용할 수 있는 할당량을 설정할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-122">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="d6d85-123">NAT 및 방화벽 작업</span><span class="sxs-lookup"><span data-stu-id="d6d85-123">Working with NATs and Firewalls</span></span>](working-with-nats-and-firewalls.md)  
 <span data-ttu-id="d6d85-124">방화벽을 사용하여 메시지를 주고 받을 경우 또는 NAT(Network Address Translation)를 사용할 경우 전송 계층을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-124">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="d6d85-125">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="d6d85-125">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)  
 <span data-ttu-id="d6d85-126">WCF의 Net.tcp 포트 공유 구성 요소를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d85-126">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d6d85-127">참고</span><span class="sxs-lookup"><span data-stu-id="d6d85-127">Reference</span></span>  

 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="d6d85-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d6d85-128">Related Sections</span></span>  

 [<span data-ttu-id="d6d85-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="d6d85-129">Bindings</span></span>](bindings.md)  
  
 [<span data-ttu-id="d6d85-130">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="d6d85-130">Extending Bindings</span></span>](../extending/extending-bindings.md)
