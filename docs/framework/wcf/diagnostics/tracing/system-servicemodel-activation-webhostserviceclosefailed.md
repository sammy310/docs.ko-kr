---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: e39ca97bdefafee840206036f89e8b165609516a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263011"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="d953f-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="d953f-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>

<span data-ttu-id="d953f-103">서비스를 정상적으로 닫을 수 없고 중단된 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d953f-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d953f-104">Description</span><span class="sxs-lookup"><span data-stu-id="d953f-104">Description</span></span>  

 <span data-ttu-id="d953f-105">이 오류 코드는 로그 파일에서만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d953f-105">This error code only appears in the log file.</span></span> <span data-ttu-id="d953f-106">예를 들어 중단을 이미 호출한 후 서비스를 닫으려는 경우와 같이 일반적으로 프로그래밍 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d953f-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d953f-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="d953f-107">Troubleshooting</span></span>  

 <span data-ttu-id="d953f-108">애플리케이션 소스 코드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d953f-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d953f-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d953f-109">See also</span></span>

- [<span data-ttu-id="d953f-110">추적</span><span class="sxs-lookup"><span data-stu-id="d953f-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="d953f-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d953f-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d953f-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="d953f-112">Administration and Diagnostics</span></span>](../index.md)
