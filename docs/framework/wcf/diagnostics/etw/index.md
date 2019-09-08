---
title: ETW를 사용한 분석 추적
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798083"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="80db1-102">ETW를 사용한 분석 추적</span><span class="sxs-lookup"><span data-stu-id="80db1-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="80db1-103">WCF (Windows Communication Foundation) 분석 추적은 WCF 서비스를 실행 하는 동안 진단 정보를 캡처하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="80db1-104">Wcf 분석 추적 이벤트는 프로덕션 환경에서 wcf 서비스의 문제를 해결할 수 있도록 WCF 스택의 주요 지점에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="80db1-105">Wcf 서비스에 대 한 분석 추적은 wcf 서비스를 호스팅하 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 는 제품 서버의 성능에 최소한의 영향을 미칩니다. 이러한 이벤트는 ETW (ETW(Windows용 이벤트 추적)) 세션으로 매우 효율적으로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80db1-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="80db1-106">In This Section</span></span>  
 [<span data-ttu-id="80db1-107">분석 추적 개요</span><span class="sxs-lookup"><span data-stu-id="80db1-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="80db1-108">에서 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]WCF 분석 추적이 작동 하는 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="80db1-109">동적으로 분석 추적을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="80db1-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="80db1-110">ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="80db1-111">메시지 흐름 추적 구성</span><span class="sxs-lookup"><span data-stu-id="80db1-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="80db1-112">메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="80db1-113">분석 추적 이벤트 참조</span><span class="sxs-lookup"><span data-stu-id="80db1-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="80db1-114">이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80db1-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80db1-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="80db1-115">See also</span></span>

- [<span data-ttu-id="80db1-116">WCF 서비스 및 Windows용 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="80db1-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="80db1-117">Windows에서 이벤트 추적으로 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="80db1-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
