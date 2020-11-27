---
title: ParticipantRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: ab34785f-f953-4428-93ca-3c50d3f50a4a
ms.openlocfilehash: 8fe65199425196ab8910d9ffc9f70d7224137825
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278572"
---
# <a name="participantrecoverylogentrycorrupt"></a><span data-ttu-id="bc9df-102">ParticipantRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="bc9df-102">ParticipantRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="bc9df-103">Id: 138</span><span class="sxs-lookup"><span data-stu-id="bc9df-103">Id: 138</span></span>  
  
 <span data-ttu-id="bc9df-104">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="bc9df-104">Severity: Error</span></span>  
  
 <span data-ttu-id="bc9df-105">범주: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="bc9df-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="bc9df-106">Description</span><span class="sxs-lookup"><span data-stu-id="bc9df-106">Description</span></span>  

 <span data-ttu-id="bc9df-107">이 이벤트는 참가자 복구 로그 항목이 손상되어 역직렬화할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc9df-107">This event indicates that a participant recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="bc9df-108">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc9df-108">Data loss may result from this error.</span></span> <span data-ttu-id="bc9df-109">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc9df-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc9df-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc9df-110">See also</span></span>

- [<span data-ttu-id="bc9df-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="bc9df-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="bc9df-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="bc9df-112">Events General Reference</span></span>](events-general-reference.md)
