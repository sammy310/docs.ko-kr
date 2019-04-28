---
title: ICorDebugRemote::DebugActiveProcessEx 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b919d90454c9424cadb1d4dfc3b0dfb09e5053
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782774"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="5d00b-102">ICorDebugRemote::DebugActiveProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="5d00b-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="5d00b-103">디버거에서 원격 컴퓨터의 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d00b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d00b-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d00b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d00b-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="5d00b-106">[in] 에 대 한 포인터를 [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="5d00b-107">이 매개 변수를 사용 하 여 프로세스가 실행 중인 컴퓨터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="5d00b-108">[in] 디버거를 연결할를 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="5d00b-109">[in] `true` 디버거 프로세스에 대 한 Win32 디버거 처럼 동작 하며 관리 되지 않는 콜백을; 디스패치 하는 경우이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="5d00b-110">[out] 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d00b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="5d00b-111">Return Value</span></span>  
 <span data-ttu-id="5d00b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d00b-112">S_OK</span></span>  
 <span data-ttu-id="5d00b-113">원격 컴퓨터의 프로세스에 연결 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="5d00b-114">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="5d00b-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5d00b-115">원격 컴퓨터의 프로세스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d00b-116">설명</span><span class="sxs-lookup"><span data-stu-id="5d00b-116">Remarks</span></span>  
 <span data-ttu-id="5d00b-117">Silverlight에는 혼합 모드 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d00b-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d00b-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d00b-118">Requirements</span></span>  
 <span data-ttu-id="5d00b-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d00b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d00b-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d00b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d00b-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d00b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d00b-122">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5d00b-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d00b-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d00b-123">See also</span></span>

- [<span data-ttu-id="5d00b-124">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d00b-124">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="5d00b-125">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d00b-125">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="5d00b-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d00b-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
