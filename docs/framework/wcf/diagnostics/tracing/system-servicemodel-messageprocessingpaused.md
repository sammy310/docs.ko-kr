---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598153"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="ae676-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="ae676-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="ae676-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="ae676-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="ae676-104">Description</span><span class="sxs-lookup"><span data-stu-id="ae676-104">Description</span></span>  
 <span data-ttu-id="ae676-105">메시지를 처리하는 동안 스레드가 전환되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ae676-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="ae676-106">메시지 처리는 다음 이유로 인해 일시 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae676-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="ae676-107">ConcurrencyMode가 단일하거나 재진입할 수 있으며, 서비스가 다른 메시지를 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae676-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="ae676-108">트랜잭션이 사용하도록 설정되어 있으며, 서비스가 다른 트랜잭션을 처리하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae676-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="ae676-109">현재 동기화 컨텍스트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae676-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae676-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae676-110">See also</span></span>

- [<span data-ttu-id="ae676-111">추적</span><span class="sxs-lookup"><span data-stu-id="ae676-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="ae676-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ae676-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ae676-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="ae676-113">Administration and Diagnostics</span></span>](../index.md)
