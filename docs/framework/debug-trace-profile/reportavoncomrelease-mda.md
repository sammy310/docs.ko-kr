---
title: reportAvOnComRelease MDA
description: .NET의 액세스 위반 및 메모리 손상 때문에 활성화 될 수 있는 reportAvOnComRelease MDA (관리 디버깅 도우미)를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
ms.openlocfilehash: c5047aa4005cdaa9ae6aabe8dcd7ee838ee13f58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267119"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="08055-103">reportAvOnComRelease MDA</span><span class="sxs-lookup"><span data-stu-id="08055-103">reportAvOnComRelease MDA</span></span>

<span data-ttu-id="08055-104">`reportAvOnComRelease` MDA(관리 디버깅 도우미)는 COM interop를 수행하고 원시 COM 호출과 결합된 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 또는 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 메서드를 사용하는 동안 사용자 참조 계산 오류로 인해 예외가 throw되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="08055-104">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="08055-105">증상</span><span class="sxs-lookup"><span data-stu-id="08055-105">Symptoms</span></span>  

 <span data-ttu-id="08055-106">액세스 위반 및 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="08055-106">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="08055-107">원인</span><span class="sxs-lookup"><span data-stu-id="08055-107">Cause</span></span>  

 <span data-ttu-id="08055-108">경우에 따라, COM interop를 수행하고 원시 COM 호출과 결합된 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 또는 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 메서드를 사용하는 동안 사용자 참조 계산 오류로 인해 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="08055-108">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="08055-109">일반적으로 이 예외는 이렇게 하지 않으면 CLR에서 액세스 위반이 발생하여 CLR이 종료되기 때문에 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08055-109">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="08055-110">이 도우미를 사용하도록 설정한 경우 이러한 예외는 단순히 무시되는 것이 아니라 감지 및 보고될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08055-110">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="08055-111">해결 방법</span><span class="sxs-lookup"><span data-stu-id="08055-111">Resolution</span></span>  

 <span data-ttu-id="08055-112">참조 계산 코드를 검토하고 오류를 검색하며, 개체의 네이티브 클라이언트에 참조 계산 오류가 있는지 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="08055-112">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="08055-113">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="08055-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="08055-114">두 가지 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08055-114">Two modes are available.</span></span> <span data-ttu-id="08055-115">`allowAv` 특성이 `true`인 경우 도우미가 런타임에서 액세스 위반을 무시하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08055-115">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="08055-116">`allowAv`가 `false`(기본값)인 경우 런타임에서 액세스 위반을 무시하지만 예외가 throw 및 무시되었음을 나타내는 경고 메시지가 사용자에게 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="08055-116">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="08055-117">출력</span><span class="sxs-lookup"><span data-stu-id="08055-117">Output</span></span>  

 <span data-ttu-id="08055-118">가능한 경우 출력에 COM 인터페이스 포인터의 원래 vtable이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="08055-118">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="08055-119">그러지 않으면 정보 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08055-119">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="08055-120">구성</span><span class="sxs-lookup"><span data-stu-id="08055-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08055-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08055-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="08055-122">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="08055-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="08055-123">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="08055-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
