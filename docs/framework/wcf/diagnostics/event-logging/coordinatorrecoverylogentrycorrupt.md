---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121630"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="3efc2-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="3efc2-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="3efc2-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="3efc2-103">Id: 139</span></span>  
  
 <span data-ttu-id="3efc2-104">심각도: Error</span><span class="sxs-lookup"><span data-stu-id="3efc2-104">Severity: Error</span></span>  
  
 <span data-ttu-id="3efc2-105">범주: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="3efc2-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="3efc2-106">설명</span><span class="sxs-lookup"><span data-stu-id="3efc2-106">Description</span></span>  
 <span data-ttu-id="3efc2-107">이 이벤트는 코디네이터 복구 로그 항목이 손상되어 deserialize할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3efc2-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="3efc2-108">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3efc2-108">Data loss may result from this error.</span></span> <span data-ttu-id="3efc2-109">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3efc2-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efc2-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="3efc2-110">See also</span></span>

- [<span data-ttu-id="3efc2-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="3efc2-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="3efc2-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="3efc2-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
