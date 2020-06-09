---
title: 엔드투엔드 추적
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fc8fc448bdcf94ab25349f6b34961a34e5ed2a5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598582"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="af5c8-102">엔드투엔드 추적</span><span class="sxs-lookup"><span data-stu-id="af5c8-102">End-to-End Tracing</span></span>
<span data-ttu-id="af5c8-103">E2e (종단 간) 추적을 사용 하면 개발자는 WCF (Windows Communication Foundation) 인프라에서 코드 실행을 따라 코드 경로가 실패 한 이유를 조사 하거나 용량 계획 및 성능 분석에 대 한 자세한 추적을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af5c8-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="af5c8-104">WCF (Windows Communication Foundation)는 오류 원인을 진단 하는 데 도움이 되는 세 가지 상관 관계 메커니즘 (작업, 전송 및 전파)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5c8-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="af5c8-105">종단 간 추적 시나리오 목록 및 해당 작업 및 추적 디자인은 [종단 간 추적 시나리오](end-to-end-tracing-scenarios.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af5c8-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af5c8-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="af5c8-106">In This Section</span></span>  
 <span data-ttu-id="af5c8-107">[활동](activity.md): WCF (Windows Communication Foundation) 추적 모델의 동작 추적에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5c8-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="af5c8-108">[전송](transfer.md): WINDOWS COMMUNICATION FOUNDATION (WCF) 추적 모델의 전송에 대해 설명 하 고, 전송을 사용 하 여 끝점 내의 작업 상관 관계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5c8-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="af5c8-109">[전파](propagation.md): WINDOWS COMMUNICATION FOUNDATION (WCF) 추적 모델의 작업 전파를 설명 하 고, 전파를 사용 하 여 끝점 간의 작업 상관 관계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="af5c8-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="af5c8-110">추적 형식 요약</span><span class="sxs-lookup"><span data-stu-id="af5c8-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="af5c8-111">모든 동작 추적 형식에 대한 요약 제공</span><span class="sxs-lookup"><span data-stu-id="af5c8-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af5c8-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af5c8-112">See also</span></span>

- [<span data-ttu-id="af5c8-113">추적 구성</span><span class="sxs-lookup"><span data-stu-id="af5c8-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="af5c8-114">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="af5c8-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="af5c8-115">엔드투엔드 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="af5c8-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="af5c8-116">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="af5c8-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
