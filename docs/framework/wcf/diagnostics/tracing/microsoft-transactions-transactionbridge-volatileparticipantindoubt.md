---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: 9434f2f902a50a37fb3efee22fd3b18b33af9129
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138972"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="0aa5e-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="0aa5e-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="0aa5e-103">WS-AT 프로토콜 서비스가 인식할 수 없는 일시적 참가자로부터 Prepared 또는 Replay 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa5e-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="0aa5e-104">트랜잭션 결과가 확실하지 않음을 선언하는 결함을 참가자에게 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="0aa5e-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0aa5e-105">설명</span><span class="sxs-lookup"><span data-stu-id="0aa5e-105">Description</span></span>  
 <span data-ttu-id="0aa5e-106">로컬 트랜잭션 관리자가 이미 잊어 버린 일시적인 인리스트먼트로부터 Prepared 또는 Replay 메시지를 받는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aa5e-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0aa5e-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="0aa5e-107">Troubleshooting</span></span>  
 <span data-ttu-id="0aa5e-108">일시적 참가자가 보내는 최신 메시지의 잠재적 원인을 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="0aa5e-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa5e-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0aa5e-109">See also</span></span>

- [<span data-ttu-id="0aa5e-110">추적</span><span class="sxs-lookup"><span data-stu-id="0aa5e-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0aa5e-111">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0aa5e-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0aa5e-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="0aa5e-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
