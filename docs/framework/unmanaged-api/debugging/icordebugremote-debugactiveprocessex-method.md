---
description: ICorDebugRemote::D ebugActiveProcessEx 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: ccbde152e59146bd852a5a0a2f991d10333fa9d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717903"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="8bb84-103">ICorDebugRemote::DebugActiveProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="8bb84-103">ICorDebugRemote::DebugActiveProcessEx Method</span></span>

<span data-ttu-id="8bb84-104">디버거의 원격 컴퓨터에서 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-104">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb84-105">구문</span><span class="sxs-lookup"><span data-stu-id="8bb84-105">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb84-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bb84-106">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="8bb84-107">진행 [ICorDebugRemoteTarget 인터페이스](icordebugremotetarget-interface.md)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-107">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="8bb84-108">이 매개 변수는 프로세스가 실행 중인 컴퓨터를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-108">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="8bb84-109">진행 디버거를 연결할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-109">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="8bb84-110">[in] `true` 디버거가 프로세스에 대 한 Win32 디버거로 동작 하 고 관리 되지 않는 콜백을 디스패치할 경우 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-110">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="8bb84-111">제한이 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-111">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bb84-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="8bb84-112">Return Value</span></span>  

 <span data-ttu-id="8bb84-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8bb84-113">S_OK</span></span>  
 <span data-ttu-id="8bb84-114">원격 컴퓨터의 프로세스에 연결 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-114">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="8bb84-115">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="8bb84-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="8bb84-116">원격 컴퓨터의 프로세스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-116">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bb84-117">설명</span><span class="sxs-lookup"><span data-stu-id="8bb84-117">Remarks</span></span>  

 <span data-ttu-id="8bb84-118">Silverlight에서는 혼합 모드 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb84-118">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb84-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bb84-119">Requirements</span></span>  

 <span data-ttu-id="8bb84-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb84-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb84-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bb84-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bb84-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bb84-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bb84-123">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8bb84-123">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb84-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bb84-124">See also</span></span>

- [<span data-ttu-id="8bb84-125">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb84-125">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="8bb84-126">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb84-126">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="8bb84-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bb84-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
