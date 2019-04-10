---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 22992b4dfad4b4867adda0fcbbd8ecc5eb67d87e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160149"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="3af67-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="3af67-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="3af67-103">일시 참가자의 결과 메시지에 대한 응답을 기다리는 동안 WS-AT 프로토콜 서비스의 시간 제한이 초과되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3af67-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="3af67-104">참가자가 반환되면 트랜잭션 결과가 확실하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af67-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3af67-105">설명</span><span class="sxs-lookup"><span data-stu-id="3af67-105">Description</span></span>  
 <span data-ttu-id="3af67-106">일시 참가자가 커밋 또는 중단으로 결정했지만 주어진 시간 내에 커밋 또는 롤백 요청에 대해 응답하지 않을 때 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af67-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3af67-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="3af67-107">Troubleshooting</span></span>  
 <span data-ttu-id="3af67-108">주어진 시간 내에 모든 일시 참가자가 응답할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3af67-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="3af67-109">기본 시간은 180초입니다.</span><span class="sxs-lookup"><span data-stu-id="3af67-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="3af67-110">이 시간이 충분하지 않으면 WS-AT에 대한 `VolatileOutcomeDelay` 타이머 정책을 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3af67-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af67-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="3af67-111">See also</span></span>

- [<span data-ttu-id="3af67-112">추적</span><span class="sxs-lookup"><span data-stu-id="3af67-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3af67-113">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3af67-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3af67-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="3af67-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
