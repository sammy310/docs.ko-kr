---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: d341953b8e12b14e6a3fe8a477c16a1b3a4454ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580439"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="4b9bd-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="4b9bd-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="4b9bd-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="4b9bd-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="4b9bd-104">Description</span><span class="sxs-lookup"><span data-stu-id="4b9bd-104">Description</span></span>  
 <span data-ttu-id="4b9bd-105">메시지가 다시 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bd-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="4b9bd-106">메시지는 한 번만 닫혀야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bd-106">A message should be closed only once.</span></span> <span data-ttu-id="4b9bd-107">사용자 확장명 코드에서 이 추적을 내보낸다는 것은 사용자 확장명 코드가 이미 닫힌 메시지를 닫고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bd-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="4b9bd-108">제품 코드를 통해 이 추적을 내보낸다는 것은 사용자 확장명 코드가 메시지를 너무 일찍 닫을 가능성이 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bd-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9bd-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b9bd-109">See also</span></span>

- [<span data-ttu-id="4b9bd-110">추적</span><span class="sxs-lookup"><span data-stu-id="4b9bd-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="4b9bd-111">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4b9bd-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="4b9bd-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="4b9bd-112">Administration and Diagnostics</span></span>](../index.md)
