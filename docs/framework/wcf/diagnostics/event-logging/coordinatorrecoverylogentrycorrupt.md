---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797978"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="5e7c8-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="5e7c8-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="5e7c8-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="5e7c8-103">Id: 139</span></span>  
  
 <span data-ttu-id="5e7c8-104">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="5e7c8-104">Severity: Error</span></span>  
  
 <span data-ttu-id="5e7c8-105">범주 TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="5e7c8-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="5e7c8-106">Description</span><span class="sxs-lookup"><span data-stu-id="5e7c8-106">Description</span></span>  
 <span data-ttu-id="5e7c8-107">이 이벤트는 코디네이터 복구 로그 항목이 손상되어 deserialize할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="5e7c8-108">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-108">Data loss may result from this error.</span></span> <span data-ttu-id="5e7c8-109">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e7c8-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7c8-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="5e7c8-110">See also</span></span>

- [<span data-ttu-id="5e7c8-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="5e7c8-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="5e7c8-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="5e7c8-112">Events General Reference</span></span>](events-general-reference.md)
