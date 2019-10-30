---
title: ICorDebugController::EnumerateThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125405"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="3d056-102">ICorDebugController::EnumerateThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="3d056-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="3d056-103">프로세스의 활성 관리 되는 스레드에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d056-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d056-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d056-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d056-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d056-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="3d056-106">제한이 프로세스에서 활성화 된 모든 관리 되는 스레드에 대 한 열거자를 나타내는 "ICorDebugThreadEnum" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d056-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d056-107">주의</span><span class="sxs-lookup"><span data-stu-id="3d056-107">Remarks</span></span>  
 <span data-ttu-id="3d056-108">[ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 콜백이 디스패치 된 후, [ICorDebugManagedCallback:: exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) 콜백이 디스패치 되기 전에는 스레드가 활성 상태인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d056-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="3d056-109">관리 되는 스레드의 스택에 관리 되는 프레임이 반드시 있어야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3d056-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="3d056-110">[ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) 콜백 전에도 스레드를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d056-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="3d056-111">열거형은 자연스럽 게 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d056-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d056-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d056-112">Requirements</span></span>  
 <span data-ttu-id="3d056-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d056-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d056-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d056-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d056-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d056-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d056-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d056-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d056-117">참조</span><span class="sxs-lookup"><span data-stu-id="3d056-117">See also</span></span>
