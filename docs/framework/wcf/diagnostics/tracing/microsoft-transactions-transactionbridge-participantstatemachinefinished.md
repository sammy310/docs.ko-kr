---
title: Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 54b677f7-03ad-40f2-9c5d-297a8ad9bf90
ms.openlocfilehash: 0652b3b76c155431b68c5ee0dc8f83977f9845a5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594363"
---
# <a name="microsofttransactionstransactionbridgeparticipantstatemachinefinished"></a><span data-ttu-id="c46a9-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="c46a9-102">Microsoft.Transactions.TransactionBridge.ParticipantStateMachineFinished</span></span>
<span data-ttu-id="c46a9-103">참가자 인리스트먼트에 대한 상태 시스템이 완료 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c46a9-103">The state machine for a participant enlistment entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c46a9-104">Description</span><span class="sxs-lookup"><span data-stu-id="c46a9-104">Description</span></span>  
 <span data-ttu-id="c46a9-105">하위 참여 인리스트먼트에서 2PC(2단계 커밋) 처리를 완료한 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46a9-105">Traced when a subordinate participant enlistment has completed 2pc processing.</span></span> <span data-ttu-id="c46a9-106">인리스트먼트 결과는 커밋됨 또는 중단됨입니다.</span><span class="sxs-lookup"><span data-stu-id="c46a9-106">The outcome for the enlistment can be Committed or Aborted.</span></span> <span data-ttu-id="c46a9-107">참가자가 준비 과정에서 ReadOnly를 선택하는 경우에도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="c46a9-107">It is also traced if any participant votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46a9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c46a9-108">See also</span></span>

- [<span data-ttu-id="c46a9-109">추적</span><span class="sxs-lookup"><span data-stu-id="c46a9-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="c46a9-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c46a9-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c46a9-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="c46a9-111">Administration and Diagnostics</span></span>](../index.md)
