---
title: 스트리밍 서비스 및 반복 되는 필드-WCF 개발자를 위한 gRPC
description: GRPC를 사용 하 여 데이터 컬렉션을 전달 하는 방법으로 반복 되는 필드를 스트리밍 서비스와 비교 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 0e717df57ba2bb52d63a063072d8a45bf0f7e395
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503376"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a><span data-ttu-id="492bf-103">gRPC 스트리밍 서비스 및 반복 되는 필드</span><span class="sxs-lookup"><span data-stu-id="492bf-103">gRPC streaming services vs. repeated fields</span></span>

<span data-ttu-id="492bf-104">gRPC 서비스는 데이터 집합 또는 개체 목록을 반환 하는 두 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="492bf-105">프로토콜 버퍼 메시지 사양은 다른 메시지 내의 목록 또는 메시지 배열을 선언 하는 데 `repeated` 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="492bf-106">GRPC 서비스 사양은 `stream` 키워드를 사용 하 여 장기 실행 영구 연결을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection.</span></span> <span data-ttu-id="492bf-107">이 연결을 통해 여러 메시지를 보내고 개별적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-107">Over that connection, multiple messages are sent, and can be processed, individually.</span></span> 

<span data-ttu-id="492bf-108">알림 또는 로그 메시지와 같은 장기 실행 임시 데이터에도 `stream` 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-108">You can also use the `stream` feature for long-running temporal data such as notifications or log messages.</span></span> <span data-ttu-id="492bf-109">그러나이 장에서는 단일 데이터 집합을 반환 하는 데 사용 하는 것을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-109">But this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="492bf-110">사용 해야 하는 작업은 다음과 같은 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-110">Which you should use depends on factors such as:</span></span>

- <span data-ttu-id="492bf-111">데이터 집합의 전체 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-111">The overall size of the dataset.</span></span>
- <span data-ttu-id="492bf-112">클라이언트 또는 서버 쪽에서 데이터 집합을 만드는 데 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-112">The time it took to create the dataset at either the client or server end.</span></span>
- <span data-ttu-id="492bf-113">데이터 집합의 소비자가 첫 번째 항목을 사용할 수 있는 즉시 해당 데이터 집합에 대 한 작업을 시작할 수 있는지 여부 또는 전체 데이터 집합이 유용한 작업을 수행 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-113">Whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="492bf-114">`repeated` 필드를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="492bf-114">When to use `repeated` fields</span></span>

<span data-ttu-id="492bf-115">크기가 제한 되 고 짧은 시간 내에 전체적으로 생성 될 수 있는 모든 데이터 집합의 경우 (예를 들어 1 초 미만) 일반 Protobuf 메시지에서 `repeated` 필드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-115">For any dataset that's constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="492bf-116">예를 들어 전자 상거래 시스템에서 주문 내의 항목 목록을 작성 하는 것이 신속 하 고 목록이 너무 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-116">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="492bf-117">`repeated` 필드를 포함 하는 단일 메시지를 반환 하는 것은 `stream`를 사용 하는 것 보다 더 빠른 크기 이며 네트워크 오버 헤드가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-117">Returning a single message with a `repeated` field is an order of magnitude faster than using `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="492bf-118">클라이언트에서 처리를 시작 하기 전에 모든 데이터를 요구 하 고 데이터 집합이 메모리에서 생성할 수 있을 만큼 작은 경우 `repeated` 필드를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-118">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field.</span></span> <span data-ttu-id="492bf-119">서버의 메모리에 데이터 집합을 만드는 속도가 느린 경우에도이를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-119">Consider it even if the creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="492bf-120">`stream` 메서드를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="492bf-120">When to use `stream` methods</span></span>

<span data-ttu-id="492bf-121">데이터 집합의 메시지 개체가 매우 클 경우 스트리밍 요청이 나 응답을 사용 하 여 전송 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-121">When the message objects in your datasets are potentially very large, it's best for you transfer them by using streaming requests or responses.</span></span> <span data-ttu-id="492bf-122">메모리에 많은 개체를 생성 하 고 네트워크에 쓴 다음 리소스를 확보 하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-122">It's more efficient to construct a large object in memory, write it to the network, and then free up the resources.</span></span> <span data-ttu-id="492bf-123">이 방법은 서비스의 확장성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-123">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="492bf-124">마찬가지로 메모리 부족으로 인 한 메모리 부족을 방지 하기 위해 제한 없는 크기의 데이터 집합을 스트림에 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-124">Similarly, you should send datasets of unconstrained size over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="492bf-125">소비자가 각 항목을 개별적으로 처리할 수 있는 데이터 집합의 경우에는 사용자에 게 진행률이 표시 될 수 있음을 의미 하는 스트림을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-125">For datasets where the consumer can separately process each item, you should consider using a stream if it means that progress can be indicated to the user.</span></span> <span data-ttu-id="492bf-126">스트림을 사용 하면 응용 프로그램의 응답성을 향상 시킬 수 있지만 응용 프로그램의 전반적인 성능과 균형을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-126">Using a stream can improve the responsiveness of an application, but you should balance it against the overall performance of the application.</span></span>

<span data-ttu-id="492bf-127">스트림이 유용할 수 있는 또 다른 시나리오는 여러 서비스에서 메시지를 처리 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-127">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="492bf-128">체인의 각 서비스가 스트림을 반환 하는 경우 터미널 서비스 (체인의 마지막 서비스)는 메시지 반환을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-128">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages.</span></span> <span data-ttu-id="492bf-129">이러한 메시지를 처리 하 고 체인을 따라 원래 요청자에 게 다시 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-129">These messages can be processed and passed back along the chain to the original requestor.</span></span> <span data-ttu-id="492bf-130">요청자는 스트림을 반환 하거나 결과를 단일 응답 메시지로 집계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-130">The requestor can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="492bf-131">이 방법은 MapReduce와 같은 패턴에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="492bf-131">This approach lends itself well to patterns like MapReduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="492bf-132">[이전](migrate-duplex-services.md)
>[다음](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="492bf-132">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
