---
title: CLR ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941af2568e72fe093860801bd2595b3037e41
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428174"
---
# <a name="clr-etw-events"></a><span data-ttu-id="76d6b-102">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-102">CLR ETW Events</span></span>
<span data-ttu-id="76d6b-103">이 섹션의 항목은 ETW(Windows용 이벤트 추적) 이벤트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="76d6b-104">각 이벤트에는 연결된 키워드 및 수준이 있으며, [CLR ETW 키워드 및 수준](clr-etw-keywords-and-levels.md) 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="76d6b-105">CLR에는 이벤트에 대한 두 개의 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-105">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="76d6b-106">런타임 공급자 - 사용하도록 설정된 키워드(이벤트 범주)에 따라 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="76d6b-107">CLR 런타임 공급자 GUID는 e13c0d23-ccbc-4e12-931b-d9cc2eee27e4입니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="76d6b-108">런다운 공급자 - 특별한 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="76d6b-109">CLR 런다운 공급자 GUID는 a669021c-c450-4609-a035-5af59af4df18입니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="76d6b-110">공급자에 대한 자세한 내용은 [CLR ETW 공급자](clr-etw-providers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76d6b-110">For more information about the providers, see [CLR ETW Providers](clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76d6b-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="76d6b-111">In This Section</span></span>  
 [<span data-ttu-id="76d6b-112">런타임 정보 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-112">Runtime Information Events</span></span>](runtime-information-etw-events.md)  
 <span data-ttu-id="76d6b-113">SKU, 버전 번호, 런타임이 활성화된 방법, 시작하는 데 사용된 명령줄 매개 변수, GUID(해당되는 경우) 및 다른 관련 정보를 비롯한 런타임 관련 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="76d6b-114">예외가 throw된 V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-114">Exception Thrown_V1 Event</span></span>](exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="76d6b-115">throw된 예외에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="76d6b-116">경합 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-116">Contention Events</span></span>](contention-etw-events.md)  
 <span data-ttu-id="76d6b-117">런타임이 사용하는 모니터 잠금이나 네이티브 잠금의 경합에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="76d6b-118">스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-118">Thread Pool Events</span></span>](thread-pool-etw-events.md)  
 <span data-ttu-id="76d6b-119">작업자 스레드 풀 및 I/O 스레드 풀에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="76d6b-120">로더 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-120">Loader Events</span></span>](loader-etw-events.md)  
 <span data-ttu-id="76d6b-121">애플리케이션 도메인, 어셈블리 및 모듈 로딩 및 언로딩에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="76d6b-122">메서드 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-122">Method Events</span></span>](method-etw-events.md)  
 <span data-ttu-id="76d6b-123">기호 확인을 위한 CLR 메서드에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="76d6b-124">가비지 수집 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-124">Garbage Collection Events</span></span>](garbage-collection-etw-events.md)  
 <span data-ttu-id="76d6b-125">진단 및 디버깅에 도움이 되는 가비지 수집 관련 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="76d6b-126">JIT 추적 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-126">JIT Tracing Events</span></span>](jit-tracing-etw-events.md)  
 <span data-ttu-id="76d6b-127">JIT(Just-In-Time) 인라인 및 후속 호출에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="76d6b-128">Interop 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-128">Interop Events</span></span>](interop-etw-events.md)  
 <span data-ttu-id="76d6b-129">MSIL(Microsoft intermediate language) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="76d6b-130">ARM 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-130">ARM Events</span></span>](application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="76d6b-131">애플리케이션 도메인의 상태에 대한 세부적인 진단 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="76d6b-132">보안 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-132">Security Events</span></span>](security-etw-events.md)  
 <span data-ttu-id="76d6b-133">강력한 이름 및 Authenticode 확인에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="76d6b-134">스택 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-134">Stack Event</span></span>](stack-etw-event.md)  
 <span data-ttu-id="76d6b-135">이벤트가 발생한 이후 스택 추적을 생성하기 위해 다른 이벤트와 함께 사용되는 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="76d6b-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d6b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76d6b-136">See also</span></span>

- [<span data-ttu-id="76d6b-137">ETW를 사용한 디버깅 및 성능 조정 개선</span><span class="sxs-lookup"><span data-stu-id="76d6b-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)
- [<span data-ttu-id="76d6b-138">Windows 성능 블로그</span><span class="sxs-lookup"><span data-stu-id="76d6b-138">Windows Performance Blog</span></span>](https://blogs.msdn.microsoft.com/pigscanfly/tag/xperf/)
- [<span data-ttu-id="76d6b-139">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="76d6b-139">Controlling .NET Framework Logging</span></span>](controlling-logging.md)
- [<span data-ttu-id="76d6b-140">CLR ETW 공급자</span><span class="sxs-lookup"><span data-stu-id="76d6b-140">CLR ETW Providers</span></span>](clr-etw-providers.md)
- [<span data-ttu-id="76d6b-141">CLR ETW 키워드 및 수준</span><span class="sxs-lookup"><span data-stu-id="76d6b-141">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="76d6b-142">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="76d6b-142">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
