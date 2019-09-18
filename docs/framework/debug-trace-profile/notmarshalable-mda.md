---
title: notMarshalable MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ddb6b0b5c2248d215245e0f881c8e7c91b13e480
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052424"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="bb025-102">notMarshalable MDA</span><span class="sxs-lookup"><span data-stu-id="bb025-102">notMarshalable MDA</span></span>
<span data-ttu-id="bb025-103">`notMarshalable` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)이 컨텍스트 간에 인터페이스를 마샬링하는 동안 등록된 유효한 프록시/스텁이 없는 COM 인터페이스 포인터 또는 잘못된 `IMarshal` 인터페이스 구현을 발견할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb025-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bb025-104">증상</span><span class="sxs-lookup"><span data-stu-id="bb025-104">Symptoms</span></span>  
 <span data-ttu-id="bb025-105">호출이 서비스되지 않거나 COM 인터페이스 포인터에 대한 잘못된 컨텍스트에서 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bb025-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bb025-106">원인</span><span class="sxs-lookup"><span data-stu-id="bb025-106">Cause</span></span>  
 <span data-ttu-id="bb025-107">컨텍스트 간에 인터페이스를 마샬링하는 동안 등록된 유효한 프록시/스텁이 없거나 잘못된 `IMarshal`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb025-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bb025-108">해결 방법</span><span class="sxs-lookup"><span data-stu-id="bb025-108">Resolution</span></span>  
 <span data-ttu-id="bb025-109">프록시 스텁이 등록되어 있고 `IMarshal` 구현이 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb025-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bb025-110">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="bb025-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="bb025-111">이 MDA는 런타임에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb025-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bb025-112">출력</span><span class="sxs-lookup"><span data-stu-id="bb025-112">Output</span></span>  
 <span data-ttu-id="bb025-113">문제를 설명하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="bb025-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bb025-114">Configuration</span><span class="sxs-lookup"><span data-stu-id="bb025-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb025-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb025-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bb025-116">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="bb025-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bb025-117">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="bb025-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
