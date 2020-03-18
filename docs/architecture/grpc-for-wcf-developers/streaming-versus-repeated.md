---
title: 스트리밍 서비스 vs. 반복 필드 - WCF 개발자를 위한 gRPC
description: 반복되는 필드를 gRPC를 사용하여 데이터 컬렉션을 전달하는 방법으로 스트리밍 서비스와 비교합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 542ebc393f9c9c1ad717d02d01fab33d85c18917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147752"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a><span data-ttu-id="aaf2d-103">gRPC 스트리밍 서비스 vs 반복 필드</span><span class="sxs-lookup"><span data-stu-id="aaf2d-103">gRPC streaming services vs. repeated fields</span></span>

<span data-ttu-id="aaf2d-104">gRPC 서비스는 데이터 집합 또는 개체 목록을 반환하는 두 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="aaf2d-105">프로토콜 버퍼 메시지 사양은 `repeated` 다른 메시지 내의 메시지 목록 또는 배열을 선언하기 위한 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="aaf2d-106">gRPC 서비스 사양은 `stream` 키워드를 사용하여 장기 실행 영구 연결을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection.</span></span> <span data-ttu-id="aaf2d-107">이 연결을 통해 여러 메시지가 전송되고 개별적으로 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-107">Over that connection, multiple messages are sent, and can be processed, individually.</span></span>

<span data-ttu-id="aaf2d-108">알림 또는 로그 메시지와 같은 장기 실행 시간 데이터에 이 `stream` 기능을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-108">You can also use the `stream` feature for long-running temporal data such as notifications or log messages.</span></span> <span data-ttu-id="aaf2d-109">그러나 이 장에서는 단일 데이터 집합을 반환하는 데 사용하는 것을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-109">But this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="aaf2d-110">사용해야 하는 요소는 다음과 같은 요인에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-110">Which you should use depends on factors such as:</span></span>

- <span data-ttu-id="aaf2d-111">데이터 집합의 전체 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-111">The overall size of the dataset.</span></span>
- <span data-ttu-id="aaf2d-112">클라이언트 또는 서버 끝에서 데이터 집합을 만드는 데 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-112">The time it took to create the dataset at either the client or server end.</span></span>
- <span data-ttu-id="aaf2d-113">데이터 집합의 소비자가 첫 번째 항목을 사용할 수 있는 즉시 데이터 집합에 대해 작업을 시작할 수 있는지 또는 유용한 작업을 수행하려면 전체 데이터 집합이 필요한지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-113">Whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="aaf2d-114">필드를 사용하는 `repeated` 경우</span><span class="sxs-lookup"><span data-stu-id="aaf2d-114">When to use `repeated` fields</span></span>

<span data-ttu-id="aaf2d-115">크기가 제한되고 짧은 시간 안에 전체적으로 생성할 수 있는 데이터 집합의 경우 1초 미만으로 일반 `repeated` Protobuf 메시지에서 필드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-115">For any dataset that's constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="aaf2d-116">예를 들어 전자 상거래 시스템에서 주문 내에서 항목 목록을 작성하는 것은 빠르며 목록이 매우 크지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-116">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="aaf2d-117">`repeated` 필드와 함께 단일 메시지를 반환하는 것은 사용하는 `stream` 것보다 훨씬 빠르며 네트워크 오버헤드가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-117">Returning a single message with a `repeated` field is an order of magnitude faster than using `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="aaf2d-118">클라이언트가 처리를 시작하기 전에 모든 데이터가 필요하고 데이터 집합이 메모리에서 생성할 수 `repeated` 있을 만큼 작으면 필드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-118">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field.</span></span> <span data-ttu-id="aaf2d-119">서버의 메모리에 데이터 집합을 만드는 속도가 느린 경우에도 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-119">Consider it even if the creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="aaf2d-120">`stream` 메소드 사용 시기</span><span class="sxs-lookup"><span data-stu-id="aaf2d-120">When to use `stream` methods</span></span>

<span data-ttu-id="aaf2d-121">데이터 집합의 메시지 개체가 잠재적으로 매우 큰 경우 스트리밍 요청 또는 응답을 사용하여 메시지 개체를 전송하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-121">When the message objects in your datasets are potentially very large, it's best for you transfer them by using streaming requests or responses.</span></span> <span data-ttu-id="aaf2d-122">메모리에 큰 개체를 구성하고 네트워크에 작성한 다음 리소스를 확보하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-122">It's more efficient to construct a large object in memory, write it to the network, and then free up the resources.</span></span> <span data-ttu-id="aaf2d-123">이 방법을 사용하면 서비스의 확장성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-123">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="aaf2d-124">마찬가지로, 스트림을 구성하는 동안 메모리부족을 방지하기 위해 제한되지 않은 크기의 데이터 집합을 스트림에 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-124">Similarly, you should send datasets of unconstrained size over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="aaf2d-125">소비자가 각 항목을 별도로 처리할 수 있는 데이터 집합의 경우 진행률을 사용자에게 나타낼 수 있음을 의미하는 경우 스트림을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-125">For datasets where the consumer can separately process each item, you should consider using a stream if it means that progress can be indicated to the user.</span></span> <span data-ttu-id="aaf2d-126">스트림을 사용하면 응용 프로그램의 응답성이 향상될 수 있지만 응용 프로그램의 전반적인 성능과 균형을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-126">Using a stream can improve the responsiveness of an application, but you should balance it against the overall performance of the application.</span></span>

<span data-ttu-id="aaf2d-127">스트림이 유용할 수 있는 또 다른 시나리오는 여러 서비스에서 메시지가 처리되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-127">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="aaf2d-128">체인의 각 서비스가 스트림을 반환하는 경우 터미널 서비스(즉, 체인의 마지막 서비스)가 메시지 반환을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-128">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages.</span></span> <span data-ttu-id="aaf2d-129">이러한 메시지는 체인을 따라 처리되어 원래 요청자에게 다시 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-129">These messages can be processed and passed back along the chain to the original requestor.</span></span> <span data-ttu-id="aaf2d-130">요청자는 스트림을 반환하거나 결과를 단일 응답 메시지로 집계할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-130">The requestor can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="aaf2d-131">이 방법은 MapReduce와 같은 패턴에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf2d-131">This approach lends itself well to patterns like MapReduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aaf2d-132">[이전](migrate-duplex-services.md)
>[다음](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="aaf2d-132">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
