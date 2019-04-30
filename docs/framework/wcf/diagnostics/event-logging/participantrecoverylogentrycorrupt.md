---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 566517a122e17078156a61e0d3808ae06d0cf93c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61999091"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="b6cf4-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="b6cf4-102">ParticipantRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="b6cf4-103">ID: 138</span><span class="sxs-lookup"><span data-stu-id="b6cf4-103">Id: 138</span></span>  
  
 <span data-ttu-id="b6cf4-104">심각도: Error</span><span class="sxs-lookup"><span data-stu-id="b6cf4-104">Severity: Error</span></span>  
  
 <span data-ttu-id="b6cf4-105">범주: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="b6cf4-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="b6cf4-106">설명</span><span class="sxs-lookup"><span data-stu-id="b6cf4-106">Description</span></span>  
 <span data-ttu-id="b6cf4-107">이 이벤트는 참가자 복구 로그 항목이 손상되어 deserialize할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6cf4-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="b6cf4-108">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cf4-108">Data loss may result from this error.</span></span> <span data-ttu-id="b6cf4-109">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6cf4-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cf4-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6cf4-110">See also</span></span>

- [<span data-ttu-id="b6cf4-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="b6cf4-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="b6cf4-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="b6cf4-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
