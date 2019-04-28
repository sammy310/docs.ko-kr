---
title: 종단 간 추적
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fd2964b39c758e41620fb453ddd8f61a1aa550aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912537"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="e51f6-102">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="e51f6-102">End-to-End Tracing</span></span>
<span data-ttu-id="e51f6-103">종단 간 (e2e) 추적을 통해 개발자가 코드 경로가 실패 한 이유를 조사 하거나 용량 계획 및 성능 분석에 대 한 추적 정보를 제공 하는 Windows Communication Foundation (WCF) 인프라에서 코드 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51f6-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="e51f6-104">Windows Communication Foundation (WCF) 오류의 원인을 진단 하기 위해 세 가지 상관 관계 메커니즘을 제공 합니다: 동작, 전송 및 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51f6-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="e51f6-105">참조 [종단 간 추적 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) 종단 간 추적 시나리오 및 해당 동작과 추적 디자인의 목록은 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51f6-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e51f6-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e51f6-106">In This Section</span></span>  
 <span data-ttu-id="e51f6-107">[활동](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Windows Communication Foundation (WCF) 추적 모델의 동작 추적을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e51f6-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="e51f6-108">[전송](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Windows Communication Foundation (WCF) 추적 모델에서 전송을 설명 하 고 전송을 사용 하 여 끝점 내의 동작을 상호 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51f6-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="e51f6-109">[전파](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  동작 전파를에 Windows 통신 Foundation (WCF) 모델, 추적 및 전파를 사용 하 여 동작을 상호 연결 끝점을 통해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51f6-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="e51f6-110">추적 형식 요약</span><span class="sxs-lookup"><span data-stu-id="e51f6-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="e51f6-111">모든 동작 추적 형식에 대한 요약 제공</span><span class="sxs-lookup"><span data-stu-id="e51f6-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e51f6-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="e51f6-112">See also</span></span>

- [<span data-ttu-id="e51f6-113">추적 구성</span><span class="sxs-lookup"><span data-stu-id="e51f6-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="e51f6-114">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e51f6-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="e51f6-115">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="e51f6-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="e51f6-116">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="e51f6-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
