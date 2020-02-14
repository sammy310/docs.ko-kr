---
title: illegalPrepareConstrainedRegion MDA
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: b80d6160876834b22e8d9d1eb7112b8b67c15fcc
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216468"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="f9788-102">illegalPrepareConstrainedRegion MDA</span><span class="sxs-lookup"><span data-stu-id="f9788-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="f9788-103">`illegalPrepareConstrainedRegion` MDA(관리 디버깅 도우미)는 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> 메서드가 예외 처리기의 `try` 문의 바로 앞에 호출되지 않을 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="f9788-104">이 제한은 MSIL 수준에 적용되므로 호출과 `try` 사이에 코드가 아닌 생성 소스(예: 주석)를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f9788-105">증상</span><span class="sxs-lookup"><span data-stu-id="f9788-105">Symptoms</span></span>  
 <span data-ttu-id="f9788-106">CER(제약이 있는 실행 영역)이 이와 같이 처리되지 않고 간단한 예외 처리 블록(`finally` 또는 `catch`)으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="f9788-107">따라서 메모리 부족 조건 또는 스레드 중단이 발생할 경우 해당 영역이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f9788-108">원인</span><span class="sxs-lookup"><span data-stu-id="f9788-108">Cause</span></span>  
 <span data-ttu-id="f9788-109">CER에 대한 준비 패턴을 제대로 따르지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="f9788-110">이것은 오류 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-110">This is an error event.</span></span> <span data-ttu-id="f9788-111"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 메서드 호출은 `catch`/`finally`/`fault`/`filter` 문 바로 앞에 사용 해야 하는 CER을 소개 하는 예외 처리기를 표시 하는 데 사용 됩니다.`try`</span><span class="sxs-lookup"><span data-stu-id="f9788-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f9788-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f9788-112">Resolution</span></span>  
 <span data-ttu-id="f9788-113"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 호출이 `try` 문의 바로 앞에 실행되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f9788-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="f9788-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="f9788-115">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f9788-116">출력</span><span class="sxs-lookup"><span data-stu-id="f9788-116">Output</span></span>  
 <span data-ttu-id="f9788-117">MDA는 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 메서드를 호출하는 메서드 이름, MSIL 오프셋 및 호출이 try 블록 시작 부분의 바로 앞에 실행됨을 나타내는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f9788-118">구성</span><span class="sxs-lookup"><span data-stu-id="f9788-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f9788-119">예제</span><span class="sxs-lookup"><span data-stu-id="f9788-119">Example</span></span>  
 <span data-ttu-id="f9788-120">다음 코드 예제에서는 MDA를 활성화하는 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9788-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9788-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9788-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="f9788-122">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="f9788-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f9788-123">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="f9788-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
