---
title: Net MSMQ 바인딩
ms.date: 03/30/2017
ms.assetid: fe4bb696-f57c-4cb3-9b7e-9d95fe6b8323
ms.openlocfilehash: 22b82e9335f3bf5861000a62374ab9e8dccce8cf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259982"
---
# <a name="net-msmq-binding"></a><span data-ttu-id="937a0-102">Net MSMQ 바인딩</span><span class="sxs-lookup"><span data-stu-id="937a0-102">Net MSMQ Binding</span></span>

<span data-ttu-id="937a0-103">이 단원에는 엔드포인트 요소의 MSMQ 바인딩 특성을 사용하는 방법을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-103">This section contains samples that demonstrate using MSMQ binding attributes of an endpoint element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="937a0-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="937a0-104">In This Section</span></span>  

 [<span data-ttu-id="937a0-105">트랜잭션된 MSMQ 바인딩</span><span class="sxs-lookup"><span data-stu-id="937a0-105">Transacted MSMQ Binding</span></span>](transacted-msmq-binding.md)  
 <span data-ttu-id="937a0-106">MSMQ(메시지 큐)를 사용하여 큐에 있는 트랜잭션된 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-106">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="937a0-107">일시 대기 통신</span><span class="sxs-lookup"><span data-stu-id="937a0-107">Volatile Queued Communication</span></span>](volatile-queued-communication.md)  
 <span data-ttu-id="937a0-108">MSMQ(메시지 큐) 전송에서 일시 대기 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-108">Demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="937a0-109">배달 못 한 편지 큐</span><span class="sxs-lookup"><span data-stu-id="937a0-109">Dead Letter Queues</span></span>](dead-letter-queues.md)  
 <span data-ttu-id="937a0-110">배달에 실패한 메시지를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-110">Demonstrates how to handle and process messages that have failed delivery.</span></span>  
  
 [<span data-ttu-id="937a0-111">Poison Message Handling in MSMQ 4.0</span><span class="sxs-lookup"><span data-stu-id="937a0-111">Poison Message Handling in MSMQ 4.0</span></span>](poison-message-handling-in-msmq-4-0.md)  
 <span data-ttu-id="937a0-112">MSMQ 4.0을 사용하여 서비스에서 포이즌 메시지 처리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-112">Demonstrates how to perform poison message handling in a service using MSMQ 4.0.</span></span>  
  
 [<span data-ttu-id="937a0-113">세션 및 큐</span><span class="sxs-lookup"><span data-stu-id="937a0-113">Sessions and Queues</span></span>](sessions-and-queues.md)  
 <span data-ttu-id="937a0-114">MSMQ(메시지 큐) 전송을 통해 대기 중인 통신으로 일련의 관련된 메시지를 보내고 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-114">Demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="937a0-115">상호 통신</span><span class="sxs-lookup"><span data-stu-id="937a0-115">Two-Way Communication</span></span>](two-way-communication.md)  
 <span data-ttu-id="937a0-116">MSMQ를 통해 트랜잭션된 대기 중인 양방향 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-116">Demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span>
  
 [<span data-ttu-id="937a0-117">SRMP</span><span class="sxs-lookup"><span data-stu-id="937a0-117">SRMP</span></span>](srmp.md)  
 <span data-ttu-id="937a0-118">HTTP를 통해 MSMQ(메시지 큐)를 사용하여 큐에 있는 트랜잭션된 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-118">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 [<span data-ttu-id="937a0-119">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="937a0-119">Message Security over Message Queuing</span></span>](message-security-over-message-queuing.md)  
 <span data-ttu-id="937a0-120">MSMQ를 통해 서버의 X.509v3 인증서를 사용하는 서버 인증을 요구하고 클라이언트에 대해 X.509v3 인증서 인증과 함께 WS-Security를 사용하는 애플리케이션을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="937a0-120">Demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span>
