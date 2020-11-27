---
title: invalidIUnknown MDA
description: 네이티브 코드에서 관리 코드에 잘못 된 IUnknown 포인터를 전달할 때 활성화 되는 invalidIUnknown MDA (관리 디버깅 도우미)를 검토 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 8e7ca6c9c43c4f507d235c879498b2e831c6eba9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272542"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="476a5-103">invalidIUnknown MDA</span><span class="sxs-lookup"><span data-stu-id="476a5-103">invalidIUnknown MDA</span></span>

<span data-ttu-id="476a5-104">`invalidIUnknown` MDA(관리 디버깅 도우미)는 잘못된 `IUnknown` 포인터가 네이티브 코드에서 관리 코드로 전달될 때 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-104">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="476a5-105">`IUnknown` 인터페이스에 대해 쿼리될 때 `IUnknown`에서 성공을 반환하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-105">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="476a5-106">증상</span><span class="sxs-lookup"><span data-stu-id="476a5-106">Symptoms</span></span>  

 <span data-ttu-id="476a5-107">인수 마샬링 중 COM 인터페이스 포인터를 마샬링할 때 예기치 않은 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-107">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="476a5-108">원인</span><span class="sxs-lookup"><span data-stu-id="476a5-108">Cause</span></span>  

 <span data-ttu-id="476a5-109">COM 인터페이스의 잘못된 `QueryInterface` 구현이 CLR에 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-109">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="476a5-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="476a5-110">Resolution</span></span>  

 <span data-ttu-id="476a5-111">`QueryInterface` 구현을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-111">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="476a5-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="476a5-112">Effect on the Runtime</span></span>  

 <span data-ttu-id="476a5-113">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-113">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="476a5-114">출력</span><span class="sxs-lookup"><span data-stu-id="476a5-114">Output</span></span>  

 <span data-ttu-id="476a5-115">오류에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="476a5-115">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="476a5-116">구성</span><span class="sxs-lookup"><span data-stu-id="476a5-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="476a5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="476a5-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="476a5-118">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="476a5-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="476a5-119">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="476a5-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
