---
description: 자세한 내용은 ParticipantStateMachineFinished를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: f49027b82957969779423d0895ff24a4a36d1f4f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99759382"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="08348-103">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="08348-103">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>

<span data-ttu-id="08348-104">참가자 인리스트먼트에 대한 상태 시스템이 완료 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08348-104">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="08348-105">설명</span><span class="sxs-lookup"><span data-stu-id="08348-105">Description</span></span>  

 <span data-ttu-id="08348-106">하위 참여 인리스트먼트에서 2PC(2단계 커밋) 처리를 완료한 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="08348-106">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="08348-107">인리스트먼트 결과는 커밋됨 또는 중단됨입니다.</span><span class="sxs-lookup"><span data-stu-id="08348-107">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="08348-108">참가자가 준비 과정에서 ReadOnly를 선택하는 경우에도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="08348-108">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08348-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08348-109">See also</span></span>

- [<span data-ttu-id="08348-110">추적</span><span class="sxs-lookup"><span data-stu-id="08348-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="08348-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="08348-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="08348-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="08348-112">Administration and Diagnostics</span></span>](../index.md)
