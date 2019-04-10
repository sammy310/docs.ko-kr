---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: f634816b2459d2e0b6137e2e87fef907824af017
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163035"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="ee7de-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="ee7de-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="ee7de-103">WS-AT 프로토콜 서비스가 코디네이터로부터 Register 메시지에 대한 오류 응답을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="ee7de-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ee7de-104">설명</span><span class="sxs-lookup"><span data-stu-id="ee7de-104">Description</span></span>  
 <span data-ttu-id="ee7de-105">로컬 TransactionManager가 반환되는 오류 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee7de-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ee7de-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="ee7de-106">Troubleshooting</span></span>  
 <span data-ttu-id="ee7de-107">반환된 오류에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ee7de-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee7de-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee7de-108">See also</span></span>

- [<span data-ttu-id="ee7de-109">추적</span><span class="sxs-lookup"><span data-stu-id="ee7de-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ee7de-110">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ee7de-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ee7de-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="ee7de-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
