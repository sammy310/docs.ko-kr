---
description: 자세한 내용은 VolatileParticipantInDoubt를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: c9d95285e09d017aa82c86e7c5c6f9fd758b9f80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803245"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="f4aa7-103">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="f4aa7-103">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>

<span data-ttu-id="f4aa7-104">WS-AT 프로토콜 서비스가 인식할 수 없는 일시적 참가자로부터 Prepared 또는 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa7-104">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="f4aa7-105">트랜잭션 결과가 확실하지 않음을 선언하는 결함을 참가자에게 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa7-105">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f4aa7-106">설명</span><span class="sxs-lookup"><span data-stu-id="f4aa7-106">Description</span></span>  

 <span data-ttu-id="f4aa7-107">로컬 트랜잭션 관리자가 이미 잊어 버린 일시적인 인리스트먼트로부터 Prepared 또는 Replay 메시지를 받는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa7-107">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f4aa7-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="f4aa7-108">Troubleshooting</span></span>  

 <span data-ttu-id="f4aa7-109">일시적 참가자가 보내는 최신 메시지의 잠재적 원인을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="f4aa7-109">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4aa7-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4aa7-110">See also</span></span>

- [<span data-ttu-id="f4aa7-111">추적</span><span class="sxs-lookup"><span data-stu-id="f4aa7-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="f4aa7-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f4aa7-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f4aa7-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="f4aa7-113">Administration and Diagnostics</span></span>](../index.md)
