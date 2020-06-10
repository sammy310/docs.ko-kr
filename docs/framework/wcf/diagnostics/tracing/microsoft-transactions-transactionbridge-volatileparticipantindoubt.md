---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: ab1c2c8afe3a66536810a614cc6deac12519cb9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599635"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="727e3-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="727e3-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="727e3-103">WS-AT 프로토콜 서비스가 인식할 수 없는 일시적 참가자로부터 Prepared 또는 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="727e3-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="727e3-104">트랜잭션 결과가 확실하지 않음을 선언하는 결함을 참가자에게 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="727e3-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="727e3-105">Description</span><span class="sxs-lookup"><span data-stu-id="727e3-105">Description</span></span>  
 <span data-ttu-id="727e3-106">로컬 트랜잭션 관리자가 이미 잊어 버린 일시적인 인리스트먼트로부터 Prepared 또는 Replay 메시지를 받는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="727e3-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="727e3-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="727e3-107">Troubleshooting</span></span>  
 <span data-ttu-id="727e3-108">일시적 참가자가 보내는 최신 메시지의 잠재적 원인을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="727e3-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727e3-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="727e3-109">See also</span></span>

- [<span data-ttu-id="727e3-110">추적</span><span class="sxs-lookup"><span data-stu-id="727e3-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="727e3-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="727e3-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="727e3-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="727e3-112">Administration and Diagnostics</span></span>](../index.md)
