---
title: ETW Events in the .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework ETW events
- ETW events in the .NET Framework
ms.assetid: d186276f-6afb-4dfd-bf3c-4251edc2c299
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fa36399320a8c396a222619172264a32f3eb3505
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723604"
---
# <a name="etw-events-in-the-net-framework"></a><span data-ttu-id="3af40-102">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3af40-102">ETW Events in the .NET Framework</span></span>
<span data-ttu-id="3af40-103">ETW(Windows용 이벤트 추적)는 Windows 운영 체제에서 제공되는 오버헤드가 낮고 확장 가능한 고성능 추적 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="3af40-103">Event tracing for Windows (ETW) is a high-performance, low-overhead, scalable tracing system provided by Windows operating systems.</span></span> <span data-ttu-id="3af40-104">ETW는 .NET Framework에서 제공되는 프로파일링 및 디버깅 지원을 보완하며 다양한 시나리오 관련 문제를 해결하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af40-104">It supplements the profiling and debugging support provided by the .NET Framework and can be used to troubleshoot a variety of scenarios.</span></span>  
  
 <span data-ttu-id="3af40-105">.NET Framework에서 ETW 이벤트 추적은 CLR(공용 언어 런타임), [작업 병렬 라이브러리](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) 및 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af40-105">In the .NET Framework, ETW event tracing is available for the common language runtime (CLR), the [Task Parallel Library](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md), and [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3af40-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3af40-106">In This Section</span></span>  
 [<span data-ttu-id="3af40-107">작업 병렬 라이브러리 및 PLINQ의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="3af40-107">ETW Events in Task Parallel Library and PLINQ</span></span>](../../../docs/framework/performance/etw-events-in-task-parallel-library-and-plinq.md)  
 <span data-ttu-id="3af40-108">병렬 애플리케이션 코드를 프로파일링하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3af40-108">Describes how to profile parallel application code.</span></span>  
  
 [<span data-ttu-id="3af40-109">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="3af40-109">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)  
 <span data-ttu-id="3af40-110">CLR ETW 이벤트가 공용 언어 런타임에서 제공되는 프로파일링 및 디버깅 지원을 보완하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3af40-110">Describes how CLR ETW events supplement the profiling and debugging support provided by the common language runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af40-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="3af40-111">See also</span></span>

- [<span data-ttu-id="3af40-112">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="3af40-112">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
- [<span data-ttu-id="3af40-113">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="3af40-113">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
- [<span data-ttu-id="3af40-114">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="3af40-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
