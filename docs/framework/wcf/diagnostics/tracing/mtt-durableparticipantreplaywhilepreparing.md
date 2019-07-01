---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486764"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="dfa9e-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="dfa9e-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="dfa9e-103">WS-AT 프로토콜 서비스가 Prepare 메시지에 응답하지 않은 영속 참가자로부터 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa9e-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="dfa9e-104">따라서 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dfa9e-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="dfa9e-105">설명</span><span class="sxs-lookup"><span data-stu-id="dfa9e-105">Description</span></span>  
 <span data-ttu-id="dfa9e-106">영속 참가자가 준비하는 동안 Reply 메시지를 받을 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfa9e-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="dfa9e-107">이 상태에 대한 잘못된 메시지로 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfa9e-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="dfa9e-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="dfa9e-108">Troubleshooting</span></span>

<span data-ttu-id="dfa9e-109">이 오류가 Subordinate 등 영 속 참가자 실패에서 복구 되었기를 나타낼 수 있습니다 그러나 트랜잭션 결과가 확인 하 고 해당 상태를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfa9e-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa9e-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="dfa9e-110">See also</span></span>

- [<span data-ttu-id="dfa9e-111">추적</span><span class="sxs-lookup"><span data-stu-id="dfa9e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="dfa9e-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="dfa9e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="dfa9e-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="dfa9e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
