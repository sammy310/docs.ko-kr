---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a8aa5e600789df1b64a8a3f1a6355aaae6a6cf4b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294432"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="a12f2-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="a12f2-102">System.ServiceModel.MessageClosedAgain</span></span>

<span data-ttu-id="a12f2-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="a12f2-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="a12f2-104">Description</span><span class="sxs-lookup"><span data-stu-id="a12f2-104">Description</span></span>  

 <span data-ttu-id="a12f2-105">메시지가 다시 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="a12f2-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="a12f2-106">메시지는 한 번만 닫혀야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a12f2-106">A message should be closed only once.</span></span> <span data-ttu-id="a12f2-107">사용자 확장명 코드에서 이 추적을 내보낸다는 것은 사용자 확장명 코드가 이미 닫힌 메시지를 닫고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a12f2-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="a12f2-108">제품 코드를 통해 이 추적을 내보낸다는 것은 사용자 확장명 코드가 메시지를 너무 일찍 닫을 가능성이 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a12f2-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a12f2-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a12f2-109">See also</span></span>

- [<span data-ttu-id="a12f2-110">추적</span><span class="sxs-lookup"><span data-stu-id="a12f2-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="a12f2-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a12f2-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a12f2-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="a12f2-112">Administration and Diagnostics</span></span>](../index.md)
