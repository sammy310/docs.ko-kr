---
title: 추적을 사용하여 애플리케이션 문제 해결
ms.date: 03/30/2017
ms.assetid: 7676b9bb-cbd1-41fd-9a93-cc615af6e2d0
ms.openlocfilehash: 3b684bf2dc6b075906921f56c6aa07ee55ca7fd5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291247"
---
# <a name="using-tracing-to-troubleshoot-your-application"></a><span data-ttu-id="0f2a7-102">추적을 사용하여 애플리케이션 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0f2a7-102">Using Tracing to Troubleshoot Your Application</span></span>

<span data-ttu-id="0f2a7-103">이 단원에는 추적을 사용하여 애플리케이션 문제를 해결할 수 있는 방법에 대해 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-103">This section contains various topics that describe how you can use tracing to troubleshoot your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f2a7-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0f2a7-104">In This Section</span></span>  

 [<span data-ttu-id="0f2a7-105">추적 및 메시지 로깅에 권장되는 설정</span><span class="sxs-lookup"><span data-stu-id="0f2a7-105">Recommended Settings for Tracing and Message Logging</span></span>](recommended-settings-for-tracing-and-message-logging.md)  
 <span data-ttu-id="0f2a7-106">프로덕션 환경 및 디버깅 환경의 제안된 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-106">Describes suggested settings for production and debugging environments.</span></span>  
  
 [<span data-ttu-id="0f2a7-107">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0f2a7-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 <span data-ttu-id="0f2a7-108">Service Trace Viewer 도구를 사용하여 추적 데이터를 보고, 상호 연결하고 분석하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-108">Describes how you can use the Service Trace Viewer tool to view, correlate and analyze trace data.</span></span>  
  
 [<span data-ttu-id="0f2a7-109">중요한 추적</span><span class="sxs-lookup"><span data-stu-id="0f2a7-109">Significant Traces</span></span>](significant-traces.md)  
 <span data-ttu-id="0f2a7-110">WCF에서 내보내는 주요 추적 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-110">A list of major traces emitted by WCF.</span></span>  
  
 [<span data-ttu-id="0f2a7-111">클라이언트에서의 디버깅</span><span class="sxs-lookup"><span data-stu-id="0f2a7-111">Debugging on the Client</span></span>](debugging-on-the-client.md)  
 <span data-ttu-id="0f2a7-112">클라이언트가 애플리케이션을 디버깅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-112">Enables clients to debug your application.</span></span>  
  
 [<span data-ttu-id="0f2a7-113">엔드투엔드 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="0f2a7-113">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="0f2a7-114">E2E WCF 시나리오에 사용 되는 추적에 대해 설명 합니다 (예: 동기 Wcf-wshttp 요청-회신 및 비동기 TCP 단방향 요청).</span><span class="sxs-lookup"><span data-stu-id="0f2a7-114">Describes traces used for E2E WCF scenarios, for example, synchronous wsHttp request-replies, and asynchronous TCP one-way requests.</span></span>  
  
 [<span data-ttu-id="0f2a7-115">사용자 코드 추적 내보내기</span><span class="sxs-lookup"><span data-stu-id="0f2a7-115">Emitting User-Code Traces</span></span>](emitting-user-code-traces.md)  
 <span data-ttu-id="0f2a7-116">사용자 코드에서 프로그래밍 방식으로 추적을 내보내는 방법에 대해 설명합니다. 이 방법을 통해 나중에 진단을 위해 사용하거나 WCF 추적과 상호 연결하여 사용할 계측 데이터를 사전에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f2a7-116">Describes how to emit traces programmatically in user code, so that you can proactively create instrumentation data to be used later for diagnostic purpose, and in correlation with WCF traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2a7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f2a7-117">See also</span></span>

- [<span data-ttu-id="0f2a7-118">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="0f2a7-118">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
- [<span data-ttu-id="0f2a7-119">추적</span><span class="sxs-lookup"><span data-stu-id="0f2a7-119">Tracing</span></span>](index.md)
- [<span data-ttu-id="0f2a7-120">엔드투엔드 추적</span><span class="sxs-lookup"><span data-stu-id="0f2a7-120">End-to-End Tracing</span></span>](end-to-end-tracing.md)
