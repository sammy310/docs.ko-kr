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
ms.openlocfilehash: c9847fd6122aa32c95aecd5643a62a6775ae38d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712120"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="ba39f-102">ICorDebugRemote::DebugActiveProcessEx 메서드</span><span class="sxs-lookup"><span data-stu-id="ba39f-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>

<span data-ttu-id="ba39f-103">디버거의 원격 컴퓨터에서 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba39f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba39f-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba39f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba39f-105">Parameters</span></span>  

 `pRemoteTarget`  
 <span data-ttu-id="ba39f-106">진행 [ICorDebugRemoteTarget 인터페이스](icordebugremotetarget-interface.md)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="ba39f-107">이 매개 변수는 프로세스가 실행 중인 컴퓨터를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="ba39f-108">진행 디버거를 연결할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="ba39f-109">[in] `true` 디버거가 프로세스에 대 한 Win32 디버거로 동작 하 고 관리 되지 않는 콜백을 디스패치할 경우 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ba39f-110">제한이 디버거가 연결 된 프로세스를 나타내는 "ICorDebugProcess" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba39f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ba39f-111">Return Value</span></span>  

 <span data-ttu-id="ba39f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba39f-112">S_OK</span></span>  
 <span data-ttu-id="ba39f-113">원격 컴퓨터의 프로세스에 연결 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="ba39f-114">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="ba39f-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ba39f-115">원격 컴퓨터의 프로세스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba39f-116">설명</span><span class="sxs-lookup"><span data-stu-id="ba39f-116">Remarks</span></span>  

 <span data-ttu-id="ba39f-117">Silverlight에서는 혼합 모드 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba39f-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba39f-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba39f-118">Requirements</span></span>  

 <span data-ttu-id="ba39f-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba39f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba39f-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba39f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba39f-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba39f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba39f-122">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ba39f-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba39f-123">참조</span><span class="sxs-lookup"><span data-stu-id="ba39f-123">See also</span></span>

- [<span data-ttu-id="ba39f-124">ICorDebugRemote 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba39f-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="ba39f-125">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba39f-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="ba39f-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba39f-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
