---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: e4466df2ce96760db4790b6545484704c22f0842
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254300"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="bb425-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="bb425-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>

<span data-ttu-id="bb425-103">처리되지 않은 실행 예외로 인해 지정된 작업에 대한 지정된 트랜잭션이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb425-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bb425-104">Description</span><span class="sxs-lookup"><span data-stu-id="bb425-104">Description</span></span>  

 <span data-ttu-id="bb425-105">현재 트랜잭션을 완료하는 동안 오류가 발생하는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb425-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="bb425-106">이러한 경우는 회신이나 오류가 호출자에게 보내지기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bb425-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bb425-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="bb425-107">Troubleshooting</span></span>  

 <span data-ttu-id="bb425-108">예외 메시지 및 실행 가능한 항목에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bb425-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb425-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb425-109">See also</span></span>

- [<span data-ttu-id="bb425-110">추적</span><span class="sxs-lookup"><span data-stu-id="bb425-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="bb425-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bb425-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bb425-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="bb425-112">Administration and Diagnostics</span></span>](../index.md)
