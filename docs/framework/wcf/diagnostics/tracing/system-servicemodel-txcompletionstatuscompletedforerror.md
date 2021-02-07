---
description: TxCompletionStatusCompletedForError에 대해 자세히 알아보세요.
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 83cd5c258b3a60f69cc94426aed7ccc1d27f6013
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735610"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="2e936-103">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="2e936-103">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>

<span data-ttu-id="2e936-104">처리되지 않은 실행 예외로 인해 지정된 작업에 대한 지정된 트랜잭션이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e936-104">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e936-105">설명</span><span class="sxs-lookup"><span data-stu-id="2e936-105">Description</span></span>  

 <span data-ttu-id="2e936-106">현재 트랜잭션을 완료하는 동안 오류가 발생하는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e936-106">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="2e936-107">이러한 경우는 회신이나 오류가 호출자에게 보내지기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2e936-107">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2e936-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e936-108">Troubleshooting</span></span>  

 <span data-ttu-id="2e936-109">예외 메시지 및 실행 가능한 항목에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2e936-109">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e936-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e936-110">See also</span></span>

- [<span data-ttu-id="2e936-111">추적</span><span class="sxs-lookup"><span data-stu-id="2e936-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="2e936-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e936-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2e936-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="2e936-113">Administration and Diagnostics</span></span>](../index.md)
