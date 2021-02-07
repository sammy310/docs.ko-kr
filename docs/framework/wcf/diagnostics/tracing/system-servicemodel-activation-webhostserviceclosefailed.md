---
description: 자세한 내용은 WebHostServiceCloseFailed를 확인 하세요.
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: fae41b72e2eb9aba76993081769afc42c0ec8975
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720451"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="6abc3-103">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="6abc3-103">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>

<span data-ttu-id="6abc3-104">서비스를 정상적으로 닫을 수 없고 중단된 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6abc3-104">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6abc3-105">설명</span><span class="sxs-lookup"><span data-stu-id="6abc3-105">Description</span></span>  

 <span data-ttu-id="6abc3-106">이 오류 코드는 로그 파일에서만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6abc3-106">This error code only appears in the log file.</span></span> <span data-ttu-id="6abc3-107">예를 들어 중단을 이미 호출한 후 서비스를 닫으려는 경우와 같이 일반적으로 프로그래밍 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6abc3-107">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6abc3-108">문제 해결</span><span class="sxs-lookup"><span data-stu-id="6abc3-108">Troubleshooting</span></span>  

 <span data-ttu-id="6abc3-109">애플리케이션 소스 코드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6abc3-109">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abc3-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6abc3-110">See also</span></span>

- [<span data-ttu-id="6abc3-111">추적</span><span class="sxs-lookup"><span data-stu-id="6abc3-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="6abc3-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6abc3-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="6abc3-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="6abc3-113">Administration and Diagnostics</span></span>](../index.md)
