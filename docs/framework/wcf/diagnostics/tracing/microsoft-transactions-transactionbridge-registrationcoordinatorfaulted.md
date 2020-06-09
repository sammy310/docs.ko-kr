---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: ad9d82162313e46626e5e2fa6f4ef99bf0139162
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599648"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="05ab9-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="05ab9-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="05ab9-103">WS-AT 프로토콜 서비스가 코디네이터로부터 Register 메시지에 대한 오류 응답을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="05ab9-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="05ab9-104">Description</span><span class="sxs-lookup"><span data-stu-id="05ab9-104">Description</span></span>  
 <span data-ttu-id="05ab9-105">로컬 TransactionManager가 반환되는 오류 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ab9-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="05ab9-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="05ab9-106">Troubleshooting</span></span>  
 <span data-ttu-id="05ab9-107">반환된 오류에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="05ab9-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ab9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05ab9-108">See also</span></span>

- [<span data-ttu-id="05ab9-109">추적</span><span class="sxs-lookup"><span data-stu-id="05ab9-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="05ab9-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="05ab9-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="05ab9-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="05ab9-111">Administration and Diagnostics</span></span>](../index.md)
