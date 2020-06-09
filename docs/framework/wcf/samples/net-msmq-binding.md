---
title: Net MSMQ 바인딩
ms.date: 03/30/2017
ms.assetid: fe4bb696-f57c-4cb3-9b7e-9d95fe6b8323
ms.openlocfilehash: 622341ef00f5d8950fa0c013e427f20e02187893
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602429"
---
# <a name="net-msmq-binding"></a><span data-ttu-id="22815-102">Net MSMQ 바인딩</span><span class="sxs-lookup"><span data-stu-id="22815-102">Net MSMQ Binding</span></span>
<span data-ttu-id="22815-103">이 단원에는 엔드포인트 요소의 MSMQ 바인딩 특성을 사용하는 방법을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22815-103">This section contains samples that demonstrate using MSMQ binding attributes of an endpoint element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22815-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="22815-104">In This Section</span></span>  
 [<span data-ttu-id="22815-105">트랜잭션된 MSMQ 바인딩</span><span class="sxs-lookup"><span data-stu-id="22815-105">Transacted MSMQ Binding</span></span>](transacted-msmq-binding.md)  
 <span data-ttu-id="22815-106">MSMQ(메시지 큐)를 사용하여 큐에 있는 트랜잭션된 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-106">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="22815-107">일시 대기 통신</span><span class="sxs-lookup"><span data-stu-id="22815-107">Volatile Queued Communication</span></span>](volatile-queued-communication.md)  
 <span data-ttu-id="22815-108">MSMQ(메시지 큐) 전송에서 일시 대기 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-108">Demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="22815-109">배달 못 한 편지 큐</span><span class="sxs-lookup"><span data-stu-id="22815-109">Dead Letter Queues</span></span>](dead-letter-queues.md)  
 <span data-ttu-id="22815-110">배달에 실패한 메시지를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-110">Demonstrates how to handle and process messages that have failed delivery.</span></span>  
  
 [<span data-ttu-id="22815-111">Poison Message Handling in MSMQ 4.0</span><span class="sxs-lookup"><span data-stu-id="22815-111">Poison Message Handling in MSMQ 4.0</span></span>](poison-message-handling-in-msmq-4-0.md)  
 <span data-ttu-id="22815-112">MSMQ 4.0을 사용하여 서비스에서 포이즌 메시지 처리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-112">Demonstrates how to perform poison message handling in a service using MSMQ 4.0.</span></span>  
  
 [<span data-ttu-id="22815-113">세션 및 큐</span><span class="sxs-lookup"><span data-stu-id="22815-113">Sessions and Queues</span></span>](sessions-and-queues.md)  
 <span data-ttu-id="22815-114">MSMQ(메시지 큐) 전송을 통해 대기 중인 통신으로 일련의 관련된 메시지를 보내고 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-114">Demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="22815-115">상호 통신</span><span class="sxs-lookup"><span data-stu-id="22815-115">Two-Way Communication</span></span>](two-way-communication.md)  
 <span data-ttu-id="22815-116">MSMQ를 통해 트랜잭션된 대기 중인 양방향 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-116">Demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span>
  
 [<span data-ttu-id="22815-117">SRMP</span><span class="sxs-lookup"><span data-stu-id="22815-117">SRMP</span></span>](srmp.md)  
 <span data-ttu-id="22815-118">HTTP를 통해 MSMQ(메시지 큐)를 사용하여 큐에 있는 트랜잭션된 통신을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-118">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 [<span data-ttu-id="22815-119">메시지 큐에 대한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="22815-119">Message Security over Message Queuing</span></span>](message-security-over-message-queuing.md)  
 <span data-ttu-id="22815-120">MSMQ를 통해 서버의 X.509v3 인증서를 사용하는 서버 인증을 요구하고 클라이언트에 대해 X.509v3 인증서 인증과 함께 WS-Security를 사용하는 애플리케이션을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22815-120">Demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span>
