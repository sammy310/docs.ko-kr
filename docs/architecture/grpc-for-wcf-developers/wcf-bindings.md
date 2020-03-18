---
title: WCF 바인딩 및 전송 - WCF 개발자를 위한 gRPC
description: 다양한 WCF 바인딩 및 전송이 gRPC와 어떻게 비교되는지 알아봅니다.
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147726"
---
# <a name="wcf-bindings-and-transports"></a><span data-ttu-id="14dec-103">WCF 바인딩 및 전송</span><span class="sxs-lookup"><span data-stu-id="14dec-103">WCF bindings and transports</span></span>

<span data-ttu-id="14dec-104">WCF(Windows 통신 Foundation)에는 서로 다른 네트워크 프로토콜, 와이어 형식 및 기타 구현 세부 정보를 지정하는 기본 제공 *바인딩이* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-104">Windows Communication Foundation (WCF) has built-in *bindings* that specify different network protocols, wire formats, and other implementation details.</span></span> <span data-ttu-id="14dec-105">gRPC는 하나의 네트워크 프로토콜과 하나의 와이어 형식만 효과적으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-105">gRPC effectively has just one network protocol and one wire format.</span></span> <span data-ttu-id="14dec-106">기술적으로 는 와이어 형식을 사용자 *지정할 수* 있지만 이 책의 범위를 벗어납니다. 대부분의 경우 gRPC가 최상의 솔루션을 제공한다는 사실을 알게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-106">(Technically you *can* customize the wire format, but that's beyond the scope of this book.) You're likely to discover that gRPC offers the best solution in most cases.</span></span>

<span data-ttu-id="14dec-107">다음은 가장 관련성이 가장 관련성이 있는 WCF 바인딩과 gRPC에서 해당 바인딩과 비교하는 방법에 대한 짧은 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-107">What follows is a short discussion about the most relevant WCF bindings and how they compare to their equivalents in gRPC.</span></span>

## <a name="nettcp"></a><span data-ttu-id="14dec-108">Nettcp</span><span class="sxs-lookup"><span data-stu-id="14dec-108">NetTCP</span></span>

<span data-ttu-id="14dec-109">WCF의 NetTCP 바인딩을 사용하면 영구 연결, 작은 메시지 및 양방향 메시징을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-109">WCF's NetTCP binding allows for persistent connections, small messages, and two-way messaging.</span></span> <span data-ttu-id="14dec-110">그러나 .NET 클라이언트와 서버 간에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-110">But it works only between .NET clients and servers.</span></span> <span data-ttu-id="14dec-111">gRPC는 동일한 기능을 허용하지만 여러 프로그래밍 언어 및 플랫폼에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-111">gRPC allows the same functionality but is supported across multiple programming languages and platforms.</span></span>

<span data-ttu-id="14dec-112">gRPC에는 WCF의 NetTCP 바인딩의 많은 기능이 있지만 항상 같은 방식으로 구현되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-112">gRPC has many features of WCF's NetTCP binding, but they're not always implemented in the same way.</span></span> <span data-ttu-id="14dec-113">예를 들어 WCF에서 암호화는 구성을 통해 제어되고 프레임워크에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-113">For example, in WCF, encryption is controlled through configuration and handled in the framework.</span></span> <span data-ttu-id="14dec-114">gRPC에서 암호화는 TLS를 통해 HTTP/2를 통해 연결 수준에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-114">In gRPC, encryption is achieved at the connection level through HTTP/2 over TLS.</span></span>

## <a name="http"></a><span data-ttu-id="14dec-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="14dec-115">HTTP</span></span>

<span data-ttu-id="14dec-116">BasicHttpBinding이라는 WCF 바인딩은 일반적으로 텍스트 기반이며 SOAP를 와이어 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-116">The WCF binding called BasicHttpBinding is usually text based and uses SOAP as the wire format.</span></span> <span data-ttu-id="14dec-117">NetTCP 바인딩에 비해 속도가 느립니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-117">It's slow compared to the NetTCP binding.</span></span> <span data-ttu-id="14dec-118">일반적으로 플랫폼 간 상호 운용성 또는 인터넷 인프라를 통해 연결을 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-118">It's generally used to provide cross-platform interoperability, or connection over internet infrastructure.</span></span>

<span data-ttu-id="14dec-119">gRPC에서 해당하는 메시지에 대한 이진 Protobuf 와이어 형식의 기본 전송 계층으로 HTTP/2를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-119">The equivalent in gRPC uses HTTP/2 as the underlying transport layer with the binary Protobuf wire format for messages.</span></span> <span data-ttu-id="14dec-120">따라서 NetTCP 서비스 수준에서 성능을 제공하고 모든 최신 프로그래밍 언어 및 프레임워크와의 전체 플랫폼 간 상호 운용성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-120">So it can offer performance at the NetTCP service level and full cross-platform interoperability with all modern programming languages and frameworks.</span></span>

## <a name="named-pipes"></a><span data-ttu-id="14dec-121">명명된 파이프</span><span class="sxs-lookup"><span data-stu-id="14dec-121">Named pipes</span></span>

<span data-ttu-id="14dec-122">WCF는 동일한 물리적 컴퓨터에서 프로세스 간의 통신을 위해 *명명된 파이프* 바인딩을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-122">WCF provided a *named pipes* binding for communication between processes on the same physical machine.</span></span> <span data-ttu-id="14dec-123">ASP.NET 코어 gRPC의 첫 번째 릴리스는 명명된 파이프를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-123">The first release of ASP.NET Core gRPC does not support named pipes.</span></span> <span data-ttu-id="14dec-124">명명된 파이프(및 유닉스 도메인 소켓)에 대한 클라이언트 및 서버 지원을 추가하는 것이 향후 릴리스의 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-124">Adding client and server support for named pipes (and Unix domain sockets) is a goal for a future release.</span></span>

## <a name="msmq"></a><span data-ttu-id="14dec-125">MSMQ</span><span class="sxs-lookup"><span data-stu-id="14dec-125">MSMQ</span></span>

<span data-ttu-id="14dec-126">MSMQ는 독점적인 Windows 메시지 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-126">MSMQ is a proprietary Windows message queue.</span></span> <span data-ttu-id="14dec-127">WCF가 MSMQ에 바인딩하면 나중에 언제든지 처리될 수 있는 클라이언트의 요청을 "발생 및 잊어버리기" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-127">WCF's binding to MSMQ enables "fire and forget" requests from clients that might be processed at any time in the future.</span></span> <span data-ttu-id="14dec-128">gRPC는 기본적으로 메시지 큐 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-128">gRPC doesn't natively provide any message queue functionality.</span></span>

<span data-ttu-id="14dec-129">가장 좋은 방법은 Azure 서비스 버스, RabbitMQ 또는 Kafka와 같은 메시징 시스템을 직접 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-129">The best alternative is to directly use a messaging system like Azure Service Bus, RabbitMQ, or Kafka.</span></span> <span data-ttu-id="14dec-130">클라이언트가 큐에 직접 메시지를 배치하거나 메시지를 큐에 큐에 넣는 gRPC 클라이언트 스트리밍 서비스를 사용하여 이를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-130">You can implement this with the client placing messages directly onto the queue, or a gRPC client streaming service that enqueues the messages.</span></span>

## <a name="webhttpbinding"></a><span data-ttu-id="14dec-131">WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="14dec-131">WebHttpBinding</span></span>

<span data-ttu-id="14dec-132">WebHttpBinding (WCF REST라고도 `WebGet` 함)와 `WebInvoke` 특성을 통해 JSON을 말할 수있는 RESTful API를 개발할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-132">WebHttpBinding (also known as WCF REST), with the `WebGet` and `WebInvoke` attributes, enabled you to develop RESTful APIs that could speak JSON at a time when this was less common.</span></span> <span data-ttu-id="14dec-133">WCF REST로 빌드된 RESTful API가 있는 경우 일반 ASP.NET 코어 MVC 웹 API 응용 프로그램으로 마이그레이션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-133">If you have a RESTful API built with WCF REST, consider migrating it to a regular ASP.NET Core MVC Web API application.</span></span> <span data-ttu-id="14dec-134">이 마이그레이션은 gRPC로 변환하는 것과 동일한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14dec-134">This migration would provide the same functionality as a conversion to gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="14dec-135">[이전](wcf-endpoints-grpc-methods.md)
>[다음](rpc-types.md)</span><span class="sxs-lookup"><span data-stu-id="14dec-135">[Previous](wcf-endpoints-grpc-methods.md)
[Next](rpc-types.md)</span></span>
