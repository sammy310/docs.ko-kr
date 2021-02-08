---
description: 자세한 내용은 RegistrationCoordinatorFaulted를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: aae2d5824f4205a05e98c7ef00d27c6a844e1566
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770601"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="1f54d-103">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="1f54d-103">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>

<span data-ttu-id="1f54d-104">WS-AT 프로토콜 서비스가 코디네이터로부터 Register 메시지에 대한 오류 응답을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="1f54d-104">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1f54d-105">설명</span><span class="sxs-lookup"><span data-stu-id="1f54d-105">Description</span></span>  

 <span data-ttu-id="1f54d-106">로컬 TransactionManager가 반환되는 오류 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f54d-106">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1f54d-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="1f54d-107">Troubleshooting</span></span>  

 <span data-ttu-id="1f54d-108">반환된 오류에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1f54d-108">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f54d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f54d-109">See also</span></span>

- [<span data-ttu-id="1f54d-110">추적</span><span class="sxs-lookup"><span data-stu-id="1f54d-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="1f54d-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1f54d-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1f54d-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="1f54d-112">Administration and Diagnostics</span></span>](../index.md)
