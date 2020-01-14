---
title: 공용 언어 런타임의 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: 49d1141540fb00ab7ef462da5af84f02e6d9fc4d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937866"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="d8d0b-102">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8d0b-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="d8d0b-103">CLR(공용 언어 런타임)은 다양한 디버깅 및 프로파일링 이벤트를 통해 ETW(Windows용 이벤트 추적) 진단 정보에 대한 유용한 이벤트 추적을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="d8d0b-104">CLR ETW 이벤트는 Windows ETW 추적 시스템을 사용하여 공용 언어 런타임에서 제공되는 기존 프로파일링 및 디버깅 지원을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="d8d0b-105">ETW에 대 한 자세한 내용은 ETW를 [사용한 디버깅 및 성능 조정 개선](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) 문서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-105">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="d8d0b-106">Xperf에 대한 자세한 내용은 NTDebugging 블로그의 [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf)(Windows 성능 도구 키트 - Xperf) 항목에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="d8d0b-107">.NET Framework 4 이상은 이벤트 항목에 설명 된 모든 이벤트에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-107">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="d8d0b-108">Windows Vista 운영 체제가 최소 지원 클라이언트이고, Windows Server 2008이 최소 지원 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8d0b-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d8d0b-109">In This Section</span></span>  
 [<span data-ttu-id="d8d0b-110">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="d8d0b-110">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="d8d0b-111">ETW 이벤트를 캡처하고 보기 위한 도구와 명령을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="d8d0b-112">CLR ETW 공급자</span><span class="sxs-lookup"><span data-stu-id="d8d0b-112">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="d8d0b-113">런타임 및 런다운 공급자와 ETW 데이터 수집에 이러한 공급자를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="d8d0b-114">CLR ETW 키워드 및 수준</span><span class="sxs-lookup"><span data-stu-id="d8d0b-114">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="d8d0b-115">범주별 이벤트 필터링을 가능하게 하는 런타임 및 런다운 공급자에 대한 키워드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="d8d0b-116">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8d0b-116">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="d8d0b-117">CLR ETW 이벤트, 해당 키워드 및 이벤트 데이터를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d0b-118">참조</span><span class="sxs-lookup"><span data-stu-id="d8d0b-118">See also</span></span>

- [<span data-ttu-id="d8d0b-119">.NET Framework의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="d8d0b-119">ETW Events in the .NET Framework</span></span>](etw-events.md)
