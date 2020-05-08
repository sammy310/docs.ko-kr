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
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892749"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="57cf3-102">ICorDebugController::EnumerateThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="57cf3-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="57cf3-103">프로세스의 활성 관리 되는 스레드에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="57cf3-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57cf3-104">구문</span><span class="sxs-lookup"><span data-stu-id="57cf3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57cf3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="57cf3-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="57cf3-106">제한이 프로세스에서 활성화 된 모든 관리 되는 스레드에 대 한 열거자를 나타내는 "ICorDebugThreadEnum" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="57cf3-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57cf3-107">설명</span><span class="sxs-lookup"><span data-stu-id="57cf3-107">Remarks</span></span>  
 <span data-ttu-id="57cf3-108">[ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) 콜백이 디스패치 된 후, [ICorDebugManagedCallback:: exitthread](icordebugmanagedcallback-exitthread-method.md) 콜백이 디스패치 되기 전에는 스레드가 활성 상태인 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57cf3-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="57cf3-109">관리 되는 스레드의 스택에 관리 되는 프레임이 반드시 있어야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="57cf3-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="57cf3-110">[ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 전에도 스레드를 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf3-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="57cf3-111">열거형은 자연스럽 게 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf3-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57cf3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="57cf3-112">Requirements</span></span>  
 <span data-ttu-id="57cf3-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57cf3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57cf3-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57cf3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57cf3-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57cf3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57cf3-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57cf3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57cf3-117">참조</span><span class="sxs-lookup"><span data-stu-id="57cf3-117">See also</span></span>
