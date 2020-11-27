---
title: invalidFunctionPointerInDelegate MDA
description: 대리자를 만들기 위해 잘못 된 함수 포인터를 전달 하는 경우 호출 되는 MDA (invalidFunctionPointerInDelegate 관리 디버깅 도우미)를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
ms.openlocfilehash: 8072d35a45cb1e0590aa5533210d0e0f86913164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272620"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="c1689-103">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="c1689-103">invalidFunctionPointerInDelegate MDA</span></span>

<span data-ttu-id="c1689-104">`invalidFunctionPointerInDelegate` MDA(관리 디버깅 도우미)는 잘못된 함수 포인터가 네이티브 함수 포인터를 통해 대리자를 생성하도록 전달되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1689-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c1689-105">증상</span><span class="sxs-lookup"><span data-stu-id="c1689-105">Symptoms</span></span>  

 <span data-ttu-id="c1689-106">함수 포인터를 통해 대리자를 사용할 때 액세스 위반 또는 예기치 않은 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c1689-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c1689-107">원인</span><span class="sxs-lookup"><span data-stu-id="c1689-107">Cause</span></span>  

 <span data-ttu-id="c1689-108">잘못된 함수 포인터가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1689-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c1689-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="c1689-109">Resolution</span></span>  

 <span data-ttu-id="c1689-110">유효한 함수 포인터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1689-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c1689-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="c1689-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="c1689-112">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1689-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c1689-113">출력</span><span class="sxs-lookup"><span data-stu-id="c1689-113">Output</span></span>  

 <span data-ttu-id="c1689-114">잘못된 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1689-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c1689-115">구성</span><span class="sxs-lookup"><span data-stu-id="c1689-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1689-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1689-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c1689-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="c1689-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c1689-118">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="c1689-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
