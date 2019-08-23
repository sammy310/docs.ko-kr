---
title: ICorDebugThread2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d21c221bba3ac668924003f96580bb660229ad7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962998"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="9dae8-102">ICorDebugThread2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9dae8-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="9dae8-103">ICorDebugThread 인터페이스에 대 한 논리적 확장으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9dae8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-104">Methods</span></span>  
  
|<span data-ttu-id="9dae8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-105">Method</span></span>|<span data-ttu-id="9dae8-106">Description</span><span class="sxs-lookup"><span data-stu-id="9dae8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9dae8-107">GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="9dae8-108">스레드의 프레임에서 활성 함수에 대 한 데이터를 포함 하는 COR_ACTIVE_FUNCTION instances의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="9dae8-109">GetConnectionID 메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="9dae8-110">이 `ICorDebugThread2`에 대 한 연결 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="9dae8-111">GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="9dae8-112">이 `ICorDebugThread2`에 대 한 작업 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="9dae8-113">GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="9dae8-114">이 `ICorDebugThread2`에 대 한 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="9dae8-115">InterceptCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="9dae8-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="9dae8-116">디버거가 스레드의 현재 예외를 가로챌 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dae8-117">설명</span><span class="sxs-lookup"><span data-stu-id="9dae8-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9dae8-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dae8-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dae8-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9dae8-119">Requirements</span></span>  
 <span data-ttu-id="9dae8-120">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9dae8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dae8-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9dae8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dae8-122">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dae8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dae8-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dae8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dae8-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="9dae8-124">See also</span></span>

- [<span data-ttu-id="9dae8-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9dae8-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
