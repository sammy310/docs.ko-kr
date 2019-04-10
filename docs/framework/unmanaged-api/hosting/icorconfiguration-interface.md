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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24e278b3449d0e17377495cef0f445c1ebed734
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149814"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="d04fb-102">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d04fb-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="d04fb-103">CLR (공용 언어 런타임) 구성 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04fb-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d04fb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d04fb-104">Methods</span></span>  
  
|<span data-ttu-id="d04fb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d04fb-105">Method</span></span>|<span data-ttu-id="d04fb-106">설명</span><span class="sxs-lookup"><span data-stu-id="d04fb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d04fb-107">AddDebuggerSpecialThread 메서드</span><span class="sxs-lookup"><span data-stu-id="d04fb-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="d04fb-108">디버깅 서비스에 특정 스레드를 계속 디버거가 응용 프로그램을 중지 하는 동안 관리 되거나 관리 되지 않는 디버깅 시나리오는 동시 실행 수 있어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d04fb-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="d04fb-109">SetDebuggerThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="d04fb-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="d04fb-110">디버깅 서비스를 호출 하는 CLR 스레드를 차단 하 고 차단을 해제 때 디버깅을 위해 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04fb-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="d04fb-111">SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="d04fb-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="d04fb-112">가비지 수집기에 의해 가상 메모리의 한계를 변경 하도록 호스트에 요청에 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04fb-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="d04fb-113">SetGCThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="d04fb-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="d04fb-114">가비지 컬렉션에 대해 차단 될 수 있는 런타임 이외의 작업에 대 한 스레드를 예약 하는 것에 대 한 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04fb-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d04fb-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d04fb-115">Requirements</span></span>  
 <span data-ttu-id="d04fb-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d04fb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d04fb-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d04fb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d04fb-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d04fb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d04fb-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d04fb-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d04fb-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="d04fb-120">See also</span></span>

- [<span data-ttu-id="d04fb-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d04fb-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d04fb-122">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="d04fb-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
