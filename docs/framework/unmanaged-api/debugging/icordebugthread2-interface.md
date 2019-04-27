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
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993943"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="29934-102">ICorDebugThread2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29934-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="29934-103">ICorDebugThread 인터페이스를 논리적으로 확장으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29934-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29934-104">메서드</span><span class="sxs-lookup"><span data-stu-id="29934-104">Methods</span></span>  
  
|<span data-ttu-id="29934-105">메서드</span><span class="sxs-lookup"><span data-stu-id="29934-105">Method</span></span>|<span data-ttu-id="29934-106">설명</span><span class="sxs-lookup"><span data-stu-id="29934-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29934-107">GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="29934-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="29934-108">COR_ACTIVE_FUNCTION 인스턴스 스레드 프레임의 현재 함수에 대 한 데이터를 포함 하는 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="29934-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="29934-109">GetConnectionID 메서드</span><span class="sxs-lookup"><span data-stu-id="29934-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="29934-110">이 대 한 연결 식별자를 가져옵니다 `ICorDebugThread2`합니다.</span><span class="sxs-lookup"><span data-stu-id="29934-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="29934-111">GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="29934-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="29934-112">이 대 한 작업 식별자를 가져옵니다 `ICorDebugThread2`합니다.</span><span class="sxs-lookup"><span data-stu-id="29934-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="29934-113">GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="29934-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="29934-114">이 대 한 운영 체제 스레드 식별자를 가져옵니다 `ICorDebugThread2`합니다.</span><span class="sxs-lookup"><span data-stu-id="29934-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="29934-115">InterceptCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="29934-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="29934-116">디버거에서를 스레드에서 현재 예외를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29934-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29934-117">설명</span><span class="sxs-lookup"><span data-stu-id="29934-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29934-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29934-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29934-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29934-119">Requirements</span></span>  
 <span data-ttu-id="29934-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="29934-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29934-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29934-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29934-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29934-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29934-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29934-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29934-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="29934-124">See also</span></span>

- [<span data-ttu-id="29934-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29934-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
