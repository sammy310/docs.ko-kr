---
title: Windows Communication Foundation의 전송
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933733"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="bad9c-102">Windows Communication Foundation의 전송</span><span class="sxs-lookup"><span data-stu-id="bad9c-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="bad9c-103">전송 계층은 채널 스택의 최하위 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="bad9c-104">Windows Communication Foundation (WCF)에서 사용 되는 기본 전송은 HTTP, HTTPS, TCP 및 명명 된 파이프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="bad9c-105">이 단원의 항목에서는 이러한 전송 중에서 특정 전송을 선택하여 구성하고 조정 속성을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="bad9c-106">WCF에는 추가 전송을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-106">WCF includes additional transports.</span></span> <span data-ttu-id="bad9c-107">메시지 큐 (MSMQ 라고도 함) 전송에 대 한 정보를 참조 하세요 [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="bad9c-108">피어-투-피어 전송에 대 한 정보를 참조 하세요 [피어-투-피어 네트워킹](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bad9c-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bad9c-109">In This Section</span></span>  
 [<span data-ttu-id="bad9c-110">전송 선택</span><span class="sxs-lookup"><span data-stu-id="bad9c-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="bad9c-111">세 가지 기본 전송과 그 중 하나를 선택하기 위해 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="bad9c-112">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="bad9c-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="bad9c-113">메시지 인코딩 바인딩 요소를 선택할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="bad9c-114">스트리밍 메시지 전송</span><span class="sxs-lookup"><span data-stu-id="bad9c-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="bad9c-115">스트리밍을 수행하도록 전송 계층을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="bad9c-116">HTTP 및 HTTPS 구성</span><span class="sxs-lookup"><span data-stu-id="bad9c-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="bad9c-117">HTTP 및 HTTPS 전송 바인딩 요소를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="bad9c-118">방법: WCF URL 예약을 제한 된 예약으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="bad9c-119">제한 된 WCFURL 예약을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="bad9c-120">전송 할당량</span><span class="sxs-lookup"><span data-stu-id="bad9c-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="bad9c-121">전송 계층에 사용할 수 있는 할당량을 설정할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="bad9c-122">NAT 및 방화벽 작업</span><span class="sxs-lookup"><span data-stu-id="bad9c-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="bad9c-123">방화벽을 사용하여 메시지를 주고 받을 경우 또는 NAT(Network Address Translation)를 사용할 경우 전송 계층을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="bad9c-124">Net.TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="bad9c-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="bad9c-125">WCF의 Net.TCP 포트 공유 구성 요소를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad9c-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bad9c-126">참조</span><span class="sxs-lookup"><span data-stu-id="bad9c-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="bad9c-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="bad9c-127">Related Sections</span></span>  
 [<span data-ttu-id="bad9c-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="bad9c-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="bad9c-129">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="bad9c-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
