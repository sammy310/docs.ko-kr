---
title: contextSwitchDeadlock MDA
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
ms.openlocfilehash: e3fc4a2cb35cdcc713ba0ef362071083af08a27b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217564"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="3e91a-102">contextSwitchDeadlock MDA</span><span class="sxs-lookup"><span data-stu-id="3e91a-102">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="3e91a-103">`contextSwitchDeadlock` MDA(관리 디버깅 도우미)는 COM 컨텍스트 전환이 시도되는 동안 교착 상태가 감지되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="3e91a-104">증상</span><span class="sxs-lookup"><span data-stu-id="3e91a-104">Symptoms</span></span>

<span data-ttu-id="3e91a-105">가장 일반적인 증상은 관리 코드에서 관리되지 않는 COM 구성 요소에 대한 호출이 반환되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="3e91a-106">다른 증상은 시간이 지남에 따라 메모리 사용이 늘어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-106">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="3e91a-107">원인</span><span class="sxs-lookup"><span data-stu-id="3e91a-107">Cause</span></span>

<span data-ttu-id="3e91a-108">가장 가능성 있는 원인은 STA(단일 스레드 아파트) 스레드가 메시지를 펌핑하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="3e91a-109">STA 스레드가 메시지를 펌핑하지 않고 기다리고 있거나, 시간이 많이 걸리는 작업을 수행 중이며 메시지 큐가 펌핑되는 것을 허용하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="3e91a-110">시간이 지남에 따라 메모리 사용이 늘어나는 것은 종료자 스레드가 관리되지 않는 COM 구성 요소에 대해 `Release`를 호출하려고 하고 구성 요소가 반환되지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="3e91a-111">따라서 종료자가 다른 개체를 회수하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-111">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="3e91a-112">기본적으로 Visual Basic 콘솔 애플리케이션의 주 스레드에 대한 스레딩 모델은 STA입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="3e91a-113">이 MDA는 STA 스레드가 직접적으로 또는 공용 언어 런타임이나 타사 컨트롤을 통해 간접적으로 COM 상호 운용성을 사용하는 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="3e91a-114">Visual Basic 콘솔 애플리케이션에서 이 MDA가 활성화되지 않도록 하려면 Main 메서드에 <xref:System.MTAThreadAttribute> 특성을 적용하거나 메시지를 펌핑하도록 애플리케이션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="3e91a-115">다음 조건이 모두 충족되면 이 MDA가 잘못 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

- <span data-ttu-id="3e91a-116">애플리케이션이 직접적으로 또는 라이브러리를 통해 간접적으로 STA 스레드에서 COM 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

- <span data-ttu-id="3e91a-117">애플리케이션이 디버거에서 중지되었고 사용자가 애플리케이션을 계속했거나 단계 작업을 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

- <span data-ttu-id="3e91a-118">관리되지 않는 디버깅이 사용하도록 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-118">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="3e91a-119">MDA가 잘못 활성화되었는지 확인하려면 모든 중단점을 사용하지 않도록 설정하고 애플리케이션을 다시 시작한 후 애플리케이션이 중지되지 않고 실행되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="3e91a-120">MDA가 활성화되지 않으면 초기 활성화가 잘못된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="3e91a-121">이 경우 MDA를 사용하지 않도록 설정하여 디버깅 세션의 방해를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="3e91a-122">이 MDA는 Visual Studio에 대 한 기본 설정에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-122">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="3e91a-123">Mda를 사용 하지 않는 방법에 대 한 자세한 내용은 [관리 디버깅 도우미를 사용 하 여 오류 진단](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e91a-123">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="3e91a-124">해결 방법</span><span class="sxs-lookup"><span data-stu-id="3e91a-124">Resolution</span></span>

<span data-ttu-id="3e91a-125">STA 메시지 펌핑 관련 COM 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-125">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="3e91a-126">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="3e91a-126">Effect on the Runtime</span></span>

<span data-ttu-id="3e91a-127">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-127">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="3e91a-128">COM 컨텍스트에 대한 데이터를 보고할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-128">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="3e91a-129">출력</span><span class="sxs-lookup"><span data-stu-id="3e91a-129">Output</span></span>

<span data-ttu-id="3e91a-130">현재 컨텍스트 및 대상 컨텍스트를 설명하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="3e91a-130">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="3e91a-131">구성</span><span class="sxs-lookup"><span data-stu-id="3e91a-131">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="3e91a-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e91a-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3e91a-133">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="3e91a-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3e91a-134">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="3e91a-134">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
