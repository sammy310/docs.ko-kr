---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997778"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="dc13c-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="dc13c-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="dc13c-103">WS-AT 프로토콜 서비스가 코디네이터에게 Register 메시지를 보내지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="dc13c-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="dc13c-104">설명</span><span class="sxs-lookup"><span data-stu-id="dc13c-104">Description</span></span>  
 <span data-ttu-id="dc13c-105">로컬 TransactionManager가 메시지를 보낼 수 없기 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc13c-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="dc13c-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="dc13c-106">Troubleshooting</span></span>  
 <span data-ttu-id="dc13c-107">메시지 보내기 오류의 원인인 예외에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="dc13c-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc13c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc13c-108">See also</span></span>

- [<span data-ttu-id="dc13c-109">추적</span><span class="sxs-lookup"><span data-stu-id="dc13c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="dc13c-110">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="dc13c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="dc13c-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="dc13c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
