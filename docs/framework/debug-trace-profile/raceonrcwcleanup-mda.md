---
title: raceOnRCWCleanup MDA
description: 다른 스레드에서 RCW를 사용 하거나 .NET의 스레드를 해제할 때 활성화 되는 raceOnRCWCleanup MDA (관리 디버깅 도우미)를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
ms.openlocfilehash: 393c5ea44108445a9a1a9d16e7d1d192eced5740
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271449"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="f396a-103">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="f396a-103">raceOnRCWCleanup MDA</span></span>

<span data-ttu-id="f396a-104">`raceOnRCWCleanup` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)에서 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> 메서드와 같은 명령을 사용하여 해제 호출을 수행할 때 RCW( [런타임 호출 가능 래퍼](../../standard/native-interop/runtime-callable-wrapper.md))가 사용 중임을 발견할 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f396a-104">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f396a-105">증상</span><span class="sxs-lookup"><span data-stu-id="f396a-105">Symptoms</span></span>  

 <span data-ttu-id="f396a-106"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 또는 이와 비슷한 메서드를 사용하여 RCW를 해제하는 중이나 그 이후에 액세스 위반 또는 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f396a-106">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f396a-107">원인</span><span class="sxs-lookup"><span data-stu-id="f396a-107">Cause</span></span>  

 <span data-ttu-id="f396a-108">RCW가 다른 스레드나 해제 스레드 스택에서 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="f396a-108">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="f396a-109">사용 중인 RCW는 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f396a-109">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f396a-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f396a-110">Resolution</span></span>  

 <span data-ttu-id="f396a-111">현재 스레드나 다른 스레드에서 사용 중일 수 있는 RCW는 해제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f396a-111">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f396a-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="f396a-112">Effect on the Runtime</span></span>  

 <span data-ttu-id="f396a-113">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f396a-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f396a-114">출력</span><span class="sxs-lookup"><span data-stu-id="f396a-114">Output</span></span>  

 <span data-ttu-id="f396a-115">오류를 설명하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f396a-115">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f396a-116">구성</span><span class="sxs-lookup"><span data-stu-id="f396a-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f396a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f396a-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f396a-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="f396a-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f396a-119">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="f396a-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
