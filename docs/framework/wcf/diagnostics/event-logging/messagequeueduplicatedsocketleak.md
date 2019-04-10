---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 8533d53dc6a2d4510ffec2dcbf0e9bef15cde6ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206124"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="80fff-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="80fff-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="80fff-103">ID: 165</span><span class="sxs-lookup"><span data-stu-id="80fff-103">Id: 165</span></span>  
  
 <span data-ttu-id="80fff-104">심각도: Error</span><span class="sxs-lookup"><span data-stu-id="80fff-104">Severity: Error</span></span>  
  
 <span data-ttu-id="80fff-105">범주: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="80fff-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="80fff-106">설명</span><span class="sxs-lookup"><span data-stu-id="80fff-106">Description</span></span>  
 <span data-ttu-id="80fff-107">이 이벤트는 중복 소켓을 발송하는 동안 발생한 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="80fff-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="80fff-108">현재 이 핸들은 프로세스에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="80fff-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="80fff-109">이 이벤트는 소스, 예외, 프로세스 이름 및 프로세스 ID를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="80fff-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fff-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="80fff-110">See also</span></span>

- [<span data-ttu-id="80fff-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="80fff-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="80fff-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="80fff-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
