---
title: gcManagedToUnmanaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
ms.openlocfilehash: f7e6334e20a6e0db1d52307a833de0ecd0d74cc4
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217481"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="bda5e-102">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="bda5e-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="bda5e-103">`gcManagedToUnmanaged` MDA(관리 디버깅 도우미)는 위협이 관리 코드에서 비관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bda5e-104">증상</span><span class="sxs-lookup"><span data-stu-id="bda5e-104">Symptoms</span></span>  
 <span data-ttu-id="bda5e-105">COM에 노출된 관리되는 개체를 사용하려고 하면 관리되지 않는 사용자 구성 요소에서 액세스 위반이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="bda5e-106">COM 개체가 해제된 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-106">The COM object appears to have been released.</span></span> <span data-ttu-id="bda5e-107">액세스 위반은 비결정적입니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bda5e-108">원인</span><span class="sxs-lookup"><span data-stu-id="bda5e-108">Cause</span></span>  
 <span data-ttu-id="bda5e-109">관리되지 않는 구성 요소가 관리되는 COM 개체 계산을 올바르게 참조하지 않을 경우 관리되지 않는 구성 요소가 여전히 개체 참조를 보유하고 있을 때 런타임에서 COM에 노출된 관리되는 개체를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="bda5e-110">런타임은 가비지 컬렉션 중에 <xref:System.Runtime.InteropServices.Marshal.Release%2A>를 호출하므로 가비지 컬렉션이 발생하기 전에 사용자 구성 요소가 개체를 사용하는 경우 아직 수집되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="bda5e-111">이는 비결정성 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bda5e-112">해결 방법</span><span class="sxs-lookup"><span data-stu-id="bda5e-112">Resolution</span></span>  
 <span data-ttu-id="bda5e-113">이 도우미를 사용하도록 설정하면 개체가 컬렉션에 적격한 시간 사이의 간격이 감소하며, <xref:System.Runtime.InteropServices.Marshal.Release%2A>가 호출되어 수집된 개체에 처음 액세스하려고 시도하는 관리되지 않는 구성 요소를 추적할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bda5e-114">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="bda5e-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="bda5e-115">위협이 관리 코드에서 비관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bda5e-116">출력</span><span class="sxs-lookup"><span data-stu-id="bda5e-116">Output</span></span>  
 <span data-ttu-id="bda5e-117">이 MDA는 출력을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bda5e-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="bda5e-118">구성</span><span class="sxs-lookup"><span data-stu-id="bda5e-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bda5e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bda5e-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="bda5e-120">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="bda5e-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="bda5e-121">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="bda5e-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="bda5e-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="bda5e-122">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
