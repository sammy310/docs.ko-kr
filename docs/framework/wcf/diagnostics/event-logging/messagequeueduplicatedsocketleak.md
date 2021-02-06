---
description: '자세히 알아보기: MessageQueueDuplicatedSocketLeak'
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: d439485a00c7d9c155cad78d741d16a40c37a438
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99656009"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="0c905-103">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="0c905-103">MessageQueueDuplicatedSocketLeak</span></span>

<span data-ttu-id="0c905-104">Id: 165</span><span class="sxs-lookup"><span data-stu-id="0c905-104">Id: 165</span></span>  
  
 <span data-ttu-id="0c905-105">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="0c905-105">Severity: Error</span></span>  
  
 <span data-ttu-id="0c905-106">범주: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="0c905-106">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="0c905-107">설명</span><span class="sxs-lookup"><span data-stu-id="0c905-107">Description</span></span>  

 <span data-ttu-id="0c905-108">이 이벤트는 중복 소켓을 발송하는 동안 발생한 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c905-108">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="0c905-109">현재 이 핸들은 프로세스에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c905-109">This handle is now leaked in the process.</span></span> <span data-ttu-id="0c905-110">이 이벤트는 소스, 예외, 프로세스 이름 및 프로세스 ID를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0c905-110">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c905-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c905-111">See also</span></span>

- [<span data-ttu-id="0c905-112">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="0c905-112">Event Logging</span></span>](index.md)
- [<span data-ttu-id="0c905-113">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="0c905-113">Events General Reference</span></span>](events-general-reference.md)
