---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 742e80a3115e8f8caa728e0d8c460ee8b964ddc9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588719"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="35524-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="35524-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="35524-103">WS-AT 프로토콜 서비스가 제공된 코디네이션 컨텍스트를 사용하여 트랜잭션에 참여하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="35524-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="35524-104">Description</span><span class="sxs-lookup"><span data-stu-id="35524-104">Description</span></span>  
 <span data-ttu-id="35524-105">제공된 2PC(2단계 커밋) 프로토콜에 대한 트랜잭션에 MSDTC가 참여할 수 없을 때 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="35524-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="35524-106">이는 트랜잭션이 더 이상 존재하지 않거나, 참여가 허용되지 않거나, 인리스트먼트가 너무 많이 있을 경우 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35524-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="35524-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="35524-107">Troubleshooting</span></span>  
 <span data-ttu-id="35524-108">추적 메시지 내의 상태 문자열을 검사하여 실행 가능한 항목이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="35524-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35524-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35524-109">See also</span></span>

- [<span data-ttu-id="35524-110">추적</span><span class="sxs-lookup"><span data-stu-id="35524-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="35524-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="35524-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="35524-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="35524-112">Administration and Diagnostics</span></span>](../index.md)
