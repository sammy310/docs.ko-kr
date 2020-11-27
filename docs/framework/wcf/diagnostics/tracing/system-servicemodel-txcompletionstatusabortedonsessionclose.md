---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 0d8c77d01351b0c62e0186e5aee69ca70aebe15e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274324"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="3973d-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="3973d-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>

<span data-ttu-id="3973d-103">세션을 닫고 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute가 false로 설정되었을 때 지정된 트랜잭션이 완료되지 않았기 때문에 해당 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3973d-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3973d-104">Description</span><span class="sxs-lookup"><span data-stu-id="3973d-104">Description</span></span>  

 <span data-ttu-id="3973d-105">현재 활성 세션을 닫고 트랜잭션이 완료되지 않았으며 TransactionAutoCompleteOnSessionClose가 `false`로 설정된 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="3973d-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3973d-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="3973d-106">Troubleshooting</span></span>  

 <span data-ttu-id="3973d-107">이 추적은 조사해야 하는 발생 가능한 애플리케이션 버그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3973d-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3973d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3973d-108">See also</span></span>

- [<span data-ttu-id="3973d-109">추적</span><span class="sxs-lookup"><span data-stu-id="3973d-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="3973d-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3973d-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3973d-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="3973d-111">Administration and Diagnostics</span></span>](../index.md)
