---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2c9ea77cdd76d4593c2ee5b09a4b917677b8925f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601415"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="e8d46-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="e8d46-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="e8d46-103">지정된 코디네이션 컨텍스트에 대해 OleTransactions 프로토콜 협상을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d46-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e8d46-104">Description</span><span class="sxs-lookup"><span data-stu-id="e8d46-104">Description</span></span>  
 <span data-ttu-id="e8d46-105">OleTx 정보가 포함된 들어오는 트랜잭션이 첨부된 OleTx 정보를 사용할 수 없고 대신 WS-AT를 사용하는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8d46-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="e8d46-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="e8d46-106">Troubleshooting</span></span>  
 <span data-ttu-id="e8d46-107">시스템 간의 MSDTC RPC 통신 관련 잠재적 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8d46-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="e8d46-108">이렇게 많은 추적이 로그에 나타날 경우 성능이 많이 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8d46-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="e8d46-109">OleTx를 사용하지 않는 경우 WS-AT 레지스트리 구성에서 `OleTxUpgradeEnabled`를 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d46-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d46-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8d46-110">See also</span></span>

- [<span data-ttu-id="e8d46-111">추적</span><span class="sxs-lookup"><span data-stu-id="e8d46-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="e8d46-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e8d46-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="e8d46-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="e8d46-113">Administration and Diagnostics</span></span>](../index.md)
