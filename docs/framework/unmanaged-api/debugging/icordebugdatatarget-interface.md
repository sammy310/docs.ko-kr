---
title: ICorDebugDataTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
ms.openlocfilehash: f8b216d370f7278f6d2a4beed5bab88afa666200
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122209"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="da7bc-102">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da7bc-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="da7bc-103">특정 대상 프로세스에 대한 액세스를 제공하는 콜백 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da7bc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="da7bc-104">Methods</span></span>  
  
|<span data-ttu-id="da7bc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="da7bc-105">Method</span></span>|<span data-ttu-id="da7bc-106">설명</span><span class="sxs-lookup"><span data-stu-id="da7bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da7bc-107">GetPlatform 메서드</span><span class="sxs-lookup"><span data-stu-id="da7bc-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="da7bc-108">대상 프로세스가 실행 되는 프로세서 아키텍처 및 운영 체제를 포함 하 여 플랫폼에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="da7bc-109">ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="da7bc-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="da7bc-110">지정 된 주소에서 시작 하는 연속 메모리 블록을 가져와 제공 된 버퍼에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="da7bc-111">GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="da7bc-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="da7bc-112">지정 된 스레드에 대 한 현재 스레드 컨텍스트를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da7bc-113">주의</span><span class="sxs-lookup"><span data-stu-id="da7bc-113">Remarks</span></span>  
 <span data-ttu-id="da7bc-114">`ICorDebugDataTarget`와 해당 메서드에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="da7bc-115">디버깅 서비스는이 인터페이스의 메서드를 호출 하 여 대상 프로세스의 메모리 및 기타 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="da7bc-116">디버거 클라이언트는 특정 대상에 적합 하 게이 인터페이스를 구현 해야 합니다 (예: 라이브 프로세스 또는 메모리 덤프).</span><span class="sxs-lookup"><span data-stu-id="da7bc-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="da7bc-117">`ICorDebugDataTarget` 메서드는 다른 `ICorDebug*` 인터페이스에서 구현 된 메서드 내 에서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="da7bc-118">이렇게 하면 디버거 클라이언트에서 호출 되는 스레드 및 시기를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="da7bc-119">`ICorDebugDataTarget` 구현은 항상 대상에 대 한 최신 정보를 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="da7bc-120">대상 프로세스를 중지 하 고 변경 하지 않아야 합니다. `ICorDebug*` 인터페이스 (따라서 `ICorDebugDataTarget` 메서드)를 호출 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="da7bc-121">대상이 라이브 프로세스이 고 상태가 변경 되 면 [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드를 다시 호출 하 여 대체 ICorDebugProcess 인스턴스를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da7bc-122">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da7bc-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da7bc-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da7bc-123">Requirements</span></span>  
 <span data-ttu-id="da7bc-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da7bc-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da7bc-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da7bc-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da7bc-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da7bc-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da7bc-127">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da7bc-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7bc-128">참조</span><span class="sxs-lookup"><span data-stu-id="da7bc-128">See also</span></span>

- [<span data-ttu-id="da7bc-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da7bc-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="da7bc-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="da7bc-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
