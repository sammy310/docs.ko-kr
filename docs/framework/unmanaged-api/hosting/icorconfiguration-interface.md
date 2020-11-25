---
title: ICorConfiguration 인터페이스
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: fa8d15bc8e504a57d5cc87c170a3a5b022798add
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715786"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="fb7dd-102">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb7dd-102">ICorConfiguration Interface</span></span>

<span data-ttu-id="fb7dd-103">CLR (공용 언어 런타임)을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb7dd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fb7dd-104">Methods</span></span>  
  
|<span data-ttu-id="fb7dd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fb7dd-105">Method</span></span>|<span data-ttu-id="fb7dd-106">설명</span><span class="sxs-lookup"><span data-stu-id="fb7dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb7dd-107">AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="fb7dd-107">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="fb7dd-108">관리 되거나 관리 되지 않는 디버깅 시나리오에서 디버거가 응용 프로그램을 중지 하는 동안 특정 스레드가 계속 실행 되도록 허용 해야 하는 디버깅 서비스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="fb7dd-109">SetDebuggerThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="fb7dd-109">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="fb7dd-110">디버깅을 위해 CLR 스레드가 차단 되 고 차단 해제 될 때 디버깅 서비스에서 호출할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="fb7dd-111">SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="fb7dd-111">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="fb7dd-112">가비지 수집기에서 가상 메모리의 한도를 변경 하는 호스트를 요청 하는 데 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="fb7dd-113">SetGCThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="fb7dd-113">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="fb7dd-114">가비지 컬렉션에 대해 차단 되는 런타임 이외의 작업에 대해 스레드를 예약 하는 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb7dd-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb7dd-115">Requirements</span></span>  

 <span data-ttu-id="fb7dd-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7dd-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fb7dd-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb7dd-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb7dd-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb7dd-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7dd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7dd-120">참조</span><span class="sxs-lookup"><span data-stu-id="fb7dd-120">See also</span></span>

- [<span data-ttu-id="fb7dd-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb7dd-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="fb7dd-122">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="fb7dd-122">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
