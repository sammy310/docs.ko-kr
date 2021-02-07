---
description: TxCompletionStatusAbortedOnSessionClose에 대해 자세히 알아보세요.
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: d47dc1a87c7f44b58f70f9590b4233f1e0a9074e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735714"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="52733-103">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="52733-103">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>

<span data-ttu-id="52733-104">세션을 닫고 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute가 false로 설정되었을 때 지정된 트랜잭션이 완료되지 않았기 때문에 해당 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="52733-104">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="52733-105">설명</span><span class="sxs-lookup"><span data-stu-id="52733-105">Description</span></span>  

 <span data-ttu-id="52733-106">현재 활성 세션을 닫고 트랜잭션이 완료되지 않았으며 TransactionAutoCompleteOnSessionClose가 `false`로 설정된 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="52733-106">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="52733-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="52733-107">Troubleshooting</span></span>  

 <span data-ttu-id="52733-108">이 추적은 조사해야 하는 발생 가능한 애플리케이션 버그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52733-108">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52733-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52733-109">See also</span></span>

- [<span data-ttu-id="52733-110">추적</span><span class="sxs-lookup"><span data-stu-id="52733-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="52733-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="52733-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="52733-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="52733-112">Administration and Diagnostics</span></span>](../index.md)
