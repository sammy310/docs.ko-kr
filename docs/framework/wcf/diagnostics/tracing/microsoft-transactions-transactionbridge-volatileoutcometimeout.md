---
description: 자세한 내용은 VolatileOutcomeTimeout를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 5dd6ecce995d315581e1335e4dc83c425a6381b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677238"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="4b551-103">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="4b551-103">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>

<span data-ttu-id="4b551-104">일시 참가자의 결과 메시지에 대한 응답을 기다리는 동안 WS-AT 프로토콜 서비스의 시간 제한이 초과되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4b551-104">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="4b551-105">참가자가 반환되면 트랜잭션 결과가 확실하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b551-105">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4b551-106">설명</span><span class="sxs-lookup"><span data-stu-id="4b551-106">Description</span></span>  

 <span data-ttu-id="4b551-107">일시 참가자가 커밋 또는 중단으로 결정했지만 주어진 시간 내에 커밋 또는 롤백 요청에 대해 응답하지 않을 때 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b551-107">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4b551-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="4b551-108">Troubleshooting</span></span>  

 <span data-ttu-id="4b551-109">주어진 시간 내에 모든 일시 참가자가 응답할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b551-109">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="4b551-110">기본 시간은 180초입니다.</span><span class="sxs-lookup"><span data-stu-id="4b551-110">The default time period is 180 seconds.</span></span>  <span data-ttu-id="4b551-111">이 시간이 충분하지 않으면 WS-AT에 대한 `VolatileOutcomeDelay` 타이머 정책을 증가시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4b551-111">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b551-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b551-112">See also</span></span>

- [<span data-ttu-id="4b551-113">추적</span><span class="sxs-lookup"><span data-stu-id="4b551-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="4b551-114">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4b551-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4b551-115">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="4b551-115">Administration and Diagnostics</span></span>](../index.md)
