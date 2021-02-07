---
description: MessageClosedAgain에 대해 자세히 알아보세요.
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: 40e6dcc8974440bd7d7f10ca30e36447c4ae790a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716200"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="62a42-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="62a42-103">System.ServiceModel.MessageClosedAgain</span></span>

<span data-ttu-id="62a42-104">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="62a42-104">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="62a42-105">설명</span><span class="sxs-lookup"><span data-stu-id="62a42-105">Description</span></span>  

 <span data-ttu-id="62a42-106">메시지가 다시 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="62a42-106">A message was closed again.</span></span>  
  
 <span data-ttu-id="62a42-107">메시지는 한 번만 닫혀야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a42-107">A message should be closed only once.</span></span> <span data-ttu-id="62a42-108">사용자 확장명 코드에서 이 추적을 내보낸다는 것은 사용자 확장명 코드가 이미 닫힌 메시지를 닫고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62a42-108">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="62a42-109">제품 코드를 통해 이 추적을 내보낸다는 것은 사용자 확장명 코드가 메시지를 너무 일찍 닫을 가능성이 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62a42-109">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a42-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62a42-110">See also</span></span>

- [<span data-ttu-id="62a42-111">추적</span><span class="sxs-lookup"><span data-stu-id="62a42-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="62a42-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="62a42-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="62a42-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="62a42-113">Administration and Diagnostics</span></span>](../index.md)
