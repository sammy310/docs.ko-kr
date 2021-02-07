---
description: TxCompletionStatusCompletedForAsyncAbort에 대해 자세히 알아보세요.
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: 892a867607d1c6d34c06a59947cc336db067fb19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735688"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="4f50f-103">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="4f50f-103">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>

<span data-ttu-id="4f50f-104">비동기 중단으로 인해 지정된 작업에 대한 지정된 트랜잭션이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f50f-104">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4f50f-105">설명</span><span class="sxs-lookup"><span data-stu-id="4f50f-105">Description</span></span>  

 <span data-ttu-id="4f50f-106">다른 참가자가 중단을 응답하거나, 시간 초과가 발생하거나, 트랜잭션 참가자 내부에서 다른 오류가 발생하여 현재 트랜잭션이 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f50f-106">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4f50f-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="4f50f-107">Troubleshooting</span></span>  

 <span data-ttu-id="4f50f-108">이 중단이 예기치 않은 동작인 경우 모든 시스템 로그에서 실제 중단 이유를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4f50f-108">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f50f-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f50f-109">See also</span></span>

- [<span data-ttu-id="4f50f-110">추적</span><span class="sxs-lookup"><span data-stu-id="4f50f-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="4f50f-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4f50f-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4f50f-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="4f50f-112">Administration and Diagnostics</span></span>](../index.md)
