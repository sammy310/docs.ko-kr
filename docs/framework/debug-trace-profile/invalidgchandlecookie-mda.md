---
title: invalidGCHandleCookie MDA
description: 잘못 된 IntPtr 쿠키에서 GCHandle로의 변환이 시도 될 때 활성화 되는 invalidGCHandleCookie MDA (관리 디버깅 도우미)를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
ms.openlocfilehash: 1063b7be902d3063717b6639564d819ef3292c0e
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051300"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="a2968-103">invalidGCHandleCookie MDA</span><span class="sxs-lookup"><span data-stu-id="a2968-103">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="a2968-104">`invalidGCHandleCookie` MDA(관리 디버깅 도우미)는 잘못된 <xref:System.IntPtr> 쿠키에서 <xref:System.Runtime.InteropServices.GCHandle>로 변환하려고 시도하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2968-104">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a2968-105">증상</span><span class="sxs-lookup"><span data-stu-id="a2968-105">Symptoms</span></span>  
 <span data-ttu-id="a2968-106"><xref:System.IntPtr>에서 <xref:System.Runtime.InteropServices.GCHandle>을 사용하거나 검색하려고 시도할 때 액세스 위반 및 메모리 손상과 같은 정의되지 않은 동작이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a2968-106">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a2968-107">원인</span><span class="sxs-lookup"><span data-stu-id="a2968-107">Cause</span></span>  
 <span data-ttu-id="a2968-108">쿠키가 원래 <xref:System.Runtime.InteropServices.GCHandle>에서 만들어지지 않았거나, 이미 해제된 <xref:System.Runtime.InteropServices.GCHandle>을 나타내거나, 다음 애플리케이션 도메인의 <xref:System.Runtime.InteropServices.GCHandle>에 대한 쿠키이거나, 네이티브 코드에 <xref:System.Runtime.InteropServices.GCHandle>로 마샬링되지만 캐스팅이 시도된 <xref:System.IntPtr>로 다시 CLR에 전달되었기 때문에 쿠키가 잘못될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2968-108">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a2968-109">해결 방법</span><span class="sxs-lookup"><span data-stu-id="a2968-109">Resolution</span></span>  
 <span data-ttu-id="a2968-110"><xref:System.Runtime.InteropServices.GCHandle>에 대한 유효한 <xref:System.IntPtr> 쿠키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2968-110">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a2968-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="a2968-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="a2968-112">이 MDA가 사용하도록 설정되면 다시 전달된 쿠키 값이 MDA가 사용되지 않을 경우 반환되는 쿠키 값과 다르기 때문에 디버거는 더 이상 원래 개체에 대한 루트를 추적할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2968-112">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a2968-113">출력</span><span class="sxs-lookup"><span data-stu-id="a2968-113">Output</span></span>  
 <span data-ttu-id="a2968-114">잘못된 <xref:System.IntPtr> 쿠키 값이 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2968-114">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a2968-115">Configuration</span><span class="sxs-lookup"><span data-stu-id="a2968-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2968-116">참조</span><span class="sxs-lookup"><span data-stu-id="a2968-116">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="a2968-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="a2968-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
