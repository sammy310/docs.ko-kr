---
description: 자세한 내용은 DurableParticipantReplayWhilePreparing를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fcaa50dd4faa548cad8ff085f1c66f94c63bd010
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635664"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="39854-103">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="39854-103">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>

<span data-ttu-id="39854-104">WS-AT 프로토콜 서비스가 Prepare 메시지에 응답하지 않은 영속 참가자로부터 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="39854-104">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="39854-105">따라서 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39854-105">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="39854-106">설명</span><span class="sxs-lookup"><span data-stu-id="39854-106">Description</span></span>  

 <span data-ttu-id="39854-107">영속 참가자가 준비하는 동안 Reply 메시지를 받을 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="39854-107">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="39854-108">이 상태에 대한 잘못된 메시지로 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="39854-108">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="39854-109">문제 해결</span><span class="sxs-lookup"><span data-stu-id="39854-109">Troubleshooting</span></span>

<span data-ttu-id="39854-110">이 오류는 영 속 참가자 (하위 TransactionManagers 포함)가 오류를 복구 했음을 나타낼 수 있습니다. 그러나 트랜잭션 결과가 확실 하지 않으며 상태를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="39854-110">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39854-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39854-111">See also</span></span>

- [<span data-ttu-id="39854-112">추적</span><span class="sxs-lookup"><span data-stu-id="39854-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="39854-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="39854-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="39854-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="39854-114">Administration and Diagnostics</span></span>](../index.md)
