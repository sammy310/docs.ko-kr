---
title: ICorDebug::CanLaunchOrAttach 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c29859a54b89956e017f06b8eeb97a6171eabbb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476219"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="9e8a5-102">ICorDebug::CanLaunchOrAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="9e8a5-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="9e8a5-103">새 프로세스를 시작 하거나 지정한 기존 프로세스에 연결 하는 현재 컴퓨터 및 런타임 구성 컨텍스트 내에서 가능한 지 여부를 나타내는 HRESULT를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e8a5-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e8a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e8a5-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="9e8a5-106">[in] 기존 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="9e8a5-107">[in] 전달 `true` Win32 디버깅 사용을 시작 하려고 하거나 Win32 디버깅, 그렇지 않으면 연결을 전달 하면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e8a5-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9e8a5-108">Return Value</span></span>  
 <span data-ttu-id="9e8a5-109">디버깅 서비스를 확인 하는 새 프로세스를 시작 하거나 지정된 된 프로세스에 연결 하는 경우 S_OK이 현재 컴퓨터 및 런타임 구성에 대 한 정보 지정 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="9e8a5-110">가능한 HRESULT 값은:</span><span class="sxs-lookup"><span data-stu-id="9e8a5-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="9e8a5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e8a5-111">S_OK</span></span>  
  
-   <span data-ttu-id="9e8a5-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="9e8a5-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="9e8a5-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="9e8a5-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="9e8a5-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="9e8a5-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e8a5-115">설명</span><span class="sxs-lookup"><span data-stu-id="9e8a5-115">Remarks</span></span>  
 <span data-ttu-id="9e8a5-116">이 메서드는 순수 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-116">This method is purely informational.</span></span> <span data-ttu-id="9e8a5-117">인터페이스는 중지 되지 것입니다 하에서 시작 또는에서 반환 된 값에 관계 없이 프로세스에 연결 `CanLaunchOrAttach`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="9e8a5-118">Win32 디버깅이 설정 된 시작 또는 Win32 디버깅 하도록 설정한 연결을 전달 하려는 경우 `true` 에 대 한 `win32DebuggingEnabled`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="9e8a5-119">반환 된 HRESULT `CanLaunchOrAttach` 이 옵션을 사용 하는 경우 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e8a5-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e8a5-120">Requirements</span></span>  
 <span data-ttu-id="9e8a5-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e8a5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8a5-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e8a5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e8a5-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e8a5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e8a5-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8a5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8a5-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e8a5-125">See also</span></span>
- [<span data-ttu-id="9e8a5-126">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e8a5-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
