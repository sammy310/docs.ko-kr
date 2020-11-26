---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: e4c8040d2350e3824b5d68dc6f32376007792a7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235118"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="26584-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="26584-102">System.ServiceModel.MessageProcessingPaused</span></span>

<span data-ttu-id="26584-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="26584-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="26584-104">Description</span><span class="sxs-lookup"><span data-stu-id="26584-104">Description</span></span>  

 <span data-ttu-id="26584-105">메시지를 처리하는 동안 스레드가 전환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26584-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="26584-106">메시지 처리는 다음 이유로 인해 일시 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26584-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="26584-107">ConcurrencyMode가 단일하거나 재진입할 수 있으며, 서비스가 다른 메시지를 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26584-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="26584-108">트랜잭션이 사용하도록 설정되어 있으며, 서비스가 다른 트랜잭션을 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26584-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="26584-109">현재 동기화 컨텍스트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="26584-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26584-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26584-110">See also</span></span>

- [<span data-ttu-id="26584-111">추적</span><span class="sxs-lookup"><span data-stu-id="26584-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="26584-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="26584-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="26584-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="26584-113">Administration and Diagnostics</span></span>](../index.md)
