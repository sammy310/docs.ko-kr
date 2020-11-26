---
title: fatalExecutionEngineError MDA
description: 예기치 않은 프로세스 종료로 인해 활성화 될 수 있는 .NET의 fatalExecutionEngineError MDA (관리 디버깅 도우미)를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
ms.openlocfilehash: a9347338d53755b74b3ff291f75cb6b221134130
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244277"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="407e4-103">fatalExecutionEngineError MDA</span><span class="sxs-lookup"><span data-stu-id="407e4-103">fatalExecutionEngineError MDA</span></span>

<span data-ttu-id="407e4-104">`fatalExecutionEngineError` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)에서 오류가 발견될 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="407e4-105">프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="407e4-106">증상</span><span class="sxs-lookup"><span data-stu-id="407e4-106">Symptoms</span></span>  

 <span data-ttu-id="407e4-107">예기치 않은 프로세스 종료.</span><span class="sxs-lookup"><span data-stu-id="407e4-107">Unexpected process termination.</span></span> <span data-ttu-id="407e4-108">다양한 이유로 CLR 오류가 발생할 수 있으므로 다른 증상을 결정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="407e4-109">원인</span><span class="sxs-lookup"><span data-stu-id="407e4-109">Cause</span></span>  

 <span data-ttu-id="407e4-110">CLR이 심각하게 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="407e4-111">이 오류의 가장 많은 원인은 잘못된 형식의 플랫폼 호출 함수를 호출하거나 잘못된 데이터를 CLR에 전달하는 것과 같은 다양한 문제로 인해 발생할 수 있는 데이터 손상입니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="407e4-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="407e4-112">Resolution</span></span>  

 <span data-ttu-id="407e4-113">추가적인 MDA를 사용하면 문제를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="407e4-114">다음 MDA는 문제를 진단하는 데 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="407e4-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="407e4-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="407e4-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="407e4-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="407e4-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="407e4-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="407e4-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="407e4-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="407e4-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="407e4-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="407e4-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="407e4-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="407e4-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="407e4-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="407e4-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="407e4-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="407e4-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="407e4-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="407e4-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="407e4-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="407e4-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="407e4-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="407e4-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="407e4-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="407e4-127">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="407e4-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="407e4-128">이 MDA는 런타임 동작에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="407e4-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="407e4-129">출력</span><span class="sxs-lookup"><span data-stu-id="407e4-129">Output</span></span>  

 <span data-ttu-id="407e4-130">오류를 초래한 CLR 함수의 주소, 오류가 발생한 스레드의 ID 및 오류 코드.</span><span class="sxs-lookup"><span data-stu-id="407e4-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="407e4-131">구성</span><span class="sxs-lookup"><span data-stu-id="407e4-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="407e4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="407e4-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="407e4-133">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="407e4-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
