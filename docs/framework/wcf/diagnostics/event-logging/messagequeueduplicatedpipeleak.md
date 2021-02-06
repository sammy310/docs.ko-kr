---
description: '자세히 알아보기: MessageQueueDuplicatedPipeLeak'
title: MessageQueueDuplicatedPipeLeak
ms.date: 03/30/2017
ms.assetid: 743db7f1-32cc-4a3b-8d1a-5d1cf25e439c
ms.openlocfilehash: 07c3b9fdf3cc4644b65695f0d08beb69eea31f7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99656022"
---
# <a name="messagequeueduplicatedpipeleak"></a><span data-ttu-id="26210-103">MessageQueueDuplicatedPipeLeak</span><span class="sxs-lookup"><span data-stu-id="26210-103">MessageQueueDuplicatedPipeLeak</span></span>

<span data-ttu-id="26210-104">Id: 166</span><span class="sxs-lookup"><span data-stu-id="26210-104">Id: 166</span></span>  
  
 <span data-ttu-id="26210-105">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="26210-105">Severity: Error</span></span>  
  
 <span data-ttu-id="26210-106">범주: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="26210-106">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="26210-107">설명</span><span class="sxs-lookup"><span data-stu-id="26210-107">Description</span></span>  

 <span data-ttu-id="26210-108">이 이벤트는 중복 명명된 파이프를 발송하는 동안 오류가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26210-108">This event indicates that an error occurred while dispatching a duplicated named pipe.</span></span> <span data-ttu-id="26210-109">현재 이 핸들은 프로세스에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="26210-109">This handle is now leaked in the process.</span></span> <span data-ttu-id="26210-110">이 이벤트는 소스, 예외, 프로세스 이름 및 프로세스 ID를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="26210-110">The event lists the source, exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26210-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26210-111">See also</span></span>

- [<span data-ttu-id="26210-112">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="26210-112">Event Logging</span></span>](index.md)
- [<span data-ttu-id="26210-113">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="26210-113">Events General Reference</span></span>](events-general-reference.md)
