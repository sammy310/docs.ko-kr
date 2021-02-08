---
description: '자세히 알아보기: CoordinatorRecoveryLogEntryCorrupt'
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: 3a848c634a226b34023a24898f9827162b4dafc7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771342"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="9aa4d-103">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="9aa4d-103">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="9aa4d-104">Id: 139</span><span class="sxs-lookup"><span data-stu-id="9aa4d-104">Id: 139</span></span>  
  
 <span data-ttu-id="9aa4d-105">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="9aa4d-105">Severity: Error</span></span>  
  
 <span data-ttu-id="9aa4d-106">범주: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="9aa4d-106">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="9aa4d-107">설명</span><span class="sxs-lookup"><span data-stu-id="9aa4d-107">Description</span></span>  

 <span data-ttu-id="9aa4d-108">이 이벤트는 코디네이터 복구 로그 항목이 손상되어 역직렬화할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-108">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="9aa4d-109">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-109">Data loss may result from this error.</span></span> <span data-ttu-id="9aa4d-110">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aa4d-110">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa4d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9aa4d-111">See also</span></span>

- [<span data-ttu-id="9aa4d-112">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="9aa4d-112">Event Logging</span></span>](index.md)
- [<span data-ttu-id="9aa4d-113">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="9aa4d-113">Events General Reference</span></span>](events-general-reference.md)
