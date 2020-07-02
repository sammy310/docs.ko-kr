---
title: notMarshalable MDA
description: 호출이 서비스 되지 않거나 COM 인터페이스 포인터에 대 한 잘못 된 컨텍스트에서 발생 하는 경우에 활성화할 수 있는 notMarshalable 수 있는 관리 디버깅 도우미를 검토 합니다.
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
ms.openlocfilehash: b464d914a8d83504daaf4cb276914da7798262dc
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803796"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="df54f-103">notMarshalable MDA</span><span class="sxs-lookup"><span data-stu-id="df54f-103">notMarshalable MDA</span></span>
<span data-ttu-id="df54f-104">`notMarshalable` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)이 컨텍스트 간에 인터페이스를 마샬링하는 동안 등록된 유효한 프록시/스텁이 없는 COM 인터페이스 포인터 또는 잘못된 `IMarshal` 인터페이스 구현을 발견할 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="df54f-104">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="df54f-105">증상</span><span class="sxs-lookup"><span data-stu-id="df54f-105">Symptoms</span></span>  
 <span data-ttu-id="df54f-106">호출이 서비스되지 않거나 COM 인터페이스 포인터에 대한 잘못된 컨텍스트에서 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="df54f-106">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="df54f-107">원인</span><span class="sxs-lookup"><span data-stu-id="df54f-107">Cause</span></span>  
 <span data-ttu-id="df54f-108">컨텍스트 간에 인터페이스를 마샬링하는 동안 등록된 유효한 프록시/스텁이 없거나 잘못된 `IMarshal`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df54f-108">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="df54f-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="df54f-109">Resolution</span></span>  
 <span data-ttu-id="df54f-110">프록시 스텁이 등록되어 있고 `IMarshal` 구현이 유효한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="df54f-110">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="df54f-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="df54f-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="df54f-112">이 MDA는 런타임에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df54f-112">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="df54f-113">출력</span><span class="sxs-lookup"><span data-stu-id="df54f-113">Output</span></span>  
 <span data-ttu-id="df54f-114">문제를 설명하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="df54f-114">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="df54f-115">Configuration</span><span class="sxs-lookup"><span data-stu-id="df54f-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="df54f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df54f-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="df54f-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="df54f-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="df54f-118">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="df54f-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
