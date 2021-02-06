---
description: ManualFlowThrottleLimitReached에 대해 자세히 알아보세요.
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 90c911131259ea02023eb05a97793f00f3eb43fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99633337"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="58e7f-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="58e7f-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>

<span data-ttu-id="58e7f-104">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="58e7f-104">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="58e7f-105">설명</span><span class="sxs-lookup"><span data-stu-id="58e7f-105">Description</span></span>  

 <span data-ttu-id="58e7f-106">시스템이 ManualFlowControlLimit 스로틀에 대해 설정된 제한에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="58e7f-106">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="58e7f-107">스로틀 값은 ServiceHost 또는 InstanceContext에서 ManualFlowControlLimit 속성을 수정하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e7f-107">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="58e7f-108">수동 흐름 제어 제한을 처음에 0으로 줄인 경우 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="58e7f-108">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="58e7f-109">다음에 0으로 변경하면 추적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58e7f-109">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="58e7f-110">인스턴스 컨텍스트에 대한 흐름 제어 제한은 각 컨텍스트에 대해 한 번 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e7f-110">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e7f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58e7f-111">See also</span></span>

- [<span data-ttu-id="58e7f-112">추적</span><span class="sxs-lookup"><span data-stu-id="58e7f-112">Tracing</span></span>](index.md)
- [<span data-ttu-id="58e7f-113">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="58e7f-113">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="58e7f-114">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="58e7f-114">Administration and Diagnostics</span></span>](../index.md)
