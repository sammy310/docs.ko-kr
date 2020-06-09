---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: bffa6361df5a50748f45aa3004f7a307ad516d7b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580491"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="a2b38-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="a2b38-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="a2b38-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="a2b38-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="a2b38-104">Description</span><span class="sxs-lookup"><span data-stu-id="a2b38-104">Description</span></span>  
 <span data-ttu-id="a2b38-105">시스템이 ManualFlowControlLimit 스로틀에 대해 설정된 제한에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b38-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="a2b38-106">스로틀 값은 ServiceHost 또는 InstanceContext에서 ManualFlowControlLimit 속성을 수정하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b38-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="a2b38-107">수동 흐름 제어 제한을 처음에 0으로 줄인 경우 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2b38-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="a2b38-108">다음에 0으로 변경하면 추적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2b38-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="a2b38-109">인스턴스 컨텍스트에 대한 흐름 제어 제한은 각 컨텍스트에 대해 한 번 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b38-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b38-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2b38-110">See also</span></span>

- [<span data-ttu-id="a2b38-111">추적</span><span class="sxs-lookup"><span data-stu-id="a2b38-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="a2b38-112">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a2b38-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a2b38-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="a2b38-113">Administration and Diagnostics</span></span>](../index.md)
