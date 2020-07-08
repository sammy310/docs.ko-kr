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
ms.openlocfilehash: a17427d117c62ba782af3c9549c84623a3013b06
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051742"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="62017-103">invalidFunctionPointerInDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="62017-103">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="62017-104">`invalidFunctionPointerInDelegate` MDA(관리 디버깅 도우미)는 잘못된 함수 포인터가 네이티브 함수 포인터를 통해 대리자를 생성하도록 전달되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="62017-104">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="62017-105">증상</span><span class="sxs-lookup"><span data-stu-id="62017-105">Symptoms</span></span>  
 <span data-ttu-id="62017-106">함수 포인터를 통해 대리자를 사용할 때 액세스 위반 또는 예기치 않은 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="62017-106">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="62017-107">원인</span><span class="sxs-lookup"><span data-stu-id="62017-107">Cause</span></span>  
 <span data-ttu-id="62017-108">잘못된 함수 포인터가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62017-108">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="62017-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="62017-109">Resolution</span></span>  
 <span data-ttu-id="62017-110">유효한 함수 포인터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="62017-110">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="62017-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="62017-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="62017-112">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62017-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="62017-113">출력</span><span class="sxs-lookup"><span data-stu-id="62017-113">Output</span></span>  
 <span data-ttu-id="62017-114">잘못된 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62017-114">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="62017-115">Configuration</span><span class="sxs-lookup"><span data-stu-id="62017-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62017-116">참조</span><span class="sxs-lookup"><span data-stu-id="62017-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="62017-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="62017-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="62017-118">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="62017-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
