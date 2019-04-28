---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: ac1dacef94d6446aa407e4a390b9561d033af1bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927025"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="eff61-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="eff61-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="eff61-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="eff61-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="eff61-104">설명</span><span class="sxs-lookup"><span data-stu-id="eff61-104">Description</span></span>  
 <span data-ttu-id="eff61-105">메시지를 처리하는 동안 스레드가 전환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eff61-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="eff61-106">메시지 처리는 다음 이유로 인해 일시 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff61-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="eff61-107">ConcurrencyMode가 단일하거나 재진입할 수 있으며, 서비스가 다른 메시지를 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff61-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="eff61-108">트랜잭션이 사용하도록 설정되어 있으며, 서비스가 다른 트랜잭션을 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eff61-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="eff61-109">현재 동기화 컨텍스트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eff61-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff61-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="eff61-110">See also</span></span>

- [<span data-ttu-id="eff61-111">추적</span><span class="sxs-lookup"><span data-stu-id="eff61-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="eff61-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="eff61-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="eff61-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="eff61-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
