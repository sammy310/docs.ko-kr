---
description: 자세한 내용은 RegistrationCoordinatorFailed를 확인 하세요.
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: f522fb91db6c721c43d2768a9eb79d627fbc2a59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770614"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="3dc23-103">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="3dc23-103">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>

<span data-ttu-id="3dc23-104">WS-AT 프로토콜 서비스가 코디네이터에게 Register 메시지를 보내지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc23-104">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="3dc23-105">설명</span><span class="sxs-lookup"><span data-stu-id="3dc23-105">Description</span></span>  

 <span data-ttu-id="3dc23-106">로컬 TransactionManager가 메시지를 보낼 수 없기 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc23-106">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3dc23-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="3dc23-107">Troubleshooting</span></span>  

 <span data-ttu-id="3dc23-108">메시지 보내기 오류의 원인인 예외에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc23-108">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc23-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dc23-109">See also</span></span>

- [<span data-ttu-id="3dc23-110">추적</span><span class="sxs-lookup"><span data-stu-id="3dc23-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="3dc23-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3dc23-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3dc23-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="3dc23-112">Administration and Diagnostics</span></span>](../index.md)
