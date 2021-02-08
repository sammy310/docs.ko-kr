---
description: 자세한 내용은 ReplayMessageRetry를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: e4de1416fab2cf7098d0276b6130999c01ea6e3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803258"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="64633-103">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="64633-103">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>

<span data-ttu-id="64633-104">되풀이 메시지 재시도를 응답하지 않는 코디네이터에게 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="64633-104">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="64633-105">설명</span><span class="sxs-lookup"><span data-stu-id="64633-105">Description</span></span>  

 <span data-ttu-id="64633-106">로컬 트랜잭션 관리자가 주어진 시간 내에 응답을 받지 못해서 되풀이 메시지를 상위 코디네이터에게 다시 전송해야 할 경우에 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="64633-106">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="64633-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="64633-107">Troubleshooting</span></span>  

 <span data-ttu-id="64633-108">응답을 제시간에 전달하지 못하도록 하는 잠재적인 네트워크 문제 또는 제품 문제를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="64633-108">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="64633-109">이러한 메시지 중 대부분이 표시되면 이는 인프라 문제 또는 비정상적으로 긴 응답 시간을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64633-109">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="64633-110">두 가지 문제 모두 시스템 내의 트랜잭션 처리량을 심각하게 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="64633-110">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64633-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64633-111">See also</span></span>

- [<span data-ttu-id="64633-112">추적</span><span class="sxs-lookup"><span data-stu-id="64633-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="64633-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="64633-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="64633-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="64633-114">Administration and Diagnostics</span></span>](../index.md)
