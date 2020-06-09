---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 3b9a3703e49c3932f62fcfb6994c9028b074bbe8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594415"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="83064-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="83064-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>
<span data-ttu-id="83064-103">코디네이터 인리스트먼트를 위한 상태 시스템이 완료 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83064-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="83064-104">Description</span><span class="sxs-lookup"><span data-stu-id="83064-104">Description</span></span>  
 <span data-ttu-id="83064-105">로컬 트랜잭션 관리자가 상위 코디네이터 인리스트먼트에서 2PC(2단계 커밋) 처리를 완료한 것으로 간주할 때 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="83064-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="83064-106">인리스트먼트 결과는 커밋됨 또는 중단됨 또는 잊어버림입니다.</span><span class="sxs-lookup"><span data-stu-id="83064-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="83064-107">로컬 트랜잭션 관리자가 준비 과정에서 ReadOnly를 선택하는 경우에도 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="83064-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83064-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83064-108">See also</span></span>

- [<span data-ttu-id="83064-109">추적</span><span class="sxs-lookup"><span data-stu-id="83064-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="83064-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="83064-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="83064-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="83064-111">Administration and Diagnostics</span></span>](../index.md)
