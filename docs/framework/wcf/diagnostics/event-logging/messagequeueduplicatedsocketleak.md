---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: e7ccbdce37981dfd8971f0d7ef0031b52cad2379
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262439"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="5f995-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="5f995-102">MessageQueueDuplicatedSocketLeak</span></span>

<span data-ttu-id="5f995-103">Id: 165</span><span class="sxs-lookup"><span data-stu-id="5f995-103">Id: 165</span></span>  
  
 <span data-ttu-id="5f995-104">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="5f995-104">Severity: Error</span></span>  
  
 <span data-ttu-id="5f995-105">범주: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="5f995-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="5f995-106">Description</span><span class="sxs-lookup"><span data-stu-id="5f995-106">Description</span></span>  

 <span data-ttu-id="5f995-107">이 이벤트는 중복 소켓을 발송하는 동안 발생한 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f995-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="5f995-108">현재 이 핸들은 프로세스에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f995-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="5f995-109">이 이벤트는 소스, 예외, 프로세스 이름 및 프로세스 ID를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f995-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f995-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f995-110">See also</span></span>

- [<span data-ttu-id="5f995-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="5f995-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="5f995-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="5f995-112">Events General Reference</span></span>](events-general-reference.md)
