---
title: gcUnmanagedToManaged MDA
description: .NET에서 gcManagedToUnmanaged 관리 디버깅 길잡이를 검토 합니다. 이 MDA는 관리 코드로 전환 하는 동안 가비지 힙 손상이 발생 하 여 활성화할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
ms.openlocfilehash: 320d55224e6a204d330447d6c68eabe0fa6cf892
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415903"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="e8f7a-104">gcUnmanagedToManaged MDA</span><span class="sxs-lookup"><span data-stu-id="e8f7a-104">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="e8f7a-105">`gcUnmanagedToManaged` MDA(관리 디버깅 도우미)는 위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="e8f7a-106">증상</span><span class="sxs-lookup"><span data-stu-id="e8f7a-106">Symptoms</span></span>  
 <span data-ttu-id="e8f7a-107">COM 및 플랫폼 호출을 사용하여 관리되지 않는 사용자 구성 요소를 실행하는 애플리케이션은 CLR에서 비결정적 액세스 위반을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="e8f7a-108">원인</span><span class="sxs-lookup"><span data-stu-id="e8f7a-108">Cause</span></span>  
 <span data-ttu-id="e8f7a-109">애플리케이션이 관리되지 않는 사용자 구성 요소를 실행하는 경우 해당 구성 요소로 인해 가비지 수집된 힙이 손상되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="e8f7a-110">이 경우 가비지 수집기가 개체 그래프를 검색하려고 하면 CLR에서 액세스 위반이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="e8f7a-111">해결 방법</span><span class="sxs-lookup"><span data-stu-id="e8f7a-111">Resolution</span></span>  
 <span data-ttu-id="e8f7a-112">이 도우미를 사용하도록 설정하면 관리되는 각 전환 전에 가비지 수집이 강제로 수행되어 관리되지 않는 구성 요소로 인해 가비지 수집된 힙이 손상되는 시간과 액세스 위반이 발생하는 시간 사이의 간격이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e8f7a-113">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="e8f7a-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="e8f7a-114">위협이 비관리 코드에서 관리 코드로 전환될 때마다 가비지 컬렉션을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e8f7a-115">출력</span><span class="sxs-lookup"><span data-stu-id="e8f7a-115">Output</span></span>  
 <span data-ttu-id="e8f7a-116">이 MDA는 출력을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e8f7a-117">구성</span><span class="sxs-lookup"><span data-stu-id="e8f7a-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8f7a-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="e8f7a-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="e8f7a-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="e8f7a-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e8f7a-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="e8f7a-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="e8f7a-121">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="e8f7a-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
