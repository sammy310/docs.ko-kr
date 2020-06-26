---
title: gcManagedToUnmanaged MDA
description: GcManagedToUnmanaged 관리 디버깅 도우미를 검토 합니다. 비관리 코드로 전환 하는 동안 가비지 수집이 중간에 발생 하 여이 MDA를 활성화할 수 있습니다.
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
ms.openlocfilehash: 76c621a1f2bb780d38228f2a84d4c77441774770
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415916"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="b9301-104">gcManagedToUnmanaged MDA</span><span class="sxs-lookup"><span data-stu-id="b9301-104">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="b9301-105">`gcManagedToUnmanaged` MDA(관리 디버깅 도우미)는 위협이 관리 코드에서 비관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-105">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b9301-106">증상</span><span class="sxs-lookup"><span data-stu-id="b9301-106">Symptoms</span></span>  
 <span data-ttu-id="b9301-107">COM에 노출된 관리되는 개체를 사용하려고 하면 관리되지 않는 사용자 구성 요소에서 액세스 위반이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-107">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="b9301-108">COM 개체가 해제된 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-108">The COM object appears to have been released.</span></span> <span data-ttu-id="b9301-109">액세스 위반은 비결정적입니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-109">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b9301-110">원인</span><span class="sxs-lookup"><span data-stu-id="b9301-110">Cause</span></span>  
 <span data-ttu-id="b9301-111">관리되지 않는 구성 요소가 관리되는 COM 개체 계산을 올바르게 참조하지 않을 경우 관리되지 않는 구성 요소가 여전히 개체 참조를 보유하고 있을 때 런타임에서 COM에 노출된 관리되는 개체를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-111">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="b9301-112">런타임은 가비지 컬렉션 중에 <xref:System.Runtime.InteropServices.Marshal.Release%2A>를 호출하므로 가비지 컬렉션이 발생하기 전에 사용자 구성 요소가 개체를 사용하는 경우 아직 수집되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-112">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="b9301-113">이는 비결정성 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-113">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b9301-114">해결 방법</span><span class="sxs-lookup"><span data-stu-id="b9301-114">Resolution</span></span>  
 <span data-ttu-id="b9301-115">이 도우미를 사용하도록 설정하면 개체가 컬렉션에 적격한 시간 사이의 간격이 감소하며, <xref:System.Runtime.InteropServices.Marshal.Release%2A>가 호출되어 수집된 개체에 처음 액세스하려고 시도하는 관리되지 않는 구성 요소를 추적할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-115">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b9301-116">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="b9301-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="b9301-117">위협이 관리 코드에서 비관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-117">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b9301-118">출력</span><span class="sxs-lookup"><span data-stu-id="b9301-118">Output</span></span>  
 <span data-ttu-id="b9301-119">이 MDA는 출력을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9301-119">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b9301-120">구성</span><span class="sxs-lookup"><span data-stu-id="b9301-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9301-121">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b9301-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b9301-122">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="b9301-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b9301-123">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="b9301-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="b9301-124">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="b9301-124">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
