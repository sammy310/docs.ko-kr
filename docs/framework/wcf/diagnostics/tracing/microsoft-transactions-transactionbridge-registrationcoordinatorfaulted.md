---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: 5066501faf4c336e095910e7e2d8ba1186ba3386
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251869"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="83c7e-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="83c7e-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>

<span data-ttu-id="83c7e-103">WS-AT 프로토콜 서비스가 코디네이터로부터 Register 메시지에 대한 오류 응답을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="83c7e-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="83c7e-104">Description</span><span class="sxs-lookup"><span data-stu-id="83c7e-104">Description</span></span>  

 <span data-ttu-id="83c7e-105">로컬 TransactionManager가 반환되는 오류 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c7e-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="83c7e-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="83c7e-106">Troubleshooting</span></span>  

 <span data-ttu-id="83c7e-107">반환된 오류에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="83c7e-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c7e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83c7e-108">See also</span></span>

- [<span data-ttu-id="83c7e-109">추적</span><span class="sxs-lookup"><span data-stu-id="83c7e-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="83c7e-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="83c7e-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="83c7e-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="83c7e-111">Administration and Diagnostics</span></span>](../index.md)
