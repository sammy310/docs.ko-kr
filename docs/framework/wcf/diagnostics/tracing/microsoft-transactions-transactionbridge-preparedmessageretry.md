---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: edab153123ae48702811532df3b5b5bf0849c26a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275920"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="eaa9c-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="eaa9c-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>

<span data-ttu-id="eaa9c-103">준비됨 메시지 재시도를 응답하지 않는 코디네이터에게 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9c-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="eaa9c-104">Description</span><span class="sxs-lookup"><span data-stu-id="eaa9c-104">Description</span></span>  

 <span data-ttu-id="eaa9c-105">로컬 트랜잭션 관리자가 주어진 시간 내에 응답을 받지 못해서 준비됨 메시지를 상위 코디네이터에게 다시 전송해야 할 경우에 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9c-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="eaa9c-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="eaa9c-106">Troubleshooting</span></span>  

 <span data-ttu-id="eaa9c-107">응답을 제시간에 전달하지 못하도록 하는 잠재적인 네트워크 문제 또는 제품 문제를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9c-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="eaa9c-108">이러한 메시지 중 대부분이 표시되면 이는 인프라 문제 또는 비정상적으로 긴 응답 시간을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9c-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="eaa9c-109">두 가지 문제 모두 시스템 내의 트랜잭션 처리량을 심각하게 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="eaa9c-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa9c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaa9c-110">See also</span></span>

- [<span data-ttu-id="eaa9c-111">추적</span><span class="sxs-lookup"><span data-stu-id="eaa9c-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="eaa9c-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="eaa9c-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="eaa9c-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="eaa9c-113">Administration and Diagnostics</span></span>](../index.md)
