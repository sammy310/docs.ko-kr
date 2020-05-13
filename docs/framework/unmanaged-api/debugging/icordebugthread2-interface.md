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
ms.openlocfilehash: a7a8d96548704f223f05826af79a4e227bdfab06
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379828"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="1ba78-102">ICorDebugThread2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ba78-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="1ba78-103">ICorDebugThread 인터페이스에 대 한 논리적 확장으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ba78-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ba78-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-104">Methods</span></span>  
  
|<span data-ttu-id="1ba78-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-105">Method</span></span>|<span data-ttu-id="1ba78-106">설명</span><span class="sxs-lookup"><span data-stu-id="1ba78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ba78-107">GetActiveFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="1ba78-108">스레드의 프레임에 있는 활성 함수에 대 한 데이터를 포함 하는 COR_ACTIVE_FUNCTION 인스턴스의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ba78-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="1ba78-109">GetConnectionID 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="1ba78-110">이에 대 한 연결 식별자를 가져옵니다 `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="1ba78-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="1ba78-111">GetTaskID 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="1ba78-112">이에 대 한 작업 식별자를 가져옵니다 `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="1ba78-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="1ba78-113">GetVolatileOSThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="1ba78-114">이에 대 한 운영 체제 스레드 식별자를 가져옵니다 `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="1ba78-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="1ba78-115">InterceptCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba78-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="1ba78-116">디버거가 스레드의 현재 예외를 가로챌 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba78-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ba78-117">설명</span><span class="sxs-lookup"><span data-stu-id="1ba78-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ba78-118">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba78-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba78-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ba78-119">Requirements</span></span>  
 <span data-ttu-id="1ba78-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ba78-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba78-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ba78-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ba78-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ba78-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ba78-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba78-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba78-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ba78-124">See also</span></span>

- [<span data-ttu-id="1ba78-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ba78-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
