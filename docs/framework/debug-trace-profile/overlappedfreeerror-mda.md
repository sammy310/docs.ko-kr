---
title: overlappedFreeError MDA
description: .NET의 MDA (overlappedFreeError 관리 디버깅 도우미)를 검토 합니다 .이는 액세스 위반 또는 가비지 수집 힙의 손상에 대해 활성화할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
ms.openlocfilehash: 9be33c59723ecb2743f2bc610d7fb69d24ff388c
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803919"
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="f9e92-103">overlappedFreeError MDA</span><span class="sxs-lookup"><span data-stu-id="f9e92-103">overlappedFreeError MDA</span></span>
<span data-ttu-id="f9e92-104">`overlappedFreeError` MDA(관리 디버깅 도우미)는 겹치는 작업이 완료되기 전에 <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> 메서드를 호출하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-104">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f9e92-105">증상</span><span class="sxs-lookup"><span data-stu-id="f9e92-105">Symptoms</span></span>  
 <span data-ttu-id="f9e92-106">액세스 위반 또는 가비지 수집된 힙의 손상입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-106">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f9e92-107">원인</span><span class="sxs-lookup"><span data-stu-id="f9e92-107">Cause</span></span>  
 <span data-ttu-id="f9e92-108">작업이 완료되기 전에 겹친 구조체가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-108">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="f9e92-109">겹친 포인터를 사용하는 함수는 나중에 해제된 후 구조체에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-109">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="f9e92-110">따라서 다른 개체가 현재 해당 지역을 사용하고 있을 수 있으므로 힙이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-110">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="f9e92-111">겹친 작업이 성공적으로 시작하지 않은 경우 이 MDA는 오류를 나타내지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-111">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f9e92-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f9e92-112">Resolution</span></span>  
 <span data-ttu-id="f9e92-113"><xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> 메서드를 호출하기 전에 겹친 구조체를 사용하는 I/O 작업이 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-113">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f9e92-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="f9e92-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="f9e92-115">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f9e92-116">출력</span><span class="sxs-lookup"><span data-stu-id="f9e92-116">Output</span></span>  
 <span data-ttu-id="f9e92-117">다음은 이 MDA의 샘플 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e92-117">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="f9e92-118">Configuration</span><span class="sxs-lookup"><span data-stu-id="f9e92-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9e92-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9e92-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f9e92-120">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="f9e92-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f9e92-121">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="f9e92-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
