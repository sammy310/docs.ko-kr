---
title: contextSwitchDeadlock MDA
description: COM 컨텍스트를 전환 하는 동안 교착 상태가 발견 될 때 활성화 되는 .NET에서 contextSwitchDeadlock 상태 MDA (관리 디버깅 도우미)에 대해 읽어 보십시오.
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
ms.openlocfilehash: 52db4f2c88bac4e8cac621cca989fa10acb43f94
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416020"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="4191f-103">contextSwitchDeadlock MDA</span><span class="sxs-lookup"><span data-stu-id="4191f-103">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="4191f-104">`contextSwitchDeadlock` MDA(관리 디버깅 도우미)는 COM 컨텍스트 전환이 시도되는 동안 교착 상태가 감지되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-104">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="4191f-105">증상</span><span class="sxs-lookup"><span data-stu-id="4191f-105">Symptoms</span></span>

<span data-ttu-id="4191f-106">가장 일반적인 증상은 관리 코드에서 관리되지 않는 COM 구성 요소에 대한 호출이 반환되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-106">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="4191f-107">다른 증상은 시간이 지남에 따라 메모리 사용이 늘어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-107">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="4191f-108">원인</span><span class="sxs-lookup"><span data-stu-id="4191f-108">Cause</span></span>

<span data-ttu-id="4191f-109">가장 가능성 있는 원인은 STA(단일 스레드 아파트) 스레드가 메시지를 펌핑하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-109">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="4191f-110">STA 스레드가 메시지를 펌핑하지 않고 기다리고 있거나, 시간이 많이 걸리는 작업을 수행 중이며 메시지 큐가 펌핑되는 것을 허용하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-110">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="4191f-111">시간이 지남에 따라 메모리 사용이 늘어나는 것은 종료자 스레드가 관리되지 않는 COM 구성 요소에 대해 `Release`를 호출하려고 하고 구성 요소가 반환되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-111">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="4191f-112">따라서 종료자가 다른 개체를 회수하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-112">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="4191f-113">기본적으로 Visual Basic 콘솔 애플리케이션의 주 스레드에 대한 스레딩 모델은 STA입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-113">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="4191f-114">이 MDA는 STA 스레드가 직접적으로 또는 공용 언어 런타임이나 타사 컨트롤을 통해 간접적으로 COM 상호 운용성을 사용하는 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-114">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="4191f-115">Visual Basic 콘솔 애플리케이션에서 이 MDA가 활성화되지 않도록 하려면 Main 메서드에 <xref:System.MTAThreadAttribute> 특성을 적용하거나 메시지를 펌핑하도록 애플리케이션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-115">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="4191f-116">다음 조건이 모두 충족되면 이 MDA가 잘못 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-116">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="4191f-117">애플리케이션이 직접적으로 또는 라이브러리를 통해 간접적으로 STA 스레드에서 COM 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-117">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="4191f-118">애플리케이션이 디버거에서 중지되었고 사용자가 애플리케이션을 계속했거나 단계 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-118">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="4191f-119">관리되지 않는 디버깅이 사용하도록 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-119">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="4191f-120">MDA가 잘못 활성화되었는지 확인하려면 모든 중단점을 사용하지 않도록 설정하고 애플리케이션을 다시 시작한 후 애플리케이션이 중지되지 않고 실행되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-120">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="4191f-121">MDA가 활성화되지 않으면 초기 활성화가 잘못된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-121">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="4191f-122">이 경우 MDA를 사용하지 않도록 설정하여 디버깅 세션의 방해를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-122">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="4191f-123">이 MDA는 Visual Studio에 대 한 기본 설정에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-123">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="4191f-124">Mda를 사용 하지 않는 방법에 대 한 자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4191f-124">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="4191f-125">해결 방법</span><span class="sxs-lookup"><span data-stu-id="4191f-125">Resolution</span></span>

<span data-ttu-id="4191f-126">STA 메시지 펌핑 관련 COM 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-126">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="4191f-127">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="4191f-127">Effect on the Runtime</span></span>

<span data-ttu-id="4191f-128">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-128">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="4191f-129">COM 컨텍스트에 대한 데이터를 보고할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-129">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="4191f-130">출력</span><span class="sxs-lookup"><span data-stu-id="4191f-130">Output</span></span>

<span data-ttu-id="4191f-131">현재 컨텍스트 및 대상 컨텍스트를 설명하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4191f-131">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="4191f-132">구성</span><span class="sxs-lookup"><span data-stu-id="4191f-132">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="4191f-133">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4191f-133">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="4191f-134">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="4191f-134">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="4191f-135">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="4191f-135">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
